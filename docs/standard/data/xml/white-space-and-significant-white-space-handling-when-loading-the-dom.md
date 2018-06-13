---
title: Control de espacios en blanco y de espacios en blanco significativos al cargar DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8e2279023029b5047cc7d9b4d0d97ac1f21e3f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569075"
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>Control de espacios en blanco y de espacios en blanco significativos al cargar DOM
Al cargar el documento, se puede establecer la opción de conservar los espacios en blanco y crear nodos **XmlWhitespace** en el árbol del documento. Para crear nodos de espacio en blanco, debe establecerse la propiedad **PreserveWhitespace** como true. Si se establece como **false**, que es el valor predeterminado, no se crean nodos de espacio en blanco. Siempre se conservan los nodos de espacio en blanco significativos y se crean nodos **XmlSignificantWhitespace** en la memoria para representar estos datos, independientemente de la configuración de la marca **PreserveWhitespace**.  
  
 Si el documento se carga desde un sistema de lectura, la configuración de la propiedad de la marca **PreserveWhitespace** en la clase **XmlDocument** afecta a la creación de nodos **XmlWhitespace** solo cuando la propiedad **WhitespaceHandling** en **XmlTextReader** no se establece en **WhitespaceHandling.None**. Es el valor de la propiedad **WhitespaceHandling** en el sistema de lectura la que tiene prioridad sobre la configuración de dicha marca en **XmlDocument**. Para obtener más información sobre **XmlSignificantWhitespace**, vea <xref:System.Xml.XmlSignificantWhitespace>.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
