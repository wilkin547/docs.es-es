---
title: '&#39;Obtener&#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt; &#39; no es accesible'
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 0972c0909f8b07aa1c6700ec32d1a1ca55d00cc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590210"
---
# <a name="39get39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="342c0-102">&#39;Obtener&#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt; &#39; no es accesible</span><span class="sxs-lookup"><span data-stu-id="342c0-102">&#39;Get&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="342c0-103">Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso a la propiedad `Get` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="342c0-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>  
  
 <span data-ttu-id="342c0-104">Si el [instrucción Get](../../../visual-basic/language-reference/statements/get-statement.md) está marcada con un acceso más restrictivo nivel que su [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md), se producirá un error en un intento de leer el valor de propiedad en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="342c0-104">If the [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="342c0-105">El `Get` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código que realiza la llamada está fuera de la clase o estructura en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="342c0-105">The `Get` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="342c0-106">El `Get` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="342c0-106">The `Get` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="342c0-107">El `Get` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="342c0-107">The `Get` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="342c0-108">**Id. de error:** BC31103</span><span class="sxs-lookup"><span data-stu-id="342c0-108">**Error ID:** BC31103</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="342c0-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="342c0-109">To correct this error</span></span>  
  
-   <span data-ttu-id="342c0-110">Si tiene control sobre el código de origen define la propiedad, considere la posibilidad de declarar el `Get` procedimiento con el mismo nivel de acceso que la propiedad en Sí.</span><span class="sxs-lookup"><span data-stu-id="342c0-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="342c0-111">Si no tiene control sobre el código de origen define la propiedad, o si debe restringir el `Get` procedimiento nivel de acceso a la propiedad en Sí, intente mover la instrucción que lee el valor de propiedad a una región de código que tiene un mejor acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="342c0-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="342c0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="342c0-112">See Also</span></span>  
 [<span data-ttu-id="342c0-113">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="342c0-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="342c0-114">Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="342c0-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
