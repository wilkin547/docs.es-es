---
title: Palabra clave readonly (Referencia de C#)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d09ce4ea972a3064298eebdf0b8b80999ee8441e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397548"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="d92b4-102">readonly (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d92b4-102">readonly (C# Reference)</span></span>

<span data-ttu-id="d92b4-103">La palabra clave `readonly` es un modificador que se puede usar en tres contextos:</span><span class="sxs-lookup"><span data-stu-id="d92b4-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="d92b4-104">En una [declaración de campo](#readonly-field-example), `readonly` indica que la asignación a un campo solo se puede producir como parte de la declaración o en un constructor de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="d92b4-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span>
- <span data-ttu-id="d92b4-105">En una [definición de `readonly struct`](#readonly-struct-example), `readonly` indica que `struct` es inmutable.</span><span class="sxs-lookup"><span data-stu-id="d92b4-105">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="d92b4-106">En una [devolución del método `ref readonly`](#ref-readonly-return-example), el modificador `readonly` indica que el método devuelve una referencia y las operaciones de escritura no se permiten en esa referencia.</span><span class="sxs-lookup"><span data-stu-id="d92b4-106">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="d92b4-107">Los dos contextos finales se agregaron en C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="d92b4-107">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="d92b4-108">Ejemplo de campo readonly</span><span class="sxs-lookup"><span data-stu-id="d92b4-108">Readonly field example</span></span>

<span data-ttu-id="d92b4-109">En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:</span><span class="sxs-lookup"><span data-stu-id="d92b4-109">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="d92b4-110">Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="d92b4-110">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="d92b4-111">Cuando la variable se inicializa en la declaración, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d92b4-111">When the variable is initialized in the declaration, for example:</span></span>

```csharp
public readonly int y = 5;
```

- <span data-ttu-id="d92b4-112">En un constructor de instancia de la clase que contiene la declaración de campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="d92b4-112">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="d92b4-113">En el constructor estático de la clase que contiene la declaración de campo estático.</span><span class="sxs-lookup"><span data-stu-id="d92b4-113">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="d92b4-114">Estos contextos de constructor son también los únicos en los que es válido pasar un campo `readonly` como parámetro [out](out-parameter-modifier.md) o [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="d92b4-114">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="d92b4-115">La palabra clave `readonly` es diferente de la palabra clave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="d92b4-115">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="d92b4-116">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="d92b4-116">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="d92b4-117">Un campo `readonly` se puede inicializar en la declaración o en un constructor.</span><span class="sxs-lookup"><span data-stu-id="d92b4-117">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="d92b4-118">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="d92b4-118">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="d92b4-119">Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d92b4-119">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="d92b4-120">En el ejemplo anterior, si se usa una instrucción como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d92b4-120">In the preceding example, if you use a statement like the following example:</span></span>

`p2.y = 66;        // Error`

<span data-ttu-id="d92b4-121">se obtendrá el siguiente mensaje de error del compilador:</span><span class="sxs-lookup"><span data-stu-id="d92b4-121">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="d92b4-122">Ejemplo de estructura de solo lectura</span><span class="sxs-lookup"><span data-stu-id="d92b4-122">Readonly struct example</span></span>

<span data-ttu-id="d92b4-123">El modificador `readonly` en una definición `struct` declara que la estructura es **inmutable**.</span><span class="sxs-lookup"><span data-stu-id="d92b4-123">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="d92b4-124">Todos los campos de instancia de `struct` se deben marcar como `readonly`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d92b4-124">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="d92b4-125">En el ejemplo anterior se usan [propiedades automáticas de solo lectura](../../properties.md#read-only) para declarar su almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d92b4-125">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="d92b4-126">Eso indica al compilador que cree campos de respaldo `readonly` para esas propiedades.</span><span class="sxs-lookup"><span data-stu-id="d92b4-126">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="d92b4-127">También se podrían declarar campos `readonly` directamente:</span><span class="sxs-lookup"><span data-stu-id="d92b4-127">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="d92b4-128">La adición de un campo `readonly` no marcado genera el error del compilador `CS8340`: "Los campos de instancia de las estructuras readonly deben ser readonly".</span><span class="sxs-lookup"><span data-stu-id="d92b4-128">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="d92b4-129">Ejemplo de devolución de Ref readonly</span><span class="sxs-lookup"><span data-stu-id="d92b4-129">Ref readonly return example</span></span>

<span data-ttu-id="d92b4-130">El modificador `readonly` en una `ref return` indica que la referencia devuelta no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="d92b4-130">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="d92b4-131">En el ejemplo siguiente se devuelve una referencia al origen.</span><span class="sxs-lookup"><span data-stu-id="d92b4-131">The following example returns a reference to the origin.</span></span> <span data-ttu-id="d92b4-132">Usa el modificador `readonly` para indicar que los autores de la llamada no pueden modificar el origen:</span><span class="sxs-lookup"><span data-stu-id="d92b4-132">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="d92b4-133">No es necesario que el tipo devuelto sea una `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="d92b4-133">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="d92b4-134">Cualquier tipo que `ref` pueda devolver `ref readonly` también puede devolver.</span><span class="sxs-lookup"><span data-stu-id="d92b4-134">Any type that can be returned by `ref` can be returned by `ref readonly`</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d92b4-135">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d92b4-135">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="d92b4-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d92b4-136">See also</span></span>

- [<span data-ttu-id="d92b4-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d92b4-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d92b4-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d92b4-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d92b4-139">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="d92b4-139">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d92b4-140">Modificadores</span><span class="sxs-lookup"><span data-stu-id="d92b4-140">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="d92b4-141">const</span><span class="sxs-lookup"><span data-stu-id="d92b4-141">const</span></span>](const.md)
- [<span data-ttu-id="d92b4-142">Campos</span><span class="sxs-lookup"><span data-stu-id="d92b4-142">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
