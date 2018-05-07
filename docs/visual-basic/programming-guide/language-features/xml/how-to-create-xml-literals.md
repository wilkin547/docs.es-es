---
title: 'Cómo: Crear literales XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-xml-literals-visual-basic"></a>Cómo: Crear literales XML (Visual Basic)
Puede crear un documento XML, fragmento o elemento directamente en el código mediante un literal XML. Los ejemplos de este tema muestran cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.  
  
 También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos. Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.  
  
### <a name="to-create-an-xml-element"></a>Para crear un elemento XML  
  
-   Crear el XML en línea mediante la sintaxis de literales de XML, que es el mismo que la sintaxis XML propiamente dicha.  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     Ejecute el código. El resultado de este código es:  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a>Para crear un documento XML  
  
-   Crear el documento XML insertado. El código siguiente crea un documento XML que tiene sintaxis de literales, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     Ejecute el código. El resultado de este código es:  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a>Vea también  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
