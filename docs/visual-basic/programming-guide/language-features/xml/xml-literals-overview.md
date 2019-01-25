---
title: Información general sobre literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: c6d2600b590e01fff062828f8e0f48d9cfad0190
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681396"
---
# <a name="xml-literals-overview-visual-basic"></a>Información general sobre literales XML (Visual Basic)
Un *literal XML* le permite incorporar XML directamente en el código de Visual Basic. La sintaxis de literales XML representa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos y es similar a la sintaxis XML 1.0. Esto facilita la creación de elementos y documentos XML mediante programación porque el código tiene la misma estructura que el código XML final.  
  
 Visual Basic compila literales XML en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Proporciona un modelo de objetos simple para crear y manipular XML y este modelo se integra bien con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.  
  
 Puede insertar una expresión de Visual Basic en un literal XML. En tiempo de ejecución, la aplicación crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para cada literal incorporando los valores de las expresiones incrustadas. Esto le permite especificar el contenido dinámico dentro de un literal XML. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Para obtener más información sobre las diferencias entre la sintaxis de literales XML y la sintaxis XML 1.0, vea [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Literales simples  
 Puede crear un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto en el código de Visual Basic escribiéndola o pegándola en XML válido. Un literal de elemento XML devuelve un <xref:System.Xml.Linq.XElement> objeto. Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). El ejemplo siguiente crea un elemento XML que tiene varios elementos secundarios.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Se puede crear un documento XML a partir de un literal XML con `<?xml version="1.0"?>`, como se muestra en el ejemplo siguiente. Un literal de documento XML devuelve un <xref:System.Xml.Linq.XDocument> objeto. Para obtener más información, consulte [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  La sintaxis de literales XML en Visual Basic no es idéntica a la sintaxis en la especificación XML 1.0. Para obtener más información, consulte [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuación de línea  
 Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea (la secuencia de espacio de subrayado-entrar). Esto facilita la comparación de los literales XML en código con documentos XML.  
  
 El compilador trata los caracteres de continuación de línea como parte de un literal XML. Por lo tanto, debe usar la secuencia de espacio de subrayado-entrar solo al que pertenece el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto.  
  
 Sin embargo, es necesario que los caracteres de continuación de línea si tiene una expresión de varias líneas en una expresión incrustada. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incrustar consultas en literales XML  
 Puede usar una consulta en una expresión incrustada. Al hacerlo, los elementos devueltos por la consulta se agregan al elemento XML. Esto le permite agregar contenido dinámico, como el resultado de consulta de un usuario, a un literal XML.  
  
 Por ejemplo, el código siguiente utiliza una consulta incrustada para crear elementos XML de los miembros de la `phoneNumbers2` de matriz y, a continuación, agregue esos elementos como elementos secundarios de `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Cómo el compilador crea objetos a partir de los literales XML  
 El compilador de Visual Basic traduce los literales XML a llamadas al equivalente [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] constructores para crear el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto. Por ejemplo, el compilador de Visual Basic traducirá el siguiente ejemplo de código en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction> constructor para la instrucción de la versión XML, las llamadas a la <xref:System.Xml.Linq.XElement> constructor para la `<contact>`, `<name>`, y `<phone>` los elementos y las llamadas a la <xref:System.Xml.Linq.XAttribute> constructor para la `type` atributo. En concreto, dados los atributos en el ejemplo siguiente, el compilador de Visual Basic llamará el <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> constructor dos veces. La primera pasará el valor `type` para el `name` parámetro y el valor `home` para el `value` parámetro. El segundo también pasará el valor `type` para el `name` parámetro, pero el valor `work` para el `value` parámetro.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.Linq.XElement>
- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)
