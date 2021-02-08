---
description: "Más información sobre: BC30157: el principio '. ' o '! ' solo puede aparecer dentro de una instrucción ' with '"
title: "'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e0325ac3c54046718d71df37edaac1edaf12f43e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795903"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="653ff-103">BC30157: '. ' o '! ' inicial solo puede aparecer dentro de una instrucción ' with '</span><span class="sxs-lookup"><span data-stu-id="653ff-103">BC30157: Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="653ff-104">Un punto (.) o un signo de exclamación (!) que no está dentro de un `With` bloque se produce sin una expresión a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="653ff-104">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="653ff-105">El acceso a miembros ( `.` ) y el acceso a miembros de diccionario ( `!` ) requieren una expresión que especifique el elemento que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="653ff-105">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="653ff-106">Debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de un `With` bloque que contiene el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="653ff-106">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>

 <span data-ttu-id="653ff-107">**Identificador de error:** BC30157</span><span class="sxs-lookup"><span data-stu-id="653ff-107">**Error ID:** BC30157</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="653ff-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="653ff-108">To correct this error</span></span>

1. <span data-ttu-id="653ff-109">Asegúrese de que el `With` bloque tenga el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="653ff-109">Ensure that the `With` block is correctly formatted.</span></span>

2. <span data-ttu-id="653ff-110">Si no hay ningún `With` bloque, agregue una expresión a la izquierda del descriptor de acceso que se evalúe como un elemento definido que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="653ff-110">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>

## <a name="see-also"></a><span data-ttu-id="653ff-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="653ff-111">See also</span></span>

- [<span data-ttu-id="653ff-112">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="653ff-112">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="653ff-113">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="653ff-113">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
