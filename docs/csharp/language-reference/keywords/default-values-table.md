---
title: 'Tabla de valores predeterminados: referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de C#.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 23fba8269670156000cb68b3aa07ae7c770eada1
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627740"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="f4f36-103">Tabla de valores predeterminados (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f4f36-103">Default values table (C# reference)</span></span>

<span data-ttu-id="f4f36-104">En la tabla siguiente se muestran los valores predeterminados de los tipos de C#:</span><span class="sxs-lookup"><span data-stu-id="f4f36-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="f4f36-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4f36-105">Type</span></span>|<span data-ttu-id="f4f36-106">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="f4f36-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="f4f36-107">Cualquier tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="f4f36-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="f4f36-108">Cualquier [tipo numérico entero integrado](../builtin-types/integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="f4f36-108">Any [built-in integral numeric type](../builtin-types/integral-numeric-types.md)</span></span>|<span data-ttu-id="f4f36-109">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="f4f36-109">0 (zero)</span></span>|
|<span data-ttu-id="f4f36-110">Cualquier [tipo numérico de punto flotante integrado](../builtin-types/floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="f4f36-110">Any [built-in floating-point numeric type](../builtin-types/floating-point-numeric-types.md)</span></span>|<span data-ttu-id="f4f36-111">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="f4f36-111">0 (zero)</span></span>|
|[<span data-ttu-id="f4f36-112">bool</span><span class="sxs-lookup"><span data-stu-id="f4f36-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="f4f36-113">char</span><span class="sxs-lookup"><span data-stu-id="f4f36-113">char</span></span>](char.md)|<span data-ttu-id="f4f36-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="f4f36-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="f4f36-115">enum</span><span class="sxs-lookup"><span data-stu-id="f4f36-115">enum</span></span>](enum.md)|<span data-ttu-id="f4f36-116">Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="f4f36-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="f4f36-117">struct</span><span class="sxs-lookup"><span data-stu-id="f4f36-117">struct</span></span>](struct.md)|<span data-ttu-id="f4f36-118">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="f4f36-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="f4f36-119">Cualquier [tipo de valor que acepta valores NULL](../../programming-guide/nullable-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="f4f36-119">Any [nullable value type](../../programming-guide/nullable-types/index.md)</span></span>|<span data-ttu-id="f4f36-120">Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.</span><span class="sxs-lookup"><span data-stu-id="f4f36-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="f4f36-121">Este valor predeterminado también se conoce con el valor *null* del tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="f4f36-121">That default value is also known as the *null* value of the nullable value type.</span></span>|

<span data-ttu-id="f4f36-122">Use la [expresión de valor predeterminado](../../programming-guide/statements-expressions-operators/default-value-expressions.md) para generar el valor predeterminado de un tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4f36-122">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="f4f36-123">A partir de C# 7.1, se puede usar el [literal `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) para inicializar una variable con el valor predeterminado de su tipo:</span><span class="sxs-lookup"><span data-stu-id="f4f36-123">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="f4f36-124">Para un tipo de valor, el constructor implícito sin parámetros también genera el valor predeterminado del tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f4f36-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a><span data-ttu-id="f4f36-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f4f36-125">C# language specification</span></span>

<span data-ttu-id="f4f36-126">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="f4f36-126">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="f4f36-127">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="f4f36-127">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="f4f36-128">Constructores predeterminados</span><span class="sxs-lookup"><span data-stu-id="f4f36-128">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="f4f36-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4f36-129">See also</span></span>

- [<span data-ttu-id="f4f36-130">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f4f36-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f4f36-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f4f36-131">C# keywords</span></span>](index.md)
- [<span data-ttu-id="f4f36-132">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="f4f36-132">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="f4f36-133">Constructores</span><span class="sxs-lookup"><span data-stu-id="f4f36-133">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
