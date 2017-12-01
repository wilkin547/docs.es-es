---
title: Control de espacios en blanco y de espacios en blanco significativos al cargar DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Control de espacios en blanco y de espacios en blanco significativos al cargar DOM
Al cargar el documento, puede establecer la opción de conservar los espacios en blanco y crear **XmlWhitespace** nodos en el árbol del documento. Para crear nodos de espacio en blanco, establezca la **PreserveWhitespace** propiedad en true. Si la propiedad se establece en **false**, que es el valor predeterminado, no se crean nodos de espacio en blanco. Siempre se conservan los nodos de espacios en blanco significativos y **XmlSignificantWhitespace** nodos siempre se crean en la memoria para representar estos datos, independientemente de la configuración de la **PreserveWhitespace** marca.  
  
 Si el documento se carga desde un lector, a continuación, configuración de la **PreserveWhitespace** marca de propiedad en el **XmlDocument** clase afecta a la creación de **XmlWhitespace** nodos solo cuando la **WhitespaceHandling** propiedad en el **XmlTextReader** no está establecido en **WhitespaceHandling.None**. Es el valor de la **WhitespaceHandling** propiedad en el lector que tiene prioridad sobre la configuración de dicha marca en el **XmlDocument**. Para obtener más información sobre **XmlSignificantWhitespace**, consulte <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
