---
description: 'Más información acerca de cómo: cargar XML desde un archivo, una cadena o una secuencia (Visual Basic)'
title: Procedimiento para cargar XML desde un archivo, cadena o secuencia
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 375190642c93d929abe2ae10bb6ccba927e3bc8a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480068"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>Cómo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic)

Puede crear [literales XML](../../../language-reference/xml-literals/index.md) y rellenarlos con el contenido de un origen externo, como un archivo, una cadena o una secuencia mediante varios métodos. Estos métodos se muestran en los ejemplos siguientes.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a>Para cargar XML desde un archivo

Para rellenar un literal XML como <xref:System.Xml.Linq.XElement> un <xref:System.Xml.Linq.XDocument> objeto o de un archivo, use el `Load` método. Este método puede tomar como entrada una ruta de acceso de archivo, una secuencia de texto o una secuencia XML.

En el ejemplo de código siguiente se muestra el uso del <xref:System.Xml.Linq.XDocument.Load%28System.String%29> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML de un archivo de texto.

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a>Para cargar XML desde una cadena

Para rellenar un literal XML como <xref:System.Xml.Linq.XElement> un <xref:System.Xml.Linq.XDocument> objeto o de una cadena, puede usar el `Parse` método.

En el ejemplo de código siguiente se muestra el uso del <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML a partir de una cadena.

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a>Para cargar XML desde un flujo

Para rellenar un literal XML como <xref:System.Xml.Linq.XElement> un <xref:System.Xml.Linq.XDocument> objeto o de una secuencia, puede usar el `Load` método o el <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> método.

En el ejemplo de código siguiente se muestra el uso del <xref:System.Xml.Linq.XNode.ReadFrom%2A> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML a partir de una secuencia XML.

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a>Consulte también

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [Literales XML](../../../language-reference/xml-literals/index.md)
- [XML](index.md)
- [Manipular XML en Visual Basic](manipulating-xml.md)
