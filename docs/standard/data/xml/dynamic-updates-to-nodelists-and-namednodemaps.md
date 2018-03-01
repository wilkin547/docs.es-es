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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8a7abbb7344530ca993b8d07b774da17e6d0349b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dynamic-updates-to-nodelists-and-namednodemaps"></a>Actualizaciones dinámicas en NodeLists y NamedNodeMaps
Puesto que **XmlNodeList** y **XmlNamedNodeMap** contienen un conjunto de nodos, el documento XML se carga en la memoria y se modifica, el World Wide Web Consortium (W3C) establece que es necesario que estos objetos que contienen conjuntos de nodos sean dinámicos. Es decir, si el documento subyacente cambia, deberían cambiar también los datos incluidos en estos dos objetos. Por lo tanto, si tiene una clase **XmlNodeList** que contiene todos los elementos secundarios de un elemento en particular (por ejemplo, elemento X), entonces añade un elemento adicional, elemento Q, al documento bajo el elemento X. La clase **XmlNodeList** debería tener el nuevo elemento Q añadido a esta colección. Lo mismo sucede a la inversa. Si se agrega un nodo a **XmlNodeList**, el documento subyacente también se actualiza.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
