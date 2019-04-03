---
title: <type1>'<typename>'debe implementar'<methodname>'para la interfaz'<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b8bcb16798284a09608ba6942226ef07c6859d4f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824210"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="b4205-102">\<tipo1 >'\<typename >' debe implementar '\<methodname >' para la interfaz '\<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="b4205-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="b4205-103">Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b4205-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="b4205-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b4205-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="b4205-105">**Identificador de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="b4205-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b4205-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b4205-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b4205-107">Declare un procedimiento con el mismo nombre y firma, tal como se define en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b4205-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="b4205-108">No olvide incluir al menos el `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b4205-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="b4205-109">Agregar un `Implements` cláusula al final de la `Function` o `Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="b4205-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="b4205-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4205-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b4205-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4205-111">See also</span></span>

- [<span data-ttu-id="b4205-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="b4205-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="b4205-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b4205-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
