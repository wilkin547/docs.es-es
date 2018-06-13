---
title: Nothing y cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647198"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="7efc8-102">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7efc8-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="7efc8-103">El tiempo de ejecución de Visual Basic y [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluar `Nothing` forma diferente cuando se trata de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7efc8-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="7efc8-104">En tiempo de ejecución de Visual Basic y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7efc8-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="7efc8-105">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7efc8-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="7efc8-106">El tiempo de ejecución de Visual Basic normalmente evalúa `Nothing` como una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="7efc8-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="7efc8-107">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] no es así, sin embargo y producirá una excepción cuando se realiza un intento para realizar una operación de cadena en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="7efc8-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7efc8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7efc8-108">See Also</span></span>  
 [<span data-ttu-id="7efc8-109">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7efc8-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
