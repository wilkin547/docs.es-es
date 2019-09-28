---
title: <type1>"<typename>" debe implementar "<methodname>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591590"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="6089c-102">\<type1 > ' \<typename > ' debe implementar ' \<methodname > ' para la interfaz ' \<interfacename > '</span><span class="sxs-lookup"><span data-stu-id="6089c-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="6089c-103">Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="6089c-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="6089c-104">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="6089c-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="6089c-105">**IDENTIFICADOR de error:** BC30149</span><span class="sxs-lookup"><span data-stu-id="6089c-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6089c-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6089c-106">To correct this error</span></span>  
  
1. <span data-ttu-id="6089c-107">Declare un procedimiento con el mismo nombre y la misma signatura que el definido en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="6089c-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="6089c-108">Asegúrese de incluir al menos la instrucción `End Function` o `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="6089c-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="6089c-109">Agregue una cláusula `Implements` al final de la instrucción `Function` o `Sub`.</span><span class="sxs-lookup"><span data-stu-id="6089c-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="6089c-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6089c-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6089c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="6089c-111">See also</span></span>

- [<span data-ttu-id="6089c-112">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6089c-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="6089c-113">Interfaces</span><span class="sxs-lookup"><span data-stu-id="6089c-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
