---
title: "Gestion des données avec Variables de données de Document | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c737557d503ca7e0959d159a0818f1ca78280ea2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="managing-data-with-document-data-variables"></a>Gestion des données avec variables de données de document
Implémenter des données de votre document en tant que variables membres de votre classe de document. Par exemple, le programme Scribble déclare un membre de données de type `CObList` : une liste liée qui stocke des pointeurs vers `CObject` objets. Cette liste est utilisée pour stocker des tableaux de points qui composent un dessin au trait à main levée.  
  
 La procédure d’implémentation de données membres de votre document dépend de la nature de votre application. Pour vous aider, MFC fournit un groupe de « classes de collection » — tableaux, listes et mappages (dictionnaires), y compris les collections basées sur des modèles C++, ainsi que des classes qui encapsulent une variété de types de données courants tels que `CString`, `CRect`, `CPoint`, `CSize`, et `CTime`. Pour plus d’informations sur ces classes, consultez le [vue d’ensemble de la bibliothèque de classes](../mfc/class-library-overview.md) dans les *référence MFC*.  
  
 Lorsque vous définissez les données membres de votre document, vous ajouterez généralement les fonctions membres à la classe de document pour définir et obtenir des éléments de données et effectuer d’autres opérations utiles sur ces derniers.  
  
 Les vues d’accéder à l’objet de document à l’aide du pointeur de la vue vers le document, installé dans la vue au moment de la création. Vous pouvez extraire ce pointeur dans les fonctions de membre d’une vue en appelant le `CView` fonction membre **GetDocument**. Veillez à effectuer un cast de ce pointeur vers votre propre type de document. Vous pouvez ensuite accéder membres de documents publics via le pointeur.  
  
 Si le transfert de données fréquentes nécessite un accès direct ou si vous souhaitez utiliser les membres non publics de la classe de document, vous voudrez que votre affichage de classe friend (en termes de C++) de la classe de document.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de documents](../mfc/using-documents.md)
