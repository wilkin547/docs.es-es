---
title: 'Registros: Guía de programación de C#'
description: Obtenga información sobre los tipos de registros y cómo crearlos
ms.date: 02/26/2021
helpviewer_keywords:
- records [C#]
- C# language, records
ms.openlocfilehash: a45ed08da18e58f11793d6874d7275d9f5216be4
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102260043"
---
# <a name="records-c-programming-guide"></a><span data-ttu-id="d57f6-103">Registros (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d57f6-103">Records (C# Programming Guide)</span></span>

<span data-ttu-id="d57f6-104">Un [registro](../../language-reference/builtin-types/record.md) es una [clase](../../language-reference/keywords/class.md) que proporciona sintaxis y comportamiento especiales para trabajar con modelos de datos.</span><span class="sxs-lookup"><span data-stu-id="d57f6-104">A [record](../../language-reference/builtin-types/record.md) is a [class](../../language-reference/keywords/class.md) that provides special syntax and behavior for working with data models.</span></span> <span data-ttu-id="d57f6-105">Para obtener más información sobre las clases, consulte [Clases (Guía de programación de C#)](classes.md).</span><span class="sxs-lookup"><span data-stu-id="d57f6-105">For information about classes, see [Classes (C# Programming Guide)](classes.md).</span></span>

## <a name="when-to-use-records"></a><span data-ttu-id="d57f6-106">Cuándo se usan los registros</span><span class="sxs-lookup"><span data-stu-id="d57f6-106">When to use records</span></span>

<span data-ttu-id="d57f6-107">Considere la posibilidad de usar un registro en lugar de una clase en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="d57f6-107">Consider using a record in place of a class in the following scenarios:</span></span>

* <span data-ttu-id="d57f6-108">Desea definir un tipo de referencia para el que los objetos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="d57f6-108">You want to define a reference type for which objects are immutable.</span></span>
* <span data-ttu-id="d57f6-109">Desea definir un modelo de datos que dependa de la [igualdad de valores](../statements-expressions-operators/equality-comparisons.md#value-equality).</span><span class="sxs-lookup"><span data-stu-id="d57f6-109">You want to define a data model that depends on [value equality](../statements-expressions-operators/equality-comparisons.md#value-equality).</span></span>

### <a name="immutability"></a><span data-ttu-id="d57f6-110">Inmutabilidad</span><span class="sxs-lookup"><span data-stu-id="d57f6-110">Immutability</span></span>

<span data-ttu-id="d57f6-111">Un tipo inmutable es aquél que impide cambiar cualquier valor de propiedad o campo de un objeto una vez creada su instancia.</span><span class="sxs-lookup"><span data-stu-id="d57f6-111">An immutable type is one that prevents you from changing any property or field values of an object after it's instantiated.</span></span> <span data-ttu-id="d57f6-112">La inmutabilidad puede ser útil cuando se necesita que un tipo sea seguro para los subprocesos o si depende de que un código hash quede igual en una tabla hash.</span><span class="sxs-lookup"><span data-stu-id="d57f6-112">Immutability can be useful when you need a type to be thread-safe or you're depending on a hash code remaining the same in a hash table.</span></span> <span data-ttu-id="d57f6-113">Los registros proporcionan una sintaxis concisa para crear y trabajar con tipos inmutables.</span><span class="sxs-lookup"><span data-stu-id="d57f6-113">Records provide concise syntax for creating and working with immutable types.</span></span>

<span data-ttu-id="d57f6-114">La inmutabilidad no es adecuada para todos los escenarios de datos.</span><span class="sxs-lookup"><span data-stu-id="d57f6-114">Immutability isn't appropriate for all data scenarios.</span></span> <span data-ttu-id="d57f6-115">Por ejemplo, [Entity Framework Core](/ef/core/) no admite la actualización con tipos de entidad inmutables.</span><span class="sxs-lookup"><span data-stu-id="d57f6-115">[Entity Framework Core](/ef/core/), for example, doesn't support updating with immutable entity types.</span></span>

### <a name="value-equality"></a><span data-ttu-id="d57f6-116">Igualdad de valores</span><span class="sxs-lookup"><span data-stu-id="d57f6-116">Value equality</span></span>

<span data-ttu-id="d57f6-117">En el caso de los registros, la igualdad de valores significa que dos variables de un tipo de registro son iguales si los tipos coinciden y todos los valores de propiedad y campo coinciden.</span><span class="sxs-lookup"><span data-stu-id="d57f6-117">For records, value equality means that two variables of a record type are equal if the types match and all property and field values match.</span></span> <span data-ttu-id="d57f6-118">Para otros tipos de referencia, como las clases, la igualdad significa [igualdad de referencias](../statements-expressions-operators/equality-comparisons.md#reference-equality).</span><span class="sxs-lookup"><span data-stu-id="d57f6-118">For other reference types such as classes, equality means [reference equality](../statements-expressions-operators/equality-comparisons.md#reference-equality).</span></span> <span data-ttu-id="d57f6-119">Es decir, dos variables de un tipo de clase son iguales si hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="d57f6-119">That is, two variables of a class type are equal if they refer to the same object.</span></span> <span data-ttu-id="d57f6-120">Los métodos y operadores que determinan la igualdad de dos instancias de registro usan la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="d57f6-120">Methods and operators that determine equality of two record instances use value equality.</span></span>

<span data-ttu-id="d57f6-121">No todos los modelos de datos funcionan bien con la igualdad de valores.</span><span class="sxs-lookup"><span data-stu-id="d57f6-121">Not all data models work well with value equality.</span></span> <span data-ttu-id="d57f6-122">Por ejemplo, [Entity Framework Core](/ef/core/) depende de la igualdad de referencias para garantizar que solo usa una instancia de un tipo de entidad para lo que es conceptualmente una entidad.</span><span class="sxs-lookup"><span data-stu-id="d57f6-122">For example, [Entity Framework Core](/ef/core/) depends on reference equality to ensure that it uses only one instance of an entity type for what is conceptually one entity.</span></span> <span data-ttu-id="d57f6-123">Por esta razón, los tipos de registro no son adecuados para su uso como tipos de entidad en Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="d57f6-123">For this reason, record types aren't appropriate for use as entity types in Entity Framework Core.</span></span>

## <a name="how-records-differ-from-classes"></a><span data-ttu-id="d57f6-124">Diferencias entre los registros y las clases</span><span class="sxs-lookup"><span data-stu-id="d57f6-124">How records differ from classes</span></span>

<span data-ttu-id="d57f6-125">La misma sintaxis que [declara](classes.md#declaring-classes) y [crea instancias](classes.md#creating-objects) de clases se puede usar con los registros.</span><span class="sxs-lookup"><span data-stu-id="d57f6-125">The same syntax that [declares](classes.md#declaring-classes) and [instantiates](classes.md#creating-objects) classes can be used with records.</span></span> <span data-ttu-id="d57f6-126">Basta con sustituir la palabra clave `record` por la palabra clave `class`.</span><span class="sxs-lookup"><span data-stu-id="d57f6-126">Just substitute the `record` keyword for the `class` keyword.</span></span> <span data-ttu-id="d57f6-127">Del mismo modo, los registros admiten la misma sintaxis para expresar las relaciones de herencia.</span><span class="sxs-lookup"><span data-stu-id="d57f6-127">Likewise, the same syntax for expressing inheritance relationships is supported by records.</span></span> <span data-ttu-id="d57f6-128">Los registros se diferencian de las clases de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="d57f6-128">Records differ from classes in the following ways:</span></span>

* <span data-ttu-id="d57f6-129">Puede usar [parámetros posicionales](../../language-reference/builtin-types/record.md#positional-syntax-for-property-definition) para crear un tipo y sus instancias con propiedades inmutables.</span><span class="sxs-lookup"><span data-stu-id="d57f6-129">You can use [positional parameters](../../language-reference/builtin-types/record.md#positional-syntax-for-property-definition) to create and instantiate a type with immutable properties.</span></span>
* <span data-ttu-id="d57f6-130">Los mismos métodos y operadores que indican la igualdad o desigualdad de la referencia en las clases (como <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> y `==`), indican la [igualdad o desigualdad de valores](../../language-reference/builtin-types/record.md#value-equality) en los registros.</span><span class="sxs-lookup"><span data-stu-id="d57f6-130">The same methods and operators that indicate reference equality or inequality in classes (such as <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> and `==`), indicate [value equality or inequality](../../language-reference/builtin-types/record.md#value-equality) in records.</span></span>
* <span data-ttu-id="d57f6-131">Puede usar una [expresión `with`](../../language-reference/builtin-types/record.md#nondestructive-mutation) para crear una copia de un objeto inmutable con nuevos valores en las propiedades seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d57f6-131">You can use a [`with` expression](../../language-reference/builtin-types/record.md#nondestructive-mutation) to create a copy of an immutable object with new values in selected properties.</span></span>
* <span data-ttu-id="d57f6-132">El método `ToString` de un registro crea una cadena con formato que muestra el nombre de tipo de un objeto y los nombres y valores de todas sus propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="d57f6-132">A record's `ToString` method creates a formatted string that shows an object's type name and the names and values of all its public properties.</span></span>
* <span data-ttu-id="d57f6-133">Un registro puede [heredar de otro registro](../../language-reference/builtin-types/record.md#inheritance).</span><span class="sxs-lookup"><span data-stu-id="d57f6-133">A record can [inherit from another record](../../language-reference/builtin-types/record.md#inheritance).</span></span> <span data-ttu-id="d57f6-134">Un registro no puede heredar de una clase y una clase no puede heredar de un registro.</span><span class="sxs-lookup"><span data-stu-id="d57f6-134">A record can't inherit from a class, and a class can't inherit from a record.</span></span>

## <a name="examples"></a><span data-ttu-id="d57f6-135">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d57f6-135">Examples</span></span>

<span data-ttu-id="d57f6-136">En el ejemplo siguiente se define un registro público que usa parámetros posicionales para declarar y crear instancias de un registro.</span><span class="sxs-lookup"><span data-stu-id="d57f6-136">The following example defines a public record that uses positional parameters to declare and instantiate a record.</span></span> <span data-ttu-id="d57f6-137">A continuación, imprime el nombre de tipo y los valores de propiedad:</span><span class="sxs-lookup"><span data-stu-id="d57f6-137">It then prints out the type name and property values:</span></span>

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="InstantiatePositional":::

<span data-ttu-id="d57f6-138">En el ejemplo siguiente se muestra la igualdad de valores en los registros:</span><span class="sxs-lookup"><span data-stu-id="d57f6-138">The following example demonstrates value equality in records:</span></span>

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="Equality":::

<span data-ttu-id="d57f6-139">En el ejemplo siguiente se muestra el uso de una expresión `with` para copiar un objeto inmutable y cambiar una de las propiedades:</span><span class="sxs-lookup"><span data-stu-id="d57f6-139">The following example demonstrates use of a `with` expression to copy an immutable object and change one of the properties:</span></span>

:::code language="csharp" source="../../language-reference/builtin-types/snippets/shared/RecordType.cs" id="WithExpressions":::

<span data-ttu-id="d57f6-140">Para obtener más información, consulte [Registros (Referencia de C#)](../../language-reference/builtin-types/record.md).</span><span class="sxs-lookup"><span data-stu-id="d57f6-140">For more information, see [Records (C# reference)](../../language-reference/builtin-types/record.md).</span></span>
  
## <a name="c-language-specification"></a><span data-ttu-id="d57f6-141">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d57f6-141">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d57f6-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d57f6-142">See also</span></span>

- [<span data-ttu-id="d57f6-143">Clases (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="d57f6-143">Classes (C# Programming Guide)</span></span>](classes.md)
- <span data-ttu-id="d57f6-144">[Registros (Referencia de C#)](../../language-reference/builtin-types/record.md)</span><span class="sxs-lookup"><span data-stu-id="d57f6-144">[Records (C# reference)](../../language-reference/builtin-types/record.md).</span></span>
- [<span data-ttu-id="d57f6-145">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d57f6-145">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d57f6-146">Programación orientada a objetos</span><span class="sxs-lookup"><span data-stu-id="d57f6-146">Object-Oriented Programming</span></span>](../../tutorials/intro-to-csharp/object-oriented-programming.md)
- [<span data-ttu-id="d57f6-147">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="d57f6-147">Polymorphism</span></span>](polymorphism.md)
- [<span data-ttu-id="d57f6-148">Nombres de identificador</span><span class="sxs-lookup"><span data-stu-id="d57f6-148">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="d57f6-149">Miembros</span><span class="sxs-lookup"><span data-stu-id="d57f6-149">Members</span></span>](members.md)
- [<span data-ttu-id="d57f6-150">Métodos</span><span class="sxs-lookup"><span data-stu-id="d57f6-150">Methods</span></span>](methods.md)
- [<span data-ttu-id="d57f6-151">Constructores</span><span class="sxs-lookup"><span data-stu-id="d57f6-151">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="d57f6-152">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="d57f6-152">Finalizers</span></span>](destructors.md)
- [<span data-ttu-id="d57f6-153">Objects</span><span class="sxs-lookup"><span data-stu-id="d57f6-153">Objects</span></span>](objects.md)
