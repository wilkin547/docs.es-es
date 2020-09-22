---
title: <type1>"<typename>" debe implementar "<membername>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 7b74ee3a05000f5d6cd94176b48dea116b647a2a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872173"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="b694d-102">\<type1>"\<typename>" debe implementar "\<membername>" para la interfaz "\<interfacename>"</span><span class="sxs-lookup"><span data-stu-id="b694d-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="b694d-103">' \<typename> ' debe implementar ' \<membername> ' para la interfaz ' \<interfacename> '.</span><span class="sxs-lookup"><span data-stu-id="b694d-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="b694d-104">La implementación de la propiedad debe tener especificadores ' ReadOnly '/' WriteOnly ' coincidentes.</span><span class="sxs-lookup"><span data-stu-id="b694d-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="b694d-105">Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento, una propiedad o un evento definidos por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b694d-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="b694d-106">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b694d-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="b694d-107">**Identificador de error:** BC30154</span><span class="sxs-lookup"><span data-stu-id="b694d-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b694d-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="b694d-108">To correct this error</span></span>  
  
1. <span data-ttu-id="b694d-109">Declare un miembro con el mismo nombre y la misma signatura que el definido en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b694d-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="b694d-110">Asegúrese de incluir al menos la `End Function` instrucción, `End Sub` o `End Property` .</span><span class="sxs-lookup"><span data-stu-id="b694d-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="b694d-111">Agregue una `Implements` cláusula al final de la `Function` instrucción, `Sub` , `Property` o `Event` .</span><span class="sxs-lookup"><span data-stu-id="b694d-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="b694d-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b694d-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="b694d-113">Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se utiliza de la misma manera que en la definición de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b694d-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="b694d-114">Al implementar una propiedad, declare `Get` `Set` los procedimientos y, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b694d-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b694d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b694d-115">See also</span></span>

- [<span data-ttu-id="b694d-116">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="b694d-116">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="b694d-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b694d-117">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
