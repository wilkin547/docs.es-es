---
description: 'Palabra clave const: Referencia de C#'
title: 'Palabra clave const: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 312725c3a231f0ca766d5b99bf7d9308ddd634c4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142094"
---
# <a name="const-c-reference"></a><span data-ttu-id="9de64-103">const (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9de64-103">const (C# Reference)</span></span>

<span data-ttu-id="9de64-104">La palabra clave `const` se usa para declarar un campo constante o una local constante.</span><span class="sxs-lookup"><span data-stu-id="9de64-104">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="9de64-105">Los campos y locales constantes no son variables y no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="9de64-105">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="9de64-106">Las constantes pueden ser números, valores booleanos, cadenas o una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="9de64-106">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="9de64-107">No cree una constante para representar información que esperas que cambie en algún momento.</span><span class="sxs-lookup"><span data-stu-id="9de64-107">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="9de64-108">Por ejemplo, no use un campo constante para almacenar el precio de un servicio, un número de versión de producto o el nombre comercial de una compañía.</span><span class="sxs-lookup"><span data-stu-id="9de64-108">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="9de64-109">Estos valores pueden cambiar con el tiempo y, como los compiladores propagan las constantes, otro código compilado con sus bibliotecas tendrán que volver a compilarse para ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="9de64-109">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="9de64-110">Vea también la palabra clave [readonly](./readonly.md).</span><span class="sxs-lookup"><span data-stu-id="9de64-110">See also the [readonly](./readonly.md) keyword.</span></span> <span data-ttu-id="9de64-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9de64-111">For example:</span></span>

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="9de64-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9de64-112">Remarks</span></span>

<span data-ttu-id="9de64-113">El tipo de una declaración constante especifica el tipo de los miembros que la declaración presenta.</span><span class="sxs-lookup"><span data-stu-id="9de64-113">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="9de64-114">El inicializador de una local constante o de un campo constante debe ser una expresión constante que se pueda convertir implícitamente al tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="9de64-114">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="9de64-115">Una expresión constante es una expresión que se puede evaluar por completo en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="9de64-115">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="9de64-116">Por lo tanto, los únicos valores posibles para las constantes de tipos de referencia son `string` y una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="9de64-116">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="9de64-117">La declaración de constante puede declarar varias constantes, tales como:</span><span class="sxs-lookup"><span data-stu-id="9de64-117">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

<span data-ttu-id="9de64-118">El modificador `static` no se permite en una declaración de constante.</span><span class="sxs-lookup"><span data-stu-id="9de64-118">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="9de64-119">Una constante puede participar en una expresión constante, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9de64-119">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> <span data-ttu-id="9de64-120">La palabra clave [readonly](./readonly.md) difiere de la palabra clave `const`.</span><span class="sxs-lookup"><span data-stu-id="9de64-120">The [readonly](./readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="9de64-121">Un campo `const` solo se puede inicializar en la declaración del campo.</span><span class="sxs-lookup"><span data-stu-id="9de64-121">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="9de64-122">Un campo `readonly` se puede inicializar en la declaración o en un constructor.</span><span class="sxs-lookup"><span data-stu-id="9de64-122">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="9de64-123">Por lo tanto, los campos `readonly` pueden tener diferentes valores en función del constructor que se use.</span><span class="sxs-lookup"><span data-stu-id="9de64-123">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="9de64-124">Además, aunque un campo `const` es una constante en tiempo de compilación, el campo `readonly` se puede usar para constantes en tiempo de ejecución, como en esta línea: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="9de64-124">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="9de64-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9de64-125">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="9de64-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9de64-126">Example</span></span>

<span data-ttu-id="9de64-127">Este ejemplo demuestra cómo usar las constantes como variables locales.</span><span class="sxs-lookup"><span data-stu-id="9de64-127">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="9de64-128">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9de64-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9de64-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de64-129">See also</span></span>

- [<span data-ttu-id="9de64-130">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9de64-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9de64-131">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9de64-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9de64-132">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="9de64-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="9de64-133">Modificadores</span><span class="sxs-lookup"><span data-stu-id="9de64-133">Modifiers</span></span>](index.md)
- [<span data-ttu-id="9de64-134">readonly</span><span class="sxs-lookup"><span data-stu-id="9de64-134">readonly</span></span>](./readonly.md)
