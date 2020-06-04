---
title: <type1>"<typename>" debe implementar "<methodname>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 90d2b6d70390bfb732af4a5868c935de61d18f94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408507"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="d8da3-102">\<type1>"\<typename>" debe implementar "\<methodname>" para la interfaz "\<interfacename>"</span><span class="sxs-lookup"><span data-stu-id="d8da3-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="d8da3-103">Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d8da3-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="d8da3-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d8da3-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="d8da3-105">**Identificador de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="d8da3-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8da3-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d8da3-106">To correct this error</span></span>  
  
1. <span data-ttu-id="d8da3-107">Declare un procedimiento con el mismo nombre y la misma signatura que el definido en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="d8da3-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="d8da3-108">Asegúrese de incluir al menos la `End Function` instrucción o `End Sub` .</span><span class="sxs-lookup"><span data-stu-id="d8da3-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="d8da3-109">Agregue una `Implements` cláusula al final de la `Function` instrucción o `Sub` .</span><span class="sxs-lookup"><span data-stu-id="d8da3-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="d8da3-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d8da3-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8da3-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8da3-111">See also</span></span>

- [<span data-ttu-id="d8da3-112">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d8da3-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="d8da3-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d8da3-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
