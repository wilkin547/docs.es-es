---
title: readonly (palabra clave) - Referencia de C#
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 66a096e8831f72a2216e8ba5dd9866046504624f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368626"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="585bc-102">readonly (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="585bc-102">readonly (C# Reference)</span></span>

<span data-ttu-id="585bc-103">La palabra clave `readonly` es un modificador que se puede usar en cuatro contextos:</span><span class="sxs-lookup"><span data-stu-id="585bc-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="585bc-104">En una [declaración de campo](#readonly-field-example), `readonly` indica que la asignación a un campo solo se puede producir como parte de la declaración o en un constructor de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="585bc-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="585bc-105">Se puede asignar y reasignar varias veces un campo de solo lectura dentro de la declaración de campo y el constructor.</span><span class="sxs-lookup"><span data-stu-id="585bc-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="585bc-106">No se puede asignar un campo `readonly` después de que el constructor salga.</span><span class="sxs-lookup"><span data-stu-id="585bc-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="585bc-107">Esta regla tiene diferentes implicaciones para los tipos de valor y tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="585bc-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="585bc-108">Debido a que los tipos de valor contienen directamente sus datos, un campo que es un tipo de valor `readonly` es inmutable.</span><span class="sxs-lookup"><span data-stu-id="585bc-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="585bc-109">Dado que los tipos de referencia contienen una referencia a sus datos, un campo que es un tipo de referencia `readonly` debe referirse siempre al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="585bc-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="585bc-110">Ese objeto no es inmutable.</span><span class="sxs-lookup"><span data-stu-id="585bc-110">That object isn't immutable.</span></span> <span data-ttu-id="585bc-111">El modificador `readonly` evita que el campo se reemplace por una instancia diferente del tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="585bc-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="585bc-112">Sin embargo, el modificador no impide que los datos de instancia del campo se modifiquen a través del campo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="585bc-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="585bc-113">Un tipo visible externamente que contenga un campo de solo lectura visible externamente que sea un tipo de referencia mutable puede ser una vulnerabilidad de seguridad y puede desencadenar la advertencia [CA2104](/visualstudio/code-quality/ca2104): "No declarar tipos de referencias mutables de solo lectura".</span><span class="sxs-lookup"><span data-stu-id="585bc-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="585bc-114">En una definición de tipo de `readonly struct`, `readonly` indica que el tipo de estructura es inmutable.</span><span class="sxs-lookup"><span data-stu-id="585bc-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="585bc-115">Para obtener más información, vea la sección [ struct `readonly`](../builtin-types/struct.md#readonly-struct) del artículo [tipos de estructura](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="585bc-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="585bc-116">En una declaración de miembro de instancia dentro de un tipo de estructura, `readonly` indica que un miembro de instancia no modifica el estado de la estructura.</span><span class="sxs-lookup"><span data-stu-id="585bc-116">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="585bc-117">Para obtener más información, vea la sección [Miembros de instancia `readonly`](../builtin-types/struct.md#readonly-instance-members) del artículo [Tipos de estructura](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="585bc-117">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="585bc-118">En una [devolución del método `ref readonly`](#ref-readonly-return-example), el modificador `readonly` indica que el método devuelve una referencia y las operaciones de escritura no se permiten en esa referencia.</span><span class="sxs-lookup"><span data-stu-id="585bc-118">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="585bc-119">Los contextos `readonly struct` y `ref readonly` se han agregado en C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="585bc-119">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="585bc-120">Los miembros de estructura `readonly` se han agregado en C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="585bc-120">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="585bc-121">Ejemplo de campo readonly</span><span class="sxs-lookup"><span data-stu-id="585bc-121">Readonly field example</span></span>

<span data-ttu-id="585bc-122">En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:</span><span class="sxs-lookup"><span data-stu-id="585bc-122">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="585bc-123">Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="585bc-123">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="585bc-124">Cuando la variable se inicializa en la declaración, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="585bc-124">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="585bc-125">En un constructor de instancia de la clase que contiene la declaración de campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="585bc-125">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="585bc-126">En el constructor estático de la clase que contiene la declaración de campo estático.</span><span class="sxs-lookup"><span data-stu-id="585bc-126">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="585bc-127">Estos contextos de constructor son también los únicos en los que es válido pasar un campo `readonly` como parámetro [out](out-parameter-modifier.md) o [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="585bc-127">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="585bc-128">La palabra clave `readonly` es diferente de la palabra clave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="585bc-128">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="585bc-129">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="585bc-129">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="585bc-130">Un campo `readonly` se puede asignar varias veces en la declaración de campo y en cualquier constructor.</span><span class="sxs-lookup"><span data-stu-id="585bc-130">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="585bc-131">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="585bc-131">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="585bc-132">Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="585bc-132">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="585bc-133">En el ejemplo anterior, si se usa una instrucción como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="585bc-133">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="585bc-134">se obtendrá el siguiente mensaje de error del compilador:</span><span class="sxs-lookup"><span data-stu-id="585bc-134">you'll get the compiler error message:</span></span>

<span data-ttu-id="585bc-135">**No se puede asignar un campo de solo lectura (excepto en un constructor o inicializador de variable)** .</span><span class="sxs-lookup"><span data-stu-id="585bc-135">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="585bc-136">Ejemplo de devolución de Ref readonly</span><span class="sxs-lookup"><span data-stu-id="585bc-136">Ref readonly return example</span></span>

<span data-ttu-id="585bc-137">El modificador `readonly` en un elemento `ref return` indica que la referencia devuelta no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="585bc-137">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="585bc-138">En el ejemplo siguiente se devuelve una referencia al origen.</span><span class="sxs-lookup"><span data-stu-id="585bc-138">The following example returns a reference to the origin.</span></span> <span data-ttu-id="585bc-139">Usa el modificador `readonly` para indicar que los autores de la llamada no pueden modificar el origen:</span><span class="sxs-lookup"><span data-stu-id="585bc-139">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="585bc-140">No es necesario que el tipo devuelto sea una `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="585bc-140">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="585bc-141">Cualquier tipo que pueda devolver `ref` también puede devolver `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="585bc-141">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="585bc-142">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="585bc-142">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="585bc-143">También puede ver las propuestas de especificación del lenguaje:</span><span class="sxs-lookup"><span data-stu-id="585bc-143">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="585bc-144">referencia de solo lectura y estructura de solo lectura</span><span class="sxs-lookup"><span data-stu-id="585bc-144">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="585bc-145">miembros de estructura de solo lectura</span><span class="sxs-lookup"><span data-stu-id="585bc-145">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="585bc-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="585bc-146">See also</span></span>

- [<span data-ttu-id="585bc-147">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="585bc-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="585bc-148">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="585bc-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="585bc-149">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="585bc-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="585bc-150">Modificadores</span><span class="sxs-lookup"><span data-stu-id="585bc-150">Modifiers</span></span>](index.md)
- [<span data-ttu-id="585bc-151">const</span><span class="sxs-lookup"><span data-stu-id="585bc-151">const</span></span>](const.md)
- [<span data-ttu-id="585bc-152">Campos</span><span class="sxs-lookup"><span data-stu-id="585bc-152">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
