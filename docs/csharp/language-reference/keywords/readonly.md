---
title: readonly (palabra clave) - Referencia de C#
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 4a51bb0e854de127c632c28f613a7602bf09f432
ms.sourcegitcommit: 127343afce8422bfa944c8b0c4ecc8f79f653255
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "67348013"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="71e89-102">readonly (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="71e89-102">readonly (C# Reference)</span></span>

<span data-ttu-id="71e89-103">La palabra clave `readonly` es un modificador que se puede usar en tres contextos:</span><span class="sxs-lookup"><span data-stu-id="71e89-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="71e89-104">En una [declaración de campo](#readonly-field-example), `readonly` indica que la asignación a un campo solo se puede producir como parte de la declaración o en un constructor de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="71e89-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="71e89-105">Se puede asignar y reasignar varias veces un campo de solo lectura dentro de la declaración de campo y el constructor.</span><span class="sxs-lookup"><span data-stu-id="71e89-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> 
  
  <span data-ttu-id="71e89-106">No se puede asignar un campo `readonly` después de que el constructor salga.</span><span class="sxs-lookup"><span data-stu-id="71e89-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="71e89-107">Tiene diferentes implicaciones para los tipos de valor y tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="71e89-107">That has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="71e89-108">Debido a que los tipos de valor contienen directamente sus datos, un campo que es un tipo de valor `readonly` es inmutable.</span><span class="sxs-lookup"><span data-stu-id="71e89-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
  - <span data-ttu-id="71e89-109">Dado que los tipos de referencia contienen una referencia a sus datos, un campo que es un tipo de referencia `readonly` debe referirse siempre al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="71e89-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="71e89-110">Ese objeto no es inmutable.</span><span class="sxs-lookup"><span data-stu-id="71e89-110">That object is not immutable.</span></span> <span data-ttu-id="71e89-111">El modificador `readonly` evita que el campo se reemplace por una instancia diferente del tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="71e89-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="71e89-112">Sin embargo, el modificador no impide que los datos de instancia del campo se modifiquen a través del campo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="71e89-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="71e89-113">Un tipo visible externamente que contenga un campo de solo lectura visible externamente que sea un tipo de referencia mutable puede ser una vulnerabilidad de seguridad y puede desencadenar la advertencia [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types): "No declarar tipos de referencias mutables de solo lectura".</span><span class="sxs-lookup"><span data-stu-id="71e89-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="71e89-114">En una [definición de `readonly struct`](#readonly-struct-example), `readonly` indica que `struct` es inmutable.</span><span class="sxs-lookup"><span data-stu-id="71e89-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="71e89-115">En una [devolución del método `ref readonly`](#ref-readonly-return-example), el modificador `readonly` indica que el método devuelve una referencia y las operaciones de escritura no se permiten en esa referencia.</span><span class="sxs-lookup"><span data-stu-id="71e89-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="71e89-116">Los dos contextos finales se agregaron en C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="71e89-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="71e89-117">Ejemplo de campo readonly</span><span class="sxs-lookup"><span data-stu-id="71e89-117">Readonly field example</span></span>

<span data-ttu-id="71e89-118">En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:</span><span class="sxs-lookup"><span data-stu-id="71e89-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="71e89-119">Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="71e89-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="71e89-120">Cuando la variable se inicializa en la declaración, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71e89-120">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="71e89-121">En un constructor de instancia de la clase que contiene la declaración de campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="71e89-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="71e89-122">En el constructor estático de la clase que contiene la declaración de campo estático.</span><span class="sxs-lookup"><span data-stu-id="71e89-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="71e89-123">Estos contextos de constructor son también los únicos en los que es válido pasar un campo `readonly` como parámetro [out](out-parameter-modifier.md) o [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="71e89-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="71e89-124">La palabra clave `readonly` es diferente de la palabra clave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="71e89-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="71e89-125">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="71e89-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="71e89-126">Un campo `readonly` se puede asignar varias veces en la declaración de campo y en cualquier constructor.</span><span class="sxs-lookup"><span data-stu-id="71e89-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="71e89-127">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="71e89-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="71e89-128">Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="71e89-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="71e89-129">En el ejemplo anterior, si se usa una instrucción como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="71e89-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="71e89-130">se obtendrá el siguiente mensaje de error del compilador:</span><span class="sxs-lookup"><span data-stu-id="71e89-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="71e89-131">Ejemplo de estructura de solo lectura</span><span class="sxs-lookup"><span data-stu-id="71e89-131">Readonly struct example</span></span>

<span data-ttu-id="71e89-132">El modificador `readonly` en una definición `struct` declara que la estructura es **inmutable**.</span><span class="sxs-lookup"><span data-stu-id="71e89-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="71e89-133">Todos los campos de instancia de `struct` se deben marcar como `readonly`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="71e89-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="71e89-134">En el ejemplo anterior se usan [propiedades automáticas de solo lectura](../../properties.md#read-only) para declarar su almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="71e89-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="71e89-135">Eso indica al compilador que cree campos de respaldo `readonly` para esas propiedades.</span><span class="sxs-lookup"><span data-stu-id="71e89-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="71e89-136">También se podrían declarar campos `readonly` directamente:</span><span class="sxs-lookup"><span data-stu-id="71e89-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="71e89-137">La adición de un campo no marcado `readonly` genera el error del compilador `CS8340`: "Los campos de instancia de las estructuras readonly deben ser readonly".</span><span class="sxs-lookup"><span data-stu-id="71e89-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="71e89-138">Ejemplo de devolución de Ref readonly</span><span class="sxs-lookup"><span data-stu-id="71e89-138">Ref readonly return example</span></span>

<span data-ttu-id="71e89-139">El modificador `readonly` en una `ref return` indica que la referencia devuelta no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="71e89-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="71e89-140">En el ejemplo siguiente se devuelve una referencia al origen.</span><span class="sxs-lookup"><span data-stu-id="71e89-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="71e89-141">Usa el modificador `readonly` para indicar que los autores de la llamada no pueden modificar el origen:</span><span class="sxs-lookup"><span data-stu-id="71e89-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="71e89-142">No es necesario que el tipo devuelto sea una `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="71e89-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="71e89-143">Cualquier tipo que pueda devolver `ref` también puede devolver `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="71e89-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="71e89-144">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="71e89-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="71e89-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="71e89-145">See also</span></span>

- [<span data-ttu-id="71e89-146">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="71e89-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="71e89-147">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="71e89-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="71e89-148">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="71e89-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="71e89-149">Modificadores</span><span class="sxs-lookup"><span data-stu-id="71e89-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="71e89-150">const</span><span class="sxs-lookup"><span data-stu-id="71e89-150">const</span></span>](const.md)
- [<span data-ttu-id="71e89-151">Campos</span><span class="sxs-lookup"><span data-stu-id="71e89-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
