---
title: Erreur du compilateur C2856 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac67538a10d39bc68059b0a7d1aaf73a381abb2a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2856"></a>Erreur du compilateur C2856
\#pragma hdrstop ne peut pas être à l’intérieur d’un bloc #if  
  
 Le `hdrstop` pragma ne peut pas être placé dans le corps d’un bloc de compilation conditionnelle.  
  
 Déplacer le `#pragma hdrstop` instruction dans une zone qui n’est pas contenue dans un `#if/#endif` bloc.