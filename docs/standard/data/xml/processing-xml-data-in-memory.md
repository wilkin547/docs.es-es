---
title: Procesamiento de datos XML en memoria
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 317021318153cc87b2eab3db508a9dede9dc05e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="processing-xml-data-in-memory"></a>Procesamiento de datos XML en memoria
Microsoft .NET Framework incluye tres modelos para el procesamiento de datos XML: la clase <xref:System.Xml.XmlDocument>, la clase <xref:System.Xml.XPath.XPathDocument> y [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 La clase <xref:System.Xml.XmlDocument> implementa el nivel 1 principal del Modelo de objetos de documento (DOM) y las recomendaciones principales del nivel 2 del DOM del W3C. El DOM es una representación de árbol en memoria (caché) de un documento XML. Con <xref:System.Xml.XmlDocument> y  sus clases relacionadas, puede construir documentos XML, cargar datos y tener acceso a ellos, modificar datos y guardar cambios.  
  
 La clase <xref:System.Xml.XPath.XPathDocument> es un almacén de datos en memoria y de solo lectura que se basa en el modelo de datos XPath. La clase <xref:System.Xml.XPath.XPathNavigator> ofrece diversas opciones de edición y capacidades de navegación utilizando un modelo de cursor sobre documentos XML contenidos en la clase <xref:System.Xml.XPath.XPathDocument> de solo lectura, así como en la clase <xref:System.Xml.XmlDocument>.  
  
 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) es el nuevo modelo que incorpora .NET Framework 3.5 para el procesamiento de datos XML. Es un modelo en memoria que usa [LINQ (Language Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d). LINQ amplía la sintaxis del lenguaje C# y Visual Basic para proporcionar nuevas capacidades de consulta.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procesamiento de datos XML con el modelo DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Describe el uso de <xref:System.Xml.XmlDocument> y sus clases relacionadas para procesar datos XML.  
  
 [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Describe el uso de las clases <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> y <xref:System.Xml.XPath.XPathNavigator> para procesar datos XML.  
  
 [Procesamiento de datos XML utilizando LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Propociona una descripción general acerca de LINQ to XML, así como vínculos que hacen referencia a la documentación de LINQ to XML.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Documentos y datos XML](../../../../docs/standard/data/xml/index.md)
