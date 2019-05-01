---
title: <type1>'<typename>'debe implementar'<methodname>'para la interfaz'<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013613"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="2d969-102">\<tipo1 >'\<typename >' debe implementar '\<methodname >' para la interfaz '\<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="2d969-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="2d969-103">Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d969-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="2d969-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d969-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="2d969-105">**Identificador de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="2d969-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d969-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2d969-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2d969-107">Declare un procedimiento con el mismo nombre y firma, tal como se define en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d969-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="2d969-108">No olvide incluir al menos el `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2d969-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="2d969-109">Agregar un `Implements` cláusula al final de la `Function` o `Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2d969-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="2d969-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2d969-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2d969-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d969-111">See also</span></span>

- [<span data-ttu-id="2d969-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2d969-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="2d969-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="2d969-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
