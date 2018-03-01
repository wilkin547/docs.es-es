---
title: "Literal de instrucción de procesamiento XML (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ce0f2d0dff80072beefdb4f84643ea28e2cf165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="ca9cc-102">Literal de instrucción de procesamiento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca9cc-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="ca9cc-103">Un literal que representa un <xref:System.Xml.Linq.XProcessingInstruction> objeto.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca9cc-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="ca9cc-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ca9cc-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="ca9cc-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-106">Required.</span></span> <span data-ttu-id="ca9cc-107">Denota el inicio de la instrucción de procesamiento XML literal.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="ca9cc-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-108">Required.</span></span> <span data-ttu-id="ca9cc-109">El nombre que indica la aplicación que los destinos de instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="ca9cc-110">No puede comenzar con "xml" o "XML".</span><span class="sxs-lookup"><span data-stu-id="ca9cc-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="ca9cc-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-111">Optional.</span></span> <span data-ttu-id="ca9cc-112">Cadena que indica cómo la aplicación de destino de `piName` debe procesar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="ca9cc-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-113">Required.</span></span> <span data-ttu-id="ca9cc-114">Denota el final de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca9cc-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ca9cc-115">Return Value</span></span>  
 <span data-ttu-id="ca9cc-116">Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca9cc-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca9cc-117">Remarks</span></span>  
 <span data-ttu-id="ca9cc-118">Los literales de instrucción de procesamiento XML indican cómo las aplicaciones deben procesar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="ca9cc-119">Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="ca9cc-120">La aplicación interpreta el significado de `piName` y `piData`.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="ca9cc-121">El literal de documento XML utiliza la sintaxis que son similar a la de la instrucción de procesamiento de XML.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="ca9cc-122">Para obtener más información, consulte [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="ca9cc-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca9cc-123">El `piName` elemento no puede comenzar con las cadenas "xml" o "XML", porque la especificación XML 1.0 reserva esos identificadores.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="ca9cc-124">Puede asignar un literal de instrucción de procesamiento XML a una variable o incluirlo en un literal de documento XML.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca9cc-125">Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="ca9cc-126">Esto le permite copiar el contenido de un documento XML y pegarlos directamente en un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programa.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="ca9cc-127">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte el literal de instrucción de procesamiento XML en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-127">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca9cc-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca9cc-128">Example</span></span>  
 <span data-ttu-id="ca9cc-129">En el ejemplo siguiente se crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ca9cc-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ca9cc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca9cc-130">See Also</span></span>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [<span data-ttu-id="ca9cc-131">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="ca9cc-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="ca9cc-132">Literales XML</span><span class="sxs-lookup"><span data-stu-id="ca9cc-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="ca9cc-133">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca9cc-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
