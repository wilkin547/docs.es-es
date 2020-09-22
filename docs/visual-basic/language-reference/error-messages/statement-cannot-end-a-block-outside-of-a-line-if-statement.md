---
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 5e75c29e57a9c04c66e6bca79d99bb18c513f667
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870737"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="037ba-102">La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'</span><span class="sxs-lookup"><span data-stu-id="037ba-102">Statement cannot end a block outside of a line 'If' statement</span></span>

<span data-ttu-id="037ba-103">Una instrucción de una sola línea `If` contiene varias instrucciones separadas por dos puntos (:), una de las cuales es una `End` instrucción para un bloque de control fuera de la línea única `If` .</span><span class="sxs-lookup"><span data-stu-id="037ba-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="037ba-104">Las instrucciones de una línea `If` no utilizan la `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="037ba-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="037ba-105">**Identificador de error:** BC32005</span><span class="sxs-lookup"><span data-stu-id="037ba-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="037ba-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="037ba-106">To correct this error</span></span>  
  
- <span data-ttu-id="037ba-107">Mueva la instrucción de una sola línea `If` fuera del bloque de control que contiene la `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="037ba-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037ba-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="037ba-108">See also</span></span>

- [<span data-ttu-id="037ba-109">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="037ba-109">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
