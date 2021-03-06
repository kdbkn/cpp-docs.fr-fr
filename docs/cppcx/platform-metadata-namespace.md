---
title: Platform::Metadata Namespace | Documents Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
dev_langs:
- C++
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 11dc54463207efade9a8ebb7179654d0b1e18909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="platformmetadata-namespace"></a>Platform::Metadata (espace de noms)
Cet espace de noms contient les attributs qui modifient les déclarations de types.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
  
namespace Platform {  
   namespace Metadata {  
}}  
```  
  
### <a name="members"></a>Membres  
 Bien que cet espace de noms est destiné à un usage interne, les navigateurs peuvent afficher les membres suivants de cet espace de noms.  
  
|Name|Note|  
|----------|------------|  
|Attribut|Classe de base des attributs.|  
|[Platform::Metadata::DefaultMemberAttribute (attribut)](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Indique la fonction par défaut à appeler parmi plusieurs fonctions surchargées possibles.|  
|Indicateurs de l'[attribut Platform::Metadata::Attribute](../cppcx/platform-metadata-flagsattribute-attribute.md)|Déclare une énumération comme une énumération de champs de bits.<br /><br /> L'exemple ci-dessous montre comment appliquer une énumération à l'attribut `Flags` .<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|  
|[Platform::Metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Garantie qu'une classe ref privée dispose d'un nom de classe d'exécution valide.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `Platform`  
  
### <a name="requirements"></a>Spécifications  
 **Métadonnées :** platform.winmd  
  
 **Espace de noms :** Platform::Metadata  
  
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)