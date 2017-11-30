---
title: Tabla de valores predeterminados (Referencia de C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.assetid: 4af2c1df-9e3a-48c1-83ac-b192986fc5bc
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d034c1daf495c50e299fec4c5bf399652dad08ce
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2017
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="44651-102">Tabla de valores predeterminados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="44651-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="44651-103">En la siguiente tabla se muestran los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="44651-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="44651-104">Los constructores predeterminados se invocan mediante el operador `new`, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="44651-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="44651-105">La instrucción anterior tiene el mismo efecto que la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="44651-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="44651-106">Recuerde que no se permite el uso de variables sin inicializar en C#.</span><span class="sxs-lookup"><span data-stu-id="44651-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="44651-107">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="44651-107">Value type</span></span>|<span data-ttu-id="44651-108">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="44651-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="44651-109">bool</span><span class="sxs-lookup"><span data-stu-id="44651-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="44651-110">byte</span><span class="sxs-lookup"><span data-stu-id="44651-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="44651-111">0</span><span class="sxs-lookup"><span data-stu-id="44651-111">0</span></span>|
|[<span data-ttu-id="44651-112">char</span><span class="sxs-lookup"><span data-stu-id="44651-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="44651-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="44651-113">'\0'</span></span>|
|[<span data-ttu-id="44651-114">decimal</span><span class="sxs-lookup"><span data-stu-id="44651-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="44651-115">M 0</span><span class="sxs-lookup"><span data-stu-id="44651-115">0M</span></span>|
|[<span data-ttu-id="44651-116">double</span><span class="sxs-lookup"><span data-stu-id="44651-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="44651-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="44651-117">0.0D</span></span>|
|[<span data-ttu-id="44651-118">enum</span><span class="sxs-lookup"><span data-stu-id="44651-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="44651-119">El valor generado por la expresión (E)0, donde E es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="44651-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="44651-120">float</span><span class="sxs-lookup"><span data-stu-id="44651-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="44651-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="44651-121">0.0F</span></span>|
|[<span data-ttu-id="44651-122">int</span><span class="sxs-lookup"><span data-stu-id="44651-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="44651-123">0</span><span class="sxs-lookup"><span data-stu-id="44651-123">0</span></span>|
|[<span data-ttu-id="44651-124">long</span><span class="sxs-lookup"><span data-stu-id="44651-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="44651-125">0L</span><span class="sxs-lookup"><span data-stu-id="44651-125">0L</span></span>|
|[<span data-ttu-id="44651-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="44651-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="44651-127">0</span><span class="sxs-lookup"><span data-stu-id="44651-127">0</span></span>|
|[<span data-ttu-id="44651-128">short</span><span class="sxs-lookup"><span data-stu-id="44651-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="44651-129">0</span><span class="sxs-lookup"><span data-stu-id="44651-129">0</span></span>|
|[<span data-ttu-id="44651-130">struct</span><span class="sxs-lookup"><span data-stu-id="44651-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="44651-131">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="44651-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="44651-132">uint</span><span class="sxs-lookup"><span data-stu-id="44651-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="44651-133">0</span><span class="sxs-lookup"><span data-stu-id="44651-133">0</span></span>|
|[<span data-ttu-id="44651-134">ulong</span><span class="sxs-lookup"><span data-stu-id="44651-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="44651-135">0</span><span class="sxs-lookup"><span data-stu-id="44651-135">0</span></span>|
|[<span data-ttu-id="44651-136">ushort</span><span class="sxs-lookup"><span data-stu-id="44651-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="44651-137">0</span><span class="sxs-lookup"><span data-stu-id="44651-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="44651-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="44651-138">See also</span></span>
 [<span data-ttu-id="44651-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="44651-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="44651-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="44651-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="44651-141">Tabla de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="44651-141">Value Types Table</span></span>](../../../csharp/language-reference/keywords/value-types-table.md)  
 [<span data-ttu-id="44651-142">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="44651-142">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="44651-143">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="44651-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="44651-144">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="44651-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
