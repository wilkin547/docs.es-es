---
title: byte (Referencia de C#)
ms.date: 03/14/2017
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords:
- byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
ms.openlocfilehash: ee70b7c804423a35e2db3fe20ac4b66d8d1b98e2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505100"
---
# <a name="byte-c-reference"></a><span data-ttu-id="ad2d9-102">byte (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ad2d9-102">byte (C# Reference)</span></span>

<span data-ttu-id="ad2d9-103">`byte` denota un tipo entero que almacena valores como se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="ad2d9-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="ad2d9-104">Type</span></span>|<span data-ttu-id="ad2d9-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="ad2d9-105">Range</span></span>|<span data-ttu-id="ad2d9-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="ad2d9-106">Size</span></span>|<span data-ttu-id="ad2d9-107">Tipo de .NET</span><span class="sxs-lookup"><span data-stu-id="ad2d9-107">.NET type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="ad2d9-108">De 0 a 255</span><span class="sxs-lookup"><span data-stu-id="ad2d9-108">0 to 255</span></span>|<span data-ttu-id="ad2d9-109">Entero de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="ad2d9-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="ad2d9-110">Literales</span><span class="sxs-lookup"><span data-stu-id="ad2d9-110">Literals</span></span>  

 <span data-ttu-id="ad2d9-111">Puede declarar e inicializar una variable `byte` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7.0) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7.0) a binary literal to it.</span></span> <span data-ttu-id="ad2d9-112">Si el literal entero está fuera del intervalo de `byte` (es decir, si es inferior a <xref:System.Byte.MinValue?displayProperty=nameWithType> o mayor que <xref:System.Byte.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="ad2d9-113">En el ejemplo siguiente, los enteros que equivalen a 201 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `byte`.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="ad2d9-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="ad2d9-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="ad2d9-116">A partir de C# 7.0, se han agregado un par de características para mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-116">Starting with C# 7.0, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="ad2d9-117">C# 7.0 permite usar el carácter de subrayado, `_`, como separador de dígitos.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="ad2d9-118">C# 7.2 permite usar `_` como separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="ad2d9-119">Un literal decimal no puede tener un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="ad2d9-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="ad2d9-121">Conversiones</span><span class="sxs-lookup"><span data-stu-id="ad2d9-121">Conversions</span></span>  
 <span data-ttu-id="ad2d9-122">Hay una conversión implícita predefinida de `byte` a [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="ad2d9-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="ad2d9-123">No se pueden convertir implícitamente los tipos numéricos no literales de mayor tamaño de almacenamiento a `byte`.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="ad2d9-124">Para más información sobre los tamaños de almacenamiento de los tipos enteros, vea la [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="ad2d9-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="ad2d9-125">Considere, por ejemplo, las dos siguientes variables de `byte` `x` y `y`:</span><span class="sxs-lookup"><span data-stu-id="ad2d9-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```csharp  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="ad2d9-126">La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética del lado derecho del operador de asignación da como resultado `int` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="ad2d9-127">Para corregir este problema, use una conversión:</span><span class="sxs-lookup"><span data-stu-id="ad2d9-127">To fix this problem, use a cast:</span></span>  
  
```csharp  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="ad2d9-128">Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:</span><span class="sxs-lookup"><span data-stu-id="ad2d9-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="ad2d9-129">Además, no hay ninguna conversión implícita de tipos de punto flotante a `byte`.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="ad2d9-130">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="ad2d9-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="ad2d9-131">Al llamar a métodos sobrecargados, debe usarse una conversión.</span><span class="sxs-lookup"><span data-stu-id="ad2d9-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="ad2d9-132">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `byte` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="ad2d9-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="ad2d9-133">El uso de la conversión `byte` garantiza que se llama al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ad2d9-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="ad2d9-134">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="ad2d9-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="ad2d9-135">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="ad2d9-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ad2d9-136">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ad2d9-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad2d9-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad2d9-137">See Also</span></span>  

- <xref:System.Byte>  
- [<span data-ttu-id="ad2d9-138">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ad2d9-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ad2d9-139">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ad2d9-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ad2d9-140">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ad2d9-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ad2d9-141">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="ad2d9-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="ad2d9-142">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="ad2d9-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="ad2d9-143">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="ad2d9-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="ad2d9-144">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="ad2d9-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
