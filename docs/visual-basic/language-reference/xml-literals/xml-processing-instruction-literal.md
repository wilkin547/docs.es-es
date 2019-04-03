---
title: Literal de instrucción de procesamiento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3fbb16a4d47801b671d37566573215d3a57afff1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820157"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="33cff-102">Literal de instrucción de procesamiento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33cff-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="33cff-103">Un literal que representa un <xref:System.Xml.Linq.XProcessingInstruction> objeto.</span><span class="sxs-lookup"><span data-stu-id="33cff-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33cff-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="33cff-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="33cff-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="33cff-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33cff-106">Required.</span></span> <span data-ttu-id="33cff-107">Denota el inicio de la instrucción de procesamiento XML literal.</span><span class="sxs-lookup"><span data-stu-id="33cff-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="33cff-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33cff-108">Required.</span></span> <span data-ttu-id="33cff-109">Asigne un nombre que indica qué aplicación los destinos de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="33cff-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="33cff-110">No puede empezar por "xml" o "XML".</span><span class="sxs-lookup"><span data-stu-id="33cff-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="33cff-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="33cff-111">Optional.</span></span> <span data-ttu-id="33cff-112">Cadena que indica cómo la aplicación de destino de `piName` debe procesar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="33cff-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="33cff-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33cff-113">Required.</span></span> <span data-ttu-id="33cff-114">Denota el final de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="33cff-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33cff-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33cff-115">Return Value</span></span>  
 <span data-ttu-id="33cff-116">Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="33cff-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33cff-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33cff-117">Remarks</span></span>  
 <span data-ttu-id="33cff-118">Los literales de instrucción de procesamiento XML indican cómo las aplicaciones deben procesar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="33cff-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="33cff-119">Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento.</span><span class="sxs-lookup"><span data-stu-id="33cff-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="33cff-120">La aplicación interpreta el significado de `piName` y `piData`.</span><span class="sxs-lookup"><span data-stu-id="33cff-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="33cff-121">El literal de documento XML usa la sintaxis que es similar de la instrucción de procesamiento de XML.</span><span class="sxs-lookup"><span data-stu-id="33cff-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="33cff-122">Para obtener más información, consulte [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="33cff-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33cff-123">El `piName` elemento no puede comenzar con las cadenas "xml" o "XML", ya que los identificadores de reserva de la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="33cff-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="33cff-124">Puede asignar un literal de instrucción de procesamiento de XML a una variable o incluirlo en un literal de documento XML.</span><span class="sxs-lookup"><span data-stu-id="33cff-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33cff-125">Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="33cff-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="33cff-126">Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="33cff-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="33cff-127">El compilador de Visual Basic convierte el literal de instrucción de procesamiento XML en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="33cff-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33cff-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33cff-128">Example</span></span>  
 <span data-ttu-id="33cff-129">El ejemplo siguiente crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.</span><span class="sxs-lookup"><span data-stu-id="33cff-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="33cff-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="33cff-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="33cff-131">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="33cff-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="33cff-132">Literales XML</span><span class="sxs-lookup"><span data-stu-id="33cff-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="33cff-133">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="33cff-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
