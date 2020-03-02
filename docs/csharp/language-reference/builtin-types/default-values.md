---
title: 'Valores predeterminados de los tipos de C#: referencia de C#'
description: Aprenda los valores predeterminados de C#, como bool, char, int, float, double y más.
ms.date: 12/18/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: 93b6079b9a3bbf6d537094cab9dfb305ace7f6bf
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625870"
---
# <a name="default-values-of-c-types-c-reference"></a><span data-ttu-id="d49f5-103">Valores predeterminados de los tipos de C# (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d49f5-103">Default values of C# types (C# reference)</span></span>

<span data-ttu-id="d49f5-104">En la tabla siguiente se muestran los valores predeterminados de los tipos de C#:</span><span class="sxs-lookup"><span data-stu-id="d49f5-104">The following table shows the default values of C# types:</span></span>

|<span data-ttu-id="d49f5-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="d49f5-105">Type</span></span>|<span data-ttu-id="d49f5-106">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="d49f5-106">Default value</span></span>|
|---------|------------------|
|<span data-ttu-id="d49f5-107">Cualquier tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="d49f5-107">Any reference type</span></span>|`null`|
|<span data-ttu-id="d49f5-108">Cualquier [tipo numérico entero integrado](integral-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="d49f5-108">Any [built-in integral numeric type](integral-numeric-types.md)</span></span>|<span data-ttu-id="d49f5-109">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="d49f5-109">0 (zero)</span></span>|
|<span data-ttu-id="d49f5-110">Cualquier [tipo numérico de punto flotante integrado](floating-point-numeric-types.md)</span><span class="sxs-lookup"><span data-stu-id="d49f5-110">Any [built-in floating-point numeric type](floating-point-numeric-types.md)</span></span>|<span data-ttu-id="d49f5-111">0 (cero)</span><span class="sxs-lookup"><span data-stu-id="d49f5-111">0 (zero)</span></span>|
|[<span data-ttu-id="d49f5-112">bool</span><span class="sxs-lookup"><span data-stu-id="d49f5-112">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="d49f5-113">char</span><span class="sxs-lookup"><span data-stu-id="d49f5-113">char</span></span>](char.md)|<span data-ttu-id="d49f5-114">`'\0'` (U+0000)</span><span class="sxs-lookup"><span data-stu-id="d49f5-114">`'\0'` (U+0000)</span></span>|
|[<span data-ttu-id="d49f5-115">enum</span><span class="sxs-lookup"><span data-stu-id="d49f5-115">enum</span></span>](enum.md)|<span data-ttu-id="d49f5-116">Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="d49f5-116">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="d49f5-117">struct</span><span class="sxs-lookup"><span data-stu-id="d49f5-117">struct</span></span>](struct.md)|<span data-ttu-id="d49f5-118">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="d49f5-118">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|<span data-ttu-id="d49f5-119">Cualquier [tipo de valor que acepta valores NULL](nullable-value-types.md)</span><span class="sxs-lookup"><span data-stu-id="d49f5-119">Any [nullable value type](nullable-value-types.md)</span></span>|<span data-ttu-id="d49f5-120">Instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.</span><span class="sxs-lookup"><span data-stu-id="d49f5-120">An instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span> <span data-ttu-id="d49f5-121">Este valor predeterminado también se conoce con el valor *null* de un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="d49f5-121">That default value is also known as the *null* value of a nullable value type.</span></span>|

<span data-ttu-id="d49f5-122">Use el [operador predeterminado](../operators/default.md) para generar el valor predeterminado de un tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d49f5-122">Use the [default operator](../operators/default.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="d49f5-123">A partir de C# 7.1, se puede usar el [literal `default`](../operators/default.md#default-literal) para inicializar una variable con el valor predeterminado de su tipo:</span><span class="sxs-lookup"><span data-stu-id="d49f5-123">Beginning with C# 7.1, you can use the [`default` literal](../operators/default.md#default-literal) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="d49f5-124">Para un tipo de valor, el constructor implícito sin parámetros también genera el valor predeterminado del tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d49f5-124">For a value type, the implicit parameterless constructor also produces the default value of the type, as the following example shows:</span></span>

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

<span data-ttu-id="d49f5-125">En tiempo de ejecución, si la instancia de <xref:System.Type?displayProperty=nameWithType> representa un tipo de valor, puede usar el método <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> para invocar el constructor sin parámetros y obtener el valor predeterminado del tipo.</span><span class="sxs-lookup"><span data-stu-id="d49f5-125">At run time, if the <xref:System.Type?displayProperty=nameWithType> instance represents a value type, you can use the <xref:System.Activator.CreateInstance(System.Type)?displayProperty=nameWithType> method to invoke the parameterless constructor to obtain the default value of the type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="d49f5-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="d49f5-126">C# language specification</span></span>

<span data-ttu-id="d49f5-127">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="d49f5-127">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="d49f5-128">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="d49f5-128">Default values</span></span>](~/_csharplang/spec/variables.md#default-values)
- [<span data-ttu-id="d49f5-129">Constructores predeterminados</span><span class="sxs-lookup"><span data-stu-id="d49f5-129">Default constructors</span></span>](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a><span data-ttu-id="d49f5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d49f5-130">See also</span></span>

- [<span data-ttu-id="d49f5-131">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d49f5-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="d49f5-132">Constructores</span><span class="sxs-lookup"><span data-stu-id="d49f5-132">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)
