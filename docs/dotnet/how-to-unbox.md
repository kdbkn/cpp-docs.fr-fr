---
title: 'Comment : effectuer une conversion unboxing | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- unboxing
ms.assetid: 75794696-9275-47bf-9a7d-5abe6585ab91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: afddbad696dc513546d14749c0d98ec5d81a597a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-unbox"></a>Comment : effectuer une conversion unbox
Montre comment effectuer une conversion unboxing et modifier une valeur.  
  
## <a name="example"></a>Exemple  
  
```  
// vcmcppv2_unboxing.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   int ^ i = gcnew int(13);  
   int j;  
   Console::WriteLine(*i);   // unboxing  
   *i = 14;   // unboxing and assignment  
   Console::WriteLine(*i);  
   j = safe_cast<int>(i);   // unboxing and assignment  
   Console::WriteLine(j);  
}  
```  
  
```Output  
13  
14  
14  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion boxing](../windows/boxing-cpp-component-extensions.md)