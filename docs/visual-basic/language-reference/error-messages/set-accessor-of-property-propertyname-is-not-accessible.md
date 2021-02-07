---
description: "Más información sobre: BC31102: el descriptor de acceso ' Set ' de la propiedad ' <propertyname> ' no es accesible"
title: El descriptor de acceso 'Set' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: da4d29933ca140bd9fa1a15758b64667013a8032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675083"
---
# <a name="bc31102-set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="6c1fe-103">BC31102: \<propertyname> no se puede acceder al descriptor de acceso ' Set ' de la propiedad ' '</span><span class="sxs-lookup"><span data-stu-id="6c1fe-103">BC31102: 'Set' accessor of property '\<propertyname>' is not accessible</span></span>

<span data-ttu-id="6c1fe-104">Una instrucción intenta almacenar el valor de una propiedad cuando no tiene acceso al procedimiento de la propiedad `Set` .</span><span class="sxs-lookup"><span data-stu-id="6c1fe-104">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>

 <span data-ttu-id="6c1fe-105">Si la [instrucción set](../statements/set-statement.md) está marcada con un nivel de acceso más restrictivo que su [instrucción Property](../statements/property-statement.md), se podría producir un error al intentar establecer el valor de la propiedad en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c1fe-105">If the [Set Statement](../statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>

- <span data-ttu-id="6c1fe-106">La `Set` instrucción está marcada como [privada](../modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-106">The `Set` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>

- <span data-ttu-id="6c1fe-107">La `Set` instrucción se marca como [protegida](../modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-107">The `Set` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>

- <span data-ttu-id="6c1fe-108">La `Set` instrucción está marcada como [Friend](../modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-108">The `Set` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>

 <span data-ttu-id="6c1fe-109">**Identificador de error:** BC31102</span><span class="sxs-lookup"><span data-stu-id="6c1fe-109">**Error ID:** BC31102</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6c1fe-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6c1fe-110">To correct this error</span></span>

- <span data-ttu-id="6c1fe-111">Si tiene el control del código fuente que define la propiedad, considere la posibilidad de declarar el `Set` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-111">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>

- <span data-ttu-id="6c1fe-112">Si no tiene control sobre el código fuente que define la propiedad o si debe restringir el `Set` nivel de acceso del procedimiento más que la propiedad, intente trasladar la instrucción que establece el valor de la propiedad a una región de código que tenga un mejor acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c1fe-112">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c1fe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c1fe-113">See also</span></span>

- [<span data-ttu-id="6c1fe-114">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="6c1fe-114">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="6c1fe-115">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="6c1fe-115">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
