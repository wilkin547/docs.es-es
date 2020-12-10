---
description: Obtenga información sobre los tipos de valor, sus variedades y los que están integrados en C#.
title: Tipos de valor (Referencia de C#)
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 64c9e9eba2495531cfef8a603d53fb21c95c87a4
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599400"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="97ce6-103">Tipos de valor (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="97ce6-103">Value types (C# reference)</span></span>

<span data-ttu-id="97ce6-104">Los *tipos de valor* y los [tipos de referencia](../keywords/reference-types.md) son las dos categorías principales de tipos de C#.</span><span class="sxs-lookup"><span data-stu-id="97ce6-104">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="97ce6-105">Una variable de un tipo de valor contiene una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="97ce6-105">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="97ce6-106">Esto difiere de una variable de un tipo de referencia, que contiene una referencia a una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="97ce6-106">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="97ce6-107">De forma predeterminada, al [asignar](../operators/assignment-operator.md), pasar un argumento a un método o devolver el resultado de un método, se copian los valores de variable.</span><span class="sxs-lookup"><span data-stu-id="97ce6-107">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="97ce6-108">En el caso de las variables de tipo de valor, se copian las instancias de tipo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="97ce6-108">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="97ce6-109">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="97ce6-109">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](snippets/shared/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="97ce6-110">Como se muestra en el ejemplo anterior, las operaciones en una variable de tipo de valor solo afectan a esa instancia del tipo de valor, almacenado en la variable.</span><span class="sxs-lookup"><span data-stu-id="97ce6-110">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="97ce6-111">Si un tipo de valor contiene un miembro de datos de un tipo de referencia, solo se copia la referencia a la instancia del tipo de referencia al copiar una instancia de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="97ce6-111">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="97ce6-112">Tanto la instancia de tipo de valor original como la copia tienen acceso a la misma instancia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="97ce6-112">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="97ce6-113">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="97ce6-113">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](snippets/shared/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="97ce6-114">Para que el código sea menos propenso a errores y más sólido, defina y use tipos de valor inmutables.</span><span class="sxs-lookup"><span data-stu-id="97ce6-114">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="97ce6-115">En este artículo se usan tipos de valor mutables solo con fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="97ce6-115">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types-and-type-constraints"></a><span data-ttu-id="97ce6-116">Clases de tipos de valor y restricciones de tipo</span><span class="sxs-lookup"><span data-stu-id="97ce6-116">Kinds of value types and type constraints</span></span>

<span data-ttu-id="97ce6-117">Un tipo de valor puede ser de una de las dos clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="97ce6-117">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="97ce6-118">un [tipo de estructura](struct.md), que encapsula los datos y la funcionalidad relacionada;</span><span class="sxs-lookup"><span data-stu-id="97ce6-118">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="97ce6-119">un [tipo de enumeración](enum.md), que se define mediante un conjunto de constantes con nombre y representa una opción o una combinación de opciones.</span><span class="sxs-lookup"><span data-stu-id="97ce6-119">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="97ce6-120">Un [tipo de valor que admite valores NULL](nullable-value-types.md) `T?` representa todos los valores de su tipo de valor subyacente `T` y un valor [NULL](../keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="97ce6-120">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="97ce6-121">No se puede asignar `null` a una variable de un tipo de valor, a menos que sea un tipo de valor que acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="97ce6-121">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

<span data-ttu-id="97ce6-122">Puede usar la [restricción `struct`](../../programming-guide/generics/constraints-on-type-parameters.md) para especificar que un parámetro de tipo es un tipo de valor que no acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="97ce6-122">You can use the [`struct` constraint](../../programming-guide/generics/constraints-on-type-parameters.md) to specify that a type parameter is a non-nullable value type.</span></span> <span data-ttu-id="97ce6-123">Los tipos de estructura y enumeración satisfacen la restricción `struct`.</span><span class="sxs-lookup"><span data-stu-id="97ce6-123">Both structure and enumeration types satisfy the `struct` constraint.</span></span> <span data-ttu-id="97ce6-124">A partir C# 7.3, puede usar `System.Enum` en una restricción de clase base (conocida como la [restricción de enumeración](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) para especificar que un parámetro de tipo es un tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="97ce6-124">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="97ce6-125">Tipos de valor integrados</span><span class="sxs-lookup"><span data-stu-id="97ce6-125">Built-in value types</span></span>

<span data-ttu-id="97ce6-126">C# proporciona los siguientes tipos de valor integrados, también conocidos como *tipos simples*:</span><span class="sxs-lookup"><span data-stu-id="97ce6-126">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="97ce6-127">Tipos numéricos integrales</span><span class="sxs-lookup"><span data-stu-id="97ce6-127">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="97ce6-128">Tipos numéricos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="97ce6-128">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="97ce6-129">[bool](bool.md), que representa un valor booleano</span><span class="sxs-lookup"><span data-stu-id="97ce6-129">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="97ce6-130">[char](char.md), que representa un carácter Unicode UTF-16</span><span class="sxs-lookup"><span data-stu-id="97ce6-130">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="97ce6-131">Todos los tipos simples son tipos de estructuras y se diferencian de otros tipos de estructuras en que permiten determinadas operaciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="97ce6-131">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="97ce6-132">Se pueden usar literales para proporcionar un valor de un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="97ce6-132">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="97ce6-133">Por ejemplo, `'A'` es un literal del tipo `char` y `2001` es un literal del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="97ce6-133">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="97ce6-134">Puede declarar constantes de los tipos simples con la palabra clave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="97ce6-134">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="97ce6-135">No es posible tener constantes de otros tipos de estructuras.</span><span class="sxs-lookup"><span data-stu-id="97ce6-135">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="97ce6-136">Las expresiones constantes, cuyos operandos son todas constantes de los tipos simples, se evalúan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="97ce6-136">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="97ce6-137">A partir de C# 7.0, C# admite [tuplas de valor](value-tuples.md).</span><span class="sxs-lookup"><span data-stu-id="97ce6-137">Beginning with C# 7.0, C# supports [value tuples](value-tuples.md).</span></span> <span data-ttu-id="97ce6-138">Una tupla de valor es un tipo de valor, pero no un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="97ce6-138">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="97ce6-139">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="97ce6-139">C# language specification</span></span>

<span data-ttu-id="97ce6-140">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="97ce6-140">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="97ce6-141">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="97ce6-141">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="97ce6-142">Tipos simples</span><span class="sxs-lookup"><span data-stu-id="97ce6-142">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="97ce6-143">Variables</span><span class="sxs-lookup"><span data-stu-id="97ce6-143">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="97ce6-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ce6-144">See also</span></span>

- [<span data-ttu-id="97ce6-145">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="97ce6-145">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="97ce6-146">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="97ce6-146">Reference types</span></span>](../keywords/reference-types.md)
