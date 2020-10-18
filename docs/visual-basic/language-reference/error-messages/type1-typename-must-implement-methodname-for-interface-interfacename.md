---
title: <type1>"<typename>" debe implementar "<methodname>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 68c6f65e6be229cc74458fa56fe3d3aa889c18f7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161873"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="48fd5-102">BC30149: \<type1> ' \<typename> ' debe implementar ' \<methodname> ' para la interfaz ' \<interfacename> '</span><span class="sxs-lookup"><span data-stu-id="48fd5-102">BC30149: \<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="48fd5-103">Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="48fd5-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="48fd5-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="48fd5-104">Every member of the interface must be implemented.</span></span>

 <span data-ttu-id="48fd5-105">**Identificador de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="48fd5-105">**Error ID:** BC30149</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="48fd5-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="48fd5-106">To correct this error</span></span>

1. <span data-ttu-id="48fd5-107">Declare un procedimiento con el mismo nombre y la misma signatura que el definido en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="48fd5-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="48fd5-108">Asegúrese de incluir al menos la `End Function` instrucción o `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="48fd5-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="48fd5-109">Agregue una `Implements` cláusula al final de la `Function` instrucción o `Sub` .</span><span class="sxs-lookup"><span data-stu-id="48fd5-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="48fd5-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="48fd5-110">For example:</span></span>

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a><span data-ttu-id="48fd5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="48fd5-111">See also</span></span>

- [<span data-ttu-id="48fd5-112">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="48fd5-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="48fd5-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="48fd5-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
