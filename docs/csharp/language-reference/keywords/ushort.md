---
title: ushort (Referencia de C#)
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ushort
- ushort_CSharpKeyword
helpviewer_keywords: ushort keyword [C#]
ms.assetid: 1a7dbaae-b7a0-4111-872a-c88a6d3981ac
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 83fa657303e8392997b04b7d80cdbcdbf39de887
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ushort-c-reference"></a><span data-ttu-id="4385a-102">ushort (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4385a-102">ushort (C# Reference)</span></span>

<span data-ttu-id="4385a-103">La palabra clave `ushort` indica un tipo de datos entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="4385a-103">The `ushort` keyword indicates an integral data type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="4385a-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="4385a-104">Type</span></span>|<span data-ttu-id="4385a-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="4385a-105">Range</span></span>|<span data-ttu-id="4385a-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="4385a-106">Size</span></span>|<span data-ttu-id="4385a-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4385a-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ushort`|<span data-ttu-id="4385a-108">De 0 a 65.535</span><span class="sxs-lookup"><span data-stu-id="4385a-108">0 to 65,535</span></span>|<span data-ttu-id="4385a-109">Entero de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="4385a-109">Unsigned 16-bit integer</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="4385a-110">Literales</span><span class="sxs-lookup"><span data-stu-id="4385a-110">Literals</span></span>  

<span data-ttu-id="4385a-111">Puede declarar e inicializar una variable `ushort` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="4385a-111">You can declare and initialize a `ushort` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="4385a-112">Si el literal entero está fuera del intervalo de `ushort` (es decir, si es inferior a <xref:System.UInt16.MinValue?displayProperty=nameWithType> o mayor que <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="4385a-112">If the integer literal is outside the range of `ushort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="4385a-113">En el ejemplo siguiente, los enteros que equivalen a 65 034 que se representan como literales binarios, hexadecimales y decimales se convierten implícitamente de [int](../../../csharp/language-reference/keywords/int.md) a valores `ushort`.</span><span class="sxs-lookup"><span data-stu-id="4385a-113">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `ushort` values.</span></span>    
  
[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShort)]  

> [!NOTE] 
> <span data-ttu-id="4385a-114">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="4385a-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="4385a-115">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="4385a-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="4385a-116">A partir de C# 7, se han agregado un par de características mejorar la legibilidad.</span><span class="sxs-lookup"><span data-stu-id="4385a-116">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="4385a-117">C# 7.0 permite el uso del carácter de subrayado, `_`, como un separador de dígito.</span><span class="sxs-lookup"><span data-stu-id="4385a-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="4385a-118">7.2 C# permite `_` para usarse como un separador de dígitos de un literal binario o hexadecimal, después del prefijo.</span><span class="sxs-lookup"><span data-stu-id="4385a-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="4385a-119">Un literal decimal no está permitido que tengan un carácter de subrayado inicial.</span><span class="sxs-lookup"><span data-stu-id="4385a-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="4385a-120">A continuación se muestran algunos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4385a-120">Some examples are shown below.</span></span>

[!code-csharp[UShort](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UShortS)]  
 
## <a name="compiler-overload-resolution"></a><span data-ttu-id="4385a-121">Resolución de sobrecarga del compilador</span><span class="sxs-lookup"><span data-stu-id="4385a-121">Compiler overload resolution</span></span>
  
 <span data-ttu-id="4385a-122">Debe usarse una conversión al llamar a métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="4385a-122">A cast must be used when you call overloaded methods.</span></span> <span data-ttu-id="4385a-123">Por ejemplo, considere los siguientes métodos sobrecargados que usan parámetros `ushort` e [int](../../../csharp/language-reference/keywords/int.md):</span><span class="sxs-lookup"><span data-stu-id="4385a-123">Consider, for example, the following overloaded methods that use `ushort` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ushort s) {}  
```  
 
 <span data-ttu-id="4385a-124">El uso de la conversión `ushort` garantiza que se llama al tipo correcto, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4385a-124">Using the `ushort` cast guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
// Calls the method with the int parameter:  
SampleMethod(5);  
// Calls the method with the ushort parameter:  
SampleMethod((ushort)5);    
```  
  
## <a name="conversions"></a><span data-ttu-id="4385a-125">Conversiones</span><span class="sxs-lookup"><span data-stu-id="4385a-125">Conversions</span></span>  
 <span data-ttu-id="4385a-126">Hay una conversión implícita predefinida de `ushort` a [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="4385a-126">There is a predefined implicit conversion from `ushort` to [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="4385a-127">Hay una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md) o [char](../../../csharp/language-reference/keywords/char.md) a `ushort`.</span><span class="sxs-lookup"><span data-stu-id="4385a-127">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md) or [char](../../../csharp/language-reference/keywords/char.md) to `ushort`.</span></span> <span data-ttu-id="4385a-128">De lo contrario, se debe usar una conversión para realizar una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="4385a-128">Otherwise a cast must be used to perform an explicit conversion.</span></span> <span data-ttu-id="4385a-129">Por ejemplo, considere las dos variables de `ushort` siguientes, `x` y `y`:</span><span class="sxs-lookup"><span data-stu-id="4385a-129">Consider, for example, the following two `ushort` variables `x` and `y`:</span></span>  
  
```csharp 
ushort x = 5, y = 12;  
```  
  
 <span data-ttu-id="4385a-130">La instrucción de asignación siguiente producirá un error de compilación porque la expresión aritmética de la derecha del operador de asignación da como resultado `int` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4385a-130">The following assignment statement will produce a compilation error, because the arithmetic expression on the right side of the assignment operator evaluates to `int` by default.</span></span>  
  
```csharp  
ushort z = x + y;   // Error: conversion from int to ushort  
```  
  
 <span data-ttu-id="4385a-131">Para corregir este problema, use una conversión:</span><span class="sxs-lookup"><span data-stu-id="4385a-131">To fix this problem, use a cast:</span></span>  
  
```csharp 
ushort z = (ushort)(x + y);   // OK: explicit conversion   
```  
  
 <span data-ttu-id="4385a-132">Pero es posible usar las instrucciones siguientes cuando la variable de destino tiene el mismo tamaño de almacenamiento o un tamaño de almacenamiento mayor:</span><span class="sxs-lookup"><span data-stu-id="4385a-132">It is possible though to use the following statements, where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```csharp
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="4385a-133">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `ushort`.</span><span class="sxs-lookup"><span data-stu-id="4385a-133">Notice also that there is no implicit conversion from floating-point types to `ushort`.</span></span> <span data-ttu-id="4385a-134">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="4385a-134">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ushort x = 3.0;   
// OK -- explicit conversion:  
ushort y = (ushort)3.0;  
```  
  
 <span data-ttu-id="4385a-135">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="4385a-135">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="4385a-136">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="4385a-136">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4385a-137">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4385a-137">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4385a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="4385a-138">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="4385a-139">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4385a-139">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4385a-140">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4385a-140">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4385a-141">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4385a-141">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4385a-142">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="4385a-142">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="4385a-143">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="4385a-143">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="4385a-144">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="4385a-144">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="4385a-145">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="4385a-145">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
