---
title: Literal de documento XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 8a489be46295c213b7a8b355eb3c9786d49dd8f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958499"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="4c10f-102">Literal de documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c10f-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="4c10f-103">Literal que representa un <xref:System.Xml.Linq.XDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="4c10f-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c10f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c10f-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4c10f-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="4c10f-105">Parts</span></span>  
  
|<span data-ttu-id="4c10f-106">Término</span><span class="sxs-lookup"><span data-stu-id="4c10f-106">Term</span></span>|<span data-ttu-id="4c10f-107">Definición</span><span class="sxs-lookup"><span data-stu-id="4c10f-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="4c10f-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4c10f-108">Optional.</span></span> <span data-ttu-id="4c10f-109">Texto literal que declara Qué codificación utiliza el documento.</span><span class="sxs-lookup"><span data-stu-id="4c10f-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="4c10f-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4c10f-110">Optional.</span></span> <span data-ttu-id="4c10f-111">Texto literal.</span><span class="sxs-lookup"><span data-stu-id="4c10f-111">Literal text.</span></span> <span data-ttu-id="4c10f-112">Debe ser "Yes" o "no".</span><span class="sxs-lookup"><span data-stu-id="4c10f-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="4c10f-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4c10f-113">Optional.</span></span> <span data-ttu-id="4c10f-114">Lista de instrucciones de procesamiento XML y comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="4c10f-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="4c10f-115">Tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="4c10f-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="4c10f-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="4c10f-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="4c10f-117">Cada `piComment` puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c10f-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="4c10f-118">-   [Literal de instrucción de procesamiento XML](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4c10f-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="4c10f-119">-   [Literal de comentario XML](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4c10f-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="4c10f-120">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4c10f-120">Required.</span></span> <span data-ttu-id="4c10f-121">Elemento raíz del documento.</span><span class="sxs-lookup"><span data-stu-id="4c10f-121">Root element of the document.</span></span> <span data-ttu-id="4c10f-122">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c10f-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="4c10f-123">[Literal de elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4c10f-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="4c10f-124">Expresión insertada con el `<%=` formato `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="4c10f-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="4c10f-125">`elementExp` Devuelve uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c10f-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="4c10f-126">Un objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4c10f-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="4c10f-127">Colección que contiene un <xref:System.Xml.Linq.XElement> objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction> objetos y <xref:System.Xml.Linq.XComment> .</span><span class="sxs-lookup"><span data-stu-id="4c10f-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="4c10f-128">Para obtener más información, vea [expresiones incrustadas en XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4c10f-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="4c10f-129">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4c10f-129">Return Value</span></span>  
 <span data-ttu-id="4c10f-130">Un objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="4c10f-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c10f-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c10f-131">Remarks</span></span>  
 <span data-ttu-id="4c10f-132">Un literal de documento XML se identifica mediante la declaración XML al principio del literal.</span><span class="sxs-lookup"><span data-stu-id="4c10f-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="4c10f-133">Aunque cada literal de documento XML debe tener exactamente un elemento XML raíz, puede tener cualquier número de instrucciones de procesamiento XML y comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="4c10f-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="4c10f-134">Un literal de documento XML no puede aparecer en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4c10f-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c10f-135">Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="4c10f-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="4c10f-136">Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4c10f-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="4c10f-137">El compilador Visual Basic convierte el literal del documento XML en llamadas <xref:System.Xml.Linq.XDocument.%23ctor%2A> a <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> los constructores y.</span><span class="sxs-lookup"><span data-stu-id="4c10f-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c10f-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c10f-138">Example</span></span>  
 <span data-ttu-id="4c10f-139">En el ejemplo siguiente se crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="4c10f-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="4c10f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c10f-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="4c10f-141">Literal de instrucción de procesamiento XML</span><span class="sxs-lookup"><span data-stu-id="4c10f-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="4c10f-142">Literal de comentario XML</span><span class="sxs-lookup"><span data-stu-id="4c10f-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="4c10f-143">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="4c10f-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="4c10f-144">Literales XML</span><span class="sxs-lookup"><span data-stu-id="4c10f-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="4c10f-145">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c10f-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="4c10f-146">Expresiones incrustadas en XML</span><span class="sxs-lookup"><span data-stu-id="4c10f-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
