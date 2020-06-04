---
title: Literal de CDATA XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: b9cc830d27625f192d8f5e059bd3783d05d8ba3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400233"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="4c784-102">Literal de CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c784-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="4c784-103">Literal que representa un <xref:System.Xml.Linq.XCData> objeto.</span><span class="sxs-lookup"><span data-stu-id="4c784-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c784-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c784-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="4c784-105">Partes</span><span class="sxs-lookup"><span data-stu-id="4c784-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="4c784-106">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4c784-106">Required.</span></span> <span data-ttu-id="4c784-107">Denota el inicio de la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="4c784-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="4c784-108">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4c784-108">Required.</span></span> <span data-ttu-id="4c784-109">Contenido de texto para que aparezca en la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="4c784-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="4c784-110">Necesario.</span><span class="sxs-lookup"><span data-stu-id="4c784-110">Required.</span></span> <span data-ttu-id="4c784-111">Denota el final de la sección.</span><span class="sxs-lookup"><span data-stu-id="4c784-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c784-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4c784-112">Return Value</span></span>  
 <span data-ttu-id="4c784-113">Objeto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="4c784-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c784-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c784-114">Remarks</span></span>  
 <span data-ttu-id="4c784-115">Las secciones CDATA XML contienen texto sin formato que se debe incluir, pero no analizar, con el XML que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="4c784-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="4c784-116">Una sección CDATA XML puede contener cualquier texto.</span><span class="sxs-lookup"><span data-stu-id="4c784-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="4c784-117">Esto incluye los caracteres XML reservados.</span><span class="sxs-lookup"><span data-stu-id="4c784-117">This includes reserved XML characters.</span></span> <span data-ttu-id="4c784-118">La sección CDATA XML finaliza con la secuencia "]] >".</span><span class="sxs-lookup"><span data-stu-id="4c784-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="4c784-119">Esto implica los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4c784-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="4c784-120">No se puede usar una expresión insertada en un literal CDATA XML porque los delimitadores de expresión incrustados son contenido XML CDATA válido.</span><span class="sxs-lookup"><span data-stu-id="4c784-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="4c784-121">Las secciones CDATA XML no se pueden anidar porque `content` no pueden contener el valor "]] >".</span><span class="sxs-lookup"><span data-stu-id="4c784-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="4c784-122">Puede asignar un literal CDATA XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4c784-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c784-123">Un literal XML puede abarcar varias líneas, pero no utiliza caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="4c784-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="4c784-124">Esto le permite copiar contenido de un documento XML y pegarlo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4c784-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="4c784-125">El compilador Visual Basic convierte el literal CDATA XML en una llamada al <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="4c784-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c784-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c784-126">Example</span></span>  
 <span data-ttu-id="4c784-127">En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener etiquetas literales \<XML> ".</span><span class="sxs-lookup"><span data-stu-id="4c784-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="4c784-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c784-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="4c784-129">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="4c784-129">XML Element Literal</span></span>](xml-element-literal.md)
- [<span data-ttu-id="4c784-130">Literales XML</span><span class="sxs-lookup"><span data-stu-id="4c784-130">XML Literals</span></span>](index.md)
- [<span data-ttu-id="4c784-131">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c784-131">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
