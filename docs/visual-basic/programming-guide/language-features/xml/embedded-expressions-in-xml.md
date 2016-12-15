---
title: "Expresiones incrustadas (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlEmbeddedExpression"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "expresiones incrustadas [Visual Basic]"
  - "LINQ to XML [Visual Basic], expresiones incrustadas"
  - "literales XML [Visual Basic], expresiones incrustadas"
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Expresiones incrustadas (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las expresiones incrustadas permiten crear literales XML con expresiones que se evalúan en tiempo de ejecución.  La sintaxis de una expresión incrustada es `<%=` `expression` `%>`, que es igual que la sintaxis utilizada en [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
 Por ejemplo, puede crear un literal de elemento XML, combinando las expresiones incrustadas con contenido de texto literal.  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3\/5\/2006, cuando este código se ejecute, el valor de `book` es:  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## Ubicación y validación de expresiones incrustadas  
 Las expresiones incrustadas sólo pueden aparecer en algunas ubicaciones dentro de expresiones literales XML.  La ubicación de la expresión controla los tipos de expresiones que se pueden devolver y cómo se controla `Nothing`.  La tabla siguiente describe las ubicaciones permitidas y los tipos de expresiones incrustadas.  
  
||||  
|-|-|-|  
|Ubicación en literal|Tipo de expresión|Control de `Nothing`|  
|Nombre del elemento XML|<xref:System.Xml.Linq.XName>|Error|  
|Contenido del elemento XML|`Object` o matriz de `Object`|Se omite|  
|Nombre del atributo del elemento XML|<xref:System.Xml.Linq.XName>|Error, a menos que el valor del atributo también sea `Nothing`|  
|Valor del atributo del elemento XML|`Object`|Se omite la declaración de atributos|  
|Atributo del elemento XML.|<xref:System.Xml.Linq.XAttribute> o colección de <xref:System.Xml.Linq.XAttribute>|Se omite|  
|Elemento raíz del documento XML|<xref:System.Xml.Linq.XElement> o una colección de un objeto <xref:System.Xml.Linq.XElement> y un número arbitrario de objetos <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment>|Se omite|  
  
-   Ejemplo de una expresión incrustada en el nombre de un elemento XML:  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Ejemplo de una expresión incrustada en el contenido de un elemento XML:  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Ejemplo de una expresión incrustada en el nombre del atributo de un elemento XML:  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Ejemplo de una expresión incrustada en el valor de un atributo del elemento XML:  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Ejemplo de una expresión incrustada en el atributo de un elemento XML:  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Ejemplo de una expresión incrustada en el elemento raíz de un documento XML:  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 Si habilita `Option Strict`, el compilador comprueba que el tipo de cada expresión incrustada se amplíe al tipo necesario.  La única excepción es el elemento raíz de un documento XML, que se comprueba cuando el código se ejecuta.  Si compila sin `Option Strict`, puede incrustar expresiones de tipo `Object` y su tipo se comprueba en tiempo de ejecución.  
  
 En ubicaciones en las que el contenido es opcional, se omiten las expresiones incrustadas que contienen `Nothing`.  Es decir, no tiene que comprobar ese contenido del elemento, los valores del atributo y los elementos de la matriz no son `Nothing` antes de utilizar un literal XML.  Los valores requeridos, como los nombres de elementos y atributos, no pueden ser `Nothing`.  
  
 Para obtener más información sobre cómo utilizar una expresión incrustada en un tipo determinado de literal, vea [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## Reglas de ámbito  
 El compilador convierte cada literal XML en una llamada de constructor para el tipo literal adecuado.  El contenido literal y las expresiones incrustadas en un literal XML se pasan como argumentos al constructor.  Es decir, todos los elementos de programación de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] disponibles en un literal XML también están disponibles para sus expresiones incrustadas.  
  
 En un literal XML, puede tener acceso a los prefijos de espacio de nombres XML declarados con la instrucción `Imports`.  Puede declarar un nuevo prefijo del espacio de nombres XML o sombrear un prefijo del espacio de nombres XML existente, en un elemento mediante el atributo `xmlns`.  El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML de expresiones incrustadas.  
  
> [!NOTE]
>  Al declarar un prefijo del espacio de nombres XML mediante el atributo de espacio de nombres `xmlns`, el valor del atributo debe ser una cadena constante.  A este respecto, usar el atributo `xmlns` es como utilizar la instrucción `Imports` para declarar un espacio de nombres XML.  No puede utilizar una expresión incrustada para especificar el valor del espacio de nombres XML.  
  
## Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Información general sobre literales XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)