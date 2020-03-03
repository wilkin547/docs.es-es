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
ms.openlocfilehash: 76f4a3ed929e3ac8e3e6cc74158e75af7a6c8cf2
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625952"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="bb8db-102">Tipos de valor (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bb8db-102">Value types (C# reference)</span></span>

<span data-ttu-id="bb8db-103">Los *tipos de valor* y los [tipos de referencia](../keywords/reference-types.md) son las dos categorías principales de tipos de C#.</span><span class="sxs-lookup"><span data-stu-id="bb8db-103">*Value types* and [reference types](../keywords/reference-types.md) are the two main categories of C# types.</span></span> <span data-ttu-id="bb8db-104">Una variable de un tipo de valor contiene una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="bb8db-104">A variable of a value type contains an instance of the type.</span></span> <span data-ttu-id="bb8db-105">Esto difiere de una variable de un tipo de referencia, que contiene una referencia a una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="bb8db-105">This differs from a variable of a reference type, which contains a reference to an instance of the type.</span></span> <span data-ttu-id="bb8db-106">De forma predeterminada, al [asignar](../operators/assignment-operator.md), pasar un argumento a un método o devolver el resultado de un método, se copian los valores de variable.</span><span class="sxs-lookup"><span data-stu-id="bb8db-106">By default, on [assignment](../operators/assignment-operator.md), passing an argument to a method, and returning a method result, variable values are copied.</span></span> <span data-ttu-id="bb8db-107">En el caso de las variables de tipo de valor, se copian las instancias de tipo correspondientes.</span><span class="sxs-lookup"><span data-stu-id="bb8db-107">In the case of value-type variables, the corresponding type instances are copied.</span></span> <span data-ttu-id="bb8db-108">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="bb8db-108">The following example demonstrates that behavior:</span></span>

[!code-csharp[copy of values](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ValueTypeCopied)]

<span data-ttu-id="bb8db-109">Como se muestra en el ejemplo anterior, las operaciones en una variable de tipo de valor solo afectan a esa instancia del tipo de valor, almacenado en la variable.</span><span class="sxs-lookup"><span data-stu-id="bb8db-109">As the preceding example shows, operations on a value-type variable affect only that instance of the value type, stored in the variable.</span></span>

<span data-ttu-id="bb8db-110">Si un tipo de valor contiene un miembro de datos de un tipo de referencia, solo se copia la referencia a la instancia del tipo de referencia al copiar una instancia de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="bb8db-110">If a value type contains a data member of a reference type, only the reference to the instance of the reference type is copied when a value-type instance is copied.</span></span> <span data-ttu-id="bb8db-111">Tanto la instancia de tipo de valor original como la copia tienen acceso a la misma instancia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="bb8db-111">Both the copy and original value-type instance have access to the same reference-type instance.</span></span> <span data-ttu-id="bb8db-112">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="bb8db-112">The following example demonstrates that behavior:</span></span>

[!code-csharp[shallow copy](~/samples/csharp/language-reference/builtin-types/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> <span data-ttu-id="bb8db-113">Para que el código sea menos propenso a errores y más sólido, defina y use tipos de valor inmutables.</span><span class="sxs-lookup"><span data-stu-id="bb8db-113">To make your code less error-prone and more robust, define and use immutable value types.</span></span> <span data-ttu-id="bb8db-114">En este artículo se usan tipos de valor mutables solo con fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="bb8db-114">This article uses mutable value types only for demonstration purposes.</span></span>

## <a name="kinds-of-value-types"></a><span data-ttu-id="bb8db-115">Clases de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="bb8db-115">Kinds of value types</span></span>

<span data-ttu-id="bb8db-116">Un tipo de valor puede ser de una de las dos clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb8db-116">A value type can be one of the two following kinds:</span></span>

- <span data-ttu-id="bb8db-117">un [tipo de estructura](struct.md), que encapsula los datos y la funcionalidad relacionada;</span><span class="sxs-lookup"><span data-stu-id="bb8db-117">a [structure type](struct.md), which encapsulates data and related functionality</span></span>
- <span data-ttu-id="bb8db-118">un [tipo de enumeración](enum.md), que se define mediante un conjunto de constantes con nombre y representa una opción o una combinación de opciones.</span><span class="sxs-lookup"><span data-stu-id="bb8db-118">an [enumeration type](enum.md), which is defined by a set of named constants and represents a choice or a combination of choices</span></span>

<span data-ttu-id="bb8db-119">Un [tipo de valor que admite valores NULL](nullable-value-types.md) `T?` representa todos los valores de su tipo de valor subyacente `T` y un valor [NULL](../keywords/null.md) adicional.</span><span class="sxs-lookup"><span data-stu-id="bb8db-119">A [nullable value type](nullable-value-types.md) `T?` represents all values of its underlying value type `T` and an additional [null](../keywords/null.md) value.</span></span> <span data-ttu-id="bb8db-120">No se puede asignar `null` a una variable de un tipo de valor, a menos que sea un tipo de valor que acepte valores NULL.</span><span class="sxs-lookup"><span data-stu-id="bb8db-120">You cannot assign `null` to a variable of a value type, unless it's a nullable value type.</span></span>

## <a name="built-in-value-types"></a><span data-ttu-id="bb8db-121">Tipos de valor integrados</span><span class="sxs-lookup"><span data-stu-id="bb8db-121">Built-in value types</span></span>

<span data-ttu-id="bb8db-122">C# proporciona los siguientes tipos de valor integrados, también conocidos como *tipos simples*:</span><span class="sxs-lookup"><span data-stu-id="bb8db-122">C# provides the following built-in value types, also known as *simple types*:</span></span>

- [<span data-ttu-id="bb8db-123">Tipos numéricos integrales</span><span class="sxs-lookup"><span data-stu-id="bb8db-123">Integral numeric types</span></span>](integral-numeric-types.md)
- [<span data-ttu-id="bb8db-124">Tipos numéricos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="bb8db-124">Floating-point numeric types</span></span>](floating-point-numeric-types.md)
- <span data-ttu-id="bb8db-125">[bool](bool.md), que representa un valor booleano</span><span class="sxs-lookup"><span data-stu-id="bb8db-125">[bool](bool.md) that represents a Boolean value</span></span>
- <span data-ttu-id="bb8db-126">[char](char.md), que representa un carácter Unicode UTF-16</span><span class="sxs-lookup"><span data-stu-id="bb8db-126">[char](char.md) that represents a Unicode UTF-16 character</span></span>

<span data-ttu-id="bb8db-127">Todos los tipos simples son tipos de estructuras y se diferencian de otros tipos de estructuras en que permiten determinadas operaciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="bb8db-127">All simple types are structure types and differ from other structure types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="bb8db-128">Se pueden usar literales para proporcionar un valor de un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="bb8db-128">You can use literals to provide a value of a simple type.</span></span> <span data-ttu-id="bb8db-129">Por ejemplo, `'A'` es un literal del tipo `char` y `2001` es un literal del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="bb8db-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="bb8db-130">Puede declarar constantes de los tipos simples con la palabra clave [const](../keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="bb8db-130">You can declare constants of the simple types with the [const](../keywords/const.md) keyword.</span></span> <span data-ttu-id="bb8db-131">No es posible tener constantes de otros tipos de estructuras.</span><span class="sxs-lookup"><span data-stu-id="bb8db-131">It's not possible to have constants of other structure types.</span></span>

- <span data-ttu-id="bb8db-132">Las expresiones constantes, cuyos operandos son todas constantes de los tipos simples, se evalúan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="bb8db-132">Constant expressions, whose operands are all constants of the simple types, are evaluated at compile time.</span></span>

<span data-ttu-id="bb8db-133">A partir de C# 7.0, C# admite [tuplas de valor](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="bb8db-133">Beginning with C# 7.0, C# supports [value tuples](../../tuples.md).</span></span> <span data-ttu-id="bb8db-134">Una tupla de valor es un tipo de valor, pero no un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="bb8db-134">A value tuple is a value type, but not a simple type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bb8db-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bb8db-135">C# language specification</span></span>

<span data-ttu-id="bb8db-136">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="bb8db-136">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bb8db-137">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="bb8db-137">Value types</span></span>](~/_csharplang/spec/types.md#value-types)
- [<span data-ttu-id="bb8db-138">Tipos simples</span><span class="sxs-lookup"><span data-stu-id="bb8db-138">Simple types</span></span>](~/_csharplang/spec/types.md#simple-types)
- [<span data-ttu-id="bb8db-139">Variables</span><span class="sxs-lookup"><span data-stu-id="bb8db-139">Variables</span></span>](~/_csharplang/spec/variables.md)

## <a name="see-also"></a><span data-ttu-id="bb8db-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb8db-140">See also</span></span>

- [<span data-ttu-id="bb8db-141">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bb8db-141">C# reference</span></span>](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [<span data-ttu-id="bb8db-142">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="bb8db-142">Reference types</span></span>](../keywords/reference-types.md)
