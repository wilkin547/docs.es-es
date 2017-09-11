---
title: ulong (Referencia de C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
dev_langs:
- CSharp
helpviewer_keywords:
- ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c2da253e4da7a5d6cfa71116e4fcba7816441e92
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ulong-c-reference"></a><span data-ttu-id="026ae-102">ulong (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="026ae-102">ulong (C# Reference)</span></span>

<span data-ttu-id="026ae-103">La palabra clave `ulong` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="026ae-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="026ae-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="026ae-104">Type</span></span>|<span data-ttu-id="026ae-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="026ae-105">Range</span></span>|<span data-ttu-id="026ae-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="026ae-106">Size</span></span>|<span data-ttu-id="026ae-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="026ae-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="026ae-108">De 0 a 18.446.744.073.709.551.615</span><span class="sxs-lookup"><span data-stu-id="026ae-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="026ae-109">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="026ae-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="026ae-110">Literales</span><span class="sxs-lookup"><span data-stu-id="026ae-110">Literals</span></span>  

<span data-ttu-id="026ae-111">Puede declarar e inicializar una variable `ulong` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="026ae-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="026ae-112">Si el literal entero está fuera del intervalo de `ulong` (es decir, si es inferior a <xref:System.UInt64.MinValue?displayProperty=fullName> o mayor que <xref:System.UInt64.MaxValue?displayProperty=fullName>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="026ae-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=fullName> or greater than <xref:System.UInt64.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="026ae-113">En el ejemplo siguiente, los enteros que equivalen a 7 934 076 125 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `ulong`.</span><span class="sxs-lookup"><span data-stu-id="026ae-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
<span data-ttu-id="026ae-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span><span class="sxs-lookup"><span data-stu-id="026ae-114">[!code-cs[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="026ae-115">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="026ae-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="026ae-116">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="026ae-116">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="026ae-117">A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="026ae-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="026ae-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span><span class="sxs-lookup"><span data-stu-id="026ae-118">[!code-cs[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]</span></span>  
 
 <span data-ttu-id="026ae-119">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="026ae-119">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="026ae-120">El sufijo `UL` o `ul` identifica de manera inequívoca un literal numérico como un valor `ulong`.</span><span class="sxs-lookup"><span data-stu-id="026ae-120">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="026ae-121">El sufijo `L` denota un `ulong` si el valor literal supera <xref:System.Int64.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="026ae-121">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="026ae-122">Y el sufijo `U` o `u` denota un `ulong` si el valor literal supera <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="026ae-122">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span> <span data-ttu-id="026ae-123">En el ejemplo siguiente se usa el sufijo `ul` para denotar un entero largo:</span><span class="sxs-lookup"><span data-stu-id="026ae-123">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
<span data-ttu-id="026ae-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="026ae-124">[!code-cs[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]</span></span>

<span data-ttu-id="026ae-125">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="026ae-125">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="026ae-126">int</span><span class="sxs-lookup"><span data-stu-id="026ae-126">int</span></span>](int.md)
2. [<span data-ttu-id="026ae-127">uint</span><span class="sxs-lookup"><span data-stu-id="026ae-127">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="026ae-128">long</span><span class="sxs-lookup"><span data-stu-id="026ae-128">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="026ae-129">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="026ae-129">Compiler overload resolution</span></span>
  
 <span data-ttu-id="026ae-130">El sufijo se usa habitualmente en las llamadas a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="026ae-130">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="026ae-131">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ulong` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="026ae-131">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="026ae-132">Si se usa un sufijo con el parámetro `ulong`, se garantiza la llamada al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="026ae-132">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="026ae-133">Conversiones</span><span class="sxs-lookup"><span data-stu-id="026ae-133">Conversions</span></span>  
 <span data-ttu-id="026ae-134">Existe una conversión implícita predefinida de `ulong` a [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="026ae-134">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="026ae-135">No existe conversión implícita de `ulong` a cualquier tipo entero.</span><span class="sxs-lookup"><span data-stu-id="026ae-135">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="026ae-136">Por ejemplo, la instrucción siguiente producirá un error de compilación sin una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="026ae-136">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="026ae-137">Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="026ae-137">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="026ae-138">Además, no hay ninguna conversión implícita de tipos de punto flotante a `ulong`.</span><span class="sxs-lookup"><span data-stu-id="026ae-138">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="026ae-139">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="026ae-139">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="026ae-140">Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="026ae-140">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="026ae-141">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="026ae-141">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="026ae-142">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="026ae-142">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="026ae-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="026ae-143">See Also</span></span>  
 <span data-ttu-id="026ae-144"><xref:System.UInt64></span><span class="sxs-lookup"><span data-stu-id="026ae-144"><xref:System.UInt64></span></span>   
 <span data-ttu-id="026ae-145">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="026ae-145">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="026ae-146">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="026ae-146">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="026ae-147">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="026ae-147">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="026ae-148">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="026ae-148">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="026ae-149">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="026ae-149">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="026ae-150">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="026ae-150">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="026ae-151">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="026ae-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

