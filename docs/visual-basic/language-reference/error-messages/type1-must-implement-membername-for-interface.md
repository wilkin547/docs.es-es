---
title: <type1>'<typename>'debe implementar'<membername>'para la interfaz'<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 86b0d46e0e27b2fd8d1fccb37f4a3c45e95f5f63
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295333"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="acb42-102">\<tipo1 >'\<typename >' debe implementar '\<membername >' para la interfaz '\<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="acb42-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="acb42-103">'\<typename >' debe implementar '\<membername >' para la interfaz '\<interfacename >'.</span><span class="sxs-lookup"><span data-stu-id="acb42-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="acb42-104">Propiedad de implementación debe tener coincidentes 'ReadOnly' o 'WriteOnly' especificadores.</span><span class="sxs-lookup"><span data-stu-id="acb42-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="acb42-105">Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento, propiedad o evento definido por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="acb42-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="acb42-106">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="acb42-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="acb42-107">**Identificador de error:** BC30154</span><span class="sxs-lookup"><span data-stu-id="acb42-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="acb42-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="acb42-108">To correct this error</span></span>  
  
1. <span data-ttu-id="acb42-109">Declarar a un miembro con el mismo nombre y firma, tal como se define en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="acb42-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="acb42-110">No olvide incluir al menos el `End Function`, `End Sub`, o `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="acb42-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="acb42-111">Agregar un `Implements` cláusula al final de la `Function`, `Sub`, `Property`, o `Event` instrucción.</span><span class="sxs-lookup"><span data-stu-id="acb42-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="acb42-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="acb42-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="acb42-113">Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se usa en la misma forma que la definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="acb42-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="acb42-114">Al implementar una propiedad, declare `Get` y `Set` procedimientos, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="acb42-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb42-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="acb42-115">See also</span></span>

- [<span data-ttu-id="acb42-116">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="acb42-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="acb42-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="acb42-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
