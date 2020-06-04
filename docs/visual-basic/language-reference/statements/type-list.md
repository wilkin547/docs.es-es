---
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
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412993"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="7f33b-102">Lista de tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f33b-102">Type List (Visual Basic)</span></span>

<span data-ttu-id="7f33b-103">Especifica los *parámetros de tipo* para un elemento de programación *genérico* .</span><span class="sxs-lookup"><span data-stu-id="7f33b-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="7f33b-104">Varios parámetros se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="7f33b-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="7f33b-105">A continuación se encuentra la sintaxis de un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="7f33b-105">Following is the syntax for one type parameter.</span></span>

## <a name="syntax"></a><span data-ttu-id="7f33b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f33b-106">Syntax</span></span>

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a><span data-ttu-id="7f33b-107">Partes</span><span class="sxs-lookup"><span data-stu-id="7f33b-107">Parts</span></span>

|<span data-ttu-id="7f33b-108">Término</span><span class="sxs-lookup"><span data-stu-id="7f33b-108">Term</span></span>|<span data-ttu-id="7f33b-109">Definición</span><span class="sxs-lookup"><span data-stu-id="7f33b-109">Definition</span></span>|
|---|---|
|`genericmodifier`|<span data-ttu-id="7f33b-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7f33b-110">Optional.</span></span> <span data-ttu-id="7f33b-111">Solo se puede usar en interfaces y delegados genéricos.</span><span class="sxs-lookup"><span data-stu-id="7f33b-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="7f33b-112">Puede declarar un tipo covariante mediante la palabra clave [out](../modifiers/out-generic-modifier.md) o contravariante mediante la palabra clave [in](../modifiers/in-generic-modifier.md) .</span><span class="sxs-lookup"><span data-stu-id="7f33b-112">You can declare a type covariant by using the [Out](../modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="7f33b-113">Vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="7f33b-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|
|`typename`|<span data-ttu-id="7f33b-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="7f33b-114">Required.</span></span> <span data-ttu-id="7f33b-115">Nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="7f33b-115">Name of the type parameter.</span></span> <span data-ttu-id="7f33b-116">Se trata de un marcador de posición que se reemplazará por un tipo definido proporcionado por el argumento de tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7f33b-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|
|`constraintlist`|<span data-ttu-id="7f33b-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7f33b-117">Optional.</span></span> <span data-ttu-id="7f33b-118">Lista de requisitos que restringen el tipo de datos que se puede proporcionar para `typename` .</span><span class="sxs-lookup"><span data-stu-id="7f33b-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="7f33b-119">Si tiene varias restricciones, enciérrelos entre llaves ( `{ }` ) y sepárelas con comas.</span><span class="sxs-lookup"><span data-stu-id="7f33b-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="7f33b-120">Debe introducir la lista de restricciones con la palabra clave [as](as-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="7f33b-120">You must introduce the constraint list with the [As](as-clause.md) keyword.</span></span> <span data-ttu-id="7f33b-121">Solo se usa `As` una vez, al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="7f33b-121">You use `As` only once, at the beginning of the list.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f33b-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f33b-122">Remarks</span></span>

<span data-ttu-id="7f33b-123">Cada elemento de programación genérico debe tomar al menos un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="7f33b-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="7f33b-124">Un parámetro de tipo es un marcador de posición para un tipo específico (un *elemento construido*) que el código de cliente especifica cuando crea una instancia del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="7f33b-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="7f33b-125">Puede definir una clase, una estructura, una interfaz, un procedimiento o un delegado genéricos.</span><span class="sxs-lookup"><span data-stu-id="7f33b-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>

<span data-ttu-id="7f33b-126">Para obtener más información sobre cuándo definir un tipo genérico, vea [tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="7f33b-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="7f33b-127">Para obtener más información sobre los nombres de parámetros de tipo, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="7f33b-127">For more information on type parameter names, see [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

## <a name="rules"></a><span data-ttu-id="7f33b-128">Reglas</span><span class="sxs-lookup"><span data-stu-id="7f33b-128">Rules</span></span>

- <span data-ttu-id="7f33b-129">**Paréntesis.**</span><span class="sxs-lookup"><span data-stu-id="7f33b-129">**Parentheses.**</span></span> <span data-ttu-id="7f33b-130">Si proporciona una lista de parámetros de tipo, debe encerrarla entre paréntesis y debe introducir la lista con [la palabra clave](of-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="7f33b-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](of-clause.md) keyword.</span></span> <span data-ttu-id="7f33b-131">Solo se usa `Of` una vez, al principio de la lista.</span><span class="sxs-lookup"><span data-stu-id="7f33b-131">You use `Of` only once, at the beginning of the list.</span></span>

- <span data-ttu-id="7f33b-132">**Restricciones.**</span><span class="sxs-lookup"><span data-stu-id="7f33b-132">**Constraints.**</span></span> <span data-ttu-id="7f33b-133">Una lista de *restricciones* en un parámetro de tipo puede incluir los elementos siguientes en cualquier combinación:</span><span class="sxs-lookup"><span data-stu-id="7f33b-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>

  - <span data-ttu-id="7f33b-134">Cualquier número de interfaces.</span><span class="sxs-lookup"><span data-stu-id="7f33b-134">Any number of interfaces.</span></span> <span data-ttu-id="7f33b-135">El tipo proporcionado debe implementar cada interfaz en esta lista.</span><span class="sxs-lookup"><span data-stu-id="7f33b-135">The supplied type must implement every interface in this list.</span></span>

  - <span data-ttu-id="7f33b-136">A lo sumo una clase.</span><span class="sxs-lookup"><span data-stu-id="7f33b-136">At most one class.</span></span> <span data-ttu-id="7f33b-137">El tipo proporcionado debe heredar de esa clase.</span><span class="sxs-lookup"><span data-stu-id="7f33b-137">The supplied type must inherit from that class.</span></span>

  - <span data-ttu-id="7f33b-138">Palabra clave `New`.</span><span class="sxs-lookup"><span data-stu-id="7f33b-138">The `New` keyword.</span></span> <span data-ttu-id="7f33b-139">El tipo proporcionado debe exponer un constructor sin parámetros al que pueda tener acceso el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="7f33b-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="7f33b-140">Esto resulta útil si se restringe un parámetro de tipo mediante una o más interfaces.</span><span class="sxs-lookup"><span data-stu-id="7f33b-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="7f33b-141">Un tipo que implementa interfaces no expone necesariamente un constructor y, en función del nivel de acceso de un constructor, el código dentro del tipo genérico podría no tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="7f33b-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>

  - <span data-ttu-id="7f33b-142">La `Class` palabra clave o la `Structure` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="7f33b-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="7f33b-143">La `Class` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a él sea un tipo de referencia, por ejemplo una cadena, una matriz o un delegado, o un objeto creado a partir de una clase.</span><span class="sxs-lookup"><span data-stu-id="7f33b-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="7f33b-144">La `Structure` palabra clave restringe un parámetro de tipo genérico para exigir que cualquier argumento de tipo pasado a él sea un tipo de valor, por ejemplo una estructura, una enumeración o un tipo de datos elemental.</span><span class="sxs-lookup"><span data-stu-id="7f33b-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="7f33b-145">No puede incluir `Class` y `Structure` en el mismo `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="7f33b-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>

  <span data-ttu-id="7f33b-146">El tipo proporcionado debe cumplir todos los requisitos que se incluyen en `constraintlist` .</span><span class="sxs-lookup"><span data-stu-id="7f33b-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>

  <span data-ttu-id="7f33b-147">Las restricciones de cada parámetro de tipo son independientes de las restricciones en otros parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="7f33b-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>

## <a name="behavior"></a><span data-ttu-id="7f33b-148">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="7f33b-148">Behavior</span></span>

- <span data-ttu-id="7f33b-149">**Sustitución en tiempo de compilación.**</span><span class="sxs-lookup"><span data-stu-id="7f33b-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="7f33b-150">Cuando se crea un tipo construido a partir de un elemento de programación genérico, se proporciona un tipo definido para cada parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="7f33b-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="7f33b-151">El compilador de Visual Basic sustituye el tipo proporcionado por cada aparición de `typename` dentro del elemento genérico.</span><span class="sxs-lookup"><span data-stu-id="7f33b-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>

- <span data-ttu-id="7f33b-152">**Ausencia de restricciones.**</span><span class="sxs-lookup"><span data-stu-id="7f33b-152">**Absence of Constraints.**</span></span> <span data-ttu-id="7f33b-153">Si no especifica ninguna restricción en un parámetro de tipo, el código se limita a las operaciones y miembros admitidos por el tipo de [datos Object](../data-types/object-data-type.md) para ese parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="7f33b-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../data-types/object-data-type.md) for that type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="7f33b-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f33b-154">Example</span></span>

<span data-ttu-id="7f33b-155">En el ejemplo siguiente se muestra una definición de esqueleto de una clase de diccionario genérico, incluida una función esqueleto para agregar una nueva entrada al diccionario.</span><span class="sxs-lookup"><span data-stu-id="7f33b-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a><span data-ttu-id="7f33b-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f33b-156">Example</span></span>

<span data-ttu-id="7f33b-157">Dado `dictionary` que es genérico, el código que lo usa puede crear una variedad de objetos a partir de él, cada uno con la misma funcionalidad pero que actúa en un tipo de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="7f33b-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="7f33b-158">En el ejemplo siguiente se muestra una línea de código que crea un `dictionary` objeto con `String` entradas y `Integer` claves.</span><span class="sxs-lookup"><span data-stu-id="7f33b-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a><span data-ttu-id="7f33b-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f33b-159">Example</span></span>

<span data-ttu-id="7f33b-160">En el ejemplo siguiente se muestra la definición de esqueleto equivalente generada por el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="7f33b-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="7f33b-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f33b-161">See also</span></span>

- [<span data-ttu-id="7f33b-162">De</span><span class="sxs-lookup"><span data-stu-id="7f33b-162">Of</span></span>](of-clause.md)
- [<span data-ttu-id="7f33b-163">New (operador)</span><span class="sxs-lookup"><span data-stu-id="7f33b-163">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="7f33b-164">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f33b-164">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="7f33b-165">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="7f33b-165">Object Data Type</span></span>](../data-types/object-data-type.md)
- [<span data-ttu-id="7f33b-166">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="7f33b-166">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="7f33b-167">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="7f33b-167">Structure Statement</span></span>](structure-statement.md)
- [<span data-ttu-id="7f33b-168">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="7f33b-168">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="7f33b-169">Procedimiento Uso de clases genéricas</span><span class="sxs-lookup"><span data-stu-id="7f33b-169">How to: Use a Generic Class</span></span>](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="7f33b-170">Covarianza y contravarianza</span><span class="sxs-lookup"><span data-stu-id="7f33b-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="7f33b-171">De</span><span class="sxs-lookup"><span data-stu-id="7f33b-171">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="7f33b-172">Enuncia</span><span class="sxs-lookup"><span data-stu-id="7f33b-172">Out</span></span>](../modifiers/out-generic-modifier.md)
