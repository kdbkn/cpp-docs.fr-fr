---
title: Classe de CComEnum | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17046239cf4ca5cc95afbc709f10b9c8aedaa9fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomenum-class"></a>Classe de CComEnum
Cette classe définit un objet d’énumérateur COM basé sur un tableau.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
 public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>Paramètres  
 `Base`  
 Un énumérateur COM ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) interface.  
  
 `piid`  
 Pointeur vers l’ID de l’interface de l’énumérateur.  
  
 `T`  
 Le type d’élément exposé par l’interface de l’énumérateur.  
  
 `Copy`  
 Un homogène [copier la classe de stratégie](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Le modèle de thread de la classe. Ce paramètre par défaut est le modèle de thread d’objet global utilisé dans votre projet.  
  
## <a name="remarks"></a>Notes  
 `CComEnum` définit un objet d’énumérateur COM basé sur un tableau. Cette classe est analogue à [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) qui implémente un énumérateur basé sur un conteneur de bibliothèque C++ Standard. Procédure standard d’utilisation de cette classe est décrites ci-dessous. Pour plus d’informations, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Pour utiliser cette classe :  
  
- `typedef` une spécialisation de cette classe.  
  
-   Utilisez le `typedef` comme argument template dans une spécialisation de `CComObject`.  
  
-   Créez une instance de la `CComObject` spécialisation.  
  
-   Initialiser l’objet énumérateur en appelant [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Retourne l’interface de l’énumérateur au client.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
  
## <a name="example"></a>Exemple  
 Le code ci-dessous fournit une fonction réutilisable pour la création et l’initialisation d’un objet énumérateur.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Cette fonction de modèle peut être utilisée pour implémenter le `_NewEnum` propriété d’une interface de collection, comme indiqué ci-dessous :  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Ce code crée un `typedef` pour `CComEnum` qui expose un vecteur de **VARIANT**s via le **IEnumVariant** interface. Le **CVariantArrayCollection** classe spécialisée simplement **CreateEnumerator** pour utiliser des objets d’énumérateur de ce type et la transmet les arguments nécessaires.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [Classe de CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx, classe](../../atl/reference/ccomobjectrootex-class.md)
