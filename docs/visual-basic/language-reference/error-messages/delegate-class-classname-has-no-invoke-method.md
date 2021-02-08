---
description: "Más información sobre: BC30220: la clase delegada ' <classname> ' no tiene un método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método"
title: La clase delegada '<classname>' no tiene ningún método Invoke y, por tanto, una expresión de este tipo no puede ser el destino de una llamada a método
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: c0d3f6e352a98e194b2c2ddca04bfa7254ec37a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796631"
---
# <a name="bc30220-delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="8ca5e-103">BC30220: la clase delegada ' \<classname> ' no tiene un método Invoke, por lo que una expresión de este tipo no puede ser el destino de una llamada al método</span><span class="sxs-lookup"><span data-stu-id="8ca5e-103">BC30220: Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>

<span data-ttu-id="8ca5e-104">No se pudo realizar una llamada a `Invoke` a través de un delegado porque `Invoke` no está implementado en la clase de delegado.</span><span class="sxs-lookup"><span data-stu-id="8ca5e-104">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>

 <span data-ttu-id="8ca5e-105">**Identificador de error:** BC30220</span><span class="sxs-lookup"><span data-stu-id="8ca5e-105">**Error ID:** BC30220</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8ca5e-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8ca5e-106">To correct this error</span></span>

1. <span data-ttu-id="8ca5e-107">Asegúrese de que se ha creado una instancia de la clase delegada con una `Dim` instrucción y que se ha asignado un procedimiento a la instancia de delegado con el `AddressOf` operador.</span><span class="sxs-lookup"><span data-stu-id="8ca5e-107">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>

2. <span data-ttu-id="8ca5e-108">Busque el código que implementa la clase delegada y asegúrese de que implementa el `Invoke` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8ca5e-108">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ca5e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ca5e-109">See also</span></span>

- [<span data-ttu-id="8ca5e-110">Delegados</span><span class="sxs-lookup"><span data-stu-id="8ca5e-110">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="8ca5e-111">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8ca5e-111">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="8ca5e-112">Operador AddressOf</span><span class="sxs-lookup"><span data-stu-id="8ca5e-112">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="8ca5e-113">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="8ca5e-113">Dim Statement</span></span>](../statements/dim-statement.md)
