---
title: short (Referencia de C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- short
- short_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
caps.latest.revision: 17
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
ms.openlocfilehash: ab3ccfdeb8d8a67b5fcd60b1ad6eee4dcafc9691
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="short-c-reference"></a><span data-ttu-id="da0a2-102">short (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="da0a2-102">short (C# Reference)</span></span>

<span data-ttu-id="da0a2-103">`short` denota un tipo de datos integral que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da0a2-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="da0a2-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="da0a2-104">Type</span></span>|<span data-ttu-id="da0a2-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="da0a2-105">Range</span></span>|<span data-ttu-id="da0a2-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="da0a2-106">Size</span></span>|<span data-ttu-id="da0a2-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da0a2-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="da0a2-108">De -32 768 a 32 767</span><span class="sxs-lookup"><span data-stu-id="da0a2-108">-32,768 to 32,767</span></span>|<span data-ttu-id="da0a2-109">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="da0a2-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="da0a2-110">Literales</span><span class="sxs-lookup"><span data-stu-id="da0a2-110">Literals</span></span>  

<span data-ttu-id="da0a2-111">Puede declarar e inicializar una variable `short` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="da0a2-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="da0a2-112">Si el literal entero está fuera del intervalo de `short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=fullName> o mayor que <xref:System.Int16.MaxValue?displayProperty=fullName>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="da0a2-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=fullName> or greater than <xref:System.Int16.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span> 

<span data-ttu-id="da0a2-113">En el ejemplo siguiente, los enteros que equivalen a 1034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `short`.</span><span class="sxs-lookup"><span data-stu-id="da0a2-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
<span data-ttu-id="da0a2-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span><span class="sxs-lookup"><span data-stu-id="da0a2-114">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="da0a2-115">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="da0a2-115">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="da0a2-116">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="da0a2-116">Decimal literals have no prefix.</span></span>

<span data-ttu-id="da0a2-117">A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="da0a2-117">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="da0a2-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span><span class="sxs-lookup"><span data-stu-id="da0a2-118">[!code-cs[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]</span></span>  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="da0a2-119">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="da0a2-119">Compiler overload resolution</span></span>

 <span data-ttu-id="da0a2-120">Debe usarse una conversión de tipos al llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="da0a2-120">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="da0a2-121">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `short` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="da0a2-121">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="da0a2-122">El uso de la conversión `short` garantiza que se llama al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da0a2-122">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="da0a2-123">Conversiones</span><span class="sxs-lookup"><span data-stu-id="da0a2-123">Conversions</span></span>  

 <span data-ttu-id="da0a2-124">Existe una conversión implícita predefinida de `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="da0a2-124">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="da0a2-125">No se pueden convertir implícitamente tipos numéricos no literales cuyo tamaño de almacenamiento sea superior a `short` (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).</span><span class="sxs-lookup"><span data-stu-id="da0a2-125">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="da0a2-126">Considere, por ejemplo, las dos siguientes variables de `short`, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="da0a2-126">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="da0a2-127">La instrucción de asignación siguiente produce un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa como [int](../../../csharp/language-reference/keywords/int.md) de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="da0a2-127">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="da0a2-128">Para corregir este problema, use una conversión:</span><span class="sxs-lookup"><span data-stu-id="da0a2-128">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="da0a2-129">También es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:</span><span class="sxs-lookup"><span data-stu-id="da0a2-129">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="da0a2-130">No existe conversión implícita de tipos de punto flotante a `short`.</span><span class="sxs-lookup"><span data-stu-id="da0a2-130">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="da0a2-131">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="da0a2-131">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="da0a2-132">Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="da0a2-132">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="da0a2-133">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="da0a2-133">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="da0a2-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="da0a2-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da0a2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="da0a2-135">See Also</span></span>  
 <span data-ttu-id="da0a2-136"><xref:System.Int16></span><span class="sxs-lookup"><span data-stu-id="da0a2-136"><xref:System.Int16></span></span>   
 <span data-ttu-id="da0a2-137">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="da0a2-137">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="da0a2-138">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="da0a2-138">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="da0a2-139">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="da0a2-139">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="da0a2-140">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="da0a2-140">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="da0a2-141">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="da0a2-141">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="da0a2-142">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="da0a2-142">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="da0a2-143">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="da0a2-143">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

