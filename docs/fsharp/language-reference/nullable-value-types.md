---
title: Tipos de valor que aceptan valores NULL
description: 'Aprenda a usar tipos de valor que aceptan valores NULL, una manera de representar un tipo de valor que también puede ser null, en F #.'
ms.date: 11/19/2020
ms.openlocfilehash: da0cd85bd651db81ba98c02a9db31d92dc52a8c6
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740435"
---
# <a name="nullable-value-types"></a><span data-ttu-id="b2cd0-103">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="b2cd0-103">Nullable value types</span></span>

<span data-ttu-id="b2cd0-104">Un _tipo de valor que acepta valores NULL_ `Nullable<'T>` representa cualquier tipo de [struct](structures.md) que también podría ser `null` .</span><span class="sxs-lookup"><span data-stu-id="b2cd0-104">A _nullable value type_ `Nullable<'T>` represents any [struct](structures.md) type that could also be `null`.</span></span> <span data-ttu-id="b2cd0-105">Esto resulta útil al interactuar con bibliotecas y componentes que pueden optar por representar estos tipos de tipos, como enteros, con un `null` valor por motivos de eficiencia.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-105">This is helpful when interacting with libraries and components that may choose to represent these kinds of types, like integers, with a `null` value for efficiency reasons.</span></span> <span data-ttu-id="b2cd0-106">El tipo subyacente que respalda esta construcción es <xref:System.Nullable%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b2cd0-106">The underlying type that backs this construct is <xref:System.Nullable%601?displayProperty=nameWithType>.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2cd0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2cd0-107">Syntax</span></span>

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a><span data-ttu-id="b2cd0-108">Declarar y asignar valores</span><span class="sxs-lookup"><span data-stu-id="b2cd0-108">Declare and assign with values</span></span>

<span data-ttu-id="b2cd0-109">Declarar un tipo de valor que acepta valores NULL es igual que declarar cualquier tipo de contenedor en F #:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-109">Declaring a nullable value type is just like declaring any wrapper-like type in F#:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

<span data-ttu-id="b2cd0-110">También puede Elide el parámetro de tipo genérico y permitir que la inferencia de tipos lo resuelva:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-110">You can also elide the generic type parameter and allow type inference to resolve it:</span></span>

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

<span data-ttu-id="b2cd0-111">Para asignar a un tipo de valor que acepta valores NULL, también debe ser explícito.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-111">To assign to a nullable value type, you'll need to also be explicit.</span></span> <span data-ttu-id="b2cd0-112">No hay ninguna conversión implícita para los tipos de valor que aceptan valores NULL definidos por F #:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-112">There is no implicit conversion for F#-defined nullable value types:</span></span>

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a><span data-ttu-id="b2cd0-113">Asignar null</span><span class="sxs-lookup"><span data-stu-id="b2cd0-113">Assign null</span></span>

<span data-ttu-id="b2cd0-114">No se puede asignar directamente `null` a un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-114">You cannot directly assign `null` to a nullable value type.</span></span> <span data-ttu-id="b2cd0-115">Use `Nullable()` en su lugar:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-115">Use `Nullable()` instead:</span></span>

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

<span data-ttu-id="b2cd0-116">Esto se debe `Nullable<'T>` `null` a que no tiene un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-116">This is because `Nullable<'T>` does not have `null` as a proper value.</span></span>

## <a name="pass-and-assign-to-members"></a><span data-ttu-id="b2cd0-117">Pasar y asignar a miembros</span><span class="sxs-lookup"><span data-stu-id="b2cd0-117">Pass and assign to members</span></span>

<span data-ttu-id="b2cd0-118">Una diferencia clave entre trabajar con miembros y valores de F # es que los tipos de valor que aceptan valores NULL se pueden inferir implícitamente al trabajar con miembros.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-118">A key difference between working with members and F# values is that nullable value types can be implicitly inferred when you're working with members.</span></span> <span data-ttu-id="b2cd0-119">Considere el método folling que toma un tipo de valor que acepta valores NULL como entrada:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-119">Consider the folling method that takes a nullable value type as input:</span></span>

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

