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
ms.openlocfilehash: 1906c9101f9a53bde13698d0ed17b7b8d0988c1d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981379"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="db592-102">Literal de instrucción de procesamiento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db592-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="db592-103">Un literal que representa un <xref:System.Xml.Linq.XProcessingInstruction> objeto.</span><span class="sxs-lookup"><span data-stu-id="db592-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db592-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db592-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="db592-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="db592-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="db592-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db592-106">Required.</span></span> <span data-ttu-id="db592-107">Denota el inicio de la instrucción de procesamiento XML literal.</span><span class="sxs-lookup"><span data-stu-id="db592-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="db592-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db592-108">Required.</span></span> <span data-ttu-id="db592-109">Asigne un nombre que indica qué aplicación los destinos de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="db592-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="db592-110">No puede empezar por "xml" o "XML".</span><span class="sxs-lookup"><span data-stu-id="db592-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="db592-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="db592-111">Optional.</span></span> <span data-ttu-id="db592-112">Cadena que indica cómo la aplicación de destino de `piName` debe procesar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="db592-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="db592-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="db592-113">Required.</span></span> <span data-ttu-id="db592-114">Denota el final de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="db592-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db592-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db592-115">Return Value</span></span>  
 <span data-ttu-id="db592-116">Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="db592-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db592-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db592-117">Remarks</span></span>  
 <span data-ttu-id="db592-118">Los literales de instrucción de procesamiento XML indican cómo las aplicaciones deben procesar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="db592-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="db592-119">Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento.</span><span class="sxs-lookup"><span data-stu-id="db592-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="db592-120">La aplicación interpreta el significado de `piName` y `piData`.</span><span class="sxs-lookup"><span data-stu-id="db592-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="db592-121">El literal de documento XML usa la sintaxis que es similar de la instrucción de procesamiento de XML.</span><span class="sxs-lookup"><span data-stu-id="db592-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="db592-122">Para obtener más información, consulte [Literal de documento XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="db592-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db592-123">El `piName` elemento no puede comenzar con las cadenas "xml" o "XML", ya que los identificadores de reserva de la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="db592-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="db592-124">Puede asignar un literal de instrucción de procesamiento de XML a una variable o incluirlo en un literal de documento XML.</span><span class="sxs-lookup"><span data-stu-id="db592-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db592-125">Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="db592-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="db592-126">Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="db592-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="db592-127">El compilador de Visual Basic convierte el literal de instrucción de procesamiento XML en una llamada a la <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="db592-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db592-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db592-128">Example</span></span>  
 <span data-ttu-id="db592-129">El ejemplo siguiente crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.</span><span class="sxs-lookup"><span data-stu-id="db592-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="db592-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="db592-130">See also</span></span>
- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="db592-131">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="db592-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="db592-132">Literales XML</span><span class="sxs-lookup"><span data-stu-id="db592-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="db592-133">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db592-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
