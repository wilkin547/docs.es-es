---
title: Restricciones
description: Obtenga información F# sobre las restricciones que se aplican a los parámetros de tipo genérico para especificar los requisitos de un argumento de tipo en una función o un tipo genérico.
ms.date: 05/16/2016
ms.openlocfilehash: 9912ba63138d893a7c616661dd2b1cbdbe51916c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736790"
---
# <a name="constraints"></a><span data-ttu-id="3ca32-103">Restricciones</span><span class="sxs-lookup"><span data-stu-id="3ca32-103">Constraints</span></span>

<span data-ttu-id="3ca32-104">En este tema se describen las restricciones que se pueden aplicar a los parámetros de tipo genérico para especificar los requisitos de un argumento de tipo en una función o un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="3ca32-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="3ca32-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ca32-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="3ca32-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ca32-106">Remarks</span></span>

<span data-ttu-id="3ca32-107">Hay varias restricciones diferentes que puede aplicar para limitar los tipos que se pueden usar en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="3ca32-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="3ca32-108">En la tabla siguiente se enumeran y se describen estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="3ca32-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="3ca32-109">Restricción</span><span class="sxs-lookup"><span data-stu-id="3ca32-109">Constraint</span></span>|<span data-ttu-id="3ca32-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ca32-110">Syntax</span></span>|<span data-ttu-id="3ca32-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ca32-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="3ca32-112">Restricción de tipo</span><span class="sxs-lookup"><span data-stu-id="3ca32-112">Type Constraint</span></span>|<span data-ttu-id="3ca32-113">*type-parameter* : &gt; *Type*</span><span class="sxs-lookup"><span data-stu-id="3ca32-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="3ca32-114">El tipo proporcionado debe ser igual o derivarse del tipo especificado, o bien, si el tipo es una interfaz, el tipo proporcionado debe implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="3ca32-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="3ca32-115">Restricción null</span><span class="sxs-lookup"><span data-stu-id="3ca32-115">Null Constraint</span></span>|<span data-ttu-id="3ca32-116">*type-parameter* : null</span><span class="sxs-lookup"><span data-stu-id="3ca32-116">*type-parameter* : null</span></span>|<span data-ttu-id="3ca32-117">El tipo proporcionado debe admitir el literal null.</span><span class="sxs-lookup"><span data-stu-id="3ca32-117">The provided type must support the null literal.</span></span> <span data-ttu-id="3ca32-118">Esto incluye todos los tipos de objetos de F# .net, pero no los tipos de lista, tupla, función, clase, registro o Unión.</span><span class="sxs-lookup"><span data-stu-id="3ca32-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="3ca32-119">Restricción de miembro explícita</span><span class="sxs-lookup"><span data-stu-id="3ca32-119">Explicit Member Constraint</span></span>|<span data-ttu-id="3ca32-120">[(]*parámetro de tipo* [o … o *parámetro de tipo*)]: (*firma del miembro*)</span><span class="sxs-lookup"><span data-stu-id="3ca32-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="3ca32-121">Al menos uno de los argumentos de tipo proporcionados debe tener un miembro que tenga la firma especificada; no está pensado para su uso común.</span><span class="sxs-lookup"><span data-stu-id="3ca32-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="3ca32-122">Los miembros deben estar definidos explícitamente en el tipo o parte de una extensión de tipo implícita para ser destinos válidos para una restricción de miembro explícita.</span><span class="sxs-lookup"><span data-stu-id="3ca32-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="3ca32-123">Restricción de constructor</span><span class="sxs-lookup"><span data-stu-id="3ca32-123">Constructor Constraint</span></span>|<span data-ttu-id="3ca32-124">*type-parameter* : (New: unit-&gt; ' a)</span><span class="sxs-lookup"><span data-stu-id="3ca32-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="3ca32-125">El tipo proporcionado debe tener un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="3ca32-125">The provided type must have a parameterless constructor.</span></span>|
|<span data-ttu-id="3ca32-126">Restricción de tipo de valor</span><span class="sxs-lookup"><span data-stu-id="3ca32-126">Value Type Constraint</span></span>|<span data-ttu-id="3ca32-127">: struct</span><span class="sxs-lookup"><span data-stu-id="3ca32-127">: struct</span></span>|<span data-ttu-id="3ca32-128">El tipo proporcionado debe ser un tipo de valor de .NET.</span><span class="sxs-lookup"><span data-stu-id="3ca32-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="3ca32-129">Restricción de tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="3ca32-129">Reference Type Constraint</span></span>|<span data-ttu-id="3ca32-130">: no struct</span><span class="sxs-lookup"><span data-stu-id="3ca32-130">: not struct</span></span>|<span data-ttu-id="3ca32-131">El tipo proporcionado debe ser un tipo de referencia de .NET.</span><span class="sxs-lookup"><span data-stu-id="3ca32-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="3ca32-132">Restricción de tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="3ca32-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="3ca32-133">: enum&lt;*underlying-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="3ca32-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="3ca32-134">El tipo proporcionado debe ser un tipo enumerado que tenga el tipo subyacente especificado. no está pensado para su uso común.</span><span class="sxs-lookup"><span data-stu-id="3ca32-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="3ca32-135">Restricción de delegado</span><span class="sxs-lookup"><span data-stu-id="3ca32-135">Delegate Constraint</span></span>|<span data-ttu-id="3ca32-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span><span class="sxs-lookup"><span data-stu-id="3ca32-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="3ca32-137">El tipo proporcionado debe ser un tipo de delegado que tenga los argumentos y el valor devuelto especificados. no está pensado para su uso común.</span><span class="sxs-lookup"><span data-stu-id="3ca32-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="3ca32-138">Restricción de comparación</span><span class="sxs-lookup"><span data-stu-id="3ca32-138">Comparison Constraint</span></span>|<span data-ttu-id="3ca32-139">: comparación</span><span class="sxs-lookup"><span data-stu-id="3ca32-139">: comparison</span></span>|<span data-ttu-id="3ca32-140">El tipo proporcionado debe admitir la comparación.</span><span class="sxs-lookup"><span data-stu-id="3ca32-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="3ca32-141">Restricción de igualdad</span><span class="sxs-lookup"><span data-stu-id="3ca32-141">Equality Constraint</span></span>|<span data-ttu-id="3ca32-142">: igualdad</span><span class="sxs-lookup"><span data-stu-id="3ca32-142">: equality</span></span>|<span data-ttu-id="3ca32-143">El tipo proporcionado debe admitir la igualdad.</span><span class="sxs-lookup"><span data-stu-id="3ca32-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="3ca32-144">Restricción no administrada</span><span class="sxs-lookup"><span data-stu-id="3ca32-144">Unmanaged Constraint</span></span>|<span data-ttu-id="3ca32-145">: no administrado</span><span class="sxs-lookup"><span data-stu-id="3ca32-145">: unmanaged</span></span>|<span data-ttu-id="3ca32-146">El tipo proporcionado debe ser un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="3ca32-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="3ca32-147">Los tipos no administrados son determinados tipos primitivos (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, 0, 1, 2 o 3), tipos de enumeración, 4 o un no genérico estructura cuyos campos son tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="3ca32-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="3ca32-148">Tiene que agregar una restricción cuando el código tiene que usar una característica que está disponible en el tipo de restricción, pero no en los tipos en general.</span><span class="sxs-lookup"><span data-stu-id="3ca32-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="3ca32-149">Por ejemplo, si usa la restricción de tipo para especificar un tipo de clase, puede usar cualquiera de los métodos de esa clase en la función o el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="3ca32-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="3ca32-150">A veces se requiere la especificación de restricciones cuando se escriben parámetros de tipo de forma explícita, ya que sin una restricción, el compilador no tiene ninguna manera de comprobar que las características que está usando estarán disponibles en cualquier tipo que se pueda proporcionar en tiempo de ejecución para el tipo parámetro.</span><span class="sxs-lookup"><span data-stu-id="3ca32-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="3ca32-151">Las restricciones más comunes que se usan en el F# código son restricciones de tipo que especifican clases base o interfaces.</span><span class="sxs-lookup"><span data-stu-id="3ca32-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="3ca32-152">La F# biblioteca usa las demás restricciones para implementar ciertas funciones, como la restricción explícita de miembros, que se usa para implementar la sobrecarga de operadores para los operadores aritméticos, o se proporcionan principalmente porque F# admite el conjunto completo de restricciones admitidas por el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3ca32-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="3ca32-153">Durante el proceso de inferencia de tipos, el compilador deduce algunas restricciones automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3ca32-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="3ca32-154">Por ejemplo, si usa el operador `+` en una función, el compilador deduce una restricción de miembro explícita en los tipos de variables que se usan en la expresión.</span><span class="sxs-lookup"><span data-stu-id="3ca32-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="3ca32-155">En el código siguiente se muestran algunas declaraciones de restricción:</span><span class="sxs-lookup"><span data-stu-id="3ca32-155">The following code illustrates some constraint declarations:</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> = 
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="3ca32-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ca32-156">See also</span></span>

- [<span data-ttu-id="3ca32-157">Genéricos</span><span class="sxs-lookup"><span data-stu-id="3ca32-157">Generics</span></span>](index.md)
- [<span data-ttu-id="3ca32-158">Restricciones</span><span class="sxs-lookup"><span data-stu-id="3ca32-158">Constraints</span></span>](constraints.md)
