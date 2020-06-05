---
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400323"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="f42d4-102">La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'</span><span class="sxs-lookup"><span data-stu-id="f42d4-102">Statement cannot end a block outside of a line 'If' statement</span></span>
<span data-ttu-id="f42d4-103">Una instrucción de una sola línea `If` contiene varias instrucciones separadas por dos puntos (:), una de las cuales es una `End` instrucción para un bloque de control fuera de la línea única `If` .</span><span class="sxs-lookup"><span data-stu-id="f42d4-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="f42d4-104">Las instrucciones de una línea `If` no utilizan la `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f42d4-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="f42d4-105">**Identificador de error:** BC32005</span><span class="sxs-lookup"><span data-stu-id="f42d4-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f42d4-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f42d4-106">To correct this error</span></span>  
  
- <span data-ttu-id="f42d4-107">Mueva la instrucción de una sola línea `If` fuera del bloque de control que contiene la `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f42d4-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42d4-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f42d4-108">See also</span></span>

- [<span data-ttu-id="f42d4-109">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="f42d4-109">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
