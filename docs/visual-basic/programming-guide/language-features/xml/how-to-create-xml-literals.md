---
title: Procedimiento Crear literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775913"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="1e174-102">Procedimiento Crear literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e174-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="1e174-103">Puede crear un documento, fragmento o elemento XML directamente en el código mediante el uso de un literal XML.</span><span class="sxs-lookup"><span data-stu-id="1e174-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="1e174-104">Los ejemplos de este tema muestran cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="1e174-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="1e174-105">También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="1e174-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="1e174-106">Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="1e174-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="1e174-107">Para crear un elemento XML</span><span class="sxs-lookup"><span data-stu-id="1e174-107">To create an XML element</span></span>  
  
- <span data-ttu-id="1e174-108">Crear el XML en línea mediante la sintaxis de literales XML, que es el mismo que la sintaxis XML.</span><span class="sxs-lookup"><span data-stu-id="1e174-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="1e174-109">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="1e174-109">Run the code.</span></span> <span data-ttu-id="1e174-110">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="1e174-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="1e174-111">Para crear un documento XML</span><span class="sxs-lookup"><span data-stu-id="1e174-111">To create an XML document</span></span>  
  
- <span data-ttu-id="1e174-112">Crear el documento XML en línea.</span><span class="sxs-lookup"><span data-stu-id="1e174-112">Create the XML document inline.</span></span> <span data-ttu-id="1e174-113">El código siguiente crea un documento XML que tiene la sintaxis literal, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="1e174-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="1e174-114">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="1e174-114">Run the code.</span></span> <span data-ttu-id="1e174-115">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="1e174-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="1e174-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e174-116">See also</span></span>

- [<span data-ttu-id="1e174-117">XML</span><span class="sxs-lookup"><span data-stu-id="1e174-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="1e174-118">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e174-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="1e174-119">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="1e174-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="1e174-120">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="1e174-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
