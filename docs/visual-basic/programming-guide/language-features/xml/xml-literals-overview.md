---
title: "Información general sobre literales XML (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
caps.latest.revision: 27
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
ms.openlocfilehash: 57d036910ba9e49385caca28de222a8a8e28ec56
ms.lasthandoff: 03/13/2017

---
# <a name="xml-literals-overview-visual-basic"></a>Información general sobre literales XML (Visual Basic)
Un *literal XML* permite incorporar XML directamente en su [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] código. La sintaxis de literales XML representa [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objetos y es similar a la sintaxis XML 1.0. Esto facilita la creación de documentos y elementos XML mediante programación porque el código tiene la misma estructura que el XML final.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]compila literales XML en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objetos. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Proporciona un modelo de objetos simple para crear y manipular XML y este modelo se integra bien con [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Para obtener más información, consulte <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>  
  
 Puede incrustar un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] expresión en un literal XML. En tiempo de ejecución, la aplicación crea un [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objeto para cada literal incorporando los valores de las expresiones incrustadas. Esto le permite especificar el contenido dinámico en un literal XML. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Para obtener más información acerca de las diferencias entre la sintaxis de literales XML y la sintaxis XML 1.0, consulte [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="simple-literals"></a>Literales simples  
 Puede crear un [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objeto en su [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] código escribiendo o pegando un XML válido. Un literal de elemento XML devuelve un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement> Para obtener más información, consulte [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) y [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md). En el ejemplo siguiente se crea un elemento XML que tiene varios elementos secundarios.  
  
 [!code-vb[VbXMLSamples&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_1.vb)]  
  
 Puede crear un documento XML a partir de un literal XML con `<?xml version="1.0"?>`, como se muestra en el ejemplo siguiente. Un literal de documento XML devuelve un <xref:System.Xml.Linq.XDocument>objeto.</xref:System.Xml.Linq.XDocument> Para obtener más información, consulte [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
 [!code-vb[VbXMLSamples Nº&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
> [!NOTE]
>  La sintaxis de literales XML de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no es idéntica a la sintaxis de la especificación XML 1.0. Para obtener más información, consulte [literales XML y la especificación de XML 1.0](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md).  
  
## <a name="line-continuation"></a>Continuación de línea  
 Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea (la secuencia de espacio de subrayado-entrar). Esto facilita la comparación de literales XML en código con documentos XML.  
  
 El compilador trata los caracteres de continuación de línea como parte de un literal XML. Por lo tanto, debe usar la secuencia de espacio de subrayado-entrar sólo cuando se debe incluir en la [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objeto.  
  
 Sin embargo, es necesario que los caracteres de continuación de línea si tiene una expresión multilínea en una expresión incrustada. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
## <a name="embedding-queries-in-xml-literals"></a>Incrustar consultas en literales XML  
 Puede utilizar una consulta en una expresión incrustada. Al hacerlo, los elementos devueltos por la consulta se agregan al elemento XML. Esto le permite agregar contenido dinámico, como el resultado de la consulta de un usuario, a un literal XML.  
  
 Por ejemplo, el código siguiente utiliza una consulta incrustada para crear elementos XML de los miembros de la `phoneNumbers2` de matriz y, a continuación, agregue esos elementos como elementos secundarios de `contact2`.  
  
 [!code-vb[VbXMLSamples&#7;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_3.vb)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>Cómo el compilador crea objetos de literales XML  
 El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador traduce los literales XML a llamadas en el equivalente de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] constructores para construir la [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objeto. Por ejemplo, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador traducirá en el ejemplo de código siguiente en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction>constructor para la instrucción de versión XML, se llama a la <xref:System.Xml.Linq.XElement>constructor para la `<contact>`, `<name>`, y `<phone>` elementos y llamadas a la <xref:System.Xml.Linq.XAttribute>constructor para el `type` atributo.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XProcessingInstruction> En concreto, dados los atributos en el siguiente ejemplo, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador llamará el <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29>constructor dos veces.</xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> La primera pasará el valor `type` para el `name` parámetro y el valor `home` para el `value` parámetro. La segunda también pasará el valor `type` para el `name` parámetro, pero el valor `work` para el `value` parámetro.  
  
 [!code-vb[VbXMLSamples Nº&6;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-literals-overview_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XElement>   
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)
