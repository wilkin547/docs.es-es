---
title: Tabla de valores predeterminados (Referencia de C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
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
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e249dd2f352fe6177f3afbfd089fc4dc9b1b7798
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="c7418-102">Tabla de valores predeterminados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c7418-102">Default values table (C# Reference)</span></span>

<span data-ttu-id="c7418-103">En la siguiente tabla se muestran los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c7418-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="c7418-104">Los constructores predeterminados se invocan mediante el operador `new`, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7418-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="c7418-105">La instrucción anterior tiene el mismo efecto que la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="c7418-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="c7418-106">Recuerde que no se permite el uso de variables sin inicializar en C#.</span><span class="sxs-lookup"><span data-stu-id="c7418-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="c7418-107">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="c7418-107">Value type</span></span>|<span data-ttu-id="c7418-108">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="c7418-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="c7418-109">bool</span><span class="sxs-lookup"><span data-stu-id="c7418-109">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="c7418-110">byte</span><span class="sxs-lookup"><span data-stu-id="c7418-110">byte</span></span>](byte.md)|<span data-ttu-id="c7418-111">0</span><span class="sxs-lookup"><span data-stu-id="c7418-111">0</span></span>|
|[<span data-ttu-id="c7418-112">char</span><span class="sxs-lookup"><span data-stu-id="c7418-112">char</span></span>](char.md)|<span data-ttu-id="c7418-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="c7418-113">'\0'</span></span>|
|[<span data-ttu-id="c7418-114">decimal</span><span class="sxs-lookup"><span data-stu-id="c7418-114">decimal</span></span>](decimal.md)|<span data-ttu-id="c7418-115">0M</span><span class="sxs-lookup"><span data-stu-id="c7418-115">0M</span></span>|
|[<span data-ttu-id="c7418-116">double</span><span class="sxs-lookup"><span data-stu-id="c7418-116">double</span></span>](double.md)|<span data-ttu-id="c7418-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="c7418-117">0.0D</span></span>|
|[<span data-ttu-id="c7418-118">enum</span><span class="sxs-lookup"><span data-stu-id="c7418-118">enum</span></span>](enum.md)|<span data-ttu-id="c7418-119">El valor generado por la expresión (E)0, donde E es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="c7418-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="c7418-120">float</span><span class="sxs-lookup"><span data-stu-id="c7418-120">float</span></span>](float.md)|<span data-ttu-id="c7418-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="c7418-121">0.0F</span></span>|
|[<span data-ttu-id="c7418-122">int</span><span class="sxs-lookup"><span data-stu-id="c7418-122">int</span></span>](int.md)|<span data-ttu-id="c7418-123">0</span><span class="sxs-lookup"><span data-stu-id="c7418-123">0</span></span>|
|[<span data-ttu-id="c7418-124">long</span><span class="sxs-lookup"><span data-stu-id="c7418-124">long</span></span>](long.md)|<span data-ttu-id="c7418-125">0L</span><span class="sxs-lookup"><span data-stu-id="c7418-125">0L</span></span>|
|[<span data-ttu-id="c7418-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="c7418-126">sbyte</span></span>](sbyte.md)|<span data-ttu-id="c7418-127">0</span><span class="sxs-lookup"><span data-stu-id="c7418-127">0</span></span>|
|[<span data-ttu-id="c7418-128">short</span><span class="sxs-lookup"><span data-stu-id="c7418-128">short</span></span>](short.md)|<span data-ttu-id="c7418-129">0</span><span class="sxs-lookup"><span data-stu-id="c7418-129">0</span></span>|
|[<span data-ttu-id="c7418-130">struct</span><span class="sxs-lookup"><span data-stu-id="c7418-130">struct</span></span>](struct.md)|<span data-ttu-id="c7418-131">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="c7418-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="c7418-132">uint</span><span class="sxs-lookup"><span data-stu-id="c7418-132">uint</span></span>](uint.md)|<span data-ttu-id="c7418-133">0</span><span class="sxs-lookup"><span data-stu-id="c7418-133">0</span></span>|
|[<span data-ttu-id="c7418-134">ulong</span><span class="sxs-lookup"><span data-stu-id="c7418-134">ulong</span></span>](ulong.md)|<span data-ttu-id="c7418-135">0</span><span class="sxs-lookup"><span data-stu-id="c7418-135">0</span></span>|
|[<span data-ttu-id="c7418-136">ushort</span><span class="sxs-lookup"><span data-stu-id="c7418-136">ushort</span></span>](ushort.md)|<span data-ttu-id="c7418-137">0</span><span class="sxs-lookup"><span data-stu-id="c7418-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="c7418-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7418-138">See also</span></span>
 [<span data-ttu-id="c7418-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c7418-139">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="c7418-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c7418-140">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="c7418-141">Tabla de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="c7418-141">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="c7418-142">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="c7418-142">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="c7418-143">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="c7418-143">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="c7418-144">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="c7418-144">Reference Tables for Types</span></span>](reference-tables-for-types.md)
