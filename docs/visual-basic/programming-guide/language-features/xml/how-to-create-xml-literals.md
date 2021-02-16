---
description: 'Más información acerca de cómo: crear literales XML (Visual Basic)'
title: Procedimiento para crear literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 0e57b037d0567002fd570025e147771c4fab38f4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433296"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="257e2-103">Cómo: Crear literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="257e2-103">How to: Create XML Literals (Visual Basic)</span></span>

<span data-ttu-id="257e2-104">Puede crear un documento, fragmento o elemento XML directamente en el código mediante un literal XML.</span><span class="sxs-lookup"><span data-stu-id="257e2-104">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="257e2-105">En los ejemplos de este tema se muestra cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="257e2-105">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="257e2-106">También puede usar las [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="257e2-106">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="257e2-107">Para obtener más información, vea <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="257e2-107">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="257e2-108">Para crear un elemento XML</span><span class="sxs-lookup"><span data-stu-id="257e2-108">To create an XML element</span></span>  
  
- <span data-ttu-id="257e2-109">Cree el XML insertado mediante la sintaxis de literales XML, que es la misma que la sintaxis XML real.</span><span class="sxs-lookup"><span data-stu-id="257e2-109">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="257e2-110">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="257e2-110">Run the code.</span></span> <span data-ttu-id="257e2-111">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="257e2-111">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="257e2-112">Para crear un documento XML</span><span class="sxs-lookup"><span data-stu-id="257e2-112">To create an XML document</span></span>  
  
- <span data-ttu-id="257e2-113">Cree el documento XML en línea.</span><span class="sxs-lookup"><span data-stu-id="257e2-113">Create the XML document inline.</span></span> <span data-ttu-id="257e2-114">En el código siguiente se crea un documento XML que tiene una sintaxis literal, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="257e2-114">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="257e2-115">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="257e2-115">Run the code.</span></span> <span data-ttu-id="257e2-116">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="257e2-116">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="257e2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="257e2-117">See also</span></span>

- [<span data-ttu-id="257e2-118">XML</span><span class="sxs-lookup"><span data-stu-id="257e2-118">XML</span></span>](index.md)
- [<span data-ttu-id="257e2-119">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="257e2-119">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="257e2-120">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="257e2-120">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="257e2-121">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="257e2-121">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
