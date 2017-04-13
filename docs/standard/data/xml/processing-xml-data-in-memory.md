---
title: "Procesamiento de datos XML en memoria | Microsoft Docs"
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
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Procesamiento de datos XML en memoria
El .NET Framework de Microsoft incluye tres modelos para el procesamiento de datos XML: la clase <xref:System.Xml.XmlDocument>, la clase <xref:System.Xml.XPath.XPathDocument> y [LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 La clase <xref:System.Xml.XmlDocument> implementa el nivel 1 principal del Modelo de objetos de documento \(DOM\) y las recomendaciones principales del nivel 2 del DOM del W3C.  El DOM es una representación de árbol en memoria \(caché\) de un documento XML.  Con <xref:System.Xml.XmlDocument> y  sus clases relacionadas, puede construir documentos XML, cargar datos y tener acceso a ellos, modificar datos y guardar cambios.  
  
 La clase <xref:System.Xml.XPath.XPathDocument> es un almacén de datos en memoria y de solo lectura que se basa en el modelo de datos XPath.  La clase <xref:System.Xml.XPath.XPathNavigator> ofrece diversas opciones de edición y capacidades de navegación utilizando un modelo de cursor sobre documentos XML contenidos en la clase <xref:System.Xml.XPath.XPathDocument> de solo lectura, así como en la clase <xref:System.Xml.XmlDocument>.  
  
 [LINQ to XML](../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md) es el nuevo modelo que incorpora .NET Framework versión 3.5 para el procesamiento de datos XML.  Es un modelo en memoria que aprovecha las [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md).  LINQ amplía la sintaxis del lenguaje C\# y Visual Basic para proporcionar nuevas capacidades de consulta.  
  
## En esta sección  
 [Procesamiento de datos XML con el modelo DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Describe el uso de <xref:System.Xml.XmlDocument> y sus clases relacionadas para procesar datos XML.  
  
 [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Describe el uso de las clases <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> y <xref:System.Xml.XPath.XPathNavigator> para procesar datos XML.  
  
 [Procesamiento de datos XML utilizando LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Propociona una descripción general acerca de LINQ to XML, así como vínculos que hacen referencia a la documentación de LINQ to XML.  
  
## Secciones relacionadas  
 [Documentos y datos XML](../../../../docs/standard/data/xml/index.md)