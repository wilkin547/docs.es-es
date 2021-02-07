---
description: 'Más información acerca de: sobrecargas (Visual Basic)'
title: Sobrecargas
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 7f0b440b537500595e465d8aabc7724671f3ae95
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730517"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="9ffd7-103">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-103">Overloads (Visual Basic)</span></span>

<span data-ttu-id="9ffd7-104">Especifica que una propiedad o procedimiento vuelve a declarar una o varias propiedades o procedimientos existentes con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-104">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ffd7-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ffd7-105">Remarks</span></span>

<span data-ttu-id="9ffd7-106">La *sobrecarga* es la práctica de proporcionar más de una definición para un nombre de propiedad o procedimiento determinado en el mismo ámbito.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-106">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="9ffd7-107">La Redeclaración de una propiedad o un procedimiento con una firma diferente se denomina a veces *ocultar por firma*.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-107">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>

## <a name="rules"></a><span data-ttu-id="9ffd7-108">Reglas</span><span class="sxs-lookup"><span data-stu-id="9ffd7-108">Rules</span></span>

- <span data-ttu-id="9ffd7-109">**Contexto de declaración.**</span><span class="sxs-lookup"><span data-stu-id="9ffd7-109">**Declaration Context.**</span></span> <span data-ttu-id="9ffd7-110">Solo se puede usar `Overloads` en una instrucción de declaración de propiedad o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-110">You can use `Overloads` only in a property or procedure declaration statement.</span></span>

- <span data-ttu-id="9ffd7-111">**Modificadores combinados.**</span><span class="sxs-lookup"><span data-stu-id="9ffd7-111">**Combined Modifiers.**</span></span> <span data-ttu-id="9ffd7-112">No se puede especificar `Overloads` junto con [Shadows](shadows.md) en la misma declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-112">You cannot specify `Overloads` together with [Shadows](shadows.md) in the same procedure declaration.</span></span>

- <span data-ttu-id="9ffd7-113">**Diferencias requeridas.**</span><span class="sxs-lookup"><span data-stu-id="9ffd7-113">**Required Differences.**</span></span> <span data-ttu-id="9ffd7-114">La *firma* de esta declaración debe ser diferente de la firma de cada propiedad o procedimiento que sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-114">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="9ffd7-115">La firma incluye el nombre de propiedad o procedimiento más lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ffd7-115">The signature comprises the property or procedure name together with the following:</span></span>

  - <span data-ttu-id="9ffd7-116">el número de parámetros</span><span class="sxs-lookup"><span data-stu-id="9ffd7-116">the number of parameters</span></span>

  - <span data-ttu-id="9ffd7-117">el orden de los parámetros</span><span class="sxs-lookup"><span data-stu-id="9ffd7-117">the order of the parameters</span></span>

  - <span data-ttu-id="9ffd7-118">los tipos de datos de los parámetros</span><span class="sxs-lookup"><span data-stu-id="9ffd7-118">the data types of the parameters</span></span>

  - <span data-ttu-id="9ffd7-119">el número de parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-119">the number of type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="9ffd7-120">el tipo de valor devuelto (solo para un procedimiento de operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-120">the return type (only for a conversion operator procedure)</span></span>

  <span data-ttu-id="9ffd7-121">Todas las sobrecargas deben tener el mismo nombre, pero cada una debe diferir de todas las demás en uno o varios de los aspectos anteriores.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-121">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="9ffd7-122">Esto permite al compilador distinguir qué versión debe utilizar cuando el código llama a la propiedad o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-122">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>

- <span data-ttu-id="9ffd7-123">**Diferencias no permitidas.**</span><span class="sxs-lookup"><span data-stu-id="9ffd7-123">**Disallowed Differences.**</span></span> <span data-ttu-id="9ffd7-124">El cambio de uno o varios de los siguientes aspectos no es válido para sobrecargar una propiedad o un procedimiento, porque no forman parte de la firma:</span><span class="sxs-lookup"><span data-stu-id="9ffd7-124">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>

  - <span data-ttu-id="9ffd7-125">si devuelve o no un valor (para un procedimiento)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-125">whether or not it returns a value (for a procedure)</span></span>

  - <span data-ttu-id="9ffd7-126">el tipo de datos del valor devuelto (excepto para un operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-126">the data type of the return value (except for a conversion operator)</span></span>

  - <span data-ttu-id="9ffd7-127">los nombres de los parámetros o parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="9ffd7-127">the names of the parameters or type parameters</span></span>

  - <span data-ttu-id="9ffd7-128">las restricciones en los parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-128">the constraints on the type parameters (for a generic procedure)</span></span>

  - <span data-ttu-id="9ffd7-129">palabras clave de modificador de parámetro (como `ByRef` o `Optional`)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-129">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>

  - <span data-ttu-id="9ffd7-130">palabras clave de modificador de propiedad o procedimiento (como `Public` o `Shared`)</span><span class="sxs-lookup"><span data-stu-id="9ffd7-130">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>

- <span data-ttu-id="9ffd7-131">**Modificador opcional.**</span><span class="sxs-lookup"><span data-stu-id="9ffd7-131">**Optional Modifier.**</span></span> <span data-ttu-id="9ffd7-132">No es necesario usar el `Overloads` modificador al definir varias propiedades o procedimientos sobrecargados en la misma clase.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-132">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="9ffd7-133">Sin embargo, si utiliza `Overloads` en una de las declaraciones, debe utilizarlo en todas ellas.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-133">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>

- <span data-ttu-id="9ffd7-134">**Sombreado y sobrecarga.**</span><span class="sxs-lookup"><span data-stu-id="9ffd7-134">**Shadowing and Overloading.**</span></span> <span data-ttu-id="9ffd7-135">`Overloads` también se puede utilizar para sombrear un miembro existente, o un conjunto de miembros sobrecargados, en una clase base.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-135">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="9ffd7-136">Al utilizar `Overloads` de esta forma, declara la propiedad o el método con el mismo nombre y la misma lista de parámetros que el miembro de clase base y no proporciona la palabra clave `Shadows`.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-136">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>

<span data-ttu-id="9ffd7-137">Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.</span><span class="sxs-lookup"><span data-stu-id="9ffd7-137">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>

<span data-ttu-id="9ffd7-138">El modificador `Overloads` se puede utilizar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ffd7-138">The `Overloads` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="9ffd7-139">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="9ffd7-139">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="9ffd7-140">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="9ffd7-140">Operator Statement</span></span>](../statements/operator-statement.md)

- [<span data-ttu-id="9ffd7-141">Property Statement</span><span class="sxs-lookup"><span data-stu-id="9ffd7-141">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="9ffd7-142">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="9ffd7-142">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="9ffd7-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ffd7-143">See also</span></span>

- [<span data-ttu-id="9ffd7-144">Shadows</span><span class="sxs-lookup"><span data-stu-id="9ffd7-144">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="9ffd7-145">Sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="9ffd7-145">Procedure Overloading</span></span>](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="9ffd7-146">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ffd7-146">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="9ffd7-147">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="9ffd7-147">Operator Procedures</span></span>](../../programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="9ffd7-148">Procedimiento para definir un operador de conversión</span><span class="sxs-lookup"><span data-stu-id="9ffd7-148">How to: Define a Conversion Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
