---
title: Procedimiento para crear literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 61b138c0851c747ed30eedc10cb882cc3b03c4d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392615"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Cómo: Crear literales XML (Visual Basic)
Puede crear un documento, fragmento o elemento XML directamente en el código mediante un literal XML. En los ejemplos de este tema se muestra cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.  
  
 También puede usar las [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos. Para obtener más información, vea <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Para crear un elemento XML  
  
- Cree el XML insertado mediante la sintaxis de literales XML, que es la misma que la sintaxis XML real.  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     Ejecute el código. El resultado de este código es:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Para crear un documento XML  
  
- Cree el documento XML en línea. En el código siguiente se crea un documento XML que tiene una sintaxis literal, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     Ejecute el código. El resultado de este código es:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Consulte también

- [XML](index.md)
- [Crear XML en Visual Basic](creating-xml.md)
- [Literal de elemento XML](../../../language-reference/xml-literals/xml-element-literal.md)
- [Literal de documento XML](../../../language-reference/xml-literals/xml-document-literal.md)
