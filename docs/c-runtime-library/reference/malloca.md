---
title: _malloca | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _malloca
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- malloca
- _malloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6f6b731bce5667ca992e7181518bf0a9eb2b87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="malloca"></a>_malloca

Alloue de la mémoire sur la pile. Il s’agit d’une version de [_alloca](alloca.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Syntaxe

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>Paramètres

*size*<br/>
Octets à allouer à partir de la pile.

## <a name="return-value"></a>Valeur de retour

Le **_malloca** routine retourne un **void** pointeur vers l’espace alloué, ce qui est obligatoirement aligné correctement pour le stockage de tout type d’objet. Si *taille* est 0, **_malloca** alloue un élément vide et retourne un pointeur valid vers cet élément.

Une exception de dépassement de capacité de pile est générée si l’espace ne peut pas être alloué. L’exception de dépassement de capacité de pile n’est pas une exception C++ ; il s’agit d’une exception structurée. Au lieu d’utiliser la gestion des exceptions C++, vous devez utiliser la [gestion des exceptions structurée](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Notes

**_malloca** alloue *taille* octets à partir de la pile du programme ou le segment de mémoire si la demande dépasse une certaine taille en octets donné par **_ALLOCA_S_THRESHOLD**. La différence entre **_malloca** et **_alloca** qui est **_alloca** alloue toujours sur la pile, quelle que soit la taille. Contrairement aux **_alloca**, qui ne requièrent pas ou autoriser un appel à **libre** pour libérer la mémoire allouée, **_malloca** requiert l’utilisation de [_freea](freea.md)pour libérer de la mémoire. En mode débogage, **_malloca** toujours alloue de la mémoire à partir du tas.

Il existe des restrictions à appeler explicitement **_malloca** dans un gestionnaire d’exceptions (GE). Les routines EH qui s’exécutent sur des processeurs de classe x86 opèrent dans le cadre de leur propre mémoire : elles effectuent leurs tâches dans un espace mémoire qui n’est pas basé sur l’emplacement actuel du pointeur de pile de la fonction englobante. Les implémentations les plus courantes incluent les expressions de gestion des exceptions structurées Windows NT (SEH) et les expressions de clause catch C++. Par conséquent, appeler explicitement **_malloca** dans un des résultats défaillance d’un programme pendant le retour à l’appel de la routine EH scénarios suivants :

- Expression de filtre d’exception SEH de Windows NT : **__except** (`_malloca ()` )

- Gestionnaire d’exceptions finale de Windows NT SEH : **__finally** {`_malloca ()` }

- Expression de clause catch EH C++

Toutefois, **_malloca** peut être appelée directement à partir de dans une routine de gestionnaire d’événements ou à partir d’un rappel fourni par l’application qui est appelé par un des scénarios de gestionnaire d’événements mentionnés précédemment.

> [!IMPORTANT]
> Dans Windows XP, si **_malloca** est appelée à l’intérieur d’un bloc try/catch, vous devez appeler [_resetstkoflw](resetstkoflw.md) dans le bloc catch.

Outre les restrictions ci-dessus, lorsque vous utilisez la [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) option, **_malloca** ne peut pas être utilisé dans **__except** blocs. Pour plus d'informations, consultez [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>Exemple

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>Exemple

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>Entrée

```Input
1000
```

### <a name="sample-output"></a>Résultat de l'exemple

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>Voir aussi

[Allocation de mémoire](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
