---
title: readonly (palabra clave) - Referencia de C#
ms.date: 03/26/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 344d5e54fcd500e283c52fa7953c6366823f13f0
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345147"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="39699-102">readonly (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="39699-102">readonly (C# Reference)</span></span>

<span data-ttu-id="39699-103">La palabra clave `readonly` es un modificador que se puede usar en cuatro contextos:</span><span class="sxs-lookup"><span data-stu-id="39699-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="39699-104">En una [declaración de campo](#readonly-field-example), `readonly` indica que la asignación a un campo solo se puede producir como parte de la declaración o en un constructor de la misma clase.</span><span class="sxs-lookup"><span data-stu-id="39699-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="39699-105">Se puede asignar y reasignar varias veces un campo de solo lectura dentro de la declaración de campo y el constructor.</span><span class="sxs-lookup"><span data-stu-id="39699-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="39699-106">No se puede asignar un campo `readonly` después de que el constructor salga.</span><span class="sxs-lookup"><span data-stu-id="39699-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="39699-107">Esta regla tiene diferentes implicaciones para los tipos de valor y tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="39699-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="39699-108">Debido a que los tipos de valor contienen directamente sus datos, un campo que es un tipo de valor `readonly` es inmutable.</span><span class="sxs-lookup"><span data-stu-id="39699-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="39699-109">Dado que los tipos de referencia contienen una referencia a sus datos, un campo que es un tipo de referencia `readonly` debe referirse siempre al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="39699-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="39699-110">Ese objeto no es inmutable.</span><span class="sxs-lookup"><span data-stu-id="39699-110">That object isn't immutable.</span></span> <span data-ttu-id="39699-111">El modificador `readonly` evita que el campo se reemplace por una instancia diferente del tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="39699-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="39699-112">Sin embargo, el modificador no impide que los datos de instancia del campo se modifiquen a través del campo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="39699-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="39699-113">Un tipo visible externamente que contenga un campo de solo lectura visible externamente que sea un tipo de referencia mutable puede ser una vulnerabilidad de seguridad y puede desencadenar la advertencia [CA2104](/visualstudio/code-quality/ca2104): "No declarar tipos de referencias mutables de solo lectura".</span><span class="sxs-lookup"><span data-stu-id="39699-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="39699-114">En una definición de tipo de `readonly struct`, `readonly` indica que el tipo de estructura es inmutable.</span><span class="sxs-lookup"><span data-stu-id="39699-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="39699-115">Para obtener más información, vea la sección [ struct `readonly`](../builtin-types/struct.md#readonly-struct) del artículo [tipos de estructura](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="39699-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="39699-116">En un [miembro de definición `readonly`](#readonly-member-examples), `readonly` indica que un miembro de un elemento `struct` no mutará el estado interno de la estructura.</span><span class="sxs-lookup"><span data-stu-id="39699-116">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="39699-117">En una [devolución del método `ref readonly`](#ref-readonly-return-example), el modificador `readonly` indica que el método devuelve una referencia y las operaciones de escritura no se permiten en esa referencia.</span><span class="sxs-lookup"><span data-stu-id="39699-117">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="39699-118">Los contextos `readonly struct` y `ref readonly` se han agregado en C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="39699-118">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="39699-119">Los miembros de estructura `readonly` se han agregado en C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="39699-119">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="39699-120">Ejemplo de campo readonly</span><span class="sxs-lookup"><span data-stu-id="39699-120">Readonly field example</span></span>

<span data-ttu-id="39699-121">En este ejemplo, el valor del campo `year` no se puede cambiar en el método `ChangeYear`, aunque se asigne un valor en el constructor de clase:</span><span class="sxs-lookup"><span data-stu-id="39699-121">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="39699-122">Solo se puede asignar un valor a un campo `readonly` en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="39699-122">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="39699-123">Cuando la variable se inicializa en la declaración, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39699-123">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="39699-124">En un constructor de instancia de la clase que contiene la declaración de campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="39699-124">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="39699-125">En el constructor estático de la clase que contiene la declaración de campo estático.</span><span class="sxs-lookup"><span data-stu-id="39699-125">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="39699-126">Estos contextos de constructor son también los únicos en los que es válido pasar un campo `readonly` como parámetro [out](out-parameter-modifier.md) o [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="39699-126">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="39699-127">La palabra clave `readonly` es diferente de la palabra clave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="39699-127">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="39699-128">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="39699-128">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="39699-129">Un campo `readonly` se puede asignar varias veces en la declaración de campo y en cualquier constructor.</span><span class="sxs-lookup"><span data-stu-id="39699-129">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="39699-130">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="39699-130">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="39699-131">Además, mientras que un campo `const` es una constante en tiempo de compilación, el campo `readonly` puede usarse para constantes en tiempo de ejecución, como muestra el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39699-131">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="39699-132">En el ejemplo anterior, si se usa una instrucción como el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39699-132">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="39699-133">se obtendrá el siguiente mensaje de error del compilador:</span><span class="sxs-lookup"><span data-stu-id="39699-133">you'll get the compiler error message:</span></span>

<span data-ttu-id="39699-134">**No se puede asignar un campo de solo lectura (excepto en un constructor o inicializador de variable)** .</span><span class="sxs-lookup"><span data-stu-id="39699-134">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="39699-135">Ejemplos de miembros de solo lectura</span><span class="sxs-lookup"><span data-stu-id="39699-135">Readonly member examples</span></span>

<span data-ttu-id="39699-136">Otras veces, se puede crear una estructura que admita la mutación.</span><span class="sxs-lookup"><span data-stu-id="39699-136">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="39699-137">En esos casos, es probable que algunos de los miembros de instancia no modifiquen el estado interno de la estructura.</span><span class="sxs-lookup"><span data-stu-id="39699-137">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="39699-138">Se pueden declarar esos miembros de instancia con el modificador `readonly`.</span><span class="sxs-lookup"><span data-stu-id="39699-138">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="39699-139">El compilador aplica su intención.</span><span class="sxs-lookup"><span data-stu-id="39699-139">The compiler enforces your intent.</span></span> <span data-ttu-id="39699-140">Si ese miembro modifica el estado directamente o tiene acceso a un miembro que no se declara tampoco con el modificador `readonly`, el resultado es un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="39699-140">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="39699-141">El modificador `readonly` es válido en miembros de `struct`, no en declaraciones de miembros de `class` o `interface`.</span><span class="sxs-lookup"><span data-stu-id="39699-141">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="39699-142">Para obtener dos ventajas, aplique el modificador `readonly` a los métodos `struct` aplicables.</span><span class="sxs-lookup"><span data-stu-id="39699-142">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="39699-143">Lo más importante es que el compilador aplique su intención.</span><span class="sxs-lookup"><span data-stu-id="39699-143">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="39699-144">El código que modifica el estado no es válido en un método `readonly`.</span><span class="sxs-lookup"><span data-stu-id="39699-144">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="39699-145">El compilador también puede usar el modificador `readonly` para habilitar las optimizaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="39699-145">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="39699-146">Cuando la referencia `in` pasa tipos de `struct` grandes, el compilador debe generar una copia defensiva si se puede modificar el estado de la estructura.</span><span class="sxs-lookup"><span data-stu-id="39699-146">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="39699-147">Si solo se tiene acceso a los miembros de `readonly`, es posible que el compilador no cree la copia defensiva.</span><span class="sxs-lookup"><span data-stu-id="39699-147">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="39699-148">El modificador `readonly` es válido en la mayoría de miembros de un elemento `struct`, incluidos los métodos que invalidan los métodos declarados en <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="39699-148">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="39699-149">Existen algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="39699-149">There are some restrictions:</span></span>

- <span data-ttu-id="39699-150">No se pueden declarar propiedades o métodos estáticos `readonly`.</span><span class="sxs-lookup"><span data-stu-id="39699-150">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="39699-151">No se pueden declarar constructores `readonly`.</span><span class="sxs-lookup"><span data-stu-id="39699-151">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="39699-152">Puede Agregar el modificador `readonly` a una declaración de propiedad o de indizador:</span><span class="sxs-lookup"><span data-stu-id="39699-152">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="39699-153">También puede agregar el modificador `readonly` a los descriptores de acceso individuales `get` o `set` de una propiedad o indizador:</span><span class="sxs-lookup"><span data-stu-id="39699-153">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="39699-154">No se puede Agregar el modificador `readonly` a una propiedad y a uno o varios de los descriptores de acceso de esa misma propiedad.</span><span class="sxs-lookup"><span data-stu-id="39699-154">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="39699-155">Esa misma restricción se aplica a los indizadores.</span><span class="sxs-lookup"><span data-stu-id="39699-155">That same restriction applies to indexers.</span></span>

<span data-ttu-id="39699-156">El compilador aplica implícitamente el modificador `readonly` a las propiedades implementadas automáticamente donde el código implementado por el compilador no modifica el estado.</span><span class="sxs-lookup"><span data-stu-id="39699-156">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="39699-157">Es equivalente a las declaraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="39699-157">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

<span data-ttu-id="39699-158">Se puede agregar el modificador `readonly` en esas ubicaciones, pero esta acción no tendrá ningún efecto significativo.</span><span class="sxs-lookup"><span data-stu-id="39699-158">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="39699-159">No se puede agregar el modificador `readonly` a un establecedor de propiedad implementado automáticamente o a una propiedad implementada automáticamente de lectura o escritura.</span><span class="sxs-lookup"><span data-stu-id="39699-159">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="39699-160">Ejemplo de devolución de Ref readonly</span><span class="sxs-lookup"><span data-stu-id="39699-160">Ref readonly return example</span></span>

<span data-ttu-id="39699-161">El modificador `readonly` en un elemento `ref return` indica que la referencia devuelta no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="39699-161">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="39699-162">En el ejemplo siguiente se devuelve una referencia al origen.</span><span class="sxs-lookup"><span data-stu-id="39699-162">The following example returns a reference to the origin.</span></span> <span data-ttu-id="39699-163">Usa el modificador `readonly` para indicar que los autores de la llamada no pueden modificar el origen:</span><span class="sxs-lookup"><span data-stu-id="39699-163">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="39699-164">No es necesario que el tipo devuelto sea una `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="39699-164">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="39699-165">Cualquier tipo que pueda devolver `ref` también puede devolver `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="39699-165">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="39699-166">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="39699-166">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="39699-167">También puede ver las propuestas de especificación del lenguaje:</span><span class="sxs-lookup"><span data-stu-id="39699-167">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="39699-168">referencia de solo lectura y estructura de solo lectura</span><span class="sxs-lookup"><span data-stu-id="39699-168">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="39699-169">miembros de estructura de solo lectura</span><span class="sxs-lookup"><span data-stu-id="39699-169">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="39699-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="39699-170">See also</span></span>

- [<span data-ttu-id="39699-171">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="39699-171">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39699-172">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="39699-172">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39699-173">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="39699-173">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="39699-174">Modificadores</span><span class="sxs-lookup"><span data-stu-id="39699-174">Modifiers</span></span>](index.md)
- [<span data-ttu-id="39699-175">const</span><span class="sxs-lookup"><span data-stu-id="39699-175">const</span></span>](const.md)
- [<span data-ttu-id="39699-176">Campos</span><span class="sxs-lookup"><span data-stu-id="39699-176">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
