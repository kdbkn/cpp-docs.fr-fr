---
title: deque::Clear (STL/CLR) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::deque::clear
dev_langs:
- C++
helpviewer_keywords:
- clear member [STL/CLR]
ms.assetid: 1d9a3d11-b3fa-43a7-a508-7a05cbcd91bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e684481376e4cfcd07cdb81240780232bec2ec5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="dequeclear-stlclr"></a>deque::clear (STL/CLR)
Supprime tous les éléments.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void clear();  
```  
  
## <a name="remarks"></a>Notes  
 La fonction membre appelle [deque::erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md) `(` [deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md) `(),` [deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md) `())`. Il permet de vous assurer que la séquence contrôlée est vide.  
  
## <a name="example"></a>Exemple  
  
```  
// cliext_deque_clear.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 0  
 a b  
size() = 0  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<cliext/deque >  
  
 **Namespace :** cliext  
  
## <a name="see-also"></a>Voir aussi  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [deque::erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)