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
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="65c7f-103">Cómo: Cargar XML desde un archivo, cadena o secuencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65c7f-103">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>

<span data-ttu-id="65c7f-104">Puede crear [literales XML](../../../language-reference/xml-literals/index.md) y rellenarlos con el contenido de un origen externo, como un archivo, una cadena o una secuencia mediante varios métodos.</span><span class="sxs-lookup"><span data-stu-id="65c7f-104">You can create [XML Literals](../../../language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="65c7f-105">Estos métodos se muestran en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="65c7f-105">These methods are shown in the following examples.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-load-xml-from-a-file"></a><span data-ttu-id="65c7f-106">Para cargar XML desde un archivo</span><span class="sxs-lookup"><span data-stu-id="65c7f-106">To load XML from a file</span></span>

<span data-ttu-id="65c7f-107">Para rellenar un literal XML como <xref:System.Xml.Linq.XElement> un <xref:System.Xml.Linq.XDocument> objeto o de un archivo, use el `Load` método.</span><span class="sxs-lookup"><span data-stu-id="65c7f-107">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="65c7f-108">Este método puede tomar como entrada una ruta de acceso de archivo, una secuencia de texto o una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="65c7f-108">This method can take a file path, text stream, or XML stream as input.</span></span>

<span data-ttu-id="65c7f-109">En el ejemplo de código siguiente se muestra el uso del <xref:System.Xml.Linq.XDocument.Load%28System.String%29> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="65c7f-109">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>

[!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]

## <a name="to-load-xml-from-a-string"></a><span data-ttu-id="65c7f-110">Para cargar XML desde una cadena</span><span class="sxs-lookup"><span data-stu-id="65c7f-110">To load XML from a string</span></span>

<span data-ttu-id="65c7f-111">Para rellenar un literal XML como <xref:System.Xml.Linq.XElement> un <xref:System.Xml.Linq.XDocument> objeto o de una cadena, puede usar el `Parse` método.</span><span class="sxs-lookup"><span data-stu-id="65c7f-111">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>

<span data-ttu-id="65c7f-112">En el ejemplo de código siguiente se muestra el uso del <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML a partir de una cadena.</span><span class="sxs-lookup"><span data-stu-id="65c7f-112">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>

[!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]

## <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="65c7f-113">Para cargar XML desde un flujo</span><span class="sxs-lookup"><span data-stu-id="65c7f-113">To load XML from a stream</span></span>

<span data-ttu-id="65c7f-114">Para rellenar un literal XML como <xref:System.Xml.Linq.XElement> un <xref:System.Xml.Linq.XDocument> objeto o de una secuencia, puede usar el `Load` método o el <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="65c7f-114">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="65c7f-115">En el ejemplo de código siguiente se muestra el uso del <xref:System.Xml.Linq.XNode.ReadFrom%2A> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML a partir de una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="65c7f-115">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>

[!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]

## <a name="see-also"></a><span data-ttu-id="65c7f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65c7f-116">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="65c7f-117">Literales XML</span><span class="sxs-lookup"><span data-stu-id="65c7f-117">XML Literals</span></span>](../../../language-reference/xml-literals/index.md)
- [<span data-ttu-id="65c7f-118">XML</span><span class="sxs-lookup"><span data-stu-id="65c7f-118">XML</span></span>](index.md)
- [<span data-ttu-id="65c7f-119">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65c7f-119">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
