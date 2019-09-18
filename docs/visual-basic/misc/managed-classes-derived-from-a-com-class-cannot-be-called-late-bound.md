---
title: No se pueden realizar llamadas enlazadas en tiempo de ejecución a clases administradas derivadas de una clase COM.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: c18f2b6e1751d39ceb81c190f70ee161ca716bc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054181"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="9b2f2-102">No se pueden realizar llamadas enlazadas en tiempo de ejecución a clases administradas derivadas de una clase COM.</span><span class="sxs-lookup"><span data-stu-id="9b2f2-102">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="9b2f2-103">Se intentó realizar una llamada enlazada en tiempo de ejecución a una clase administrada derivada de una clase COM; no se admiten llamadas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="9b2f2-103">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="9b2f2-104">Para solucionar el problema</span><span class="sxs-lookup"><span data-stu-id="9b2f2-104">To correct the problem</span></span>

<span data-ttu-id="9b2f2-105">Realice la llamada enlazada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="9b2f2-105">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b2f2-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b2f2-106">See also</span></span>

- [<span data-ttu-id="9b2f2-107">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="9b2f2-107">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
