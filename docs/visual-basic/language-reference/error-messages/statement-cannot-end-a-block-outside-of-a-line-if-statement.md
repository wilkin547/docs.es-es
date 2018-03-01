---
title: "La instrucción no puede terminar un bloque fuera de una línea &#39; si &#39; instrucción"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73fe3eb44e904366db7d505bbe8c5fef461eb78b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="16229-102">La instrucción no puede terminar un bloque fuera de una línea &#39; si &#39; instrucción</span><span class="sxs-lookup"><span data-stu-id="16229-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="16229-103">Una sola línea `If` instrucción contiene varias instrucciones separadas por dos puntos (:), uno de los cuales es un `End` declaración de un bloque de control fuera de la línea `If`.</span><span class="sxs-lookup"><span data-stu-id="16229-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="16229-104">Línea `If` instrucciones no utilizan el `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="16229-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="16229-105">**Id. de error:** BC32005</span><span class="sxs-lookup"><span data-stu-id="16229-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="16229-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="16229-106">To correct this error</span></span>  
  
-   <span data-ttu-id="16229-107">Mover la línea `If` instrucción fuera del bloque de control que contiene el `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="16229-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16229-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="16229-108">See Also</span></span>  
 [<span data-ttu-id="16229-109">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="16229-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
