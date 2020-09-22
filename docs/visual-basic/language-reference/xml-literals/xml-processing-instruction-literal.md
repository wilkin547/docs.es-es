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
ms.openlocfilehash: 3d18e58cb643fa075f6eb08eb6fe909d27a6737b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866410"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="b1f06-102">Literal de instrucción de procesamiento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1f06-102">XML Processing Instruction Literal (Visual Basic)</span></span>

<span data-ttu-id="b1f06-103">Literal que representa un <xref:System.Xml.Linq.XProcessingInstruction> objeto.</span><span class="sxs-lookup"><span data-stu-id="b1f06-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1f06-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="b1f06-105">Partes</span><span class="sxs-lookup"><span data-stu-id="b1f06-105">Parts</span></span>  

 `<?`  
 <span data-ttu-id="b1f06-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b1f06-106">Required.</span></span> <span data-ttu-id="b1f06-107">Denota el inicio del literal de instrucción de procesamiento XML.</span><span class="sxs-lookup"><span data-stu-id="b1f06-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="b1f06-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b1f06-108">Required.</span></span> <span data-ttu-id="b1f06-109">Nombre que indica la aplicación a la que se destina la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b1f06-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="b1f06-110">No puede comenzar por "XML" o "XML".</span><span class="sxs-lookup"><span data-stu-id="b1f06-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="b1f06-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="b1f06-111">Optional.</span></span> <span data-ttu-id="b1f06-112">Cadena que indica cómo la aplicación de destino `piName` debe procesar el documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1f06-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="b1f06-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b1f06-113">Required.</span></span> <span data-ttu-id="b1f06-114">Denota el final de la instrucción de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b1f06-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1f06-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b1f06-115">Return Value</span></span>  

 <span data-ttu-id="b1f06-116">Un objeto <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="b1f06-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1f06-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1f06-117">Remarks</span></span>  

 <span data-ttu-id="b1f06-118">Los literales de instrucciones de procesamiento XML indican cómo deben procesar las aplicaciones un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1f06-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="b1f06-119">Cuando una aplicación carga un documento XML, la aplicación puede comprobar las instrucciones de procesamiento XML para determinar cómo procesar el documento.</span><span class="sxs-lookup"><span data-stu-id="b1f06-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="b1f06-120">La aplicación interpreta el significado de `piName` y `piData` .</span><span class="sxs-lookup"><span data-stu-id="b1f06-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="b1f06-121">El literal de documento XML utiliza una sintaxis similar a la de la instrucción de procesamiento XML.</span><span class="sxs-lookup"><span data-stu-id="b1f06-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="b1f06-122">Para obtener más información, vea [literal de documento XML](xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="b1f06-122">For more information, see [XML Document Literal](xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1f06-123">El `piName` elemento no puede comenzar con las cadenas "XML" o "XML", ya que la especificación xml 1,0 reserva esos identificadores.</span><span class="sxs-lookup"><span data-stu-id="b1f06-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="b1f06-124">Puede asignar un literal de instrucción de procesamiento XML a una variable o incluirlo en un literal de documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1f06-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b1f06-125">Un literal XML puede abarcar varias líneas sin necesidad de caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="b1f06-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="b1f06-126">Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b1f06-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="b1f06-127">El compilador Visual Basic convierte el literal de instrucción de procesamiento XML en una llamada al <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="b1f06-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1f06-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1f06-128">Example</span></span>  

 <span data-ttu-id="b1f06-129">En el ejemplo siguiente se crea una instrucción de procesamiento que identifica una hoja de estilos para un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b1f06-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="b1f06-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1f06-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="b1f06-131">Literal de documento XML</span><span class="sxs-lookup"><span data-stu-id="b1f06-131">XML Document Literal</span></span>](xml-document-literal.md)
- [<span data-ttu-id="b1f06-132">Literales XML</span><span class="sxs-lookup"><span data-stu-id="b1f06-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="b1f06-133">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b1f06-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
