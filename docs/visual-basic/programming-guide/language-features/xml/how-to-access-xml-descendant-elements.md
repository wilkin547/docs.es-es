---
title: Procedimiento para obtener acceso a elementos descendientes XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 03c403aa3c187b0b9d2006104eccaa1f9cd8aec5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392641"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="a9ad6-102">Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9ad6-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="a9ad6-103">En este ejemplo se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a9ad6-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="a9ad6-104">En concreto, usa la `Value` propiedad para obtener el valor del primer elemento de la colección que `name` devuelve la propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="a9ad6-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="a9ad6-105">La `name` propiedad de eje descendiente obtiene todos los elementos denominados `name` contenidos en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="a9ad6-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="a9ad6-106">En este ejemplo también se usa la `phone` propiedad AXIS descendiente para tener acceso a todos los descendientes denominados `phone` contenidos en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="a9ad6-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9ad6-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9ad6-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="a9ad6-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a9ad6-108">Compile the code</span></span>  
 <span data-ttu-id="a9ad6-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a9ad6-109">This example requires:</span></span>  
  
- <span data-ttu-id="a9ad6-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="a9ad6-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ad6-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9ad6-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a9ad6-112">XML Descendant Axis Property</span><span class="sxs-lookup"><span data-stu-id="a9ad6-112">XML Descendant Axis Property</span></span>](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="a9ad6-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="a9ad6-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="a9ad6-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9ad6-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="a9ad6-115">XML</span><span class="sxs-lookup"><span data-stu-id="a9ad6-115">XML</span></span>](index.md)
