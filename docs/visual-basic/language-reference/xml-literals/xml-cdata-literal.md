---
title: Literal de CDATA XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: ee269ca5cf9635fec35165d1ea65d6a6483cadef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938637"
---
# <a name="xml-cdata-literal-visual-basic"></a><span data-ttu-id="8c89e-102">Literal de CDATA XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c89e-102">XML CDATA Literal (Visual Basic)</span></span>
<span data-ttu-id="8c89e-103">Un literal que representa un <xref:System.Xml.Linq.XCData> objeto.</span><span class="sxs-lookup"><span data-stu-id="8c89e-103">A literal representing an <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c89e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c89e-104">Syntax</span></span>  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a><span data-ttu-id="8c89e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8c89e-105">Parts</span></span>  
 `<![CDATA[`  
 <span data-ttu-id="8c89e-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c89e-106">Required.</span></span> <span data-ttu-id="8c89e-107">Denota el inicio de la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="8c89e-107">Denotes the start of the XML CDATA section.</span></span>  
  
 `content`  
 <span data-ttu-id="8c89e-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c89e-108">Required.</span></span> <span data-ttu-id="8c89e-109">Contenido de texto que aparezca en la sección XML CDATA.</span><span class="sxs-lookup"><span data-stu-id="8c89e-109">Text content to appear in the XML CDATA section.</span></span>  
  
 `]]>`  
 <span data-ttu-id="8c89e-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c89e-110">Required.</span></span> <span data-ttu-id="8c89e-111">Denota el final de la sección.</span><span class="sxs-lookup"><span data-stu-id="8c89e-111">Denotes the end of the section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c89e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8c89e-112">Return Value</span></span>  
 <span data-ttu-id="8c89e-113">Un objeto <xref:System.Xml.Linq.XCData>.</span><span class="sxs-lookup"><span data-stu-id="8c89e-113">An <xref:System.Xml.Linq.XCData> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c89e-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c89e-114">Remarks</span></span>  
 <span data-ttu-id="8c89e-115">Secciones de CDATA XML contienen texto sin formato que debe incluir, pero no puede analizar, con el XML que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="8c89e-115">XML CDATA sections contain raw text that should be included, but not parsed, with the XML that contains it.</span></span> <span data-ttu-id="8c89e-116">Una sección CDATA XML puede contener cualquier texto.</span><span class="sxs-lookup"><span data-stu-id="8c89e-116">A XML CDATA section can contain any text.</span></span> <span data-ttu-id="8c89e-117">Esto incluye los caracteres XML reservados.</span><span class="sxs-lookup"><span data-stu-id="8c89e-117">This includes reserved XML characters.</span></span> <span data-ttu-id="8c89e-118">La sección CDATA XML finaliza con la secuencia "]] >".</span><span class="sxs-lookup"><span data-stu-id="8c89e-118">The XML CDATA section ends with the sequence "]]>".</span></span> <span data-ttu-id="8c89e-119">Esto implica los siguientes puntos:</span><span class="sxs-lookup"><span data-stu-id="8c89e-119">This implies the following points:</span></span>  
  
- <span data-ttu-id="8c89e-120">No se puede usar una expresión incrustada en un literal de CDATA XML porque los delimitadores de expresión incrustada son contenido de CDATA XML válido.</span><span class="sxs-lookup"><span data-stu-id="8c89e-120">You cannot use an embedded expression in an XML CDATA literal because the embedded expression delimiters are valid XML CDATA content.</span></span>  
  
- <span data-ttu-id="8c89e-121">No se puede anidar las secciones de CDATA XML porque `content` no puede contener el valor "]] >".</span><span class="sxs-lookup"><span data-stu-id="8c89e-121">XML CDATA sections cannot be nested, because `content` cannot contain the value "]]>".</span></span>  
  
 <span data-ttu-id="8c89e-122">Puede asignar un literal de CDATA XML a una variable o incluirlo en un literal de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8c89e-122">You can assign an XML CDATA literal to a variable, or include it in an XML element literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c89e-123">Un literal XML puede abarcar varias líneas, pero no usa caracteres de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="8c89e-123">An XML literal can span multiple lines but does not use line continuation characters.</span></span> <span data-ttu-id="8c89e-124">Esto permite copiar el contenido de un documento XML y péguelo directamente en un programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8c89e-124">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="8c89e-125">El compilador de Visual Basic convierte el literal de CDATA XML a una llamada a la <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="8c89e-125">The Visual Basic compiler converts the XML CDATA literal to a call to the <xref:System.Xml.Linq.XCData.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c89e-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c89e-126">Example</span></span>  
 <span data-ttu-id="8c89e-127">En el ejemplo siguiente se crea una sección CDATA que contiene el texto "puede contener literal \<XML > etiquetas".</span><span class="sxs-lookup"><span data-stu-id="8c89e-127">The following example creates a CDATA section that contains the text "Can contain literal \<XML> tags".</span></span>  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="8c89e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c89e-128">See also</span></span>

- <xref:System.Xml.Linq.XCData>
- [<span data-ttu-id="8c89e-129">Literal de elemento XML</span><span class="sxs-lookup"><span data-stu-id="8c89e-129">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="8c89e-130">Literales XML</span><span class="sxs-lookup"><span data-stu-id="8c89e-130">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="8c89e-131">Crear XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c89e-131">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
