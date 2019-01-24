---
title: Nothing y cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 65a69861c2a74a3191a45eb782a97f289b0c0726
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574175"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="69ec6-102">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69ec6-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="69ec6-103">El tiempo de ejecución de Visual Basic y [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluar `Nothing` forma diferente cuando se trata de cadenas.</span><span class="sxs-lookup"><span data-stu-id="69ec6-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="69ec6-104">En tiempo de ejecución de Visual Basic y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69ec6-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="69ec6-105">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="69ec6-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="69ec6-106">Normalmente, se evalúa como el runtime de Visual Basic `Nothing` como una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="69ec6-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="69ec6-107">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] no lo hace, sin embargo y producirá una excepción cuando se intenta realizar una operación de cadena en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="69ec6-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ec6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="69ec6-108">See also</span></span>
- [<span data-ttu-id="69ec6-109">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69ec6-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
