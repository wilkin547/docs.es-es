---
title: 'Cómo: Obtener acceso a elementos secundarios XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 32bdb1ba476a954bdad1f23c3ecc6129c90ccaac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347173"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="e2d0c-102">Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2d0c-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="e2d0c-103">En este ejemplo se muestra cómo usar una propiedad de eje secundario para tener acceso a todos los elementos secundarios XML que tienen un nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="e2d0c-104">En concreto, usa la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para obtener el valor del primer elemento de la colección que devuelve la propiedad del eje secundario `name`.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="e2d0c-105">La propiedad `name` eje secundario obtiene todos los elementos secundarios denominados `phone` en el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="e2d0c-106">En este ejemplo también se usa la propiedad del eje secundario `phone` para tener acceso a todos los elementos secundarios denominados `phone` contenidos en el objeto `contact`.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2d0c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2d0c-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="e2d0c-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e2d0c-108">Compile the code</span></span>  
 <span data-ttu-id="e2d0c-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e2d0c-109">This example requires:</span></span>  
  
- <span data-ttu-id="e2d0c-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d0c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2d0c-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e2d0c-112">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="e2d0c-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="e2d0c-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="e2d0c-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="e2d0c-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2d0c-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="e2d0c-115">XML</span><span class="sxs-lookup"><span data-stu-id="e2d0c-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
