---
description: 'Más información sobre: Nothing y cadenas en Visual Basic'
title: Nothing y cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: a32dd8b38033f1845f2ada87bf5f538d45fede18
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424351"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="9d401-103">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d401-103">Nothing and Strings in Visual Basic</span></span>

<span data-ttu-id="9d401-104">El tiempo de ejecución de Visual Basic y el .NET Framework se evalúan de `Nothing` forma diferente cuando se trata de cadenas.</span><span class="sxs-lookup"><span data-stu-id="9d401-104">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="9d401-105">Visual Basic en tiempo de ejecución y el .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9d401-105">Visual Basic Runtime and the .NET Framework</span></span>  

 <span data-ttu-id="9d401-106">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9d401-106">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="9d401-107">Normalmente, el tiempo de ejecución de Visual Basic se evalúa `Nothing` como una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="9d401-107">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="9d401-108">Sin embargo, el .NET Framework no y produce una excepción cada vez que se realiza un intento de realizar una operación de cadena en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="9d401-108">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d401-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d401-109">See also</span></span>

- [<span data-ttu-id="9d401-110">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d401-110">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
