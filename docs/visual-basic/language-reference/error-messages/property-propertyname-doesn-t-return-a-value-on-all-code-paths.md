---
description: "Más información sobre: BC42107: la propiedad ' <propertyname> ' no devuelve un valor en todas las rutas de código"
title: La propiedad '<propertyname>' no devuelve un valor en todas las rutas de acceso a código
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 9aa0d6fea1feeaf7503f5f8831fbd3de910a4822
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774894"
---
# <a name="bc42107-property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="5d5db-103">BC42107: la propiedad ' \<propertyname> ' no devuelve un valor en todas las rutas de código</span><span class="sxs-lookup"><span data-stu-id="5d5db-103">BC42107: Property '\<propertyname>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="5d5db-104">La propiedad ' \<propertyname> ' no devuelve un valor en todas las rutas de acceso de código.</span><span class="sxs-lookup"><span data-stu-id="5d5db-104">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="5d5db-105">Podría producirse una excepción de referencia nula en tiempo de ejecución al usar el resultado.</span><span class="sxs-lookup"><span data-stu-id="5d5db-105">A null reference exception could occur at run time when the result is used.</span></span>

<span data-ttu-id="5d5db-106">Un procedimiento de propiedad `Get` tiene al menos una ruta de acceso posible a través de su código que no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="5d5db-106">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>

 <span data-ttu-id="5d5db-107">Puede devolver un valor de un procedimiento de propiedad `Get` de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d5db-107">You can return a value from a property `Get` procedure in any of the following ways:</span></span>

- <span data-ttu-id="5d5db-108">Asigne el valor al nombre de la propiedad y, a continuación, realice una `Exit Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5d5db-108">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>

- <span data-ttu-id="5d5db-109">Asigne el valor al nombre de la propiedad y, a continuación, realice la `End Get` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5d5db-109">Assign the value to the property name and then perform the `End Get` statement.</span></span>

- <span data-ttu-id="5d5db-110">Incluya el valor en una [instrucción return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d5db-110">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>

<span data-ttu-id="5d5db-111">Si el control pasa a `Exit Property` o `End Get` y no ha asignado ningún valor al nombre de la propiedad, el `Get` procedimiento devuelve el valor predeterminado del tipo de datos de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5d5db-111">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="5d5db-112">Para obtener más información, vea el tema sobre el comportamiento en la [instrucción function](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="5d5db-112">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>

<span data-ttu-id="5d5db-113">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="5d5db-113">By default, this message is a warning.</span></span> <span data-ttu-id="5d5db-114">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5d5db-114">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="5d5db-115">**Identificador de error:** BC42107</span><span class="sxs-lookup"><span data-stu-id="5d5db-115">**Error ID:** BC42107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="5d5db-116">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5d5db-116">To correct this error</span></span>

- <span data-ttu-id="5d5db-117">Compruebe la lógica del flujo de control y asegúrese de asignar un valor antes de cada instrucción que produce una devolución.</span><span class="sxs-lookup"><span data-stu-id="5d5db-117">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>

  <span data-ttu-id="5d5db-118">Es más fácil garantizar que todas las devoluciones del procedimiento devuelvan un valor si siempre se usa la `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5d5db-118">It's easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="5d5db-119">Si lo hace, la última instrucción antes de `End Get` debe ser una `Return` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5d5db-119">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d5db-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d5db-120">See also</span></span>

- [<span data-ttu-id="5d5db-121">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="5d5db-121">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="5d5db-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="5d5db-122">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="5d5db-123">Get (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="5d5db-123">Get Statement</span></span>](../statements/get-statement.md)
