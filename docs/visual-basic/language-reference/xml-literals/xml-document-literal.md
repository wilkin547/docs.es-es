---
title: Literal de documento XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: 3a2182d2937827bc8dc45e22307a3668420261a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400207"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="356cb-102">Literal de documento XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="356cb-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="356cb-103">Literal que representa un <xref:System.Xml.Linq.XDocument> objeto.</span><span class="sxs-lookup"><span data-stu-id="356cb-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="356cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="356cb-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="356cb-105">Partes</span><span class="sxs-lookup"><span data-stu-id="356cb-105">Parts</span></span>  
  
|<span data-ttu-id="356cb-106">Término</span><span class="sxs-lookup"><span data-stu-id="356cb-106">Term</span></span>|<span data-ttu-id="356cb-107">Definición</span><span class="sxs-lookup"><span data-stu-id="356cb-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="356cb-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="356cb-108">Optional.</span></span> <span data-ttu-id="356cb-109">Texto literal que declara Qué codificación utiliza el documento.</span><span class="sxs-lookup"><span data-stu-id="356cb-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="356cb-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="356cb-110">Optional.</span></span> <span data-ttu-id="356cb-111">Texto literal.</span><span class="sxs-lookup"><span data-stu-id="356cb-111">Literal text.</span></span> <span data-ttu-id="356cb-112">Debe ser "Yes" o "no".</span><span class="sxs-lookup"><span data-stu-id="356cb-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="356cb-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="356cb-113">Optional.</span></span> <span data-ttu-id="356cb-114">Lista de instrucciones de procesamiento XML y comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="356cb-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="356cb-115">Tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="356cb-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="356cb-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="356cb-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="356cb-117">Cada `piComment` puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="356cb-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="356cb-118">-   [Literal de instrucción de procesamiento XML](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="356cb-118">-   [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="356cb-119">-   [Literal de comentario XML](xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="356cb-119">-   [XML Comment Literal](xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="356cb-120">Necesario.</span><span class="sxs-lookup"><span data-stu-id="356cb-120">Required.</span></span> <span data-ttu-id="356cb-121">Elemento raíz del documento.</span><span class="sxs-lookup"><span data-stu-id="356cb-121">Root element of the document.</span></span> <span data-ttu-id="356cb-122">El formato es uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="356cb-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="356cb-123">[Literal de elemento XML](xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="356cb-123">[XML Element Literal](xml-element-literal.md).</span></span></li><li><span data-ttu-id="356cb-124">Expresión insertada con el formato `<%=` `elementExp` `%>` .</span><span class="sxs-lookup"><span data-stu-id="356cb-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="356cb-125">`elementExp`Devuelve uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="356cb-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="356cb-126">Objeto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="356cb-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="356cb-127">Colección que contiene un <xref:System.Xml.Linq.XElement> objeto y cualquier número de <xref:System.Xml.Linq.XProcessingInstruction> objetos y <xref:System.Xml.Linq.XComment> .</span><span class="sxs-lookup"><span data-stu-id="356cb-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="356cb-128">Para obtener más información, vea [expresiones incrustadas en XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="356cb-128">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="356cb-129">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="356cb-129">Return Value</span></span>  
 <span data-ttu-id="356cb-130">Objeto <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="356cb-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="356cb-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="356cb-131">Remarks</span></span>  
 <span data-ttu-id="356cb-132">Un literal de documento XML se identifica mediante la declaración XML al principio del literal.</span><span class="sxs-lookup"><span data-stu-id="356cb-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="356cb-133">Aunque cada literal de documento XML debe tener exactamente un elemento XML raíz, puede tener cualquier número de instrucciones de procesamiento XML y comentarios XML.</span><span class="sxs-lookup"><span data-stu-id="356cb-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="356cb-134">Un literal de documento XML no puede aparecer en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="356cb-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="356cb-135">Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="356cb-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="356cb-136">Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="356cb-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="356cb-137">El compilador Visual Basic convierte el literal del documento XML en llamadas a los <xref:System.Xml.Linq.XDocument.%23ctor%2A> <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructores y.</span><span class="sxs-lookup"><span data-stu-id="356cb-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="356cb-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="356cb-138">Example</span></span>  
 <span data-ttu-id="356cb-139">En el ejemplo siguiente se crea un documento XML que tiene una declaración XML, una instrucción de procesamiento, un comentario y un elemento que contiene otro elemento.</span><span class="sxs-lookup"><span data-stu-id="356cb-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="356cb-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="356cb-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="356cb-141">Literal de instrucción de procesamiento XML</span><span class="sxs-lookup"><span data-stu-id="356cb-141">XML Processing Instruction Literal</span></span>](xml-processing-instruction-literal.md)
- [<span data-ttu-id="356cb-142">Literal de comentario XML</span><span class="sxs-lookup"><span data-stu-id="356cb-142">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="356cb-143">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="356cb-143">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="356cb-144">Literales XML</span><span class="sxs-lookup"><span data-stu-id="356cb-144">XML Literals</span></span>](index.md)
- [<span data-ttu-id="356cb-145">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="356cb-145">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="356cb-146">Expresiones insertadas en XML</span><span class="sxs-lookup"><span data-stu-id="356cb-146">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
