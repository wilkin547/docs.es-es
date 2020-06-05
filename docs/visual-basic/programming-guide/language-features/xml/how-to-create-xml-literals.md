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
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="fafe6-102">Cómo: Crear literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fafe6-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="fafe6-103">Puede crear un documento, fragmento o elemento XML directamente en el código mediante un literal XML.</span><span class="sxs-lookup"><span data-stu-id="fafe6-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="fafe6-104">En los ejemplos de este tema se muestra cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="fafe6-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="fafe6-105">También puede usar las [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="fafe6-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="fafe6-106">Para obtener más información, vea <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="fafe6-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="fafe6-107">Para crear un elemento XML</span><span class="sxs-lookup"><span data-stu-id="fafe6-107">To create an XML element</span></span>  
  
- <span data-ttu-id="fafe6-108">Cree el XML insertado mediante la sintaxis de literales XML, que es la misma que la sintaxis XML real.</span><span class="sxs-lookup"><span data-stu-id="fafe6-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="fafe6-109">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="fafe6-109">Run the code.</span></span> <span data-ttu-id="fafe6-110">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="fafe6-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="fafe6-111">Para crear un documento XML</span><span class="sxs-lookup"><span data-stu-id="fafe6-111">To create an XML document</span></span>  
  
- <span data-ttu-id="fafe6-112">Cree el documento XML en línea.</span><span class="sxs-lookup"><span data-stu-id="fafe6-112">Create the XML document inline.</span></span> <span data-ttu-id="fafe6-113">En el código siguiente se crea un documento XML que tiene una sintaxis literal, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="fafe6-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="fafe6-114">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="fafe6-114">Run the code.</span></span> <span data-ttu-id="fafe6-115">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="fafe6-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="fafe6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fafe6-116">See also</span></span>

- [<span data-ttu-id="fafe6-117">XML</span><span class="sxs-lookup"><span data-stu-id="fafe6-117">XML</span></span>](index.md)
- [<span data-ttu-id="fafe6-118">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fafe6-118">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="fafe6-119">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="fafe6-119">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="fafe6-120">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="fafe6-120">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
