---
title: "C&#243;mo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], cargar XML desde archivos"
  - "XML [Visual Basic], cargar"
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# C&#243;mo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede crear [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) y rellenarlos con el contenido de un origen externo como un archivo, una cadena o una secuencia mediante varios métodos.  Estos métodos se muestran en los ejemplos siguientes.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### Para cargar XML de un archivo  
  
-   Para rellenar un literal XML, como un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, de un archivo, use el método `Load`.  Este método puede tomar una ruta de acceso al archivo, una secuencia de texto o una secuencia XML como entrada.  
  
     En el ejemplo de código siguiente se muestra cómo usar el método <xref:System.Xml.Linq.XDocument.Load%28System.String%29> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML de un archivo de texto.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### Para cargar XML de una cadena  
  
-   Para rellenar un literal XML, como un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, de una cadena, puede usar el método `Parse`.  
  
     En el ejemplo de código siguiente se muestra cómo usar el método <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML de una cadena.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### Para cargar XML de una secuencia  
  
-   Para rellenar un literal XLM, como un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>, de una secuencia, puede usar el método `Load` o el método <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>.  
  
 En el ejemplo de código siguiente se muestra cómo usar el método <xref:System.Xml.Linq.XNode.ReadFrom%2A> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML de una secuencia XML.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## Vea también  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)