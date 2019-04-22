---
title: El descriptor de acceso 'Set' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3bc50d6762998ca5d8f445d84c8b698c9f46436f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834470"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="956ff-102">'Set' descriptor de acceso de propiedad '\<propertyname >' no es accesible</span><span class="sxs-lookup"><span data-stu-id="956ff-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="956ff-103">Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso a la propiedad `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="956ff-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="956ff-104">Si el [instrucción Set](../../../visual-basic/language-reference/statements/set-statement.md) está marcada con un acceso más restrictivo nivel que su [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), podría producirse un error de un intento para establecer el valor de propiedad en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="956ff-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="956ff-105">El `Set` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="956ff-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="956ff-106">El `Set` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="956ff-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="956ff-107">El `Set` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="956ff-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="956ff-108">**Identificador de error:** BC31102</span><span class="sxs-lookup"><span data-stu-id="956ff-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="956ff-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="956ff-109">To correct this error</span></span>  
  
-   <span data-ttu-id="956ff-110">Si tiene el control del código fuente definiendo la propiedad, considere la posibilidad de declarar la `Set` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="956ff-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="956ff-111">Si no tiene control sobre el código fuente definiendo la propiedad, o si debe restringir el `Set` procedimiento de nivel de acceso a la propiedad propiamente dicha, intente mover la instrucción que establece el valor de propiedad en una región de código que tiene un mejor acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="956ff-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956ff-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="956ff-112">See also</span></span>

- [<span data-ttu-id="956ff-113">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="956ff-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="956ff-114">Cómo: Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="956ff-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
