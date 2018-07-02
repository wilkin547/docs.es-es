---
title: short (Referencia de C#)
ms.date: 03/14/2017
f1_keywords:
- short
- short_CSharpKeyword
helpviewer_keywords:
- short keyword [C#]
ms.assetid: 04c10688-e51a-4a87-bfec-83f7fb42ff11
ms.openlocfilehash: 7991259aadd391288caa37b35addd6e16e234878
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37027868"
---
# <a name="short-c-reference"></a><span data-ttu-id="63ba8-102">short (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="63ba8-102">short (C# Reference)</span></span>

<span data-ttu-id="63ba8-103">`short` denota un tipo de datos integral que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="63ba8-103">`short` denotes an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="63ba8-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="63ba8-104">Type</span></span>|<span data-ttu-id="63ba8-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="63ba8-105">Range</span></span>|<span data-ttu-id="63ba8-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="63ba8-106">Size</span></span>|<span data-ttu-id="63ba8-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="63ba8-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`short`|<span data-ttu-id="63ba8-108">De -32 768 a 32 767</span><span class="sxs-lookup"><span data-stu-id="63ba8-108">-32,768 to 32,767</span></span>|<span data-ttu-id="63ba8-109">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="63ba8-109">Signed 16-bit integer</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="63ba8-110">Literales</span><span class="sxs-lookup"><span data-stu-id="63ba8-110">Literals</span></span>  

<span data-ttu-id="63ba8-111">Puede declarar e inicializar una variable `short` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="63ba8-111">You can declare and initialize a `short` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span>  <span data-ttu-id="63ba8-112">Si el literal entero está fuera del intervalo de `short` (es decir, si es inferior a <xref:System.Int16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Int16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="63ba8-112">If the integer literal is outside the range of `short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="63ba8-113">En el ejemplo siguiente, los enteros que equivalen a 1034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `short`.</span><span class="sxs-lookup"><span data-stu-id="63ba8-113">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `short` values.</span></span>  
  
[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Short)]  

> [!NOTE] 
> <span data-ttu-id="63ba8-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="63ba8-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="63ba8-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="63ba8-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="63ba8-116">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="63ba8-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="63ba8-117">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="63ba8-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="63ba8-118">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="63ba8-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="63ba8-119">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="63ba8-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="63ba8-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="63ba8-120">Some examples are shown below.</span></span>

[!code-csharp[Short](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="63ba8-121">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="63ba8-121">Compiler overload resolution</span></span>

 <span data-ttu-id="63ba8-122">Debe usarse una conversión de tipos al llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="63ba8-122">A cast must be used when calling overloaded methods.</span></span> <span data-ttu-id="63ba8-123">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `short` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="63ba8-123">Consider, for example, the following overloaded methods that use `short` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(short s) {}  
```  
  
 <span data-ttu-id="63ba8-124">El uso de la conversión `short` garantiza que se llama al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="63ba8-124">Using the `short` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);         // Calling the method with the int parameter  
SampleMethod((short)5);  // Calling the method with the short parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="63ba8-125">Conversiones</span><span class="sxs-lookup"><span data-stu-id="63ba8-125">Conversions</span></span>  

 <span data-ttu-id="63ba8-126">Existe una conversión implícita predefinida de `short` a [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="63ba8-126">There is a predefined implicit conversion from `short` to [int](../../../csharp/language-reference/keywords/int.md), [long](../../../csharp/language-reference/keywords/long.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="63ba8-127">No se pueden convertir implícitamente tipos numéricos no literales cuyo tamaño de almacenamiento sea superior a `short` (vea [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) para conocer los tamaños de almacenamiento de los tipos enteros).</span><span class="sxs-lookup"><span data-stu-id="63ba8-127">You cannot implicitly convert nonliteral numeric types of larger storage size to `short` (see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) for the storage sizes of integral types).</span></span> <span data-ttu-id="63ba8-128">Considere, por ejemplo, las dos siguientes variables de `short`, `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="63ba8-128">Consider, for example, the following two `short` variables `x` and `y`:</span></span>  
  
```csharp  
short x = 5, y = 12;  
```  
  
 <span data-ttu-id="63ba8-129">La instrucción de asignación siguiente produce un error de compilación, ya que la expresión aritmética del lado derecho del operador de asignación se evalúa como [int](../../../csharp/language-reference/keywords/int.md) de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="63ba8-129">The following assignment statement produces a compilation error because the arithmetic expression on the right-hand side of the assignment operator evaluates to [int](../../../csharp/language-reference/keywords/int.md) by default.</span></span>  
  
```csharp
short z  = x + y;        // Compiler error CS0266: no conversion from int to short
```

 <span data-ttu-id="63ba8-130">Para corregir este problema, use una conversión:</span><span class="sxs-lookup"><span data-stu-id="63ba8-130">To fix this problem, use a cast:</span></span>  
  
```csharp
short z  = (short)(x + y);   // Explicit conversion
```
  
 <span data-ttu-id="63ba8-131">También es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:</span><span class="sxs-lookup"><span data-stu-id="63ba8-131">It is also possible to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="63ba8-132">No existe conversión implícita de tipos de punto flotante a `short`.</span><span class="sxs-lookup"><span data-stu-id="63ba8-132">There is no implicit conversion from floating-point types to `short`.</span></span> <span data-ttu-id="63ba8-133">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="63ba8-133">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
short x = 3.0;          // Error: no implicit conversion from double  
short y = (short)3.0;   // OK: explicit conversion  
```  
  
 <span data-ttu-id="63ba8-134">Para más información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="63ba8-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="63ba8-135">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="63ba8-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="63ba8-136">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="63ba8-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="63ba8-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ba8-137">See Also</span></span>  
 <xref:System.Int16>  
 [<span data-ttu-id="63ba8-138">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="63ba8-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="63ba8-139">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="63ba8-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="63ba8-140">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="63ba8-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="63ba8-141">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="63ba8-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="63ba8-142">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="63ba8-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="63ba8-143">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="63ba8-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="63ba8-144">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="63ba8-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
