---
title: "Informaci&#243;n general sobre LINQ to XML en Visual Basic | Microsoft Docs"
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
  - "LINQ [Visual Basic], LINQ to XML"
  - "LINQ to XML [Visual Basic], acerca de LINQ to XML"
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Informaci&#243;n general sobre LINQ to XML en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona compatibilidad con [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] a través de literales XML y propiedades de eje XML.  Esto le permite usar una sintaxis conocida y apropiada para trabajar con XML en el código de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]. Los *literales XML* permiten incluir XML directamente en el código.  Las *propiedades de eje XML* permiten tener acceso a los nodos secundarios, los nodos descendientes y los atributos de un literal XML.  Para obtener más información, vea [Información general sobre literales XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) y [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] es una API de programación XML en memoria diseñada específicamente para aprovechar la funcionalidad de [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)].  Aunque puede llamar a las API de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] directamente, solo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] permite declarar literales XML y tener acceso directo a las propiedades de eje XML.  
  
> [!NOTE]
>  Los literales XML y las propiedades de eje XML no se admiten en el código declarativo de una página ASP.NET.  Para utilizar las características de XML de Visual Basic, coloque el código en una página de código subyacente en la aplicación ASP.NET.  
  
 ![vínculo a vídeo](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") Dispone de demostraciones relacionadas en vídeo en [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) y [How D o I Create Excel Spreadsheets using LINQ to LINQ?](http://go.microsoft.com/fwlink/?LinkId=143536).  
  
## Crear XML  
 Hay dos maneras de crear árboles XML en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Puede declarar un literal XML directamente en código o puede utilizar la API de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)].  Ambos procesos permiten que el código refleje la estructura final del árbol XML.  Por ejemplo, el siguiente ejemplo de código crea un elemento XML:  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]  
  
 Para obtener más información, vea [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).  
  
## Navegar y obtener acceso a XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona propiedades de eje XML para obtener acceso y navegar por las estructuras XML.  Estas propiedades permiten tener acceso a los elementos y atributos XML especificando los nombres de los elementos secundarios XML.  O bien, puede llamar explícitamente a los métodos de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] para navegar y buscar elementos y atributos.  Por ejemplo, el ejemplo de código siguiente utiliza propiedades de eje XML para hacer referencia a los atributos y elementos secundarios de un elemento XML.  El ejemplo de código usa una consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] para recuperar los elementos secundarios y generarlos como elementos XML, realizando eficazmente una transformación.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]  
  
 Para obtener más información, vea [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).  
  
## Espacios de nombres XML  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] permite especificar un alias en un espacio de nombres XML global utilizando la instrucción `Imports`.  El ejemplo siguiente muestra cómo utilizar la instrucción `Imports` para importar un espacio de nombres XML:  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]  
  
 Puede utilizar un alias de espacio de nombres XML al obtener acceso a las propiedades de eje XML y declarar literales XML para los documentos y elementos XML.  
  
 Puede recuperar un objeto <xref:System.Xml.Linq.XNamespace> de un prefijo de espacio de nombres concreto mediante [GetXmlNamespace \(Operador\)](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).  
  
 Para obtener más información, vea [Imports \(Instrucción, Espacio de nombres XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).  
  
### Utilizar espacios de nombres XML en literales XML  
 El ejemplo siguiente muestra cómo crear un objeto <xref:System.Xml.Linq.XElement> que utiliza el espacio de nombres `ns`global:  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]  
  
 El compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] traduce literales XML que contienen los alias del espacio de nombres XML en código equivalente que utiliza la notación XML para usar los espacios de nombres XML, con el atributo `xmlns`.  Cuando se compila, el código del ejemplo de la sección anterior genera básicamente el mismo código ejecutable que el ejemplo siguiente:  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]  
  
### Usar los espacios de nombres XML en propiedades de eje XML  
 Los espacios de nombres XML declarados en literales XML no están disponibles para su uso en propiedades de eje XML.  Sin embargo, los espacios de nombres globales se pueden utilizar con las propiedades de eje XML.  Use dos puntos para separar el prefijo del espacio de nombres XML del nombre del elemento local.  A continuación, se muestra un ejemplo:  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]  
  
## Vea también  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)