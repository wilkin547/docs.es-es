---
title: "Información general sobre literales XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59ce79995025692428263120f9c21c7baf5cf231
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-literals-overview-visual-basic"></a>Información general sobre literales XML (Visual Basic)
Un *literal XML* permite incorporar código XML directamente en su [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] código. La sintaxis de los literales XML representa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos y es similar a la sintaxis XML 1.0. Esto hace más fácil crear documentos y elementos XML mediante programación porque el código tiene la misma estructura que el XML final.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]compila los literales XML en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]Proporciona un modelo de objetos simple para crear y manipular XML y este modelo se integra bien con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.  
  
 Puede incrustar un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] expresión en un literal XML. En tiempo de ejecución, la aplicación crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para cada literal incorporando los valores de las expresiones incrustadas. Esto le permite especificar el contenido dinámico dentro de un literal XML. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Para obtener más información sobre las diferencias entre la sintaxis de los literales XML y la sintaxis XML 1.0, vea [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Literales simples  
 Puede crear un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto en su [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] código escribiendo o pegando un XML válido. Un literal de elemento XML devuelve un <xref:System.Xml.Linq.XElement> objeto. Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). En el ejemplo siguiente se crea un elemento XML que tiene varios elementos secundarios.  
  
 [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Se puede crear un documento XML a partir de un literal XML con `<?xml version="1.0"?>`, tal y como se muestra en el ejemplo siguiente. Un literal de documento XML devuelve un <xref:System.Xml.Linq.XDocument> objeto. Para obtener más información, consulte [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  La sintaxis de literales de XML de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no es idéntica a la sintaxis de la especificación XML 1.0. Para obtener más información, consulte [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuación de línea  
 Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea (la secuencia de espacio de subrayado-entrar). Esto facilita la comparación de literales XML en código con documentos XML.  
  
 El compilador trata los caracteres de continuación de línea como parte de un literal XML. Por lo tanto, solo debe usar la secuencia de espacio de subrayado-ENTRAR cuando pertenece en el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto.  
  
 Sin embargo, es necesario caracteres de continuación de línea si tiene una expresión multilínea en una expresión incrustada. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incrustar consultas en literales XML  
 Puede utilizar una consulta en una expresión incrustada. Al hacer esto, los elementos devueltos por la consulta se agregan al elemento XML. Esto le permite agregar contenido dinámico, como el resultado de consulta de un usuario, a un literal XML.  
  
 Por ejemplo, el código siguiente utiliza una consulta incrustada para crear elementos XML a partir de los miembros de la `phoneNumbers2` de matriz y, a continuación, agregue esos elementos como elementos secundarios de `contact2`.  
  
 [!code-vb[VbXMLSamples#7](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Cómo el compilador crea objetos a partir de los literales XML  
 El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador traduce los literales XML a llamadas en el equivalente de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] constructores para crear la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto. Por ejemplo, el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador traducirá el ejemplo de código siguiente en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction> constructor de la instrucción de versión XML, se llama a la <xref:System.Xml.Linq.XElement> constructor para la `<contact>`, `<name>`y `<phone>`elementos y las llamadas a la <xref:System.Xml.Linq.XAttribute> constructor para el `type` atributo. En concreto, dados los atributos en el ejemplo siguiente, la [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador llamará el <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> constructor dos veces. La primera pasará el valor `type` para el `name` parámetro y el valor `home` para el `value` parámetro. La segunda también pasará el valor `type` para el `name` parámetro, pero el valor `work` para el `value` parámetro.  
  
 [!code-vb[VbXMLSamples#6](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)
