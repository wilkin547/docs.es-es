---
title: Operadores de conversión definidos por el usuario - referencia de C#
description: Obtenga información sobre cómo definir conversiones de tipos implícitas y explícitas personalizadas en C#.
ms.date: 07/09/2019
f1_keywords:
- explicit_CSharpKeyword
- implicit_CSharpKeyword
helpviewer_keywords:
- explicit keyword [C#]
- implicit keyword [C#]
- conversion operator [C#]
- user-defined conversion [C#]
ms.openlocfilehash: b59fc27be31f1a38e2a6c3cabd82598933b5ed53
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121402"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="c2ab6-103">Operadores de conversión definidos por el usuario (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c2ab6-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="c2ab6-104">Un tipo definido por el usuario puede definir una conversión implícita o explícita personalizada desde o a otro tipo.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="c2ab6-105">Las conversiones implícitas no requieren que se invoque una sintaxis especial y pueden producirse en diversas situaciones, por ejemplo, en las invocaciones de métodos y asignaciones.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="c2ab6-106">Las conversiones implícitas predefinidas en C# siempre se realizan correctamente y nunca inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="c2ab6-107">Las conversiones implícitas definidas por el usuario deben comportarse de esta manera.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="c2ab6-108">Si una conversión personalizada puede producir una excepción o perder información, se define como una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="c2ab6-109">Los operadores [is](type-testing-and-cast.md#is-operator) y [as](type-testing-and-cast.md#as-operator) no tienen en cuenta las conversiones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="c2ab6-110">Use una [expresión Cast](type-testing-and-cast.md#cast-expression) para invocar una conversión explícita definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-110">Use a [cast expression](type-testing-and-cast.md#cast-expression) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="c2ab6-111">Use las palabras clave `operator` y `implicit` o `explicit` para definir una conversión implícita o explícita, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="c2ab6-112">El tipo que define una conversión debe ser un tipo de origen o un tipo de destino de dicha conversión.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="c2ab6-113">Una conversión entre dos tipos definidos por el usuario se puede definir en cualquiera de los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="c2ab6-114">En el ejemplo siguiente se muestra cómo se define una conversión implícita y explícita:</span><span class="sxs-lookup"><span data-stu-id="c2ab6-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](snippets/UserDefinedConversions.cs)]

<span data-ttu-id="c2ab6-115">Use también la palabra clave `operator` para sobrecargar un operador predefinido en C#.</span><span class="sxs-lookup"><span data-stu-id="c2ab6-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="c2ab6-116">Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="c2ab6-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c2ab6-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c2ab6-117">C# language specification</span></span>

<span data-ttu-id="c2ab6-118">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="c2ab6-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="c2ab6-119">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="c2ab6-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="c2ab6-120">Conversiones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="c2ab6-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="c2ab6-121">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="c2ab6-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="c2ab6-122">Conversiones explícitas</span><span class="sxs-lookup"><span data-stu-id="c2ab6-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="c2ab6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2ab6-123">See also</span></span>

- [<span data-ttu-id="c2ab6-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c2ab6-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c2ab6-125">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="c2ab6-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="c2ab6-126">Sobrecarga de operadores</span><span class="sxs-lookup"><span data-stu-id="c2ab6-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="c2ab6-127">Operadores de conversión y prueba de tipos</span><span class="sxs-lookup"><span data-stu-id="c2ab6-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="c2ab6-128">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="c2ab6-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="c2ab6-129">Directrices de diseño: operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="c2ab6-129">Design guidelines - Conversion operators</span></span>](../../../standard/design-guidelines/operator-overloads.md#conversion-operators)
- <span data-ttu-id="c2ab6-130">[Chained user-defined explicit conversions in C#](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="c2ab6-130">[Chained user-defined explicit conversions in C#](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)</span></span>
