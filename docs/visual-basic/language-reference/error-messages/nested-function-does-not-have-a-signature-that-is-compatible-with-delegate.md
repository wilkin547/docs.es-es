---
title: La función anidada no tiene una signatura compatible con el delegado '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580644"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="1bc91-102">La función anidada no tiene una signatura compatible con el delegado ' \<delegatename > '</span><span class="sxs-lookup"><span data-stu-id="1bc91-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="1bc91-103">Se ha asignado una expresión lambda a un delegado que tiene una firma no compatible.</span><span class="sxs-lookup"><span data-stu-id="1bc91-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="1bc91-104">Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros de entero.</span><span class="sxs-lookup"><span data-stu-id="1bc91-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="1bc91-105">El error se produce si una expresión lambda con un argumento se declara como de tipo `Del`:</span><span class="sxs-lookup"><span data-stu-id="1bc91-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="1bc91-106">**Identificador de error:** BC36532</span><span class="sxs-lookup"><span data-stu-id="1bc91-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1bc91-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1bc91-107">To correct this error</span></span>

<span data-ttu-id="1bc91-108">Ajuste la definición de delegado o la expresión lambda asignada para que las firmas sean compatibles.</span><span class="sxs-lookup"><span data-stu-id="1bc91-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="1bc91-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bc91-109">See also</span></span>

- [<span data-ttu-id="1bc91-110">Conversión de delegado flexible</span><span class="sxs-lookup"><span data-stu-id="1bc91-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="1bc91-111">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="1bc91-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
