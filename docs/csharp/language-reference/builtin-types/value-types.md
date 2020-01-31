---
title: Tipos de valor (Referencia de C#)
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 6b96d65f657f2af1af5c9a245e956640ee06260e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76748492"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="9878e-102">Tipos de valor (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9878e-102">Value types (C# reference)</span></span>

<span data-ttu-id="9878e-103">Los *tipos de valor* y los [tipos de referencia](../keywords/reference-types.md) son las dos categorías principales de tipos de C#.</span><span class="sxs-lookup"><span data-stu-id="9878e-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="9878e-104">Una variable de un tipo de valor contiene una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="9878e-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="9878e-105">Esto difiere de una variable de un tipo de referencia, que contiene una referencia a una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="9878e-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="9878e-106">De forma predeterminada, al [asignar](../operators/assignment-operator.md), pasar un argumento a un método o devolver el resultado de un método, se copian los valores de variable.</span><span class="sxs-lookup"><span data-stu-id="9878e-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, or returning a method result, variable values are copied.</span></span> <span data-ttu-id="9878e-107">En el caso de las variables de tipo de valor, se copian las instancias de tipo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9878e-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="9878e-108">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="9878e-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="9878e-109">Como se muestra en el ejemplo anterior, las operaciones en una variable de tipo de valor solo afectan a esa instancia del tipo de valor, almacenado en la variable.</span><span class="sxs-lookup"><span data-stu-id="9878e-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="9878e-110">Si un tipo de valor contiene un miembro de datos de un tipo de referencia, solo se copia la referencia a la instancia del tipo de referencia al copiar una instancia de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="9878e-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="9878e-111">Tanto la instancia de tipo de valor original como la copia tienen acceso a la misma instancia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="9878e-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="9878e-112">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="9878e-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="9878e-113">Para que el código sea menos propenso a errores y más sólido, defina y use tipos de valor inmutables.</span><span class="sxs-lookup"><span data-stu-id="9878e-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="9878e-114">En este artículo se usan tipos de valor mutables solo con fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="9878e-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="9878e-115">Clases de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="9878e-115">Kinds of value types</span></span>

<span data-ttu-id="9878e-116">Un tipo de valor puede ser de una de las dos clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="9878e-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="9878e-117">un [tipo de estructura](../keywords/struct.md), que encapsula los datos y la funcionalidad relacionada;</span><span class="sxs-lookup"><span data-stu-id="9878e-117">a [structure type](../keywords/struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="9878e-118">un [tipo de enumeración](enum.md), que se define mediante un conjunto de constantes con nombre y representa una opción o una combinación de opciones.</span><span class="sxs-lookup"><span data-stu-id="9878e-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="9878e-119">Un [tipo de valor que admite valores NULL](nullable-value-types.md) `T?` representa todos los valores de su tipo de valor subyacente `T` y un valor [NULL](../keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="9878e-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="9878e-120">No se puede asignar `null` a una variable de un tipo de valor, a menos que sea un tipo de valor que acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9878e-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="9878e-121">Tipos de valor integrados</span><span class="sxs-lookup"><span data-stu-id="9878e-121">Built-in value types</span></span>

<span data-ttu-id="9878e-122">C# proporciona los siguientes tipos de valor integrados, también conocidos como *tipos simples*:</span><span class="sxs-lookup"><span data-stu-id="9878e-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="9878e-123">Tipos numéricos integrales</span><span class="sxs-lookup"><span data-stu-id="9878e-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="9878e-124">Tipos numéricos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="9878e-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="9878e-125">[bool](bool.md), que representa un valor booleano</span><span class="sxs-lookup"><span data-stu-id="9878e-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="9878e-126">[char](char.md), que representa un carácter Unicode UTF-16</span><span class="sxs-lookup"><span data-stu-id="9878e-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="9878e-127">Todos los tipos simples son tipos de estructuras y se diferencian de otros tipos de estructuras en que permiten determinadas operaciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="9878e-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="9878e-128">Se pueden usar literales para proporcionar un valor de un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="9878e-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="9878e-129">Por ejemplo, `'A'` es un literal del tipo `char` y `2001` es un literal del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="9878e-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="9878e-130">Puede declarar constantes de los tipos simples con la palabra clave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="9878e-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="9878e-131">No es posible tener constantes de otros tipos de estructuras.</span><span class="sxs-lookup"><span data-stu-id="9878e-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="9878e-132">Las expresiones constantes, cuyos operandos son todas constantes de los tipos simples, se evalúan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="9878e-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="9878e-133">A partir de C# 7.0, C# admite [tuplas de valor](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="9878e-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="9878e-134">Una tupla de valor es un tipo de valor, pero no un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="9878e-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9878e-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9878e-135">C# language specification</span></span>

<span data-ttu-id="9878e-136">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="9878e-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="9878e-137">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="9878e-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="9878e-138">Tipos simples</span><span class="sxs-lookup"><span data-stu-id="9878e-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="9878e-139">Variables</span><span class="sxs-lookup"><span data-stu-id="9878e-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="9878e-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="9878e-140">See also</span></span>

- [<span data-ttu-id="9878e-141">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9878e-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="9878e-142">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="9878e-142">Reference types</span></span>](../keywords/reference-types.md)
