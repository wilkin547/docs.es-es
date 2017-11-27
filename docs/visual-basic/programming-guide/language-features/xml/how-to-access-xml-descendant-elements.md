---
title: "Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b3b6c8ac96bd18a379804b83f3ab3e48a5b0c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="9ecd4-102">Cómo: Obtener acceso a elementos descendientes XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ecd4-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="9ecd4-103">Este ejemplo muestra cómo usar una propiedad de eje descendiente para tener acceso a todos los elementos XML que tienen el nombre especificado y que están incluidos en un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="9ecd4-104">En concreto, usa el `Value` propiedad para obtener el valor del primer elemento de la colección que la `name` devuelve de la propiedad de eje descendiente.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="9ecd4-105">El `name` propiedad de eje descendiente Obtiene todos los elementos llamados `name` que están contenidas en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="9ecd4-106">Este ejemplo también utiliza el `phone` propiedad de eje descendiente para tener acceso a todos los descendientes con el nombre `phone` que están contenidas en el `contacts` objeto.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ecd4-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ecd4-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ecd4-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9ecd4-108">Compiling the Code</span></span>  
 <span data-ttu-id="9ecd4-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9ecd4-109">This example requires:</span></span>  
  
-   <span data-ttu-id="9ecd4-110">Una referencia al espacio de nombres <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="9ecd4-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecd4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ecd4-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="9ecd4-112">Propiedad del eje descendiente XML</span><span class="sxs-lookup"><span data-stu-id="9ecd4-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="9ecd4-113">Propiedad de valor XML</span><span class="sxs-lookup"><span data-stu-id="9ecd4-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="9ecd4-114">Obtener acceso a XML en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ecd4-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="9ecd4-115">XML</span><span class="sxs-lookup"><span data-stu-id="9ecd4-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
