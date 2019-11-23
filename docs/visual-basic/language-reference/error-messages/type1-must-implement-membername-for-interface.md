---
title: <type1>"<typename>" debe implementar "<membername>" para la interfaz "<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: a824b66eaad964049ced5cae5eb2cc370d00ba7f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696890"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="f9ed0-102">\<Type1 > '\<TypeName > ' debe implementar '\<membername > ' para la interfaz '\<InterfaceName > '</span><span class="sxs-lookup"><span data-stu-id="f9ed0-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="f9ed0-103">'\<TypeName > ' debe implementar '\<membername > ' para la interfaz '\<InterfaceName > '.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="f9ed0-104">La implementación de la propiedad debe tener especificadores ' ReadOnly '/' WriteOnly ' coincidentes.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="f9ed0-105">Una clase o estructura notifica a que implemente una interfaz pero no implementa un procedimiento, una propiedad o un evento definidos por la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="f9ed0-106">Se deben implementar todos los miembros de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="f9ed0-107">**Identificador de error:** BC30154</span><span class="sxs-lookup"><span data-stu-id="f9ed0-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9ed0-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f9ed0-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f9ed0-109">Declare un miembro con el mismo nombre y la misma signatura que el definido en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="f9ed0-110">Asegúrese de incluir al menos la instrucción `End Function`, `End Sub`o `End Property`.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2. <span data-ttu-id="f9ed0-111">Agregue una cláusula `Implements` al final de la instrucción `Function`, `Sub`, `Property`o `Event`.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="f9ed0-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f9ed0-112">For example:</span></span>  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. <span data-ttu-id="f9ed0-113">Al implementar una propiedad, asegúrese de que `ReadOnly` o `WriteOnly` se utiliza de la misma manera que en la definición de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4. <span data-ttu-id="f9ed0-114">Al implementar una propiedad, declare `Get` y `Set` procedimientos, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="f9ed0-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ed0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9ed0-115">See also</span></span>

- [<span data-ttu-id="f9ed0-116">Implements (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f9ed0-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="f9ed0-117">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f9ed0-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
