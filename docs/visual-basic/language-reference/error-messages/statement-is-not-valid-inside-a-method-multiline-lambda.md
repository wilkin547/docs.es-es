---
title: Instrucción no válida dentro de un método o una expresión lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159682"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="27a19-102">BC30024: la instrucción no es válida dentro de un método o una expresión lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="27a19-102">BC30024: Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="27a19-103">La instrucción no es válida dentro de `Sub` un `Function` procedimiento de propiedad,, propiedad `Get` o `Set` .</span><span class="sxs-lookup"><span data-stu-id="27a19-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="27a19-104">Algunas instrucciones se pueden colocar en el nivel de módulo o de clase.</span><span class="sxs-lookup"><span data-stu-id="27a19-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="27a19-105">Otros, como `Option Strict` , deben estar en el nivel de espacio de nombres y preceder a todas las demás declaraciones.</span><span class="sxs-lookup"><span data-stu-id="27a19-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>

 <span data-ttu-id="27a19-106">**Identificador de error:** BC30024</span><span class="sxs-lookup"><span data-stu-id="27a19-106">**Error ID:** BC30024</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="27a19-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="27a19-107">To correct this error</span></span>

- <span data-ttu-id="27a19-108">Quite la instrucción del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="27a19-108">Remove the statement from the procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="27a19-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="27a19-109">See also</span></span>

- [<span data-ttu-id="27a19-110">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="27a19-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="27a19-111">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="27a19-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="27a19-112">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="27a19-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="27a19-113">Set (instrucción)</span><span class="sxs-lookup"><span data-stu-id="27a19-113">Set Statement</span></span>](../statements/set-statement.md)
