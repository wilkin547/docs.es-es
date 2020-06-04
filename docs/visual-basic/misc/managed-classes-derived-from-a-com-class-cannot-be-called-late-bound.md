---
title: No se pueden realizar llamadas enlazadas en tiempo de ejecución a clases administradas derivadas de una clase COM.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: 401cb5d7194cbef616c87d59e5b1ed7f923fe6f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402127"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="70ac4-102">No se pueden realizar llamadas enlazadas en tiempo de ejecución a clases administradas derivadas de una clase COM.</span><span class="sxs-lookup"><span data-stu-id="70ac4-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="70ac4-103">Se intentó realizar una llamada enlazada en tiempo de ejecución a una clase administrada derivada de una clase COM; no se admiten llamadas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="70ac4-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="70ac4-104">Para solucionar el problema</span><span class="sxs-lookup"><span data-stu-id="70ac4-104">To correct the problem</span></span>

<span data-ttu-id="70ac4-105">Realice la llamada enlazada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="70ac4-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="70ac4-106">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70ac4-106">See also</span></span>

- [<span data-ttu-id="70ac4-107">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="70ac4-107">Error Types</span></span>](../programming-guide/language-features/error-types.md)
