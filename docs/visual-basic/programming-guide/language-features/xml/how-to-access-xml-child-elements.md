---
title: Procedimiento para obtener acceso a elementos secundarios XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 994249801eecc2984947efac9712df0047f076a4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392823"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="8627c-102">Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8627c-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="8627c-103">En este ejemplo se muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="8627c-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="8627c-104">En concreto, usa la <xref:System.Xml.Linq.XElement.Value%2A> propiedad para obtener el valor del primer elemento de la colección que `name` devuelve la propiedad del eje secundario.</span><span class="sxs-lookup"><span data-stu-id="8627c-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="8627c-105">La `name` propiedad del eje secundario obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="8627c-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="8627c-106">En este ejemplo también se usa la `phone` propiedad del eje secundario para obtener acceso a todos los elementos secundarios denominados `phone` contenidos en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="8627c-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8627c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8627c-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="8627c-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8627c-108">Compile the code</span></span>  
 <span data-ttu-id="8627c-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="8627c-109">This example requires:</span></span>  
  
- <span data-ttu-id="8627c-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="8627c-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8627c-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8627c-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8627c-112">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="8627c-112">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="8627c-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="8627c-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="8627c-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8627c-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="8627c-115">XML</span><span class="sxs-lookup"><span data-stu-id="8627c-115">XML</span></span>](index.md)
