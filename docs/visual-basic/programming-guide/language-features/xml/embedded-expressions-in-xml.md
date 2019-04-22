---
title: Expresiones incrustadas (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 4c96665994a7e56bc70f72b66d5922f5a6472a13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827580"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Expresiones incrustadas (Visual Basic)
Expresiones incrustadas le permiten crear literales XML que contienen expresiones que se evalúan en tiempo de ejecución. La sintaxis de una expresión incrustada es `<%=` `expression` `%>`, que es la misma que la sintaxis utilizada en [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 Por ejemplo, puede crear un elemento XML literal, combinando las expresiones incrustadas con contenido de texto literal.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3/5/2006, cuando se ejecuta este código, el valor de `book` es:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Validación y la ubicación de la expresión insertada  
 Expresiones incrustadas sólo pueden aparecer en determinadas ubicaciones dentro de expresiones literales XML. Los controles de ubicación de la expresión que escribe la expresión pueden devolver y cómo `Nothing` se controla. La tabla siguiente describe las ubicaciones permitidas y tipos de expresiones incrustadas.  
  
|Ubicación en literal|Tipo de expresión|Control de `Nothing`|  
|---|---|---|  
|Nombre del elemento XML|<xref:System.Xml.Linq.XName>|Error|  
|Contenido del elemento XML|`Object` o una matriz de `Object`|Se ignora.|  
|Nombre de atributo del elemento XML|<xref:System.Xml.Linq.XName>|Error, a menos que el valor del atributo también `Nothing`|  
|Valor de atributo del elemento XML|`Object`|Omite la declaración de atributo|  
|Atributo de elemento XML|<xref:System.Xml.Linq.XAttribute> o una colección de <xref:System.Xml.Linq.XAttribute>|Se ignora.|  
|Elemento raíz del documento XML|<xref:System.Xml.Linq.XElement> o una colección de uno <xref:System.Xml.Linq.XElement> objeto y un número arbitrario de <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment> objetos|Se ignora.|  
  
-   Ejemplo de una expresión insertada en un nombre de elemento XML:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
-   Ejemplo de una expresión incrustada en el contenido de un elemento XML:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
-   Ejemplo de una expresión insertada en un nombre de atributo del elemento XML:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
-   Ejemplo de una expresión insertada en un valor de atributo del elemento XML:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
-   Ejemplo de una expresión incrustada en el atributo de un elemento XML:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
-   Ejemplo de una expresión incrustada en un elemento raíz del documento XML:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Si habilita `Option Strict`, el compilador comprueba que el tipo de cada expresión insertada se amplía al tipo requerido. La única excepción es para el elemento raíz de un documento XML, que se comprueba cuando se ejecuta el código. Si se compila sin `Option Strict`, puede incrustar expresiones de tipo `Object` y se comprueba su tipo en tiempo de ejecución.  
  
 En las ubicaciones donde el contenido es opcional, incrustar expresiones que contienen `Nothing` se omiten. Esto significa que no es necesario que comprobar ese contenido del elemento, los valores de atributo, y los elementos de matriz no son `Nothing` antes de utilizar un literal XML. Requiere valores, como los nombres de elemento y atributo, no pueden ser `Nothing`.  
  
 Para obtener más información sobre cómo usar una expresión incrustada en un determinado tipo de literal, consulte [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Reglas de ámbito  
 El compilador convierte cada literal XML en una llamada al constructor para el tipo literal adecuado. El contenido literal y expresiones incrustadas en un literal XML se pasan como argumentos al constructor. Esto significa que todos los elementos de programación de Visual Basic disponibles para un literal XML también están disponibles para sus expresiones incrustadas.  
  
 Dentro de un literal XML, puede tener acceso a espacio de nombres XML prefijos declarados con el `Imports` instrucción. Puede declarar un nuevo prefijo de espacio de nombres XML o sombrear un prefijo de espacio de nombres XML existente, en un elemento utilizando el `xmlns` atributo. El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML en expresiones incrustadas.  
  
> [!NOTE]
>  Cuando declara un prefijo de espacio de nombres XML mediante el uso de la `xmlns` namespace (atributo), el valor del atributo debe ser una constante de cadena. En este sentido, utilizando el `xmlns` atributo es similar a usar el `Imports` instrucción para declarar un espacio de nombres XML. No se puede usar una expresión incrustada para especificar el valor de espacio de nombres XML.  
  
## <a name="see-also"></a>Vea también

- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Introducción a literales XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
