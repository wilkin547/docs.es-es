---
title: Nothing y cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360571"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="3025b-102">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3025b-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="3025b-103">El tiempo de ejecución de Visual Basic y el .NET Framework se evalúan de `Nothing` forma diferente cuando se trata de cadenas.</span><span class="sxs-lookup"><span data-stu-id="3025b-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="3025b-104">Visual Basic en tiempo de ejecución y el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3025b-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="3025b-105">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3025b-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="3025b-106">Normalmente, el tiempo de ejecución de Visual Basic se evalúa `Nothing` como una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="3025b-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="3025b-107">Sin embargo, el .NET Framework no y produce una excepción cada vez que se realiza un intento de realizar una operación de cadena en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="3025b-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3025b-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3025b-108">See also</span></span>

- [<span data-ttu-id="3025b-109">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3025b-109">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
