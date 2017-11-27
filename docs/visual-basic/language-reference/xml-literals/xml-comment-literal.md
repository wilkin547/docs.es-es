---
title: Literal de comentario XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralComment
helpviewer_keywords:
- comment literal [Visual Basic]
- XML comments, adding [Visual Basic]
- XML comment literal [Visual Basic]
- XML literals [Visual Basic], comment
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36be34ac22cfe926a2eea946f5e4c4eb534de696
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-comment-literal-visual-basic"></a><span data-ttu-id="20494-102">Literal de comentario XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20494-102">XML Comment Literal (Visual Basic)</span></span>
<span data-ttu-id="20494-103">Un literal que representa un <xref:System.Xml.Linq.XComment> objeto.</span><span class="sxs-lookup"><span data-stu-id="20494-103">A literal representing an <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20494-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20494-104">Syntax</span></span>  
  
```xml  
<!-- content -->  
```  
  
## <a name="parts"></a><span data-ttu-id="20494-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="20494-105">Parts</span></span>  
  
|<span data-ttu-id="20494-106">Término</span><span class="sxs-lookup"><span data-stu-id="20494-106">Term</span></span>|<span data-ttu-id="20494-107">Definición</span><span class="sxs-lookup"><span data-stu-id="20494-107">Definition</span></span>|  
|---|---|  
|`<!--`|<span data-ttu-id="20494-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="20494-108">Required.</span></span> <span data-ttu-id="20494-109">Denota el inicio del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="20494-109">Denotes the start of the XML comment.</span></span>|  
|`content`|<span data-ttu-id="20494-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="20494-110">Required.</span></span> <span data-ttu-id="20494-111">Texto que aparecerá en el comentario XML.</span><span class="sxs-lookup"><span data-stu-id="20494-111">Text to appear in the XML comment.</span></span> <span data-ttu-id="20494-112">No puede contener una serie de dos guiones (-) ni terminar con un guión adyacente a la etiqueta de cierre.</span><span class="sxs-lookup"><span data-stu-id="20494-112">Cannot contain a series of two hyphens (--) or end with a hyphen adjacent to the closing tag.</span></span>|  
|`-->`|<span data-ttu-id="20494-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="20494-113">Required.</span></span> <span data-ttu-id="20494-114">Denota el final del comentario XML.</span><span class="sxs-lookup"><span data-stu-id="20494-114">Denotes the end of the XML comment.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="20494-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="20494-115">Return Value</span></span>  
 <span data-ttu-id="20494-116">Un objeto <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="20494-116">An <xref:System.Xml.Linq.XComment> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20494-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20494-117">Remarks</span></span>  
 <span data-ttu-id="20494-118">Los literales de comentario XML no contienen el contenido del documento; que contienen información sobre el documento.</span><span class="sxs-lookup"><span data-stu-id="20494-118">XML comment literals do not contain document content; they contain information about the document.</span></span> <span data-ttu-id="20494-119">La sección de comentario XML finaliza con la secuencia "-->".</span><span class="sxs-lookup"><span data-stu-id="20494-119">The XML comment section ends with the sequence "-->".</span></span> <span data-ttu-id="20494-120">Esto implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20494-120">This implies the following points:</span></span>  
  
-   <span data-ttu-id="20494-121">No se puede usar una expresión incrustada en un literal de comentario XML porque los delimitadores de expresión incrustada son contenido de comentario XML válido.</span><span class="sxs-lookup"><span data-stu-id="20494-121">You cannot use an embedded expression in an XML comment literal because the embedded expression delimiters are valid XML comment content.</span></span>  
  
-   <span data-ttu-id="20494-122">Secciones de comentario XML no se pueden anidar, porque `content` no puede contener el valor "-->".</span><span class="sxs-lookup"><span data-stu-id="20494-122">XML comment sections cannot be nested, because `content` cannot contain the value "-->".</span></span>  
  
 <span data-ttu-id="20494-123">Puede asignar un literal de comentario XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="20494-123">You can assign an XML comment literal to a variable, or you can include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20494-124">Un literal XML puede abarcar varias líneas sin usar caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="20494-124">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="20494-125">Esta característica le permite copiar el contenido de un documento XML y pegarlos directamente en un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programa.</span><span class="sxs-lookup"><span data-stu-id="20494-125">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="20494-126">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador convierte el literal de comentario XML a una llamada a la <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="20494-126">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML comment literal to a call to the <xref:System.Xml.Linq.XComment.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20494-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20494-127">Example</span></span>  
 <span data-ttu-id="20494-128">En el ejemplo siguiente se crea un comentario XML que contiene el texto "Esto es un comentario".</span><span class="sxs-lookup"><span data-stu-id="20494-128">The following example creates an XML comment that contains the text "This is a comment".</span></span>  
  
 [!code-vb[VbXMLSamples#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-comment-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="20494-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="20494-129">See Also</span></span>  
 <xref:System.Xml.Linq.XComment>  
 [<span data-ttu-id="20494-130">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="20494-130">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="20494-131">Literales XML</span><span class="sxs-lookup"><span data-stu-id="20494-131">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="20494-132">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20494-132">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
