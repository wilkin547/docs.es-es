---
title: Expresiones incrustadas en XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 0cdb960160457108ddf18c554dae5f5993269833
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332352"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>Expresiones incrustadas (Visual Basic)
Las expresiones incrustadas le permiten crear literales XML que contienen expresiones que se evalúan en tiempo de ejecución. La sintaxis de una expresión incrustada es `<%=` `expression` `%>`, que es igual que la sintaxis que se usa en ASP.NET.  
  
 Por ejemplo, puede crear un literal de elemento XML, combinando expresiones incrustadas con contenido de texto literal.  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 Si `isbnNumber` contiene el entero 12345 y `modifiedDate` contiene la fecha 3/5/2006, cuando se ejecuta este código, el valor de `book` es:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>Ubicación y validación de expresiones incrustadas  
 Las expresiones incrustadas solo pueden aparecer en determinadas ubicaciones dentro de expresiones literales XML. La ubicación de la expresión controla qué tipos puede devolver la expresión y cómo se controla `Nothing`. En la tabla siguiente se describen las ubicaciones permitidas y los tipos de expresiones incrustadas.  
  
|Ubicación en literal|Tipo de expresión|Control de `Nothing`|  
|---|---|---|  
|Nombre del elemento XML|<xref:System.Xml.Linq.XName>|Error|  
|Contenido del elemento XML|`Object` o matriz de `Object`|Omitido|  
|Nombre del atributo del elemento XML|<xref:System.Xml.Linq.XName>|Error, a menos que el valor del atributo también sea `Nothing`|  
|Valor del atributo del elemento XML|`Object`|Declaración de atributo omitida|  
|Atributo de elemento XML|<xref:System.Xml.Linq.XAttribute> o una colección de <xref:System.Xml.Linq.XAttribute>|Omitido|  
|Elemento raíz del documento XML|<xref:System.Xml.Linq.XElement> o una colección de un objeto <xref:System.Xml.Linq.XElement> y un número arbitrario de objetos <xref:System.Xml.Linq.XProcessingInstruction> y <xref:System.Xml.Linq.XComment>|Omitido|  
  
- Ejemplo de una expresión incrustada en un nombre de elemento XML:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- Ejemplo de una expresión incrustada en el contenido de un elemento XML:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- Ejemplo de una expresión incrustada en un nombre de atributo de elemento XML:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- Ejemplo de una expresión incrustada en un valor de atributo de elemento XML:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- Ejemplo de una expresión incrustada en un atributo de elemento XML:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- Ejemplo de una expresión incrustada en un elemento raíz de un documento XML:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 Si habilita `Option Strict`, el compilador comprueba que el tipo de cada expresión insertada se amplía al tipo requerido. La única excepción es para el elemento raíz de un documento XML, que se comprueba cuando se ejecuta el código. Si compila sin `Option Strict`, puede incrustar expresiones de tipo `Object` y se comprueba su tipo en tiempo de ejecución.  
  
 En ubicaciones donde el contenido es opcional, se omiten las expresiones incrustadas que contienen `Nothing`. Esto significa que no es necesario comprobar que el contenido de los elementos, los valores de atributo y los elementos de la matriz no se `Nothing` antes de utilizar un literal XML. Los valores obligatorios, como los nombres de elementos y atributos, no se pueden `Nothing`.  
  
 Para obtener más información sobre el uso de una expresión incrustada en un tipo determinado de literal, vea [literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="scoping-rules"></a>Reglas de ámbito  
 El compilador convierte cada literal XML en una llamada de constructor para el tipo de literal adecuado. El contenido literal y las expresiones incrustadas en un literal XML se pasan como argumentos al constructor. Esto significa que todos los elementos de programación Visual Basic disponibles para un literal XML también están disponibles para sus expresiones incrustadas.  
  
 Dentro de un literal XML, puede tener acceso a los prefijos de espacio de nombres XML declarados con la instrucción `Imports`. Puede declarar un nuevo prefijo de espacio de nombres XML, u ocultar un prefijo de espacio de nombres XML existente, en un elemento mediante el atributo `xmlns`. El nuevo espacio de nombres está disponible para los nodos secundarios de ese elemento, pero no para los literales XML de las expresiones incrustadas.  
  
> [!NOTE]
> Al declarar un prefijo de espacio de nombres XML mediante el atributo de espacio de nombres `xmlns`, el valor de atributo debe ser una cadena constante. En este sentido, el uso del atributo `xmlns` es como usar la instrucción `Imports` para declarar un espacio de nombres XML. No se puede usar una expresión insertada para especificar el valor del espacio de nombres XML.  
  
## <a name="see-also"></a>Vea también

- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Imports (instrucción), espacio de nombres y tipo .NET](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Introducción a literales XML](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
