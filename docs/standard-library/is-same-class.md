---
title: is_same, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_same
dev_langs: C++
helpviewer_keywords:
- is_same class
- is_same
ms.assetid: d9df6c1d-c270-4ec2-802a-af275648dd1d
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3714edaac63df8bf278706b41b1bb5472b817f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="issame-class"></a>is_same, classe
Teste si deux types sont identiques.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Ty1, class Ty2>  
struct is_same;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `Ty1`  
 Premier type à interroger.  
  
 `Ty2`  
 Deuxième type à interroger.  
  
## <a name="remarks"></a>Notes  
 Une instance du prédicat de type a la valeur true si les types `Ty1` et `Ty2` sont identiques. Sinon, sa valeur est false.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// std__type_traits__is_same.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct base   
    {   
    int val;   
    };   
  
struct derived   
    : public base   
    {   
    };   
  
int main()   
    {   
    std::cout << "is_same<base, base> == " << std::boolalpha   
        << std::is_same<base, base>::value << std::endl;   
    std::cout << "is_same<base, derived> == " << std::boolalpha   
        << std::is_same<base, derived>::value << std::endl;   
    std::cout << "is_same<derived, base> == " << std::boolalpha   
        << std::is_same<derived, base>::value << std::endl;   
    std::cout << "is_same<int, int> == " << std::boolalpha   
        << std::is_same<int, int>::value << std::endl;   
    std::cout << "is_same<int, const int> == " << std::boolalpha   
        << std::is_same<int, const int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_same<base, base> == true  
is_same<base, derived> == false  
is_same<derived, base> == false  
is_same<int, int> == true  
is_same<int, const int> == false  
```  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<type_traits>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_convertible, classe](../standard-library/is-convertible-class.md)   
 [is_base_of, classe](../standard-library/is-base-of-class.md)