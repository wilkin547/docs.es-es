---
title: "Creación de documentos XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a>Creación de documentos XML
Hay dos formas de crear un documento XML. Es una manera de crear un **XmlDocument** sin parámetros. El otro mecanismo consiste en crear un **XmlDocument** y pasarle una XmlNameTable como parámetro. En el ejemplo siguiente se muestra cómo crear una nueva y vacía **XmlDocument** sin ningún parámetro.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Una vez que se crea un documento, puede cargarlo con datos de una cadena, secuencia, dirección URL, el lector de texto, o un **XmlReader** deriva la clase utilizando el **cargar** método. También hay otro método de carga, el **LoadXML** método, que lee XML desde una cadena. Para obtener más información acerca de los diversos **carga** métodos, vea [leer un documento XML en el DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Hay una clase denominada el **XmlNameTable**. Esta clase es una tabla de objetos de cadena divididos en átomos. La tabla proporciona un medio eficaz para que el analizador XML utilice el mismo objeto de cadena para todos los nombres de elemento y atributo repetidos en un documento XML. Un **XmlNameTable** se crea automáticamente cuando un documento se crea como se indicó anteriormente y se carga con nombres de atributo y elemento cuando se carga el documento. Si ya tiene un documento con una tabla de nombres y dichos nombres serían útiles en otro documento, puede crear un documento nuevo mediante el **carga** método que toma un **XmlNameTable** como un parámetro. Cuando se crea el documento con este método, utiliza existente **XmlNameTable** con todos los atributos y elementos ya cargados desde el otro documento. Se puede utilizar para comparar de forma eficaz nombres de elemento y atributo. Para obtener más información sobre la **XmlNameTable**, consulte [comparación de objetos mediante XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Como referencia, vea <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
