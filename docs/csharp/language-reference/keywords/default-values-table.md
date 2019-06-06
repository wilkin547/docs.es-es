---
title: 'Tabla de valores predeterminados: Referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre los valores predeterminados de los tipos de valor de C#.
ms.date: 08/23/2018
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- parameterless constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], parameterless constructor
- types [C#], parameterless constructor return values
ms.openlocfilehash: 4fc9a35f69540e047a97c21788015ca8e54068a0
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422036"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="7b0dd-103">Tabla de valores predeterminados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7b0dd-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="7b0dd-104">En la tabla siguiente se muestran los valores predeterminados de los [tipos de valor](value-types.md).</span><span class="sxs-lookup"><span data-stu-id="7b0dd-104">The following table shows the default values of [value types](value-types.md).</span></span>

|<span data-ttu-id="7b0dd-105">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="7b0dd-105">Value type</span></span>|<span data-ttu-id="7b0dd-106">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="7b0dd-106">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="7b0dd-107">bool</span><span class="sxs-lookup"><span data-stu-id="7b0dd-107">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="7b0dd-108">byte</span><span class="sxs-lookup"><span data-stu-id="7b0dd-108">byte</span></span>](byte.md)|<span data-ttu-id="7b0dd-109">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-109">0</span></span>|
|[<span data-ttu-id="7b0dd-110">char</span><span class="sxs-lookup"><span data-stu-id="7b0dd-110">char</span></span>](char.md)|<span data-ttu-id="7b0dd-111">'\0'</span><span class="sxs-lookup"><span data-stu-id="7b0dd-111">'\0'</span></span>|
|[<span data-ttu-id="7b0dd-112">decimal</span><span class="sxs-lookup"><span data-stu-id="7b0dd-112">decimal</span></span>](decimal.md)|<span data-ttu-id="7b0dd-113">0M</span><span class="sxs-lookup"><span data-stu-id="7b0dd-113">0M</span></span>|
|[<span data-ttu-id="7b0dd-114">double</span><span class="sxs-lookup"><span data-stu-id="7b0dd-114">double</span></span>](double.md)|<span data-ttu-id="7b0dd-115">0.0D</span><span class="sxs-lookup"><span data-stu-id="7b0dd-115">0.0D</span></span>|
|[<span data-ttu-id="7b0dd-116">enum</span><span class="sxs-lookup"><span data-stu-id="7b0dd-116">enum</span></span>](enum.md)|<span data-ttu-id="7b0dd-117">Valor generado por la expresión `(E)0`, donde `E` es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-117">The value produced by the expression `(E)0`, where `E` is the enum identifier.</span></span>|
|[<span data-ttu-id="7b0dd-118">float</span><span class="sxs-lookup"><span data-stu-id="7b0dd-118">float</span></span>](float.md)|<span data-ttu-id="7b0dd-119">0.0F</span><span class="sxs-lookup"><span data-stu-id="7b0dd-119">0.0F</span></span>|
|[<span data-ttu-id="7b0dd-120">int</span><span class="sxs-lookup"><span data-stu-id="7b0dd-120">int</span></span>](int.md)|<span data-ttu-id="7b0dd-121">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-121">0</span></span>|
|[<span data-ttu-id="7b0dd-122">long</span><span class="sxs-lookup"><span data-stu-id="7b0dd-122">long</span></span>](long.md)|<span data-ttu-id="7b0dd-123">0L</span><span class="sxs-lookup"><span data-stu-id="7b0dd-123">0L</span></span>|
|[<span data-ttu-id="7b0dd-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="7b0dd-124">sbyte</span></span>](sbyte.md)|<span data-ttu-id="7b0dd-125">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-125">0</span></span>|
|[<span data-ttu-id="7b0dd-126">short</span><span class="sxs-lookup"><span data-stu-id="7b0dd-126">short</span></span>](short.md)|<span data-ttu-id="7b0dd-127">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-127">0</span></span>|
|[<span data-ttu-id="7b0dd-128">struct</span><span class="sxs-lookup"><span data-stu-id="7b0dd-128">struct</span></span>](struct.md)|<span data-ttu-id="7b0dd-129">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-129">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="7b0dd-130">uint</span><span class="sxs-lookup"><span data-stu-id="7b0dd-130">uint</span></span>](uint.md)|<span data-ttu-id="7b0dd-131">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-131">0</span></span>|
|[<span data-ttu-id="7b0dd-132">ulong</span><span class="sxs-lookup"><span data-stu-id="7b0dd-132">ulong</span></span>](ulong.md)|<span data-ttu-id="7b0dd-133">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-133">0</span></span>|
|[<span data-ttu-id="7b0dd-134">ushort</span><span class="sxs-lookup"><span data-stu-id="7b0dd-134">ushort</span></span>](ushort.md)|<span data-ttu-id="7b0dd-135">0</span><span class="sxs-lookup"><span data-stu-id="7b0dd-135">0</span></span>|

## <a name="remarks"></a><span data-ttu-id="7b0dd-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b0dd-136">Remarks</span></span>

<span data-ttu-id="7b0dd-137">En C# no se pueden usar variables sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-137">You cannot use uninitialized variables in C#.</span></span> <span data-ttu-id="7b0dd-138">Una variable se puede inicializar con el valor predeterminado de su tipo.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-138">You can initialize a variable with the default value of its type.</span></span> <span data-ttu-id="7b0dd-139">También se puede usar el valor predeterminado de un tipo para especificar el valor predeterminado del [argumento opcional](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments) de un método.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-139">You also can use the default value of a type to specify the default value of a method's [optional argument](../../programming-guide/classes-and-structs/named-and-optional-arguments.md#optional-arguments).</span></span>

<span data-ttu-id="7b0dd-140">Use la [expresión de valor predeterminado](../../programming-guide/statements-expressions-operators/default-value-expressions.md) para generar el valor predeterminado de un tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b0dd-140">Use the [default value expression](../../programming-guide/statements-expressions-operators/default-value-expressions.md) to produce the default value of a type, as the following example shows:</span></span>

```csharp
int a = default(int);
```

<span data-ttu-id="7b0dd-141">A partir de C# 7.1, se puede usar el [literal `default`](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) para inicializar una variable con el valor predeterminado de su tipo:</span><span class="sxs-lookup"><span data-stu-id="7b0dd-141">Beginning with C# 7.1, you can use the [`default` literal](../../programming-guide/statements-expressions-operators/default-value-expressions.md#default-literal-and-type-inference) to initialize a variable with the default value of its type:</span></span>

```csharp
int a = default;
```

<span data-ttu-id="7b0dd-142">También se puede usar el constructor sin parámetros o el constructor sin parámetros implícito para generar el valor predeterminado de un tipo de valor, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-142">You also can use the parameterless constructor or the implicit parameterless constructor to produce the default value of a value type, as the following example shows.</span></span> <span data-ttu-id="7b0dd-143">Para obtener más información sobre los constructores, vea el artículo [Constructores](../../programming-guide/classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="7b0dd-143">For more information about constructors, see the [Constructors](../../programming-guide/classes-and-structs/constructors.md) article.</span></span>

```csharp
int a = new int();
```

<span data-ttu-id="7b0dd-144">El valor predeterminado de cualquier [tipo de referencia](reference-types.md) es `null`.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-144">The default value of any [reference type](reference-types.md) is `null`.</span></span> <span data-ttu-id="7b0dd-145">El valor predeterminado de un [tipo que acepta valores NULL](../../programming-guide/nullable-types/index.md) es una instancia para la que la propiedad <xref:System.Nullable%601.HasValue%2A> es `false` y la propiedad <xref:System.Nullable%601.Value%2A> no está definida.</span><span class="sxs-lookup"><span data-stu-id="7b0dd-145">The default value of a [nullable type](../../programming-guide/nullable-types/index.md) is an instance for which the <xref:System.Nullable%601.HasValue%2A> property is `false` and the <xref:System.Nullable%601.Value%2A> property is undefined.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b0dd-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b0dd-146">See also</span></span>

- [<span data-ttu-id="7b0dd-147">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7b0dd-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7b0dd-148">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7b0dd-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7b0dd-149">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="7b0dd-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="7b0dd-150">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="7b0dd-150">Value types</span></span>](value-types.md)
- [<span data-ttu-id="7b0dd-151">Tabla de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="7b0dd-151">Value types table</span></span>](value-types-table.md)
- [<span data-ttu-id="7b0dd-152">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="7b0dd-152">Built-in types table</span></span>](built-in-types-table.md)
