---
title: 'Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 4ec7743a30b8101d813ac414a8f5164aeb6c593d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649209"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="414bf-102">Cómo: Obtener acceso a elementos secundarios XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="414bf-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="414bf-103">Este ejemplo muestra cómo utilizar a un elemento secundario de propiedad de eje para tener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="414bf-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="414bf-104">En concreto, usa el <xref:System.Xml.Linq.XElement.Value%2A> propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de propiedad de eje secundario.</span><span class="sxs-lookup"><span data-stu-id="414bf-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="414bf-105">El `name` propiedad de eje secundario obtiene todos los elementos secundarios llamados `phone` en la `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="414bf-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="414bf-106">Este ejemplo también utiliza el `phone` propiedad de eje secundario para obtener acceso a todos los elementos secundarios llamados `phone` que están contenidas en el `contact` objeto.</span><span class="sxs-lookup"><span data-stu-id="414bf-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="414bf-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="414bf-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="414bf-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="414bf-108">Compiling the Code</span></span>  
 <span data-ttu-id="414bf-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="414bf-109">This example requires:</span></span>  
  
-   <span data-ttu-id="414bf-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="414bf-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414bf-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="414bf-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="414bf-112">Propiedad del eje secundario XML</span><span class="sxs-lookup"><span data-stu-id="414bf-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="414bf-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="414bf-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="414bf-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="414bf-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="414bf-115">XML</span><span class="sxs-lookup"><span data-stu-id="414bf-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
