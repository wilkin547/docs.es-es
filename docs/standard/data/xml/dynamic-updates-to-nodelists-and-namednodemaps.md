---
title: "Actualizaciones dinámicas en NodeLists y NamedNodeMaps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c511fd-6704-4ca4-8078-860a68d898ad
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 459d746ff278ac4affa0318c1fad0aeb6a73e560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Actualizaciones dinámicas en NodeLists y NamedNodeMaps
Dado que la **XmlNodeList** y **XmlNamedNodeMap** contienen un conjunto de nodos, aunque el documento XML se carga en memoria y se modifica, World Wide Web Consortium (W3C) indica que estos objetos que contienen los conjuntos de nodos deben ser dinámicos. Es decir, si el documento subyacente cambia, deberían cambiar también los datos incluidos en estos dos objetos. Por lo tanto, si tiene una **XmlNodeList** que contiene todos los elementos secundarios de un elemento determinado (por ejemplo, elemento X), a continuación, agregue un elemento adicional, elemento Q, al documento bajo el elemento X. El **XmlNodeList** también debe tener el nuevo elemento Q añadido a esta colección. Lo mismo sucede a la inversa. Si se agrega un nodo a la **XmlNodeList**, el documento subyacente también se actualiza.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
