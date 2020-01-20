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
ms.openlocfilehash: 2f4858d729093d3520e97610e0eac8600093187a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936875"
---
# <a name="user-defined-conversion-operators-c-reference"></a><span data-ttu-id="0c2af-103">Operadores de conversión definidos por el usuario (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0c2af-103">User-defined conversion operators (C# reference)</span></span>

<span data-ttu-id="0c2af-104">Un tipo definido por el usuario puede definir una conversión implícita o explícita personalizada desde o a otro tipo.</span><span class="sxs-lookup"><span data-stu-id="0c2af-104">A user-defined type can define a custom implicit or explicit conversion from or to another type.</span></span>

<span data-ttu-id="0c2af-105">Las conversiones implícitas no requieren que se invoque una sintaxis especial y pueden producirse en diversas situaciones, por ejemplo, en las invocaciones de métodos y asignaciones.</span><span class="sxs-lookup"><span data-stu-id="0c2af-105">Implicit conversions don't require special syntax to be invoked and can occur in a variety of situations, for example, in assignments and methods invocations.</span></span> <span data-ttu-id="0c2af-106">Las conversiones implícitas predefinidas en C# siempre se realizan correctamente y nunca inician una excepción.</span><span class="sxs-lookup"><span data-stu-id="0c2af-106">Predefined C# implicit conversions always succeed and never throw an exception.</span></span> <span data-ttu-id="0c2af-107">Las conversiones implícitas definidas por el usuario deben comportarse de esta manera.</span><span class="sxs-lookup"><span data-stu-id="0c2af-107">User-defined implicit conversions should behave in that way as well.</span></span> <span data-ttu-id="0c2af-108">Si una conversión personalizada puede producir una excepción o perder información, se define como una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="0c2af-108">If a custom conversion can throw an exception or lose information, define it as an explicit conversion.</span></span>

<span data-ttu-id="0c2af-109">Los operadores [is](type-testing-and-cast.md#is-operator) y [as](type-testing-and-cast.md#as-operator) no tienen en cuenta las conversiones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0c2af-109">User-defined conversions are not considered by the [is](type-testing-and-cast.md#is-operator) and [as](type-testing-and-cast.md#as-operator) operators.</span></span> <span data-ttu-id="0c2af-110">Use el [operador de conversión ()](type-testing-and-cast.md#cast-operator-) para invocar una conversión explícita definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0c2af-110">Use the [cast operator ()](type-testing-and-cast.md#cast-operator-) to invoke a user-defined explicit conversion.</span></span>

<span data-ttu-id="0c2af-111">Use las palabras clave `operator` y `implicit` o `explicit` para definir una conversión implícita o explícita, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="0c2af-111">Use the `operator` and `implicit` or `explicit` keywords to define an implicit or explicit conversion, respectively.</span></span> <span data-ttu-id="0c2af-112">El tipo que define una conversión debe ser un tipo de origen o un tipo de destino de dicha conversión.</span><span class="sxs-lookup"><span data-stu-id="0c2af-112">The type that defines a conversion must be either a source type or a target type of that conversion.</span></span> <span data-ttu-id="0c2af-113">Una conversión entre dos tipos definidos por el usuario se puede definir en cualquiera de los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="0c2af-113">A conversion between two user-defined types can be defined in either of the two types.</span></span>

<span data-ttu-id="0c2af-114">En el ejemplo siguiente se muestra cómo se define una conversión implícita y explícita:</span><span class="sxs-lookup"><span data-stu-id="0c2af-114">The following example demonstrates how to define an implicit and explicit conversion:</span></span>

[!code-csharp[implicit an explicit conversions](~/samples/csharp/language-reference/operators/UserDefinedConversions.cs)]

<span data-ttu-id="0c2af-115">Use también la palabra clave `operator` para sobrecargar un operador predefinido en C#.</span><span class="sxs-lookup"><span data-stu-id="0c2af-115">You also use the `operator` keyword to overload a predefined C# operator.</span></span> <span data-ttu-id="0c2af-116">Para obtener más información, vea [Sobrecarga de operadores](operator-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="0c2af-116">For more information, see [Operator overloading](operator-overloading.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0c2af-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0c2af-117">C# language specification</span></span>

<span data-ttu-id="0c2af-118">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="0c2af-118">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="0c2af-119">Operadores de conversión</span><span class="sxs-lookup"><span data-stu-id="0c2af-119">Conversion operators</span></span>](~/_csharplang/spec/classes.md#conversion-operators)
- [<span data-ttu-id="0c2af-120">Conversiones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="0c2af-120">User-defined conversions</span></span>](~/_csharplang/spec/conversions.md#user-defined-conversions)
- [<span data-ttu-id="0c2af-121">Conversiones implícitas</span><span class="sxs-lookup"><span data-stu-id="0c2af-121">Implicit conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-conversions)
- [<span data-ttu-id="0c2af-122">Conversiones explícitas</span><span class="sxs-lookup"><span data-stu-id="0c2af-122">Explicit conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-conversions)

## <a name="see-also"></a><span data-ttu-id="0c2af-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c2af-123">See also</span></span>

- [<span data-ttu-id="0c2af-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0c2af-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0c2af-125">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0c2af-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="0c2af-126">Sobrecarga de operadores</span><span class="sxs-lookup"><span data-stu-id="0c2af-126">Operator overloading</span></span>](operator-overloading.md)
- [<span data-ttu-id="0c2af-127">Operadores de conversión y prueba de tipos</span><span class="sxs-lookup"><span data-stu-id="0c2af-127">Type-testing and cast operators</span></span>](type-testing-and-cast.md)
- [<span data-ttu-id="0c2af-128">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="0c2af-128">Casting and type conversion</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- <span data-ttu-id="0c2af-129">[Chained user-defined explicit conversions in C#](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c) (Conversiones explícitas encadenadas definidas por el usuario en C#)</span><span class="sxs-lookup"><span data-stu-id="0c2af-129">[Chained user-defined explicit conversions in C#](https://docs.microsoft.com/archive/blogs/ericlippert/chained-user-defined-explicit-conversions-in-c)</span></span>
