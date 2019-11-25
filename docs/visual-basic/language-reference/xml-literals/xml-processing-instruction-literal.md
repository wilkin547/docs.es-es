---
title: Literal de instrucción de procesamiento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3602a81feae9287a77d060bb46f10eefee4fc05d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347044"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="bd856-102">Literal de instrucción de procesamiento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd856-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="bd856-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span><span class="sxs-lookup"><span data-stu-id="bd856-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd856-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd856-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="bd856-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="bd856-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="bd856-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="bd856-106">Required.</span></span> <span data-ttu-id="bd856-107">Denotes the start of the XML processing instruction literal.</span><span class="sxs-lookup"><span data-stu-id="bd856-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="bd856-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="bd856-108">Required.</span></span> <span data-ttu-id="bd856-109">Name indicating which application the processing instruction targets.</span><span class="sxs-lookup"><span data-stu-id="bd856-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="bd856-110">Cannot begin with "xml" or "XML".</span><span class="sxs-lookup"><span data-stu-id="bd856-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="bd856-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="bd856-111">Optional.</span></span> <span data-ttu-id="bd856-112">String indicating how the application targeted by `piName` should process the XML document.</span><span class="sxs-lookup"><span data-stu-id="bd856-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="bd856-113">Requerido.</span><span class="sxs-lookup"><span data-stu-id="bd856-113">Required.</span></span> <span data-ttu-id="bd856-114">Denotes the end of the processing instruction.</span><span class="sxs-lookup"><span data-stu-id="bd856-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd856-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bd856-115">Return Value</span></span>  
 <span data-ttu-id="bd856-116">Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="bd856-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd856-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd856-117">Remarks</span></span>  
 <span data-ttu-id="bd856-118">XML processing instruction literals indicate how applications should process an XML document.</span><span class="sxs-lookup"><span data-stu-id="bd856-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="bd856-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span><span class="sxs-lookup"><span data-stu-id="bd856-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="bd856-120">The application interprets the meaning of `piName` and `piData`.</span><span class="sxs-lookup"><span data-stu-id="bd856-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="bd856-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span><span class="sxs-lookup"><span data-stu-id="bd856-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="bd856-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bd856-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd856-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span><span class="sxs-lookup"><span data-stu-id="bd856-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="bd856-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span><span class="sxs-lookup"><span data-stu-id="bd856-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd856-125">An XML literal can span multiple lines without needing line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="bd856-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="bd856-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="bd856-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="bd856-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="bd856-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd856-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd856-128">Example</span></span>  
 <span data-ttu-id="bd856-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span><span class="sxs-lookup"><span data-stu-id="bd856-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="bd856-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd856-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="bd856-131">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="bd856-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="bd856-132">Literales XML</span><span class="sxs-lookup"><span data-stu-id="bd856-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="bd856-133">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd856-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
