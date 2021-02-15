---
description: 'Más información sobre: sobrecarga de procedimientos (Visual Basic)'
title: Sobrecarga de procedimientos
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 27e79e12153bc7ac6a9e3b3b5997a50c1c354195
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466645"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="c845d-103">Sobrecarga de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c845d-103">Procedure Overloading (Visual Basic)</span></span>

<span data-ttu-id="c845d-104">*Sobrecargar* un procedimiento significa definirlo en varias versiones, con el mismo nombre pero con diferentes listas de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c845d-104">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="c845d-105">El propósito de la sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que diferenciarlas por nombre.</span><span class="sxs-lookup"><span data-stu-id="c845d-105">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="c845d-106">Para ello, variará la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="c845d-106">You do this by varying the parameter list.</span></span>

## <a name="overloading-rules"></a><span data-ttu-id="c845d-107">Sobrecargar reglas</span><span class="sxs-lookup"><span data-stu-id="c845d-107">Overloading Rules</span></span>

<span data-ttu-id="c845d-108">Al sobrecargar un procedimiento, se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="c845d-108">When you overload a procedure, the following rules apply:</span></span>

- <span data-ttu-id="c845d-109">**Mismo nombre**.</span><span class="sxs-lookup"><span data-stu-id="c845d-109">**Same Name**.</span></span> <span data-ttu-id="c845d-110">Cada versión sobrecargada debe usar el mismo nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c845d-110">Each overloaded version must use the same procedure name.</span></span>

