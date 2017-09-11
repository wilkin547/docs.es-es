---
title: uint (Referencia de C#)
ms.date: 2017-03-14
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- uint
- uint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- uint keyword [C#]
ms.assetid: e93e42c6-ec72-4b0b-89df-2fd8d36f7a7b
caps.latest.revision: 18
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
ms.openlocfilehash: 4342c08ab536f45a2e3b5fa6fe94839436600a4a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="uint-c-reference"></a><span data-ttu-id="659d0-102">uint (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="659d0-102">uint (C# Reference)</span></span>

<span data-ttu-id="659d0-103">La palabra clave `uint` denota un tipo entero que almacena valores según el tamaño y el intervalo que se indican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="659d0-103">The `uint` keyword signifies an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="659d0-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="659d0-104">Type</span></span>|<span data-ttu-id="659d0-105">Intervalo</span><span class="sxs-lookup"><span data-stu-id="659d0-105">Range</span></span>|<span data-ttu-id="659d0-106">Tamaño</span><span class="sxs-lookup"><span data-stu-id="659d0-106">Size</span></span>|<span data-ttu-id="659d0-107">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="659d0-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`uint`|<span data-ttu-id="659d0-108">De 0 a 4.294.967.295</span><span class="sxs-lookup"><span data-stu-id="659d0-108">0 to 4,294,967,295</span></span>|<span data-ttu-id="659d0-109">Entero de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="659d0-109">Unsigned 32-bit integer</span></span>|<xref:System.UInt32?displayProperty=fullName>|  
  
 <span data-ttu-id="659d0-110">**Nota**: El tipo `uint` no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="659d0-110">**Note** The `uint` type is not CLS-compliant.</span></span> <span data-ttu-id="659d0-111">Use `int` siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="659d0-111">Use `int` whenever possible.</span></span>  
  
## <a name="literals"></a><span data-ttu-id="659d0-112">Literales</span><span class="sxs-lookup"><span data-stu-id="659d0-112">Literals</span></span>  

<span data-ttu-id="659d0-113">Puede declarar e inicializar una variable `uint` mediante la asignación de un literal decimal, un literal hexadecimal o (a partir de C# 7) un literal binario.</span><span class="sxs-lookup"><span data-stu-id="659d0-113">You can declare and initialize a `uint` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="659d0-114">Si el literal entero está fuera del intervalo de `uint` (es decir, si es inferior a <xref:System.UInt32.MinValue?displayProperty=fullName> o mayor que <xref:System.UInt32.MaxValue?displayProperty=fullName>), se produce un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="659d0-114">If the integer literal is outside the range of `uint` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=fullName> or greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>), a compilation error occurs.</span></span>

<span data-ttu-id="659d0-115">En el ejemplo siguiente, los enteros que equivalen a 3 000 000 000 que se representan como literales binarios, hexadecimales y decimales se asignan a valores `uint`.</span><span class="sxs-lookup"><span data-stu-id="659d0-115">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `uint` values.</span></span>  
  
<span data-ttu-id="659d0-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span><span class="sxs-lookup"><span data-stu-id="659d0-116">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UInt)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="659d0-117">Use el prefijo `0x` o `0X` para denotar un literal hexadecimal y el prefijo `0b` o `0B` para denotar un literal binario.</span><span class="sxs-lookup"><span data-stu-id="659d0-117">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="659d0-118">Los literales decimales no tienen prefijo.</span><span class="sxs-lookup"><span data-stu-id="659d0-118">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="659d0-119">A partir de C# 7, también puede usar el carácter de subrayado, `_`, como un separador de dígitos para mejorar la legibilidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="659d0-119">Starting with C# 7, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

<span data-ttu-id="659d0-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span><span class="sxs-lookup"><span data-stu-id="659d0-120">[!code-cs[uint](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#UIntS)]</span></span>  
 
 <span data-ttu-id="659d0-121">Los literales enteros también pueden incluir un sufijo que denote el tipo.</span><span class="sxs-lookup"><span data-stu-id="659d0-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="659d0-122">El sufijo `U` o "u" denota `uint` o `ulong`, dependiendo del valor numérico del literal.</span><span class="sxs-lookup"><span data-stu-id="659d0-122">The suffix `U` or 'u' denotes either a `uint` or a `ulong`, depending on the numeric value of the literal.</span></span> <span data-ttu-id="659d0-123">En el ejemplo siguiente se usa el sufijo `u` para denotar un entero sin signo de ambos tipos.</span><span class="sxs-lookup"><span data-stu-id="659d0-123">The following example uses the `u` suffix to denote an unsigned integer of both types.</span></span> <span data-ttu-id="659d0-124">Tenga en cuenta que el primer literal es `uint` porque su valor es inferior a <xref:System.UInt32.MaxValue?displayProperty=fullName>, mientras que el segundo es `ulong` porque su valor es superior a <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="659d0-124">Note that the first literal is a `uint` because its value is less than <xref:System.UInt32.MaxValue?displayProperty=fullName>, while the second is a `ulong` because its value is greater than <xref:System.UInt32.MaxValue?displayProperty=fullName>.</span></span>

<span data-ttu-id="659d0-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="659d0-125">[!code-cs[usuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#1)]</span></span>  
 
<span data-ttu-id="659d0-126">Si un literal entero no tiene sufijo, su tipo es el primero de los siguientes tipos en el que se puede representar su valor:</span><span class="sxs-lookup"><span data-stu-id="659d0-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="659d0-127">int</span><span class="sxs-lookup"><span data-stu-id="659d0-127">int</span></span>](int.md)
2. `uint`
3. [<span data-ttu-id="659d0-128">long</span><span class="sxs-lookup"><span data-stu-id="659d0-128">long</span></span>](../../../csharp/language-reference/keywords/long.md)
4. [<span data-ttu-id="659d0-129">ulong</span><span class="sxs-lookup"><span data-stu-id="659d0-129">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md) 
  
## <a name="conversions"></a><span data-ttu-id="659d0-130">Conversiones</span><span class="sxs-lookup"><span data-stu-id="659d0-130">Conversions</span></span>  
 <span data-ttu-id="659d0-131">Existe una conversión implícita predefinida de `uint` a [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="659d0-131">There is a predefined implicit conversion from `uint` to [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="659d0-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="659d0-132">For example:</span></span>  
  
```csharp  
float myFloat = 4294967290;   // OK: implicit conversion to float  
```  
  
 <span data-ttu-id="659d0-133">Existe una conversión implícita predefinida de [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md) o [char](../../../csharp/language-reference/keywords/char.md) a `uint`.</span><span class="sxs-lookup"><span data-stu-id="659d0-133">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), or [char](../../../csharp/language-reference/keywords/char.md) to `uint`.</span></span> <span data-ttu-id="659d0-134">De lo contrario, debe usar una conversión.</span><span class="sxs-lookup"><span data-stu-id="659d0-134">Otherwise you must use a cast.</span></span> <span data-ttu-id="659d0-135">Por ejemplo, la instrucción de asignación siguiente producirá un error de compilación sin una conversión:</span><span class="sxs-lookup"><span data-stu-id="659d0-135">For example, the following assignment statement will produce a compilation error without a cast:</span></span>  
  
```csharp  
long aLong = 22;  
// Error -- no implicit conversion from long:  
uint uInt1 = aLong;   
// OK -- explicit conversion:  
uint uInt2 = (uint)aLong;  
```  
  
 <span data-ttu-id="659d0-136">Observe también que no hay ninguna conversión implícita de tipos de punto flotante a `uint`.</span><span class="sxs-lookup"><span data-stu-id="659d0-136">Notice also that there is no implicit conversion from floating-point types to `uint`.</span></span> <span data-ttu-id="659d0-137">Por ejemplo, la instrucción siguiente genera un error del compilador, a menos que se use una conversión explícita:</span><span class="sxs-lookup"><span data-stu-id="659d0-137">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
uint x = 3.0;  
// OK -- explicit conversion:  
uint y = (uint)3.0;   
```  
  
 <span data-ttu-id="659d0-138">Para obtener información sobre expresiones aritméticas con combinaciones de tipos de punto flotante y tipos enteros, vea [float](../../../csharp/language-reference/keywords/float.md) y [double](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="659d0-138">For information about arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="659d0-139">Para obtener más información sobre las reglas de conversión numéricas implícitas, vea la [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="659d0-139">For more information about implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="659d0-140">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="659d0-140">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="659d0-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="659d0-141">See Also</span></span>  
 <span data-ttu-id="659d0-142"><xref:System.UInt32></span><span class="sxs-lookup"><span data-stu-id="659d0-142"><xref:System.UInt32></span></span>   
 <span data-ttu-id="659d0-143">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="659d0-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="659d0-144">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="659d0-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="659d0-145">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="659d0-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="659d0-146">[Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="659d0-146">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="659d0-147">[Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="659d0-147">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="659d0-148">[Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="659d0-148">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="659d0-149">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="659d0-149">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

