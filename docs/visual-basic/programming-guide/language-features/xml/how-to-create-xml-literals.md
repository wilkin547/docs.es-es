---
title: "Cómo: Crear literales XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce1bf763529b436158c2d74811c4938182166f92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="99ef0-102">Cómo: Crear literales XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99ef0-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="99ef0-103">Puede crear un documento XML, fragmento o elemento directamente en el código mediante un literal XML.</span><span class="sxs-lookup"><span data-stu-id="99ef0-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="99ef0-104">Los ejemplos de este tema muestran cómo crear un elemento XML que tiene tres elementos secundarios y cómo crear un documento XML.</span><span class="sxs-lookup"><span data-stu-id="99ef0-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="99ef0-105">También puede usar el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="99ef0-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="99ef0-106">Para obtener más información, consulta <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="99ef0-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="99ef0-107">Para crear un elemento XML</span><span class="sxs-lookup"><span data-stu-id="99ef0-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="99ef0-108">Crear el XML en línea mediante la sintaxis de literales de XML, que es el mismo que la sintaxis XML propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="99ef0-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="99ef0-109">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="99ef0-109">Run the code.</span></span> <span data-ttu-id="99ef0-110">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="99ef0-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="99ef0-111">Para crear un documento XML</span><span class="sxs-lookup"><span data-stu-id="99ef0-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="99ef0-112">Crear el documento XML insertado.</span><span class="sxs-lookup"><span data-stu-id="99ef0-112">Create the XML document inline.</span></span> <span data-ttu-id="99ef0-113">El código siguiente crea un documento XML que tiene sintaxis de literales, una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="99ef0-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="99ef0-114">Ejecute el código.</span><span class="sxs-lookup"><span data-stu-id="99ef0-114">Run the code.</span></span> <span data-ttu-id="99ef0-115">El resultado de este código es:</span><span class="sxs-lookup"><span data-stu-id="99ef0-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="99ef0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ef0-116">See Also</span></span>  
 [<span data-ttu-id="99ef0-117">XML</span><span class="sxs-lookup"><span data-stu-id="99ef0-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="99ef0-118">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="99ef0-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="99ef0-119">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="99ef0-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="99ef0-120">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="99ef0-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
