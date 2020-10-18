---
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 0dde340164f1ba80d0e1d9fbb5d17ba6da0a5bc4
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160059"
---
# <a name="bc36532-nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="81cbc-102">BC36532: la función anidada no tiene una signatura compatible con el delegado ' \<delegatename> '</span><span class="sxs-lookup"><span data-stu-id="81cbc-102">BC36532: Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="81cbc-103">Se ha asignado una expresión lambda a un delegado que tiene una firma no compatible.</span><span class="sxs-lookup"><span data-stu-id="81cbc-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="81cbc-104">Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.</span><span class="sxs-lookup"><span data-stu-id="81cbc-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="81cbc-105">El error se produce si una expresión lambda con un argumento se declara como tipo `Del` :</span><span class="sxs-lookup"><span data-stu-id="81cbc-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="81cbc-106">**Identificador de error:** BC36532</span><span class="sxs-lookup"><span data-stu-id="81cbc-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="81cbc-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="81cbc-107">To correct this error</span></span>

<span data-ttu-id="81cbc-108">Ajuste la definición de delegado o la expresión lambda asignada para que las firmas sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="81cbc-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="81cbc-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="81cbc-109">See also</span></span>

- [<span data-ttu-id="81cbc-110">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="81cbc-110">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="81cbc-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="81cbc-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
