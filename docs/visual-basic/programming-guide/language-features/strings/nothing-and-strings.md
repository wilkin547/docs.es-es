---
title: Nothing y cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 5fbcf86261892e3eb8e43ee8eaa3728cd8e42ced
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032284"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="77389-102">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77389-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="77389-103">El tiempo de ejecución de Visual Basic y [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluar `Nothing` forma diferente cuando se trata de cadenas.</span><span class="sxs-lookup"><span data-stu-id="77389-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="77389-104">En tiempo de ejecución de Visual Basic y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="77389-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="77389-105">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77389-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="77389-106">Normalmente, se evalúa como el runtime de Visual Basic `Nothing` como una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="77389-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="77389-107">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] no lo hace, sin embargo y producirá una excepción cuando se intenta realizar una operación de cadena en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="77389-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77389-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="77389-108">See also</span></span>

- [<span data-ttu-id="77389-109">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77389-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
