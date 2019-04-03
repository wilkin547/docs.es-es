---
title: Filtrar Cargar XML desde un archivo, cadena o Stream (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 2b9da2062068ef25c5df97ef19b1502999ea78ed
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832143"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a><span data-ttu-id="f842d-102">Filtrar Cargar XML desde un archivo, cadena o Stream (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f842d-102">How to: Load XML from a File, String, or Stream (Visual Basic)</span></span>
<span data-ttu-id="f842d-103">Puede crear [literales XML](../../../../visual-basic/language-reference/xml-literals/index.md) y rellenarlas con el contenido de un origen externo, como un archivo, una cadena o una secuencia mediante varios métodos.</span><span class="sxs-lookup"><span data-stu-id="f842d-103">You can create [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md) and populate them with the contents from an external source such as a file, a string, or a stream by using several methods.</span></span> <span data-ttu-id="f842d-104">Estos métodos se muestran en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="f842d-104">These methods are shown in the following examples.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a><span data-ttu-id="f842d-105">Para cargar XML desde un archivo</span><span class="sxs-lookup"><span data-stu-id="f842d-105">To load XML from a file</span></span>  
  
-   <span data-ttu-id="f842d-106">Para rellenar un literal, como XML un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto desde un archivo, use el `Load` método.</span><span class="sxs-lookup"><span data-stu-id="f842d-106">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a file, use the `Load` method.</span></span> <span data-ttu-id="f842d-107">Este método puede tomar una ruta de acceso de archivo, una secuencia de texto o una secuencia XML como entrada.</span><span class="sxs-lookup"><span data-stu-id="f842d-107">This method can take a file path, text stream, or XML stream as input.</span></span>  
  
     <span data-ttu-id="f842d-108">En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XDocument.Load%28System.String%29> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML desde un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="f842d-108">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Load%28System.String%29> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a text file.</span></span>  
  
     [!code-vb[VbXMLSamples#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#43)]  
  
### <a name="to-load-xml-from-a-string"></a><span data-ttu-id="f842d-109">Para cargar XML desde una cadena</span><span class="sxs-lookup"><span data-stu-id="f842d-109">To load XML from a string</span></span>  
  
-   <span data-ttu-id="f842d-110">Para rellenar un literal, como XML un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> objeto desde una cadena, puede usar el `Parse` método.</span><span class="sxs-lookup"><span data-stu-id="f842d-110">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a string, you can use the `Parse` method.</span></span>  
  
     <span data-ttu-id="f842d-111">En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML de una cadena.</span><span class="sxs-lookup"><span data-stu-id="f842d-111">The following code example shows the use of the <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from a string.</span></span>  
  
     [!code-vb[VbXMLSamples#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#47)]  
  
### <a name="to-load-xml-from-a-stream"></a><span data-ttu-id="f842d-112">Para cargar XML desde una secuencia</span><span class="sxs-lookup"><span data-stu-id="f842d-112">To load XML from a stream</span></span>  
  
-   <span data-ttu-id="f842d-113">Para rellenar un literal, como XML un <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument> de objetos de una secuencia, puede usar el `Load` método o la <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="f842d-113">To populate an XML literal such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object from a stream, you can use the `Load` method or the <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f842d-114">En el ejemplo de código siguiente se muestra el uso de la <xref:System.Xml.Linq.XNode.ReadFrom%2A> método para rellenar un <xref:System.Xml.Linq.XDocument> objeto con XML a partir de una secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="f842d-114">The following code example shows the use of the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method to populate an <xref:System.Xml.Linq.XDocument> object with XML from an XML stream.</span></span>  
  
 [!code-vb[VbXMLSamples#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples15.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="f842d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f842d-115">See also</span></span>

- <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f842d-116">Literales XML</span><span class="sxs-lookup"><span data-stu-id="f842d-116">XML Literals</span></span>](../../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="f842d-117">XML</span><span class="sxs-lookup"><span data-stu-id="f842d-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="f842d-118">Manipular XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f842d-118">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
