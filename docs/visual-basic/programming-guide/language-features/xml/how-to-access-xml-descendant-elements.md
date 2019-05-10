---
title: Procedimiento Acceso a elementos descendientes de XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 008fd599e527ad4a8d483d2468a57ece1d2b4bdc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598598"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="117ee-102">Procedimiento Acceso a elementos descendientes de XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="117ee-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="117ee-103">En este ejemplo se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tiene un nombre especificado y que se incluyen en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="117ee-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="117ee-104">En concreto, usa el `Value` propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de la propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="117ee-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="117ee-105">El `name` propiedad de eje descendiente Obtiene todos los elementos llamados `name` que están contenidas en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="117ee-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="117ee-106">En este ejemplo también usa el `phone` propiedad de eje descendiente para tener acceso a todos los descendientes denominados `phone` que están contenidas en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="117ee-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="117ee-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="117ee-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="117ee-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="117ee-108">Compiling the Code</span></span>  
 <span data-ttu-id="117ee-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="117ee-109">This example requires:</span></span>  
  
- <span data-ttu-id="117ee-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="117ee-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117ee-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="117ee-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="117ee-112">Propiedad del eje descendiente XML</span><span class="sxs-lookup"><span data-stu-id="117ee-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="117ee-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="117ee-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="117ee-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="117ee-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="117ee-115">XML</span><span class="sxs-lookup"><span data-stu-id="117ee-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
