---
title: Expresiones incrustadas en XML (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e5cd40e55ec23de3ad1bb2f5f065762c893d9cb3
ms.lasthandoff: 03/13/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Expresiones incrustadas (Visual Basic)
Expresiones incrustadas permiten crear literales XML que contienen expresiones que se evalúan en tiempo de ejecución. La sintaxis de una expresión incrustada es `<%=` `expression` `%>`, que es la misma que la sintaxis utilizada en [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
 Por ejemplo, puede crear un elemento XML literal, combinando las expresiones incrustadas con contenido de texto literal.  
  
 [!code-vb[VbXMLSamples Nº&27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3/5/2006, cuando se ejecuta este código, el valor de `book` es:  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Validación y la ubicación de la expresión incrustada  
 Expresiones incrustadas sólo pueden aparecer en algunas ubicaciones dentro de expresiones literales XML. Los controles de la ubicación de expresión que se escribe la expresión pueden devolver y cómo `Nothing` se controla. La tabla siguiente describe las ubicaciones permitidas y los tipos de expresiones incrustadas.  
  
|Ubicación en literal|Tipo de expresión|Control de`Nothing`|  
|---|---|---|  
|Nombre del elemento XML|<xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName>|Error|  
|Contenido del elemento XML|`Object`o una matriz de`Object`|Se ignora.|  
|Nombre de atributo del elemento XML|<xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName>|Error, a menos que el valor del atributo también`Nothing`|  
|Valor de atributo del elemento XML|`Object`|Se omite la declaración de atributo|  
|Atributo del elemento XML|<xref:System.Xml.Linq.XAttribute>o un conjunto de<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute>|Se ignora.|  
|Elemento raíz del documento XML|<xref:System.Xml.Linq.XElement>o una colección de un <xref:System.Xml.Linq.XElement>objeto y un número arbitrario de <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment>objetos</xref:System.Xml.Linq.XComment> y</xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement>|Se ignora.|  
  
-   Ejemplo de una expresión incrustada en un nombre de elemento XML:  
  
     [!code-vb[VbXMLSamples&#32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   Ejemplo de una expresión incrustada en el contenido de un elemento XML:  
  
     [!code-vb[VbXMLSamples Nº&33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   Ejemplo de una expresión incrustada en un nombre de atributo del elemento XML:  
  
     [!code-vb[VbXMLSamples&#34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   Ejemplo de una expresión incrustada en un valor de atributo del elemento XML:  
  
     [!code-vb[VbXMLSamples&#35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   Ejemplo de una expresión incrustada en el atributo de un elemento XML:  
  
     [!code-vb[VbXMLSamples&#36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   Ejemplo de una expresión incrustada en un elemento raíz del documento XML:  
  
     [!code-vb[VbXMLSamples&#37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 Si habilita `Option Strict`, el compilador comprueba que el tipo de cada expresión incrustada se amplía al tipo requerido. La única excepción es para el elemento raíz de un documento XML, que se comprueba cuando se ejecuta el código. Si compila sin `Option Strict`, puede incrustar expresiones de tipo `Object` y se comprueba su tipo en tiempo de ejecución.  
  
 En ubicaciones donde es opcional, contenido incrustado expresiones que contienen `Nothing` se omiten. Esto significa que no es necesario comprobar ese contenido del elemento, los valores de atributo, y elementos de matriz no son `Nothing` antes de utilizar un literal XML. Requiere valores, como los nombres de elemento y atributo, no pueden ser `Nothing`.  
  
 Para obtener más información sobre el uso de una expresión incrustada en un determinado tipo de literal, consulte [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Reglas de ámbito  
 El compilador convierte cada literal XML en una llamada al constructor para el tipo literal adecuado. El contenido literal y las expresiones incrustadas en un literal XML se pasan como argumentos al constructor. Esto significa que todos los [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] elementos de programación disponibles en un literal XML también están disponibles para sus expresiones incrustadas.  
  
 Dentro de un literal XML, puede tener acceso a nombres XML prefijos declarados con el `Imports` instrucción. Puede declarar un nuevo prefijo de espacio de nombres XML o sombrear un prefijo de espacio de nombres XML existente, en un elemento utilizando el `xmlns` atributo. El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML de expresiones incrustadas.  
  
> [!NOTE]
>  Cuando se declara un prefijo de espacio de nombres XML mediante el uso de la `xmlns` el atributo de espacio de nombres, el valor del atributo debe ser una cadena constante. En este sentido, usando la `xmlns` atributo es similar al uso de la `Imports` instrucción para declarar un espacio de nombres XML. No puede usar una expresión incrustada para especificar el valor de espacio de nombres XML.  
  
## <a name="see-also"></a>Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Introducción a literales XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
