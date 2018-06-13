---
title: 'Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648491"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="4e28c-102">Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e28c-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="4e28c-103">Este ejemplo muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen el nombre especificado y que están incluidos en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4e28c-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="4e28c-104">En concreto, usa el `Value` propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de la propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="4e28c-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="4e28c-105">El `name` propiedad de eje descendiente Obtiene todos los elementos llamados `name` que están contenidas en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="4e28c-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="4e28c-106">Este ejemplo también utiliza el `phone` propiedad de eje descendiente para tener acceso a todos los descendientes con el nombre `phone` que están contenidas en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="4e28c-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e28c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e28c-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e28c-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4e28c-108">Compiling the Code</span></span>  
 <span data-ttu-id="4e28c-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4e28c-109">This example requires:</span></span>  
  
-   <span data-ttu-id="4e28c-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="4e28c-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e28c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e28c-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4e28c-112">Propiedad del eje descendiente XML</span><span class="sxs-lookup"><span data-stu-id="4e28c-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="4e28c-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="4e28c-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="4e28c-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e28c-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="4e28c-115">XML</span><span class="sxs-lookup"><span data-stu-id="4e28c-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
