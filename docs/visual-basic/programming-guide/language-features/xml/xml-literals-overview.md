---
title: "Informaci&#243;n general sobre literales XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declarar literales XML [Visual Basic]"
  - "LINQ to XML [Visual Basic], literales XML"
  - "literales [Visual Basic], XML"
  - "literales XML [Visual Basic], acerca de los literales XML"
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Informaci&#243;n general sobre literales XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un *literal XML* permite incorporar XML directamente en el código de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. La sintaxis del literal XML representa los objetos [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] y es el similar a la sintaxis de XML 1.0. Esto facilita la creación de elementos y documentos XML mediante programación porque el código tiene la misma estructura que el último XML.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compila los literales de XML en objetos [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] proporciona un modelo de objetos simple para crear y manipular código XML; además, este modelo se integra bien con [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].  Para obtener más información, consulte <xref:System.Xml.Linq.XElement>.  
  
 Puede incrustar una expresión de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] en un literal XML.  En tiempo de ejecución, la aplicación crea un objeto [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] por cada literal incorporando los valores de las expresiones incrustadas.  De esta forma, puede especificar el contenido dinámico en un literal XML.  Para obtener más información, vea [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Para obtener más información acerca de las diferencias entre las sintaxis de literales XML y XML 1.0, vea [Literales XML y la especificación XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## Literales simples  
 Puede crear un objeto [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] en el código de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] escribiendo o pegando un XML válido.  Un literal de elemento XML devuelve un objeto <xref:System.Xml.Linq.XElement>.  Para obtener más información, vea [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [Literales XML y la especificación XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  En el ejemplo siguiente se crea un elemento XML que tiene varios elementos secundarios.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Puede crear un documento XML iniciando un literal XML con `<?xml version="1.0"?>`, como se muestra en el ejemplo siguiente.  Un literal de documento XML devuelve un objeto <xref:System.Xml.Linq.XDocument>.  Para obtener más información, vea [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  La sintaxis de literales XML de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no es idéntica a la de la especificación XML 1.0.  Para obtener más información, vea [Literales XML y la especificación XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## Continuación de línea  
 Un literal XML puede abarcar varias líneas sin utilizar los caracteres de continuación de línea \(la secuencia espacio\-carácter de subrayado\-entrar\).  De esta forma, se facilita la comparación de literales XML en código con documentos XML.  
  
 El compilador trata los caracteres de continuación de línea como parte de un literal XML.  Por consiguiente, solo debe usar la secuencia espacio\-carácter de subrayado\-entrar cuando pertenezca al objeto [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Sin embargo, sí necesita los caracteres de continuación de línea si tiene una expresión multilínea en una expresión incrustada.  Para obtener más información, vea [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## Incrustar consultas en literales XML  
 Puede usar una consulta en una expresión incrustada.  De esta forma, los elementos devueltos por la consulta se agregan al elemento XML.  Así puede agregar contenido dinámico, como el resultado de la consulta de un usuario, a un literal XML.  
  
 Por ejemplo, el código siguiente utiliza una consulta incrustada para crear elementos XML a partir de los miembros de la matriz `phoneNumbers2` y, a continuación, agregue esos elementos como elementos secundarios de `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## Cómo crea el compilador objetos a partir de literales XML  
 El compilador [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] traduce los literales XML en las llamadas a los constructores [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] equivalentes para generar el objeto [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  Por ejemplo, el compilador [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] traducirá el ejemplo de código siguiente en una llamada al constructor <xref:System.Xml.Linq.XProcessingInstruction> para obtener la instrucción de versión XML, en llamadas al constructor <xref:System.Xml.Linq.XElement> de los elementos `<contact>`, `<name>` y `<phone>`, y en llamadas al constructor <xref:System.Xml.Linq.XAttribute> del atributo `type`.  En concreto, dados los atributos del siguiente ejemplo, el compilador [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llamará dos veces al constructor <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29>.  La primera pasará el valor `type` al parámetro `name` y el valor `home` al parámetro `value`.  La segunda también pasará el valor `type` al parámetro `name`, pero el valor `work` al parámetro `value`.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)