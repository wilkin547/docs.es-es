---
title: Tabla de tipos integrados (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 120347e5bff7f0d6c7120af0cb250936ca39ea16
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="bcb35-102">Tabla de tipos integrados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bcb35-102">Built-In Types Table (C# Reference)</span></span>
<span data-ttu-id="bcb35-103">En la siguiente tabla se muestran las palabras clave para los tipos de C# integrados, que son alias de los tipos predefinidos en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="bcb35-103">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="bcb35-104">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="bcb35-104">C# Type</span></span>|<span data-ttu-id="bcb35-105">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bcb35-105">.NET Framework Type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="bcb35-106">bool</span><span class="sxs-lookup"><span data-stu-id="bcb35-106">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[<span data-ttu-id="bcb35-107">byte</span><span class="sxs-lookup"><span data-stu-id="bcb35-107">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[<span data-ttu-id="bcb35-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="bcb35-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[<span data-ttu-id="bcb35-109">char</span><span class="sxs-lookup"><span data-stu-id="bcb35-109">char</span></span>](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[<span data-ttu-id="bcb35-110">decimal</span><span class="sxs-lookup"><span data-stu-id="bcb35-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[<span data-ttu-id="bcb35-111">double</span><span class="sxs-lookup"><span data-stu-id="bcb35-111">double</span></span>](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[<span data-ttu-id="bcb35-112">float</span><span class="sxs-lookup"><span data-stu-id="bcb35-112">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[<span data-ttu-id="bcb35-113">int</span><span class="sxs-lookup"><span data-stu-id="bcb35-113">int</span></span>](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[<span data-ttu-id="bcb35-114">uint</span><span class="sxs-lookup"><span data-stu-id="bcb35-114">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[<span data-ttu-id="bcb35-115">long</span><span class="sxs-lookup"><span data-stu-id="bcb35-115">long</span></span>](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[<span data-ttu-id="bcb35-116">ulong</span><span class="sxs-lookup"><span data-stu-id="bcb35-116">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[<span data-ttu-id="bcb35-117">object</span><span class="sxs-lookup"><span data-stu-id="bcb35-117">object</span></span>](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[<span data-ttu-id="bcb35-118">short</span><span class="sxs-lookup"><span data-stu-id="bcb35-118">short</span></span>](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[<span data-ttu-id="bcb35-119">ushort</span><span class="sxs-lookup"><span data-stu-id="bcb35-119">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[<span data-ttu-id="bcb35-120">string</span><span class="sxs-lookup"><span data-stu-id="bcb35-120">string</span></span>](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a><span data-ttu-id="bcb35-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bcb35-121">Remarks</span></span>  
 <span data-ttu-id="bcb35-122">A todos los tipos de la tabla, excepto `object` y `string`, se les hace referencia como tipos simples.</span><span class="sxs-lookup"><span data-stu-id="bcb35-122">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
 <span data-ttu-id="bcb35-123">Las palabras clave de tipo de C# y sus alias son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="bcb35-123">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="bcb35-124">Por ejemplo, puede declarar una variable de entero con cualquiera de las siguientes declaraciones:</span><span class="sxs-lookup"><span data-stu-id="bcb35-124">For example, you can declare an integer variable by using either of the following declarations:</span></span>  
  
```csharp  
int x = 123;  
System.Int32 x = 123;  
```  
  
 <span data-ttu-id="bcb35-125">Para mostrar el tipo actual de cualquier tipo de C#, use el método del sistema `GetType()`.</span><span class="sxs-lookup"><span data-stu-id="bcb35-125">To display the actual type for any C# type, use the system method `GetType()`.</span></span> <span data-ttu-id="bcb35-126">Por ejemplo, la instrucción siguiente muestra el alias de sistema que representa el tipo de `myVariable`:</span><span class="sxs-lookup"><span data-stu-id="bcb35-126">For example, the following statement displays the system alias that represents the type of `myVariable`:</span></span>  
  
```csharp  
Console.WriteLine(myVariable.GetType());  
```  
  
 <span data-ttu-id="bcb35-127">También puede usar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md).</span><span class="sxs-lookup"><span data-stu-id="bcb35-127">You can also use the [typeof](../../../csharp/language-reference/keywords/typeof.md) operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb35-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcb35-128">See Also</span></span>  
 [<span data-ttu-id="bcb35-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bcb35-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="bcb35-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bcb35-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bcb35-131">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="bcb35-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="bcb35-132">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="bcb35-132">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="bcb35-133">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="bcb35-133">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="bcb35-134">Tabla de formatos de presentación para valores numéricos</span><span class="sxs-lookup"><span data-stu-id="bcb35-134">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)  
 [<span data-ttu-id="bcb35-135">dynamic</span><span class="sxs-lookup"><span data-stu-id="bcb35-135">dynamic</span></span>](../../../csharp/language-reference/keywords/dynamic.md)  
 [<span data-ttu-id="bcb35-136">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="bcb35-136">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)
