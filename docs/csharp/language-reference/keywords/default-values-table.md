---
title: Tabla de valores predeterminados (Referencia de C#)
descripton: Learn what are the default values of value types returned by the default constructors.
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
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
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: f8cf12317f1f0163028db003ff31604480da5d1c
ms.openlocfilehash: 975d416259778e0741347829d8a9c79aaa6cfc8c
ms.contentlocale: es-es
ms.lasthandoff: 08/12/2017

---
# <a name="default-values-table-c-reference"></a><span data-ttu-id="fe6da-102">Tabla de valores predeterminados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fe6da-102">Default values table (C# Reference)</span></span>
<span data-ttu-id="fe6da-103">En la siguiente tabla se muestran los valores predeterminados de los tipos de valor devueltos por los constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="fe6da-103">The following table shows the default values of value types returned by the default constructors.</span></span> <span data-ttu-id="fe6da-104">Los constructores predeterminados se invocan mediante el operador `new`, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe6da-104">Default constructors are invoked by using the `new` operator, as follows:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="fe6da-105">La instrucción anterior tiene el mismo efecto que la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe6da-105">The preceding statement has the same effect as the following statement:</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="fe6da-106">Recuerde que no se permite el uso de variables sin inicializar en C#.</span><span class="sxs-lookup"><span data-stu-id="fe6da-106">Remember that using uninitialized variables in C# is not allowed.</span></span>

|<span data-ttu-id="fe6da-107">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="fe6da-107">Value type</span></span>|<span data-ttu-id="fe6da-108">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="fe6da-108">Default value</span></span>|
|----------------|-------------------|
|[<span data-ttu-id="fe6da-109">bool</span><span class="sxs-lookup"><span data-stu-id="fe6da-109">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`false`|
|[<span data-ttu-id="fe6da-110">byte</span><span class="sxs-lookup"><span data-stu-id="fe6da-110">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="fe6da-111">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-111">0</span></span>|
|[<span data-ttu-id="fe6da-112">char</span><span class="sxs-lookup"><span data-stu-id="fe6da-112">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="fe6da-113">'\0'</span><span class="sxs-lookup"><span data-stu-id="fe6da-113">'\0'</span></span>|
|[<span data-ttu-id="fe6da-114">decimal</span><span class="sxs-lookup"><span data-stu-id="fe6da-114">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|<span data-ttu-id="fe6da-115">0.0M</span><span class="sxs-lookup"><span data-stu-id="fe6da-115">0.0M</span></span>|
|[<span data-ttu-id="fe6da-116">double</span><span class="sxs-lookup"><span data-stu-id="fe6da-116">double</span></span>](../../../csharp/language-reference/keywords/double.md)|<span data-ttu-id="fe6da-117">0.0D</span><span class="sxs-lookup"><span data-stu-id="fe6da-117">0.0D</span></span>|
|[<span data-ttu-id="fe6da-118">enum</span><span class="sxs-lookup"><span data-stu-id="fe6da-118">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)|<span data-ttu-id="fe6da-119">El valor generado por la expresión (E)0, donde E es el identificador de enumeración.</span><span class="sxs-lookup"><span data-stu-id="fe6da-119">The value produced by the expression (E)0, where E is the enum identifier.</span></span>|
|[<span data-ttu-id="fe6da-120">float</span><span class="sxs-lookup"><span data-stu-id="fe6da-120">float</span></span>](../../../csharp/language-reference/keywords/float.md)|<span data-ttu-id="fe6da-121">0.0F</span><span class="sxs-lookup"><span data-stu-id="fe6da-121">0.0F</span></span>|
|[<span data-ttu-id="fe6da-122">int</span><span class="sxs-lookup"><span data-stu-id="fe6da-122">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="fe6da-123">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-123">0</span></span>|
|[<span data-ttu-id="fe6da-124">long</span><span class="sxs-lookup"><span data-stu-id="fe6da-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="fe6da-125">0L</span><span class="sxs-lookup"><span data-stu-id="fe6da-125">0L</span></span>|
|[<span data-ttu-id="fe6da-126">sbyte</span><span class="sxs-lookup"><span data-stu-id="fe6da-126">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="fe6da-127">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-127">0</span></span>|
|[<span data-ttu-id="fe6da-128">short</span><span class="sxs-lookup"><span data-stu-id="fe6da-128">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="fe6da-129">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-129">0</span></span>|
|[<span data-ttu-id="fe6da-130">struct</span><span class="sxs-lookup"><span data-stu-id="fe6da-130">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)|<span data-ttu-id="fe6da-131">El valor generado al establecer todos los campos de tipo de valor en sus valores predeterminados y todos los campos de tipo de referencia en `null`.</span><span class="sxs-lookup"><span data-stu-id="fe6da-131">The value produced by setting all value-type fields to their default values and all reference-type fields to `null`.</span></span>|
|[<span data-ttu-id="fe6da-132">uint</span><span class="sxs-lookup"><span data-stu-id="fe6da-132">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="fe6da-133">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-133">0</span></span>|
|[<span data-ttu-id="fe6da-134">ulong</span><span class="sxs-lookup"><span data-stu-id="fe6da-134">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="fe6da-135">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-135">0</span></span>|
|[<span data-ttu-id="fe6da-136">ushort</span><span class="sxs-lookup"><span data-stu-id="fe6da-136">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="fe6da-137">0</span><span class="sxs-lookup"><span data-stu-id="fe6da-137">0</span></span>|

## <a name="see-also"></a><span data-ttu-id="fe6da-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6da-138">See also</span></span>
 <span data-ttu-id="fe6da-139">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe6da-139">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="fe6da-140">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="fe6da-140">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="fe6da-141">[Tabla de tipos de valor](../../../csharp/language-reference/keywords/value-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="fe6da-141">[Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md) </span></span>  
 <span data-ttu-id="fe6da-142">[Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="fe6da-142">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="fe6da-143">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="fe6da-143">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 [<span data-ttu-id="fe6da-144">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="fe6da-144">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

