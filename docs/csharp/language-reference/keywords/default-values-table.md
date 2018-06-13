---
title: Tabla de valores predeterminados (Referencia de C#)
description: Sepa cuáles son los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], return values
- keywords [C#], new
- default constructor [C#]
- defaults [C#]
- value types [C#], initializing
- variables [C#], value types
- constructors [C#], default constructor
- types [C#], default constructor return values
ms.openlocfilehash: 634a55304534b4269487f29be1fbb4930f51d8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218795"
---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="153a1-103">Tabla de valores predeterminados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="153a1-103">Default values table (C# Reference)</span></span>

<span data-ttu-id="153a1-104">En la siguiente tabla se muestran los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="153a1-104">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="153a1-105">Los constructores predeterminados se invocan mediante el operador `new`, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="153a1-105">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="153a1-106">La instrucción anterior tiene el mismo efecto que la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="153a1-106">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="153a1-107">Recuerde que no se permite el uso de variables sin inicializar en C#.</span><span class="sxs-lookup"><span data-stu-id="153a1-107">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="153a1-108">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="153a1-108">Value type</span></span>|<span data-ttu-id="153a1-109">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="153a1-109">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="153a1-110">bool</span><span class="sxs-lookup"><span data-stu-id="153a1-110">bool</span></span>](bool.md)|`false`|
|[<span data-ttu-id="153a1-111">byte</span><span class="sxs-lookup"><span data-stu-id="153a1-111">byte</span></span>](byte.md)|<span data-ttu-id="153a1-112">0</span><span class="sxs-lookup"><span data-stu-id="153a1-112">0</span></span>|
|[<span data-ttu-id="153a1-113">char</span><span class="sxs-lookup"><span data-stu-id="153a1-113">char</span></span>](char.md)|<span data-ttu-id="153a1-114">'\0'</span><span class="sxs-lookup"><span data-stu-id="153a1-114">'\0'</span></span>|
|[<span data-ttu-id="153a1-115">decimal</span><span class="sxs-lookup"><span data-stu-id="153a1-115">decimal</span></span>](decimal.md)|<span data-ttu-id="153a1-116">0M</span><span class="sxs-lookup"><span data-stu-id="153a1-116">0M</span></span>|
|[<span data-ttu-id="153a1-117">double</span><span class="sxs-lookup"><span data-stu-id="153a1-117">double</span></span>](double.md)|<span data-ttu-id="153a1-118">0.0D</span><span class="sxs-lookup"><span data-stu-id="153a1-118">0.0D</span></span>|
|[<span data-ttu-id="153a1-119">enum</span><span class="sxs-lookup"><span data-stu-id="153a1-119">enum</span></span>](enum.md)|<span data-ttu-id="153a1-120">El valor generado por la expresión (E)0, donde E es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="153a1-120">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="153a1-121">float</span><span class="sxs-lookup"><span data-stu-id="153a1-121">float</span></span>](float.md)|<span data-ttu-id="153a1-122">0.0F</span><span class="sxs-lookup"><span data-stu-id="153a1-122">0.0F</span></span>|
|[<span data-ttu-id="153a1-123">int</span><span class="sxs-lookup"><span data-stu-id="153a1-123">int</span></span>](int.md)|<span data-ttu-id="153a1-124">0</span><span class="sxs-lookup"><span data-stu-id="153a1-124">0</span></span>|
|[<span data-ttu-id="153a1-125">long</span><span class="sxs-lookup"><span data-stu-id="153a1-125">long</span></span>](long.md)|<span data-ttu-id="153a1-126">0L</span><span class="sxs-lookup"><span data-stu-id="153a1-126">0L</span></span>|
|[<span data-ttu-id="153a1-127">sbyte</span><span class="sxs-lookup"><span data-stu-id="153a1-127">sbyte</span></span>](sbyte.md)|<span data-ttu-id="153a1-128">0</span><span class="sxs-lookup"><span data-stu-id="153a1-128">0</span></span>|
|[<span data-ttu-id="153a1-129">short</span><span class="sxs-lookup"><span data-stu-id="153a1-129">short</span></span>](short.md)|<span data-ttu-id="153a1-130">0</span><span class="sxs-lookup"><span data-stu-id="153a1-130">0</span></span>|
|[<span data-ttu-id="153a1-131">struct</span><span class="sxs-lookup"><span data-stu-id="153a1-131">struct</span></span>](struct.md)|<span data-ttu-id="153a1-132">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="153a1-132">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="153a1-133">uint</span><span class="sxs-lookup"><span data-stu-id="153a1-133">uint</span></span>](uint.md)|<span data-ttu-id="153a1-134">0</span><span class="sxs-lookup"><span data-stu-id="153a1-134">0</span></span>|
|[<span data-ttu-id="153a1-135">ulong</span><span class="sxs-lookup"><span data-stu-id="153a1-135">ulong</span></span>](ulong.md)|<span data-ttu-id="153a1-136">0</span><span class="sxs-lookup"><span data-stu-id="153a1-136">0</span></span>|
|[<span data-ttu-id="153a1-137">ushort</span><span class="sxs-lookup"><span data-stu-id="153a1-137">ushort</span></span>](ushort.md)|<span data-ttu-id="153a1-138">0</span><span class="sxs-lookup"><span data-stu-id="153a1-138">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="153a1-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="153a1-139">See also</span></span>
 [<span data-ttu-id="153a1-140">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="153a1-140">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="153a1-141">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="153a1-141">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="153a1-142">Tabla de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="153a1-142">Value Types Table</span></span>](value-types-table.md)  
 [<span data-ttu-id="153a1-143">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="153a1-143">Value Types</span></span>](value-types.md)  
 [<span data-ttu-id="153a1-144">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="153a1-144">Built-In Types Table</span></span>](built-in-types-table.md)  
 [<span data-ttu-id="153a1-145">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="153a1-145">Reference Tables for Types</span></span>](reference-tables-for-types.md)
