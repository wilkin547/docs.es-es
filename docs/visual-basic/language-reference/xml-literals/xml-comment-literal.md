---
title: Literal de comentario XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
ms.openlocfilehash: 93c1346e54106b93f3932a494dea85d082ec994d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400220"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="47261-102">Literal de comentario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47261-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="47261-103">Literal que representa un <xref:System.Xml.Linq.XComment> objeto.</span><span class="sxs-lookup"><span data-stu-id="47261-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47261-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47261-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="47261-105">Partes</span><span class="sxs-lookup"><span data-stu-id="47261-105">Parts</span></span>  
  
|<span data-ttu-id="47261-106">Término</span><span class="sxs-lookup"><span data-stu-id="47261-106">Term</span></span>|<span data-ttu-id="47261-107">Definición</span><span class="sxs-lookup"><span data-stu-id="47261-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="47261-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="47261-108">Required.</span></span> <span data-ttu-id="47261-109">Denota el inicio del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="47261-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="47261-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="47261-110">Required.</span></span> <span data-ttu-id="47261-111">Texto que se va a mostrar en el comentario XML.</span><span class="sxs-lookup"><span data-stu-id="47261-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="47261-112">No puede contener una serie de dos guiones (--) ni terminar con un guión adyacente a la etiqueta de cierre.</span><span class="sxs-lookup"><span data-stu-id="47261-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="47261-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="47261-113">Required.</span></span> <span data-ttu-id="47261-114">Denota el final del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="47261-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="47261-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47261-115">Return Value</span></span>  
 <span data-ttu-id="47261-116">Objeto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="47261-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47261-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47261-117">Remarks</span></span>  
 <span data-ttu-id="47261-118">Los literales de comentario XML no incluyen el contenido del documento; contienen información sobre el documento.</span><span class="sxs-lookup"><span data-stu-id="47261-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="47261-119">La sección de comentarios XML finaliza con la secuencia "-->".</span><span class="sxs-lookup"><span data-stu-id="47261-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="47261-120">Esto implica los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="47261-120">This implies the following points:</span></span>  
  
- <span data-ttu-id="47261-121">No se puede usar una expresión insertada en un literal de comentario XML porque los delimitadores de expresión incrustados son contenido de comentario XML válido.</span><span class="sxs-lookup"><span data-stu-id="47261-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="47261-122">Las secciones de comentarios XML no se pueden anidar porque `content` no pueden contener el valor "-->".</span><span class="sxs-lookup"><span data-stu-id="47261-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="47261-123">Puede asignar un literal de comentario XML a una variable o puede incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="47261-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47261-124">Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="47261-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="47261-125">Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="47261-125">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="47261-126">El compilador Visual Basic convierte el literal de comentario XML en una llamada al <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="47261-126">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47261-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47261-127">Example</span></span>  
 <span data-ttu-id="47261-128">En el ejemplo siguiente se crea un comentario XML que contiene el texto "This is a comment".</span><span class="sxs-lookup"><span data-stu-id="47261-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="47261-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47261-129">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="47261-130">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="47261-130">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="47261-131">Literales XML</span><span class="sxs-lookup"><span data-stu-id="47261-131">XML Literals</span></span>](index.md)
- [<span data-ttu-id="47261-132">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47261-132">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