- <span data-ttu-id="c845d-111">**Firma diferente**.</span><span class="sxs-lookup"><span data-stu-id="c845d-111">**Different Signature**.</span></span> <span data-ttu-id="c845d-112">Cada versión sobrecargada debe ser diferente de todas las demás versiones sobrecargadas en al menos uno de los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="c845d-112">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>

  - <span data-ttu-id="c845d-113">Cantidad de parámetros</span><span class="sxs-lookup"><span data-stu-id="c845d-113">Number of parameters</span></span>

  - <span data-ttu-id="c845d-114">Orden de los parámetros</span><span class="sxs-lookup"><span data-stu-id="c845d-114">Order of the parameters</span></span>

  - <span data-ttu-id="c845d-115">Tipos de datos de los parámetros</span><span class="sxs-lookup"><span data-stu-id="c845d-115">Data types of the parameters</span></span>

  - <span data-ttu-id="c845d-116">Número de parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="c845d-116">Number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="c845d-117">Tipo de valor devuelto (solo para un operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="c845d-117">Return type (only for a conversion operator)</span></span>

  <span data-ttu-id="c845d-118">Junto con el nombre del procedimiento, los elementos anteriores se denominan colectivamente la *firma* del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c845d-118">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="c845d-119">Cuando se llama a un procedimiento sobrecargado, el compilador usa la firma para comprobar que la llamada coincide correctamente con la definición.</span><span class="sxs-lookup"><span data-stu-id="c845d-119">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>

- <span data-ttu-id="c845d-120">**Elementos que no forman parte de la firma**.</span><span class="sxs-lookup"><span data-stu-id="c845d-120">**Items Not Part of Signature**.</span></span> <span data-ttu-id="c845d-121">No se puede sobrecargar un procedimiento sin variar la firma.</span><span class="sxs-lookup"><span data-stu-id="c845d-121">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="c845d-122">En concreto, no se puede sobrecargar un procedimiento cambiando solo uno o varios de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="c845d-122">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>

  - <span data-ttu-id="c845d-123">Palabras clave de modificador de procedimientos, como `Public` , `Shared` y `Static`</span><span class="sxs-lookup"><span data-stu-id="c845d-123">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>

  - <span data-ttu-id="c845d-124">Nombres de parámetros de tipo o parámetro</span><span class="sxs-lookup"><span data-stu-id="c845d-124">Parameter or type parameter names</span></span>

  - <span data-ttu-id="c845d-125">Restricciones de parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="c845d-125">Type parameter constraints (for a generic procedure)</span></span>

  - <span data-ttu-id="c845d-126">Palabras clave de modificador de parámetro, como `ByRef` y `Optional`</span><span class="sxs-lookup"><span data-stu-id="c845d-126">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>

  - <span data-ttu-id="c845d-127">Si devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="c845d-127">Whether it returns a value</span></span>

  - <span data-ttu-id="c845d-128">El tipo de datos del valor devuelto (excepto para un operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="c845d-128">The data type of the return value (except for a conversion operator)</span></span>

  <span data-ttu-id="c845d-129">Los elementos de la lista anterior no forman parte de la firma.</span><span class="sxs-lookup"><span data-stu-id="c845d-129">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="c845d-130">Aunque no puede usarlos para diferenciar entre las versiones sobrecargadas, puede modificarlas entre las versiones sobrecargadas que se diferencian correctamente por sus firmas.</span><span class="sxs-lookup"><span data-stu-id="c845d-130">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>

- <span data-ttu-id="c845d-131">**Argumentos enlazados en tiempo de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="c845d-131">**Late-Bound Arguments**.</span></span> <span data-ttu-id="c845d-132">Si piensa pasar una variable de objeto enlazado en tiempo de ejecución a una versión sobrecargada, debe declarar el parámetro adecuado como <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="c845d-132">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>

## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="c845d-133">Varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="c845d-133">Multiple Versions of a Procedure</span></span>

<span data-ttu-id="c845d-134">Supongamos que está escribiendo un `Sub` procedimiento para publicar una transacción en el saldo de un cliente y desea poder hacer referencia al cliente por el nombre o por el número de cuenta.</span><span class="sxs-lookup"><span data-stu-id="c845d-134">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="c845d-135">Para ello, puede definir dos `Sub` procedimientos diferentes, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c845d-135">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>

[!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]

### <a name="overloaded-versions"></a><span data-ttu-id="c845d-136">Versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="c845d-136">Overloaded Versions</span></span>

<span data-ttu-id="c845d-137">Una alternativa es sobrecargar un único nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c845d-137">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="c845d-138">Puede usar la palabra clave [Overloads](../../../language-reference/modifiers/overloads.md) para definir una versión del procedimiento para cada lista de parámetros, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c845d-138">You can use the [Overloads](../../../language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>

[!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]

#### <a name="additional-overloads"></a><span data-ttu-id="c845d-139">Sobrecargas adicionales</span><span class="sxs-lookup"><span data-stu-id="c845d-139">Additional Overloads</span></span>

<span data-ttu-id="c845d-140">Si también desease aceptar una cantidad de transacción en `Decimal` o `Single` , puede realizar una sobrecarga adicional `post` para permitir esta variación.</span><span class="sxs-lookup"><span data-stu-id="c845d-140">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="c845d-141">Si lo hizo en cada una de las sobrecargas del ejemplo anterior, tendría cuatro `Sub` procedimientos, todos con el mismo nombre pero con cuatro firmas diferentes.</span><span class="sxs-lookup"><span data-stu-id="c845d-141">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>

## <a name="advantages-of-overloading"></a><span data-ttu-id="c845d-142">Ventajas de la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="c845d-142">Advantages of Overloading</span></span>

<span data-ttu-id="c845d-143">La ventaja de sobrecargar un procedimiento es la flexibilidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c845d-143">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="c845d-144">Para usar el `post` procedimiento declarado en el ejemplo anterior, el código de llamada puede obtener la identificación del cliente como `String` o `Integer` y, a continuación, llamar al mismo procedimiento en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="c845d-144">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="c845d-145">Esto se ilustra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c845d-145">The following example illustrates this:</span></span>

[!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]

[!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]

## <a name="see-also"></a><span data-ttu-id="c845d-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c845d-146">See also</span></span>

- [<span data-ttu-id="c845d-147">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c845d-147">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c845d-148">Procedimiento para definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="c845d-148">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="c845d-149">Procedimiento para llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="c845d-149">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="c845d-150">Procedimiento para sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="c845d-150">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="c845d-151">Procedimiento para sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="c845d-151">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="c845d-152">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="c845d-152">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="c845d-153">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="c845d-153">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="c845d-154">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="c845d-154">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
- [<span data-ttu-id="c845d-155">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c845d-155">Generic Types in Visual Basic</span></span>](../data-types/generic-types.md)
