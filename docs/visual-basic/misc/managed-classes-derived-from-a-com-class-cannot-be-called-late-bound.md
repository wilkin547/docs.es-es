---
description: 'Más información sobre: las clases administradas derivadas de una clase COM no se pueden llamar enlazadas en tiempo de ejecución.'
title: No se pueden realizar llamadas enlazadas en tiempo de ejecución a clases administradas derivadas de una clase COM.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: bde124c3e5c52d4c0dbb0e6e1f7250574c83be8d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430045"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a><span data-ttu-id="ad84f-103">No se pueden realizar llamadas enlazadas en tiempo de ejecución a clases administradas derivadas de una clase COM.</span><span class="sxs-lookup"><span data-stu-id="ad84f-103">Managed classes derived from a COM class cannot be called late-bound.</span></span>

<span data-ttu-id="ad84f-104">Se intentó realizar una llamada enlazada en tiempo de ejecución a una clase administrada derivada de una clase COM; no se admiten llamadas de este tipo.</span><span class="sxs-lookup"><span data-stu-id="ad84f-104">You attempted to make a late-bound call to a managed class derived from a COM Class; such calls are not supported.</span></span>

## <a name="to-correct-the-problem"></a><span data-ttu-id="ad84f-105">Para solucionar el problema</span><span class="sxs-lookup"><span data-stu-id="ad84f-105">To correct the problem</span></span>

<span data-ttu-id="ad84f-106">Realice la llamada enlazada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ad84f-106">Make the call early bound.</span></span>

## <a name="see-also"></a><span data-ttu-id="ad84f-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad84f-107">See also</span></span>

- [<span data-ttu-id="ad84f-108">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="ad84f-108">Error Types</span></span>](../programming-guide/language-features/error-types.md)
