---
description: 'Más información sobre: lista de tipos (Visual Basic)'
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: d4c8bcab4a39af0ac0747d6be0d04408edd98a55
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740904"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="0aa12-103">Lista de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aa12-103">Type List (Visual Basic)</span></span>

<span data-ttu-id="0aa12-104">Especifica los *parámetros de tipo* para un elemento de programación *genérico* .</span><span class="sxs-lookup"><span data-stu-id="0aa12-104">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="0aa12-105">Varios parámetros se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="0aa12-105">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="0aa12-106">A continuación se encuentra la sintaxis de un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0aa12-106">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="0aa12-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0aa12-107">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="0aa12-108">Partes</span><span class="sxs-lookup"><span data-stu-id="0aa12-108">Parts</span></span>

|<span data-ttu-id="0aa12-109">Término</span><span class="sxs-lookup"><span data-stu-id="0aa12-109">Term</span></span>|<span data-ttu-id="0aa12-110">Definición</span><span class="sxs-lookup"><span data-stu-id="0aa12-110">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="0aa12-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0aa12-111">Optional.</span></span> <span data-ttu-id="0aa12-112">Solo se puede usar en interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="0aa12-112">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="0aa12-113">Puede declarar un tipo covariante mediante la palabra clave [out](../modifiers/out-generic-modifier.md) o contravariante mediante la palabra clave [in](../modifiers/in-generic-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="0aa12-113">You can declare a type covariant by using the [Out](../modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="0aa12-114">Vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="0aa12-114">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="0aa12-115">Necesario.</span><span class="sxs-lookup"><span data-stu-id="0aa12-115">Required.</span></span> <span data-ttu-id="0aa12-116">Nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0aa12-116">Name of the type parameter.</span></span> <span data-ttu-id="0aa12-117">Se trata de un marcador de posición que se reemplazará por un tipo definido proporcionado por el argumento de tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0aa12-117">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="0aa12-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0aa12-118">Optional.</span></span> <span data-ttu-id="0aa12-119">Lista de requisitos que restringen el tipo de datos que se puede proporcionar para `typename` .</span><span class="sxs-lookup"><span data-stu-id="0aa12-119">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="0aa12-120">Si tiene varias restricciones, enciérrelos entre llaves ( `{ }` ) y sepárelas con comas.</span><span class="sxs-lookup"><span data-stu-id="0aa12-120">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="0aa12-121">Debe introducir la lista de restricciones con la palabra clave [as](as-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="0aa12-121">You must introduce the constraint list with the [As](as-clause.md) keyword.</span></span> <span data-ttu-id="0aa12-122">Solo se usa `As` una vez, al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="0aa12-122">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0aa12-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0aa12-123">Remarks</span></span>

<span data-ttu-id="0aa12-124">Cada elemento de programación genérico debe tomar al menos un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0aa12-124">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="0aa12-125">Un parámetro de tipo es un marcador de posición para un tipo específico (un *elemento construido*) que el código de cliente especifica cuando crea una instancia del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0aa12-125">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="0aa12-126">Puede definir una clase, una estructura, una interfaz, un procedimiento o un delegado genéricos.</span><span class="sxs-lookup"><span data-stu-id="0aa12-126">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="0aa12-127">Para obtener más información sobre cuándo definir un tipo genérico, vea [tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="0aa12-127">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="0aa12-128">Para obtener más información sobre los nombres de parámetros de tipo, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0aa12-128">For more information on type parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="0aa12-129">Reglas</span><span class="sxs-lookup"><span data-stu-id="0aa12-129">Rules</span></span>

- <span data-ttu-id="0aa12-130">**Paréntesis.**</span><span class="sxs-lookup"><span data-stu-id="0aa12-130">**Parentheses.**</span></span> <span data-ttu-id="0aa12-131">Si proporciona una lista de parámetros de tipo, debe encerrarla entre paréntesis y debe introducir la lista con [la palabra clave](of-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="0aa12-131">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](of-clause.md) keyword.</span></span> <span data-ttu-id="0aa12-132">Solo se usa `Of` una vez, al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="0aa12-132">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="0aa12-133">**Restricciones.**</span><span class="sxs-lookup"><span data-stu-id="0aa12-133">**Constraints.**</span></span> <span data-ttu-id="0aa12-134">Una lista de *restricciones* en un parámetro de tipo puede incluir los elementos siguientes en cualquier combinación:</span><span class="sxs-lookup"><span data-stu-id="0aa12-134">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="0aa12-135">Cualquier número de interfaces.</span><span class="sxs-lookup"><span data-stu-id="0aa12-135">Any number of interfaces.</span></span> <span data-ttu-id="0aa12-136">El tipo proporcionado debe implementar cada interfaz en esta lista.</span><span class="sxs-lookup"><span data-stu-id="0aa12-136">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="0aa12-137">A lo sumo una clase.</span><span class="sxs-lookup"><span data-stu-id="0aa12-137">At most one class.</span></span> <span data-ttu-id="0aa12-138">El tipo proporcionado debe heredar de esa clase.</span><span class="sxs-lookup"><span data-stu-id="0aa12-138">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="0aa12-139">La palabra clave `New`.</span><span class="sxs-lookup"><span data-stu-id="0aa12-139">The `New` keyword.</span></span> <span data-ttu-id="0aa12-140">El tipo proporcionado debe exponer un constructor sin parámetros al que pueda tener acceso el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="0aa12-140">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="0aa12-141">Esto resulta útil si se restringe un parámetro de tipo mediante una o más interfaces.</span><span class="sxs-lookup"><span data-stu-id="0aa12-141">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="0aa12-142">Un tipo que implementa interfaces no expone necesariamente un constructor y, en función del nivel de acceso de un constructor, el código dentro del tipo genérico podría no tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="0aa12-142">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="0aa12-143">La `Class` palabra clave o la `Structure` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="0aa12-143">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="0aa12-144">La `Class` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a él sea un tipo de referencia, por ejemplo una cadena, una matriz o un delegado, o un objeto creado a partir de una clase.</span><span class="sxs-lookup"><span data-stu-id="0aa12-144">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="0aa12-145">La `Structure` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a él sea un tipo de valor, por ejemplo una estructura, una enumeración o un tipo de datos elemental.</span><span class="sxs-lookup"><span data-stu-id="0aa12-145">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="0aa12-146">No puede incluir `Class` y `Structure` en el mismo `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="0aa12-146">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="0aa12-147">El tipo proporcionado debe cumplir todos los requisitos que se incluyen en `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="0aa12-147">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="0aa12-148">Las restricciones de cada parámetro de tipo son independientes de las restricciones en otros parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="0aa12-148">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="0aa12-149">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="0aa12-149">Behavior</span></span>

- <span data-ttu-id="0aa12-150">**Sustitución en tiempo de compilación.**</span><span class="sxs-lookup"><span data-stu-id="0aa12-150">**Compile-Time Substitution.**</span></span> <span data-ttu-id="0aa12-151">Cuando se crea un tipo construido a partir de un elemento de programación genérico, se proporciona un tipo definido para cada parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0aa12-151">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="0aa12-152">El compilador de Visual Basic sustituye el tipo proporcionado por cada aparición de `typename` dentro del elemento genérico.</span><span class="sxs-lookup"><span data-stu-id="0aa12-152">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="0aa12-153">**Ausencia de restricciones.**</span><span class="sxs-lookup"><span data-stu-id="0aa12-153">**Absence of Constraints.**</span></span> <span data-ttu-id="0aa12-154">Si no especifica ninguna restricción en un parámetro de tipo, el código se limita a las operaciones y miembros admitidos por el tipo de [datos Object](../data-types/object-data-type.md) para ese parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="0aa12-154">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="0aa12-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aa12-155">Example</span></span>

<span data-ttu-id="0aa12-156">En el ejemplo siguiente se muestra una definición de esqueleto de una clase de diccionario genérico, incluida una función esqueleto para agregar una nueva entrada al diccionario.</span><span class="sxs-lookup"><span data-stu-id="0aa12-156">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="0aa12-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aa12-157">Example</span></span>

<span data-ttu-id="0aa12-158">Dado `dictionary` que es genérico, el código que lo usa puede crear una variedad de objetos a partir de él, cada uno con la misma funcionalidad pero que actúa en un tipo de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="0aa12-158">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="0aa12-159">En el ejemplo siguiente se muestra una línea de código que crea un `dictionary` objeto con `String` entradas y `Integer` claves.</span><span class="sxs-lookup"><span data-stu-id="0aa12-159">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="0aa12-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aa12-160">Example</span></span>

<span data-ttu-id="0aa12-161">En el ejemplo siguiente se muestra la definición de esqueleto equivalente generada por el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="0aa12-161">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="0aa12-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="0aa12-162">See also</span></span>

- [<span data-ttu-id="0aa12-163">De</span><span class="sxs-lookup"><span data-stu-id="0aa12-163">Of</span></span>](of-clause.md)
- [<span data-ttu-id="0aa12-164">New Operator (Nuevo operador)</span><span class="sxs-lookup"><span data-stu-id="0aa12-164">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="0aa12-165">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0aa12-165">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="0aa12-166">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="0aa12-166">Object Data Type</span></span>](../data-types/object-data-type.md)
- [<span data-ttu-id="0aa12-167">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="0aa12-167">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="0aa12-168">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="0aa12-168">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="0aa12-169">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="0aa12-169">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="0aa12-170">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="0aa12-170">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="0aa12-171">Covarianza y contravarianza</span><span class="sxs-lookup"><span data-stu-id="0aa12-171">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="0aa12-172">In</span><span class="sxs-lookup"><span data-stu-id="0aa12-172">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="0aa12-173">Fuera</span><span class="sxs-lookup"><span data-stu-id="0aa12-173">Out</span></span>](../modifiers/out-generic-modifier.md)
