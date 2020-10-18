---
title: El descriptor de acceso 'Get' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: bd6830e16ba3d1f76c61519b4456832a2efec716
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162913"
---
# <a name="bc31103-get-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="9f8e4-102">BC31103: \<propertyname> no se puede acceder al descriptor de acceso ' get ' de la propiedad ' '</span><span class="sxs-lookup"><span data-stu-id="9f8e4-102">BC31103: 'Get' accessor of property '\<propertyname>' is not accessible</span></span>

<span data-ttu-id="9f8e4-103">Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso al procedimiento de la propiedad `Get` .</span><span class="sxs-lookup"><span data-stu-id="9f8e4-103">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>

 <span data-ttu-id="9f8e4-104">Si la [instrucción Get](../statements/get-statement.md) está marcada con un nivel de acceso más restrictivo que su [instrucción Property](../statements/property-statement.md), se podría producir un error al intentar leer el valor de propiedad en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f8e4-104">If the [Get Statement](../statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>

- <span data-ttu-id="9f8e4-105">La `Get` instrucción está marcada como [privada](../modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f8e4-105">The `Get` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>

- <span data-ttu-id="9f8e4-106">La `Get` instrucción se marca como [protegida](../modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9f8e4-106">The `Get` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>

- <span data-ttu-id="9f8e4-107">La `Get` instrucción está marcada como [Friend](../modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f8e4-107">The `Get` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>

 <span data-ttu-id="9f8e4-108">**Identificador de error:** BC31103</span><span class="sxs-lookup"><span data-stu-id="9f8e4-108">**Error ID:** BC31103</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9f8e4-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="9f8e4-109">To correct this error</span></span>

- <span data-ttu-id="9f8e4-110">Si tiene el control del código fuente que define la propiedad, considere la posibilidad de declarar el `Get` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="9f8e4-110">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>

- <span data-ttu-id="9f8e4-111">Si no tiene control sobre el código fuente que define la propiedad o si debe restringir el `Get` nivel de acceso del procedimiento más que la propiedad, intente trasladar la instrucción que lee el valor de la propiedad a una región de código que tenga un mejor acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f8e4-111">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f8e4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f8e4-112">See also</span></span>

- [<span data-ttu-id="9f8e4-113">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="9f8e4-113">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="9f8e4-114">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="9f8e4-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
