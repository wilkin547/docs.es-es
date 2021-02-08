---
description: "Más información sobre: BC31103: el descriptor de acceso ' get ' de la propiedad ' <propertyname> ' no es accesible"
title: El descriptor de acceso 'Get' de la propiedad '<propertyname>' no está accesible
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: 3517bc7ec512ec99909539eb4d7cf3fafe9016fa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796137"
---
# <a name="bc31103-get-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="d216a-103">BC31103: \<propertyname> no se puede acceder al descriptor de acceso ' get ' de la propiedad ' '</span><span class="sxs-lookup"><span data-stu-id="d216a-103">BC31103: 'Get' accessor of property '\<propertyname>' is not accessible</span></span>

<span data-ttu-id="d216a-104">Una instrucción intenta recuperar el valor de una propiedad cuando no tiene acceso al procedimiento de la propiedad `Get` .</span><span class="sxs-lookup"><span data-stu-id="d216a-104">A statement attempts to retrieve the value of a property when it does not have access to the property's `Get` procedure.</span></span>

 <span data-ttu-id="d216a-105">Si la [instrucción Get](../statements/get-statement.md) está marcada con un nivel de acceso más restrictivo que su [instrucción Property](../statements/property-statement.md), se podría producir un error al intentar leer el valor de propiedad en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d216a-105">If the [Get Statement](../statements/get-statement.md) is marked with a more restrictive access level than its [Property Statement](../statements/property-statement.md), an attempt to read the property value could fail in the following cases:</span></span>

- <span data-ttu-id="d216a-106">La `Get` instrucción está marcada como [privada](../modifiers/private.md) y el código de llamada está fuera de la clase o estructura en la que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d216a-106">The `Get` statement is marked [Private](../modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>

- <span data-ttu-id="d216a-107">La `Get` instrucción se marca como [protegida](../modifiers/protected.md) y el código de llamada no está en la clase o estructura en la que se define la propiedad, ni en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d216a-107">The `Get` statement is marked [Protected](../modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>

- <span data-ttu-id="d216a-108">La `Get` instrucción está marcada como [Friend](../modifiers/friend.md) y el código de llamada no está en el mismo ensamblado en el que se define la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d216a-108">The `Get` statement is marked [Friend](../modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>

 <span data-ttu-id="d216a-109">**Identificador de error:** BC31103</span><span class="sxs-lookup"><span data-stu-id="d216a-109">**Error ID:** BC31103</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d216a-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d216a-110">To correct this error</span></span>

- <span data-ttu-id="d216a-111">Si tiene el control del código fuente que define la propiedad, considere la posibilidad de declarar el `Get` procedimiento con el mismo nivel de acceso que la propiedad propiamente dicha.</span><span class="sxs-lookup"><span data-stu-id="d216a-111">If you have control of the source code defining the property, consider declaring the `Get` procedure with the same access level as the property itself.</span></span>

- <span data-ttu-id="d216a-112">Si no tiene control sobre el código fuente que define la propiedad o si debe restringir el `Get` nivel de acceso del procedimiento más que la propiedad, intente trasladar la instrucción que lee el valor de la propiedad a una región de código que tenga un mejor acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d216a-112">If you do not have control of the source code defining the property, or you must restrict the `Get` procedure access level more than the property itself, try to move the statement that reads the property value to a region of code that has better access to the property.</span></span>

## <a name="see-also"></a><span data-ttu-id="d216a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d216a-113">See also</span></span>

- [<span data-ttu-id="d216a-114">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="d216a-114">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="d216a-115">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="d216a-115">How to: Declare a Property with Mixed Access Levels</span></span>](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
