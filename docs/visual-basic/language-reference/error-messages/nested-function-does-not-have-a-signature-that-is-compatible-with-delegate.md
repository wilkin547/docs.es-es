---
description: "Más información acerca de: BC36532: la función anidada no tiene una signatura compatible con el delegado '<delegatename>"
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 2220faacdac065718a302ef7b086f99bf1e16cef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795669"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="e5d65-103">BC36532: la función anidada no tiene una signatura compatible con el delegado ' \<delegatename> '</span><span class="sxs-lookup"><span data-stu-id="e5d65-103">BC36532: Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="e5d65-104">Se ha asignado una expresión lambda a un delegado que tiene una firma no compatible.</span><span class="sxs-lookup"><span data-stu-id="e5d65-104">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="e5d65-105">Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.</span><span class="sxs-lookup"><span data-stu-id="e5d65-105">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="e5d65-106">El error se produce si una expresión lambda con un argumento se declara como tipo `Del` :</span><span class="sxs-lookup"><span data-stu-id="e5d65-106">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="e5d65-107">**Identificador de error:** BC36532</span><span class="sxs-lookup"><span data-stu-id="e5d65-107">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e5d65-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e5d65-108">To correct this error</span></span>

<span data-ttu-id="e5d65-109">Ajuste la definición de delegado o la expresión lambda asignada para que las firmas sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="e5d65-109">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5d65-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5d65-110">See also</span></span>

- [<span data-ttu-id="e5d65-111">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="e5d65-111">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="e5d65-112">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="e5d65-112">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