<span data-ttu-id="b2cd0-120">En el ejemplo anterior, puede pasar `12` al método `M` .</span><span class="sxs-lookup"><span data-stu-id="b2cd0-120">In the previous example, you can pass `12` to the method `M`.</span></span> <span data-ttu-id="b2cd0-121">También puede asignar `12` a la propiedad auto `NVT` .</span><span class="sxs-lookup"><span data-stu-id="b2cd0-121">You can also assign `12` to the auto property `NVT`.</span></span> <span data-ttu-id="b2cd0-122">El compilador de F # convertirá implícitamente una llamada o asignación como esta cuando el tipo de destino coincida con la entrada, si la entrada se puede construir como un tipo de valor nullabel.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-122">The F# compiler will implicitly convert a call or assignment like this when the target type matches the input, if the input can be constructed as a nullabel value type.</span></span>

## <a name="examine-a-nullable-value-type-instance"></a><span data-ttu-id="b2cd0-123">Examinar una instancia de tipo de valor que acepta valores NULL</span><span class="sxs-lookup"><span data-stu-id="b2cd0-123">Examine a nullable value type instance</span></span>

<span data-ttu-id="b2cd0-124">A diferencia de [las opciones](options.md), que son una construcción generalizada para representar un valor posible, los tipos de valor que aceptan valores NULL no se usan con la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-124">Unlike [Options](options.md), which are a generalized construct for representing a possible value, nullable value types are not used with pattern matching.</span></span> <span data-ttu-id="b2cd0-125">En su lugar, debe usar una [`if`](conditional-expressions-if-then-else.md) expresión y comprobar la `HasValue` propiedad.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-125">Instead, you need to use an [`if`](conditional-expressions-if-then-else.md) expression and check the `HasValue` property.</span></span>

<span data-ttu-id="b2cd0-126">Para obtener el valor subyacente, utilice la `Value` propiedad después de una `HasValue` comprobación, como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-126">To get the underlying value, use the `Value` property after a `HasValue` check, like so:</span></span>

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a><span data-ttu-id="b2cd0-127">Operadores que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="b2cd0-127">Nullable operators</span></span>

<span data-ttu-id="b2cd0-128">Las operaciones con tipos de valor que aceptan valores NULL, como aritmética o comparación, pueden requerir el uso de [operadores que aceptan valores NULL](symbol-and-operator-reference/nullable-operators.md).</span><span class="sxs-lookup"><span data-stu-id="b2cd0-128">Operations on nullable value types, such as arithmetic or comparison, can require the use of [nullable operators](symbol-and-operator-reference/nullable-operators.md).</span></span>

<span data-ttu-id="b2cd0-129">Puede convertir de un tipo de valor que acepta valores NULL a otro usando operadores de conversión del `FSharp.Linq` espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-129">You can convert from one nullable value type to another using conversion operators from the `FSharp.Linq` namespace:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

<span data-ttu-id="b2cd0-130">También puede usar un operador que no acepte valores NULL adecuado para convertir a un tipo primitivo y arriesgar una excepción si no tiene ningún valor:</span><span class="sxs-lookup"><span data-stu-id="b2cd0-130">You can also use an appropriate non-nullable operator to convert to a primitive type, risking an exception if it has no value:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

<span data-ttu-id="b2cd0-131">También puede usar operadores que aceptan valores NULL para la comprobación `HasValue` y `Value` :</span><span class="sxs-lookup"><span data-stu-id="b2cd0-131">You can also use nullable operators as a short-hand for checking `HasValue` and `Value`:</span></span>

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

<span data-ttu-id="b2cd0-132">La `?>` comparación comprueba si el lado izquierdo admite valores NULL y solo se realiza correctamente si tiene un valor.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-132">The `?>` comparison checks if the left-hand side is nullable and only succeeds if it has a value.</span></span> <span data-ttu-id="b2cd0-133">Es equivalente a la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2cd0-133">It is equivalent to the line that follows it.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2cd0-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2cd0-134">See also</span></span>

- [<span data-ttu-id="b2cd0-135">Estructuras</span><span class="sxs-lookup"><span data-stu-id="b2cd0-135">Structures</span></span>](structures.md)
- [<span data-ttu-id="b2cd0-136">Opciones de F #</span><span class="sxs-lookup"><span data-stu-id="b2cd0-136">F# Options</span></span>](options.md)
