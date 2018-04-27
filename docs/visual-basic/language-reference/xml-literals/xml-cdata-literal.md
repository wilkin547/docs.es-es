---
title: Literal de CDATA XML (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e8dfc091409e060e20970b0b6d6bc19b4fc2aeea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="ae325-102">Literal de CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae325-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="ae325-103">Un literal que representa un <xref:System.Xml.Linq.XCData> objeto.</span><span class="sxs-lookup"><span data-stu-id="ae325-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae325-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae325-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="ae325-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ae325-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="ae325-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ae325-106">Required.</span></span> <span data-ttu-id="ae325-107">Denota el inicio de la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="ae325-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="ae325-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ae325-108">Required.</span></span> <span data-ttu-id="ae325-109">Contenido de texto que aparezca en la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="ae325-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="ae325-110">Requerido.</span><span class="sxs-lookup"><span data-stu-id="ae325-110">Required.</span></span> <span data-ttu-id="ae325-111">Denota el final de la sección.</span><span class="sxs-lookup"><span data-stu-id="ae325-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae325-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae325-112">Return Value</span></span>  
 <span data-ttu-id="ae325-113">Un objeto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="ae325-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae325-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae325-114">Remarks</span></span>  
 <span data-ttu-id="ae325-115">Secciones CDATA XML contienen texto sin formato que debe incluyen, pero no analizar, con el XML que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="ae325-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="ae325-116">Una sección CDATA XML puede contener cualquier texto.</span><span class="sxs-lookup"><span data-stu-id="ae325-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="ae325-117">Esto incluye los caracteres XML reservados.</span><span class="sxs-lookup"><span data-stu-id="ae325-117">This includes reserved XML characters.</span></span> <span data-ttu-id="ae325-118">La sección CDATA XML finaliza con la secuencia "]] >".</span><span class="sxs-lookup"><span data-stu-id="ae325-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="ae325-119">Esto implica lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae325-119">This implies the following points:</span></span>  
  
-   <span data-ttu-id="ae325-120">No se puede usar una expresión incrustada en un literal de CDATA XML porque los delimitadores de expresión incrustada son contenido de CDATA XML válido.</span><span class="sxs-lookup"><span data-stu-id="ae325-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
-   <span data-ttu-id="ae325-121">Secciones CDATA XML no se pueden anidar, porque `content` no puede contener el valor "]] >".</span><span class="sxs-lookup"><span data-stu-id="ae325-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="ae325-122">Puede asignar un literal de CDATA XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="ae325-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae325-123">Un literal XML puede abarcar varias líneas pero no usa caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="ae325-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="ae325-124">Esto le permite copiar el contenido de un documento XML y pegarlos directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ae325-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="ae325-125">El compilador de Visual Basic convierte el literal de CDATA XML a una llamada a la <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="ae325-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae325-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae325-126">Example</span></span>  
 <span data-ttu-id="ae325-127">En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener literal \<XML > etiquetas".</span><span class="sxs-lookup"><span data-stu-id="ae325-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ae325-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae325-128">See Also</span></span>  
 <xref:System.Xml.Linq.XCData>  
 [<span data-ttu-id="ae325-129">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="ae325-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="ae325-130">Literales XML</span><span class="sxs-lookup"><span data-stu-id="ae325-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="ae325-131">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae325-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
