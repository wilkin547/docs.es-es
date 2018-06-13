---
title: Restricciones (F#)
description: 'Obtenga información acerca de F # las restricciones que se aplican a los parámetros de tipo genérico para especificar los requisitos para un argumento de tipo en un tipo genérico o una función.'
ms.date: 05/16/2016
ms.openlocfilehash: f0722cafe27a4e2c38dfbf091973edb136cf5228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562315"
---
# <a name="constraints"></a><span data-ttu-id="86336-103">Restricciones</span><span class="sxs-lookup"><span data-stu-id="86336-103">Constraints</span></span>

<span data-ttu-id="86336-104">En este tema se describe las restricciones que se pueden aplicar a genérica parámetros para especificar los requisitos para un argumento de tipo en un tipo genérico o una función de tipo.</span><span class="sxs-lookup"><span data-stu-id="86336-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>


## <a name="syntax"></a><span data-ttu-id="86336-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86336-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="86336-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86336-106">Remarks</span></span>
<span data-ttu-id="86336-107">Hay varias restricciones diferentes que se pueden aplicar para limitar los tipos que se pueden usar en un tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="86336-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="86336-108">En la tabla siguiente se enumera y describe estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="86336-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="86336-109">Restricción</span><span class="sxs-lookup"><span data-stu-id="86336-109">Constraint</span></span>|<span data-ttu-id="86336-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86336-110">Syntax</span></span>|<span data-ttu-id="86336-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="86336-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="86336-112">Restricción de tipo</span><span class="sxs-lookup"><span data-stu-id="86336-112">Type Constraint</span></span>|<span data-ttu-id="86336-113">*parámetro de tipo* :&gt; *tipo*</span><span class="sxs-lookup"><span data-stu-id="86336-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="86336-114">El tipo proporcionado debe ser igual a o derivado del tipo especificado o, si el tipo es una interfaz, el tipo proporcionado debe implementar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="86336-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="86336-115">Restricción null</span><span class="sxs-lookup"><span data-stu-id="86336-115">Null Constraint</span></span>|<span data-ttu-id="86336-116">*parámetro de tipo* : null</span><span class="sxs-lookup"><span data-stu-id="86336-116">*type-parameter* : null</span></span>|<span data-ttu-id="86336-117">El tipo proporcionado debe admitir el literal null.</span><span class="sxs-lookup"><span data-stu-id="86336-117">The provided type must support the null literal.</span></span> <span data-ttu-id="86336-118">Esto incluye todos los tipos de objetos de .NET pero no F # lista, tupla, función, clase, registro o tipos de unión.</span><span class="sxs-lookup"><span data-stu-id="86336-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="86336-119">Restricción de miembro explícita</span><span class="sxs-lookup"><span data-stu-id="86336-119">Explicit Member Constraint</span></span>|<span data-ttu-id="86336-120">[()]*parámetro de tipo* [o... o *parámetro de tipo*)]: (* firma de miembro *)</span><span class="sxs-lookup"><span data-stu-id="86336-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature *)</span></span>|<span data-ttu-id="86336-121">Al menos uno de los argumentos de tipo proporcionados debe tener un miembro que tiene la firma especificada; no se ha diseñado para su uso comunes.</span><span class="sxs-lookup"><span data-stu-id="86336-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="86336-122">Miembros deben ser explícitamente definidos en el tipo o parte de una extensión de tipos implícita como destinos válidos para una restricción de miembro explícita.</span><span class="sxs-lookup"><span data-stu-id="86336-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="86336-123">Restricción de constructor</span><span class="sxs-lookup"><span data-stu-id="86336-123">Constructor Constraint</span></span>|<span data-ttu-id="86336-124">*parámetro de tipo* : (nuevo: unidad -&gt; ' un)</span><span class="sxs-lookup"><span data-stu-id="86336-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="86336-125">El tipo proporcionado debe tener un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="86336-125">The provided type must have a default constructor.</span></span>|
|<span data-ttu-id="86336-126">Restricción de tipo de valor</span><span class="sxs-lookup"><span data-stu-id="86336-126">Value Type Constraint</span></span>|<span data-ttu-id="86336-127">: struct</span><span class="sxs-lookup"><span data-stu-id="86336-127">: struct</span></span>|<span data-ttu-id="86336-128">El tipo proporcionado debe ser un tipo de valor. NET.</span><span class="sxs-lookup"><span data-stu-id="86336-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="86336-129">Restricción de tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="86336-129">Reference Type Constraint</span></span>|<span data-ttu-id="86336-130">: no struct</span><span class="sxs-lookup"><span data-stu-id="86336-130">: not struct</span></span>|<span data-ttu-id="86336-131">El tipo proporcionado debe ser un tipo de referencia. NET.</span><span class="sxs-lookup"><span data-stu-id="86336-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="86336-132">Restricción de tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="86336-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="86336-133">: enumeración&lt;*tipo subyacente*&gt;</span><span class="sxs-lookup"><span data-stu-id="86336-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="86336-134">El tipo proporcionado debe ser un tipo enumerado que tiene el tipo subyacente especificado; no se ha diseñado para su uso comunes.</span><span class="sxs-lookup"><span data-stu-id="86336-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="86336-135">Restricción de delegado</span><span class="sxs-lookup"><span data-stu-id="86336-135">Delegate Constraint</span></span>|<span data-ttu-id="86336-136">: delegar&lt;*tipo de parámetro de tupla*, *tipo de valor devuelto*&gt;</span><span class="sxs-lookup"><span data-stu-id="86336-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="86336-137">El tipo proporcionado debe ser un tipo de delegado que tiene los argumentos especificados y devuelve valor; no se ha diseñado para su uso comunes.</span><span class="sxs-lookup"><span data-stu-id="86336-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="86336-138">Restricción de comparación</span><span class="sxs-lookup"><span data-stu-id="86336-138">Comparison Constraint</span></span>|<span data-ttu-id="86336-139">: comparación</span><span class="sxs-lookup"><span data-stu-id="86336-139">: comparison</span></span>|<span data-ttu-id="86336-140">El tipo proporcionado debe admitir la comparación.</span><span class="sxs-lookup"><span data-stu-id="86336-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="86336-141">Restricción de igualdad</span><span class="sxs-lookup"><span data-stu-id="86336-141">Equality Constraint</span></span>|<span data-ttu-id="86336-142">: igualdad</span><span class="sxs-lookup"><span data-stu-id="86336-142">: equality</span></span>|<span data-ttu-id="86336-143">El tipo proporcionado debe admitir la igualdad.</span><span class="sxs-lookup"><span data-stu-id="86336-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="86336-144">Restricción no administrado</span><span class="sxs-lookup"><span data-stu-id="86336-144">Unmanaged Constraint</span></span>|<span data-ttu-id="86336-145">: no administrado</span><span class="sxs-lookup"><span data-stu-id="86336-145">: unmanaged</span></span>|<span data-ttu-id="86336-146">El tipo proporcionado debe ser un tipo no administrado.</span><span class="sxs-lookup"><span data-stu-id="86336-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="86336-147">Los tipos no administrados son cualquier ciertos tipos primitivos (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, o `decimal`), tipos de enumeración, `nativeptr&lt;_&gt;`, o una estructura no genérica cuyos campos son todos los tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="86336-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr&lt;_&gt;`, or a non-generic structure whose fields are all unmanaged types.</span></span>|
<span data-ttu-id="86336-148">Tendrá que agregar una restricción cuando el código tiene que utilizar una característica que está disponible en el tipo de restricción, pero no en los tipos en general.</span><span class="sxs-lookup"><span data-stu-id="86336-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="86336-149">Por ejemplo, si utiliza la restricción de tipo para especificar un tipo de clase, puede utilizar cualquiera de los métodos de dicha clase en la función o tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="86336-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="86336-150">Especificar restricciones a veces es necesario al escribir parámetros de tipo explícitamente, porque sin una restricción, el compilador no tiene forma de comprobar que las características que está usando estarán disponibles en cualquier tipo que se puede proporcionar en tiempo de ejecución para el tipo parámetro.</span><span class="sxs-lookup"><span data-stu-id="86336-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="86336-151">Las restricciones más comunes de que utilizar código de F # son las restricciones de tipo que especifican las interfaces o clases base.</span><span class="sxs-lookup"><span data-stu-id="86336-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="86336-152">Las demás restricciones se utilizan en la biblioteca de F # para implementar determinadas funcionalidades, como la restricción de miembro explícito, que se utiliza para implementar la sobrecarga de operadores para los operadores aritméticos, o se proporciona principalmente porque F # admite completo conjunto de restricciones que sea compatible con common language runtime.</span><span class="sxs-lookup"><span data-stu-id="86336-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="86336-153">Durante el proceso de inferencia de tipo, existen algunas restricciones se deducen automáticamente por el compilador.</span><span class="sxs-lookup"><span data-stu-id="86336-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="86336-154">Por ejemplo, si usa el `+` operador en una función, el compilador deduce una restricción de miembro explícito en tipos de variables que se utilizan en la expresión.</span><span class="sxs-lookup"><span data-stu-id="86336-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="86336-155">El código siguiente muestra algunas declaraciones de restricción.</span><span class="sxs-lookup"><span data-stu-id="86336-155">The following code illustrates some constraint declarations.</span></span>

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

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
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

## <a name="see-also"></a><span data-ttu-id="86336-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="86336-156">See Also</span></span>
[<span data-ttu-id="86336-157">Genéricos</span><span class="sxs-lookup"><span data-stu-id="86336-157">Generics</span></span>](index.md)

[<span data-ttu-id="86336-158">Restricciones</span><span class="sxs-lookup"><span data-stu-id="86336-158">Constraints</span></span>](constraints.md)
