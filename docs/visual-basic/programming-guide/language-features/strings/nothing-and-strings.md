---
title: Nothing y cadenas en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce9f81f23f50e38f6b1ad5e638e8c6ac026e992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="0e9c3-102">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e9c3-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="0e9c3-103">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] en tiempo de ejecución y el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluar `Nothing` forma diferente cuando se trata de cadenas.</span><span class="sxs-lookup"><span data-stu-id="0e9c3-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="0e9c3-104">En tiempo de ejecución de Visual Basic y .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0e9c3-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="0e9c3-105">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e9c3-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 <span data-ttu-id="0e9c3-106">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] normalmente se evalúa como el tiempo de ejecución `Nothing` como una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="0e9c3-106">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="0e9c3-107">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] no es así, sin embargo y producirá una excepción cuando se realiza un intento para realizar una operación de cadena en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="0e9c3-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9c3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e9c3-108">See Also</span></span>  
 [<span data-ttu-id="0e9c3-109">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0e9c3-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
