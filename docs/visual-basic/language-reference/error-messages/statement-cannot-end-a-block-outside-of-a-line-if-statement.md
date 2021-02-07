---
description: "Más información sobre: BC32005: la instrucción no puede terminar un bloque fuera de una línea de la instrucción ' if '"
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: afe856b2c2ea3fa1db029d35c5b876f5d67da411
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731160"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a><span data-ttu-id="af856-103">BC32005: la instrucción no puede terminar un bloque fuera de una línea de la instrucción ' if '</span><span class="sxs-lookup"><span data-stu-id="af856-103">BC32005: Statement cannot end a block outside of a line 'If' statement</span></span>

<span data-ttu-id="af856-104">Una instrucción de una sola línea `If` contiene varias instrucciones separadas por dos puntos (:), una de las cuales es una `End` instrucción para un bloque de control fuera de la línea única `If` .</span><span class="sxs-lookup"><span data-stu-id="af856-104">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="af856-105">Las instrucciones de una línea `If` no utilizan la `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="af856-105">Single-line `If` statements do not use the `End If` statement.</span></span>

 <span data-ttu-id="af856-106">**Identificador de error:** BC32005</span><span class="sxs-lookup"><span data-stu-id="af856-106">**Error ID:** BC32005</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="af856-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="af856-107">To correct this error</span></span>

- <span data-ttu-id="af856-108">Mueva la instrucción de una sola línea `If` fuera del bloque de control que contiene la `End If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="af856-108">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="af856-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="af856-109">See also</span></span>

- [<span data-ttu-id="af856-110">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="af856-110">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
