---
title: Procesamiento de datos XML con el modelo de datos XPath
ms.date: 03/30/2017
ms.assetid: 536c6fce-1453-4654-9c72-bca54d47e081
ms.openlocfilehash: cc35b570c592557658cd3dda0c844847c8b23763
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829289"
---
# <a name="process-xml-data-using-the-xpath-data-model"></a>Procesamiento de datos XML con el modelo de datos XPath
El espacio de nombres <xref:System.Xml?displayProperty=nameWithType> proporciona una representación mediante programación de documentos XML, fragmentos, nodos o conjuntos de nodos en memoria utilizando las clases <xref:System.Xml.XmlDocument> o <xref:System.Xml.XPath.XPathDocument>.  
  
 La clase <xref:System.Xml.XPath.XPathDocument> proporciona una representación en memoria rápida y de solo lectura de un documento XML utilizando el modelo de datos XPath. La clase <xref:System.Xml.XmlDocument> proporciona una representación en memoria editable de un documento XML mediante la implementación de la parte principal del nivel 1 del Modelo de objetos de documento (DOM) y el nivel 2 de la parte principal del DOM del W3C. Ambas clases implementan la interfaz <xref:System.Xml.XPath.IXPathNavigable> y devuelven un objeto <xref:System.Xml.XPath.XPathNavigator> que se utiliza para seleccionar, evaluar y navegar por los datos XML subyacentes, y en algunos casos, editarlos.  
  
 En las siguientes secciones se describe la funcionalidad de la clase <xref:System.Xml.XPath.XPathNavigator> basándose en la clase que la devuelve.  
  
## <a name="in-this-section"></a>En esta sección  
 [Lectura de datos XML con XPathDocument y XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 Se describe cómo crear un objeto de clase <xref:System.Xml.XPath.XPathDocument> de solo lectura para leer un documento XML y cómo crear un objeto de clase <xref:System.Xml.XmlDocument> editable para leer y editar un documento XML. En este tema también se describe cómo devolver un objeto <xref:System.Xml.XPath.XPathNavigator> desde cada clase para navegar por un documento XML y editarlo.  
  
 [Selección, evaluación y coincidencia de datos XML con XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 Se describen los métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se utilizan para seleccionar nodos en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una consulta XPath, evaluar y examinar los resultados de una expresión XPath y determinar si un nodo de un documento XML coincide con una expresión XPath determinada.  
  
 [Acceso a datos XML con XPathNavigator](accessing-xml-data-using-xpathnavigator.md)  
 Se describen los métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se utilizan para navegar por los nodos, extraer datos XML fuertemente tipados en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.  
  
 [Edición de datos XML con XPathNavigator](editing-xml-data-using-xpathnavigator.md)  
 Se describen los métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se utilizan para insertar, modificar y quitar nodos y valores de un documento XML contenido en un objeto <xref:System.Xml.XmlDocument>.  
  
 [Validación de esquemas con XPathNavigator](schema-validation-using-xpathnavigator.md)  
 Se describen las formas de validar el contenido XML de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo DOM](process-xml-data-using-the-dom-model.md)
