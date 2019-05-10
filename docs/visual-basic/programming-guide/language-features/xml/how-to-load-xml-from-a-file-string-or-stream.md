---
title: Procedimiento Cargar XML desde un archivo, cadena o Stream (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 097c766fc9efbc810859ab693d3b26f5c1db57ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598336"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Procedimiento Cargar XML desde un archivo, cadena o Stream (Visual Basic)
Puede crear [literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) y rellenarlas con el contenido de un origen externo, como un archivo, una cadena o una secuencia mediante varios métodos. Estos métodos se muestran en los ejemplos siguientes.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>Para cargar XML desde un archivo  
  
- Para rellenar un literal, como XML un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto desde un archivo, use el `Load` método. Este método puede tomar una ruta de acceso de archivo, una secuencia de texto o una secuencia XML como entrada.  
  
     En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XDocument.Load%28System.String%29> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML desde un archivo de texto.  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a>Para cargar XML desde una cadena  
  
- Para rellenar un literal, como XML un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto desde una cadena, puede usar el `Parse` método.  
  
     En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML de una cadena.  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a>Para cargar XML desde una secuencia  
  
- Para rellenar un literal, como XML un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> de objetos de una secuencia, puede usar el `Load` método o la <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> método.  
  
 En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XNode.ReadFrom%2A> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML a partir de una secuencia XML.  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [Literales XML](../../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
