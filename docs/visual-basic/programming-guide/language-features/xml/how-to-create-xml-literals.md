---
title: 'Cómo: Crear literales XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e3af5185d2c2106e6a696a6569ef59897d0f1fe1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333003"
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Cómo: Crear literales XML (Visual Basic)
Puede crear un documento, fragmento o elemento XML directamente en el código mediante un literal XML. En los ejemplos de este tema se muestra cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.  
  
 También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear objetos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.  
  
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
  
## <a name="see-also"></a>Vea también

- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
