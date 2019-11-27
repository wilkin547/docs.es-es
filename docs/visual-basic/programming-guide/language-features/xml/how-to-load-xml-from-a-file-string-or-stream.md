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
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="9af17-102">Cómo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9af17-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="9af17-103">Puede crear [literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) y rellenarlos con el contenido de un origen externo, como un archivo, una cadena o una secuencia mediante varios métodos.</span><span class="sxs-lookup"><span data-stu-id="9af17-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="9af17-104">Estos métodos se muestran en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="9af17-104">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="9af17-105">Para cargar XML desde un archivo</span><span class="sxs-lookup"><span data-stu-id="9af17-105">To load XML from a file</span></span>

<span data-ttu-id="9af17-106">Para rellenar un literal XML como un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto desde un archivo, use el método `Load`.</span><span class="sxs-lookup"><span data-stu-id="9af17-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="9af17-107">Este método puede tomar como entrada una ruta de acceso de archivo, una secuencia de texto o una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="9af17-107">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="9af17-108">En el ejemplo de código siguiente se muestra el uso del método <xref:System.Xml.Linq.XDocument.Load%28System.String%29> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9af17-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="9af17-109">Para cargar XML desde una cadena</span><span class="sxs-lookup"><span data-stu-id="9af17-109">To load XML from a string</span></span>

<span data-ttu-id="9af17-110">Para rellenar un literal XML como un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto de una cadena, puede usar el método `Parse`.</span><span class="sxs-lookup"><span data-stu-id="9af17-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="9af17-111">En el ejemplo de código siguiente se muestra el uso del método <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML a partir de una cadena.</span><span class="sxs-lookup"><span data-stu-id="9af17-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="9af17-112">Para cargar XML desde un flujo</span><span class="sxs-lookup"><span data-stu-id="9af17-112">To load XML from a stream</span></span>

<span data-ttu-id="9af17-113">Para rellenar un literal XML, como un objeto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> de una secuencia, puede usar el método `Load` o el método <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9af17-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="9af17-114">En el ejemplo de código siguiente se muestra el uso del método <xref:System.Xml.Linq.XNode.ReadFrom%2A> para rellenar un objeto <xref:System.Xml.Linq.XDocument> con XML a partir de una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="9af17-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="9af17-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9af17-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9af17-116">Literales XML</span><span class="sxs-lookup"><span data-stu-id="9af17-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="9af17-117">XML</span><span class="sxs-lookup"><span data-stu-id="9af17-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="9af17-118">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9af17-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
