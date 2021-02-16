---
description: "Más información sobre: BC30149: <type1> ' <typename> ' debe implementar ' <methodname> ' para la interfaz ' <interfacename> '"
title: <type1>"<typename>" debe implementar "<methodname>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b2fb7f5ea019a86b18ea89456e353778e5246d2d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473442"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="aa7fb-103">BC30149: \<type1> ' \<typename> ' debe implementar ' \<methodname> ' para la interfaz ' \<interfacename> '</span><span class="sxs-lookup"><span data-stu-id="aa7fb-103">BC30149: \<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="aa7fb-104">Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa7fb-104">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="aa7fb-105">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa7fb-105">Every member of the interface must be implemented.</span></span>

 <span data-ttu-id="aa7fb-106">**Identificador de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="aa7fb-106">**Error ID:** BC30149</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="aa7fb-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="aa7fb-107">To correct this error</span></span>

1. <span data-ttu-id="aa7fb-108">Declare un procedimiento con el mismo nombre y la misma signatura que el definido en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa7fb-108">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="aa7fb-109">Asegúrese de incluir al menos la `End Function` instrucción o `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="aa7fb-109">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="aa7fb-110">Agregue una `Implements` cláusula al final de la `Function` instrucción o `Sub` .</span><span class="sxs-lookup"><span data-stu-id="aa7fb-110">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="aa7fb-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aa7fb-111">For example:</span></span>

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a><span data-ttu-id="aa7fb-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aa7fb-112">See also</span></span>

- [<span data-ttu-id="aa7fb-113">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="aa7fb-113">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="aa7fb-114">Interfaces</span><span class="sxs-lookup"><span data-stu-id="aa7fb-114">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
