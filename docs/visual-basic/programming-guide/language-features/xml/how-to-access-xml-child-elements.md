---
description: 'Más información acerca de cómo: obtener acceso a elementos secundarios XML (Visual Basic)'
title: Procedimiento para obtener acceso a elementos secundarios XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: fad4d45853006762bc319b0ff8f9143ef13058da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433244"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="9cfd5-103">Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cfd5-103">How to: Access XML Child Elements (Visual Basic)</span></span>

<span data-ttu-id="9cfd5-104">En este ejemplo se muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="9cfd5-104">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="9cfd5-105">En concreto, usa la <xref:System.Xml.Linq.XElement.Value%2A> propiedad para obtener el valor del primer elemento de la colección que `name` devuelve la propiedad del eje secundario.</span><span class="sxs-lookup"><span data-stu-id="9cfd5-105">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="9cfd5-106">La `name` propiedad del eje secundario obtiene todos los elementos secundarios denominados `phone` en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="9cfd5-106">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="9cfd5-107">En este ejemplo también se usa la `phone` propiedad del eje secundario para obtener acceso a todos los elementos secundarios denominados `phone` contenidos en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="9cfd5-107">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cfd5-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cfd5-108">Example</span></span>  

 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="9cfd5-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9cfd5-109">Compile the code</span></span>  

 <span data-ttu-id="9cfd5-110">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9cfd5-110">This example requires:</span></span>  
  
- <span data-ttu-id="9cfd5-111">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="9cfd5-111">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cfd5-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cfd5-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9cfd5-113">XML Child Axis Property</span><span class="sxs-lookup"><span data-stu-id="9cfd5-113">XML Child Axis Property</span></span>](../../../language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="9cfd5-114">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="9cfd5-114">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="9cfd5-115">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9cfd5-115">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="9cfd5-116">XML</span><span class="sxs-lookup"><span data-stu-id="9cfd5-116">XML</span></span>](index.md)
