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
ms.locfileid: "33652875"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="fa2d8-102">Cómo: Crear literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa2d8-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="fa2d8-103">Puede crear un documento XML, fragmento o elemento directamente en el código mediante un literal XML.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="fa2d8-104">Los ejemplos de este tema muestran cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="fa2d8-105">También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="fa2d8-106">Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="fa2d8-107">Para crear un elemento XML</span><span class="sxs-lookup"><span data-stu-id="fa2d8-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="fa2d8-108">Crear el XML en línea mediante la sintaxis de literales de XML, que es el mismo que la sintaxis XML propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="fa2d8-109">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-109">Run the code.</span></span> <span data-ttu-id="fa2d8-110">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="fa2d8-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="fa2d8-111">Para crear un documento XML</span><span class="sxs-lookup"><span data-stu-id="fa2d8-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="fa2d8-112">Crear el documento XML insertado.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-112">Create the XML document inline.</span></span> <span data-ttu-id="fa2d8-113">El código siguiente crea un documento XML que tiene sintaxis de literales, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="fa2d8-114">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-114">Run the code.</span></span> <span data-ttu-id="fa2d8-115">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="fa2d8-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="fa2d8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa2d8-116">See Also</span></span>  
 [<span data-ttu-id="fa2d8-117">XML</span><span class="sxs-lookup"><span data-stu-id="fa2d8-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="fa2d8-118">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa2d8-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="fa2d8-119">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="fa2d8-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="fa2d8-120">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="fa2d8-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
