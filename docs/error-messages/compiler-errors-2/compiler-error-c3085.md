---
title: Erreur du compilateur C3085 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3085
dev_langs:
- C++
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57c85908d808243be8e6edce27ea22c18b4941f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3085"></a>Erreur du compilateur C3085
'constructeur' : un constructeur ne peut pas être 'mot_clé'  
  
 Un constructeur n’a pas été correctement déclaré. Pour plus d'informations, voir [Override Specifiers](../../windows/override-specifiers-cpp-component-extensions.md) .  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3085.  
  
```  
// C3085.cpp  
// compile with: /c /clr  
ref struct S {  
   S() abstract;   // C3085  
   S(S%) abstract;   // C3085  
};  
  
ref struct T {  
   T() sealed {}   // C3085  
   T(T%) sealed {}   // C3085  
};  
```