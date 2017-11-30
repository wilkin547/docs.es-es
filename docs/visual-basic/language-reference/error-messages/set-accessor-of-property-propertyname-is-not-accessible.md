---
title: '&#39; Conjunto de &#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt;&#39; no es accesible'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords: BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9256a09b719ad3890e1d7c2cc23ffb0d40eec62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="1baf6-102">&#39; Conjunto de &#39; descriptor de acceso de propiedad &#39; &lt;propertyname&gt;&#39; no es accesible</span><span class="sxs-lookup"><span data-stu-id="1baf6-102">&#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="1baf6-103">Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso a la propiedad `Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1baf6-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="1baf6-104">Si el [instrucción Set](../../../visual-basic/language-reference/statements/set-statement.md) está marcada con un acceso más restrictivo nivel que su [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md), se producirá un error en un intento para establecer el valor de propiedad en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1baf6-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="1baf6-105">El `Set` instrucción está marcada como [privada](../../../visual-basic/language-reference/modifiers/private.md) y el código que realiza la llamada está fuera de la clase o estructura en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1baf6-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="1baf6-106">El `Set` instrucción está marcada como [Protected](../../../visual-basic/language-reference/modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="1baf6-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="1baf6-107">El `Set` instrucción está marcada como [Friend](../../../visual-basic/language-reference/modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1baf6-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="1baf6-108">**Id. de error:** BC31102</span><span class="sxs-lookup"><span data-stu-id="1baf6-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1baf6-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1baf6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="1baf6-110">Si tiene control sobre el código de origen define la propiedad, considere la posibilidad de declarar el `Set` procedimiento con el mismo nivel de acceso que la propiedad en Sí.</span><span class="sxs-lookup"><span data-stu-id="1baf6-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="1baf6-111">Si no tiene control sobre el código de origen define la propiedad, o si debe restringir el `Set` procedimiento nivel de acceso a la propiedad en Sí, intente mover la instrucción que establece el valor de propiedad a una región de código que tiene un mejor acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1baf6-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1baf6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1baf6-112">See Also</span></span>  
 [<span data-ttu-id="1baf6-113">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="1baf6-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="1baf6-114">Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="1baf6-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
