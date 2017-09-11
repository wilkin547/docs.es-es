---
title: int (Referencia de C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- int_CSharpKeyword
- int
dev_langs:
- CSharp
helpviewer_keywords:
- int keyword [C#]
ms.assetid: 212447b4-5d2a-41aa-88ab-84fe710bdb52
caps.latest.revision: 19
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
ms.sourcegitcommit: 935428cc9442a3e1d15eeb8942176c237bff4e22
ms.openlocfilehash: 6e87893bcd9800b61297e71b782028fec5116479
ms.contentlocale: es-es
ms.lasthandoff: 08/22/2017

---
# <a name="int-c-reference"></a><span data-ttu-id="47aec-102">int (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="47aec-102">int (C# Reference)</span></span>

<span data-ttu-id="47aec-103">`int` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="47aec-103">`int` denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="47aec-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="47aec-104">Type</span></span>|<span data-ttu-id="47aec-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="47aec-105">Range</span></span>|<span data-ttu-id="47aec-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="47aec-106">Size</span></span>|<span data-ttu-id="47aec-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="47aec-107">.NET Framework type</span></span>|<span data-ttu-id="47aec-108">Default Value</span><span class="sxs-lookup"><span data-stu-id="47aec-108">Default Value</span></span>|  
|----------|-----------|----------|-------------------------|-------------------|  
|`int`|<span data-ttu-id="47aec-109">De -2.147.483.648 a 2.147.483.647</span><span class="sxs-lookup"><span data-stu-id="47aec-109">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="47aec-110">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="47aec-110">Signed 32-bit integer</span></span>|<xref:System.Int32?displayProperty=fullName>|<span data-ttu-id="47aec-111">0</span><span class="sxs-lookup"><span data-stu-id="47aec-111">0</span></span>|  
  
## <a name="literals"></a><span data-ttu-id="47aec-112">Literales</span><span class="sxs-lookup"><span data-stu-id="47aec-112">Literals</span></span>  
 
<span data-ttu-id="47aec-113">Puede declarar e inicializar una variable `int` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="47aec-113">You can declare and initialize an `int` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="47aec-114">Si el literal entero está fuera del intervalo de `int` (es decir, si es inferior a <xref:System.Int32.MinValue?displayProperty=fullName> o mayor que <xref:System.Int32.MaxValue?displayProperty=fullName>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="47aec-114">If the integer literal is outside the range of `int` (that is, if it is less than <xref:System.Int32.MinValue?displayProperty=fullName> or greater than <xref:System.Int32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="47aec-115">En el ejemplo siguiente, los enteros que equivalen a 90 946 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `int`.</span><span class="sxs-lookup"><span data-stu-id="47aec-115">In the following example, integers equal to 90,946 that are represented as decimal, hexadecimal, and binary literals are assigned to `int` values.</span></span>  
  
<span data-ttu-id="47aec-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span><span class="sxs-lookup"><span data-stu-id="47aec-116">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Int)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="47aec-117">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="47aec-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="47aec-118">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="47aec-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="47aec-119">A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="47aec-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="47aec-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span><span class="sxs-lookup"><span data-stu-id="47aec-120">[!code-cs[int](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#IntS)]</span></span>  
 
 <span data-ttu-id="47aec-121">Los literales enteros también pueden incluir un sufijo que denote el tipo, aunque no existe ningún sufijo que denote el tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="47aec-121">Integer literals can also include a suffix that denotes the type, although there is no suffix that denotes the `int` type.</span></span> <span data-ttu-id="47aec-122">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="47aec-122">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. `int`
2. [<span data-ttu-id="47aec-123">uint</span><span class="sxs-lookup"><span data-stu-id="47aec-123">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="47aec-124">long</span><span class="sxs-lookup"><span data-stu-id="47aec-124">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="47aec-125">ulong</span><span class="sxs-lookup"><span data-stu-id="47aec-125">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
 
<span data-ttu-id="47aec-126">En estos ejemplos, el literal 90946 es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="47aec-126">In these examples, the literal 90946 is of type `int`.</span></span>
  
## <a name="conversions"></a><span data-ttu-id="47aec-127">Conversiones</span><span class="sxs-lookup"><span data-stu-id="47aec-127">Conversions</span></span>  
 <span data-ttu-id="47aec-128">Hay una conversión implícita predefinida de `int` a [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="47aec-128">There is a predefined implicit conversion from `int` to [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="47aec-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="47aec-129">For example:</span></span>  
  
```csharp  
// '123' is an int, so an implicit conversion takes place here:  
float f = 123;  
```  
  
 <span data-ttu-id="47aec-130">Hay una conversión implícita predefinida de [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `int`.</span><span class="sxs-lookup"><span data-stu-id="47aec-130">There is a predefined implicit conversion from [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `int`.</span></span> <span data-ttu-id="47aec-131">Por ejemplo, la instrucción de asignación siguiente producirá un error de compilación sin una conversión:</span><span class="sxs-lookup"><span data-stu-id="47aec-131">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
int i1 = aLong;       // Error: no implicit conversion from long.  
int i2 = (int)aLong;  // OK: explicit conversion.  
```  
  
 <span data-ttu-id="47aec-132">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `int`.</span><span class="sxs-lookup"><span data-stu-id="47aec-132">Notice also that there is no implicit conversion from floating-point types to `int`.</span></span> <span data-ttu-id="47aec-133">Por ejemplo, la instrucción siguiente genera un error del compilador a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="47aec-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
int x = 3.0;         // Error: no implicit conversion from double.  
int y = (int)3.0;    // OK: explicit conversion.  
```  
  
 <span data-ttu-id="47aec-134">Para obtener más información sobre las expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="47aec-134">For more information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="47aec-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="47aec-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="47aec-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="47aec-136">See Also</span></span>  
 <span data-ttu-id="47aec-137"><xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="47aec-137"><xref:System.Int32></span></span>   
 <span data-ttu-id="47aec-138">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="47aec-138">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="47aec-139">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="47aec-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="47aec-140">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="47aec-140">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="47aec-141">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="47aec-141">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="47aec-142">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="47aec-142">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="47aec-143">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="47aec-143">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="47aec-144">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="47aec-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

