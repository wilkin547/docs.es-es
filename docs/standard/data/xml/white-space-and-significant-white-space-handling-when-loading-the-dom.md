---
title: "Control de espacios en blanco y de espacios en blanco significativos al cargar DOM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Control de espacios en blanco y de espacios en blanco significativos al cargar DOM
Al cargar el documento, se puede establecer la opción de conservar los espacios en blanco y crear nodos **XmlWhitespace** en el árbol del documento.  Para crear nodos de espacio en blanco, debe establecerse la propiedad **PreserveWhitespace** como true.  Si se establece como **false**, que es el valor predeterminado, no se crean nodos de espacio en blanco.  Siempre se conservan los nodos de espacio en blanco significativos y se crean nodos **XmlSignificantWhitespace** en la memoria para representar estos datos, independientemente de la configuración de la marca **PreserveWhitespace**.  
  
 Si el documento se carga desde un sistema de lectura, la configuración de la propiedad de la marca **PreserveWhitespace** en la clase **XmlDocument** afecta a la creación de nodos **XmlWhitespace** sólo cuando la propiedad **WhitespaceHandling** en **XmlTextReader** no se establece en **WhitespaceHandling.None**.  Es el valor de la propiedad **WhitespaceHandling** en el sistema de lectura la que tiene prioridad sobre la configuración de dicha marca en **XmlDocument**.  Para obtener más información acerca de **XmlSignificantWhitespace**, vea [XmlSignificantWhitespace \(Clase\)](frlrfSystemXmlXmlSignificantWhitespaceClassTopic).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)