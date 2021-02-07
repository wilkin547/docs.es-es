---
description: 'Más información acerca de: literal de comentario XML (Visual Basic)'
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
ms.openlocfilehash: f44d2e132236d74d312910921fabb3a85afd82d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768745"
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="a98a4-103">Literal de comentario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a98a4-103">XML Comment Literal (Visual Basic)</span></span>

<span data-ttu-id="a98a4-104">Literal que representa un <xref:System.Xml.Linq.XComment> objeto.</span><span class="sxs-lookup"><span data-stu-id="a98a4-104">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a98a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a98a4-105">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="a98a4-106">Partes</span><span class="sxs-lookup"><span data-stu-id="a98a4-106">Parts</span></span>  
  
|<span data-ttu-id="a98a4-107">Término</span><span class="sxs-lookup"><span data-stu-id="a98a4-107">Term</span></span>|<span data-ttu-id="a98a4-108">Definición</span><span class="sxs-lookup"><span data-stu-id="a98a4-108">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="a98a4-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="a98a4-109">Required.</span></span> <span data-ttu-id="a98a4-110">Denota el inicio del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="a98a4-110">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="a98a4-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="a98a4-111">Required.</span></span> <span data-ttu-id="a98a4-112">Texto que se va a mostrar en el comentario XML.</span><span class="sxs-lookup"><span data-stu-id="a98a4-112">Text to appear in the XML comment.</span></span> <span data-ttu-id="a98a4-113">No puede contener una serie de dos guiones (--) ni terminar con un guión adyacente a la etiqueta de cierre.</span><span class="sxs-lookup"><span data-stu-id="a98a4-113">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="a98a4-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="a98a4-114">Required.</span></span> <span data-ttu-id="a98a4-115">Denota el final del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="a98a4-115">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="a98a4-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a98a4-116">Return Value</span></span>  

 <span data-ttu-id="a98a4-117">Objeto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="a98a4-117">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a98a4-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a98a4-118">Remarks</span></span>  

 <span data-ttu-id="a98a4-119">Los literales de comentario XML no incluyen el contenido del documento; contienen información sobre el documento.</span><span class="sxs-lookup"><span data-stu-id="a98a4-119">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="a98a4-120">La sección de comentarios XML finaliza con la secuencia "-->".</span><span class="sxs-lookup"><span data-stu-id="a98a4-120">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="a98a4-121">Esto implica los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a98a4-121">This implies the following points:</span></span>  
  
- <span data-ttu-id="a98a4-122">No se puede usar una expresión insertada en un literal de comentario XML porque los delimitadores de expresión incrustados son contenido de comentario XML válido.</span><span class="sxs-lookup"><span data-stu-id="a98a4-122">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
- <span data-ttu-id="a98a4-123">Las secciones de comentarios XML no se pueden anidar porque `content` no pueden contener el valor "-->".</span><span class="sxs-lookup"><span data-stu-id="a98a4-123">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="a98a4-124">Puede asignar un literal de comentario XML a una variable o puede incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a98a4-124">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a98a4-125">Un literal XML puede abarcar varias líneas sin utilizar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="a98a4-125">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="a98a4-126">Esta característica permite copiar contenido de un documento XML y pegarlo directamente en un programa Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a98a4-126">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="a98a4-127">El compilador Visual Basic convierte el literal de comentario XML en una llamada al <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="a98a4-127">The Visual Basic compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a98a4-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a98a4-128">Example</span></span>  

 <span data-ttu-id="a98a4-129">En el ejemplo siguiente se crea un comentario XML que contiene el texto "This is a comment".</span><span class="sxs-lookup"><span data-stu-id="a98a4-129">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="a98a4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a98a4-130">See also</span></span>

- <xref:System.Xml.Linq.XComment>
- [<span data-ttu-id="a98a4-131">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="a98a4-131">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="a98a4-132">Literales XML</span><span class="sxs-lookup"><span data-stu-id="a98a4-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="a98a4-133">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a98a4-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
