---
title: 'Cómo: Obtener acceso a elementos descendientes XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 63a094c3c2b20736f0ef6589c76d53b7cc96b29a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332313"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="35d4f-102">Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35d4f-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="35d4f-103">En este ejemplo se muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen un nombre especificado y que están incluidos en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="35d4f-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="35d4f-104">En concreto, usa la propiedad `Value` para obtener el valor del primer elemento de la colección que devuelve la propiedad de eje descendiente `name`.</span><span class="sxs-lookup"><span data-stu-id="35d4f-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="35d4f-105">La propiedad `name` eje descendiente obtiene todos los elementos denominados `name` incluidos en el objeto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="35d4f-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="35d4f-106">En este ejemplo también se usa la propiedad de eje descendiente `phone` para tener acceso a todos los descendientes denominados `phone` incluidos en el objeto `contacts`.</span><span class="sxs-lookup"><span data-stu-id="35d4f-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d4f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35d4f-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="35d4f-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="35d4f-108">Compiling the Code</span></span>  
 <span data-ttu-id="35d4f-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="35d4f-109">This example requires:</span></span>  
  
- <span data-ttu-id="35d4f-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="35d4f-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d4f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d4f-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="35d4f-112">Propiedad del eje descendiente XML</span><span class="sxs-lookup"><span data-stu-id="35d4f-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="35d4f-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="35d4f-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="35d4f-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35d4f-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="35d4f-115">XML</span><span class="sxs-lookup"><span data-stu-id="35d4f-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
