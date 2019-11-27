---
title: 'Cómo: Cargar XML desde un archivo, cadena o secuencia'
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 7a2a0513a066ae8ea8a70f7a5ae340ab29de7d25
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330957"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Cómo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic)

Puede crear [literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) y rellenarlos con el contenido de un origen externo, como un archivo, una cadena o una secuencia mediante varios métodos. Estos métodos se muestran en los ejemplos siguientes.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Para cargar XML desde un archivo

Para rellenar un literal XML como un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto desde un archivo, use el método `Load`. Este método puede tomar como entrada una ruta de acceso de archivo, una secuencia de texto o una secuencia XML.

En el ejemplo de código siguiente se muestra el uso del método <xref:System.Xml.Linq.XDocument.Load%28System.String%29> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML de un archivo de texto.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Para cargar XML desde una cadena

Para rellenar un literal XML como un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto de una cadena, puede usar el método `Parse`.

En el ejemplo de código siguiente se muestra el uso del método <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML a partir de una cadena.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Para cargar XML desde un flujo

Para rellenar un literal XML, como un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> de una secuencia, puede usar el método `Load` o el método <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>.

En el ejemplo de código siguiente se muestra el uso del método <xref:System.Xml.Linq.XNode.ReadFrom%2A> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML a partir de una secuencia XML.

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
