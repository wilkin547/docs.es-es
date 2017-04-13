---
title: "Creaci&#243;n de documentos XML | Microsoft Docs"
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
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Creaci&#243;n de documentos XML
Hay dos formas de crear un documento XML.  Una es crear un **XmlDocument** sin parámetros.  La otra es crear un **XmlDocument** y pasarle una XmlNameTable como parámetro.  En el ejemplo siguiente se muestra cómo crear un nuevo **XmlDocument** vacío sin utilizar parámetros.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Una vez creado un documento, se pueden cargar datos desde una cadena, secuencia, dirección URL, sistema de lectura de texto o una clase derivada de **XmlReader** mediante el método **Load**.  Existe también otro método de carga, el método **LoadXML**, que lee XML a partir de una cadena.  Para obtener más información acerca de los diversos métodos **Load**, vea [Leer un documento XML en DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Hay una clase denominada **XmlNameTable**.  Esta clase es una tabla de objetos de cadena divididos en átomos.  La tabla proporciona un medio eficaz para que el analizador XML utilice el mismo objeto de cadena para todos los nombres de elemento y atributo repetidos en un documento XML.  Al crear un documento, se crea un objeto **XmlNameTable** automáticamente, como se muestra a continuación, y al cargar el documento se cargan los nombres de elemento y atributo.  Si dispone ya de un documento con una tabla de nombres y dichos nombres serían útiles en otro documento, puede crear un documento nuevo mediante el método **Load**, que acepta un **XmlNameTable** como parámetro.  Al crear el documento con este método, utiliza el **XmlNameTable** existente con todos los atributos y elementos ya cargados desde el otro documento.  Se puede utilizar para comparar de forma eficaz nombres de elemento y atributo.  Para obtener más información acerca de **XmlNameTable**, vea [Comparación de objetos mediante XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).  A modo de referencia, vea [XmlNameTable \(Miembros\)](frlrfSystemXmlXmlNameTableMembersTopic).  
  
## Vea también  
 [Modelo de objetos de documento XML \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)