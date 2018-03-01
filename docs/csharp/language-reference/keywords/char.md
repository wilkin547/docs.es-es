---
title: char (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 41f672e9b12481fa5cce78015e95d2c5245a26db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="char-c-reference"></a><span data-ttu-id="271b6-102">char (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="271b6-102">char (C# Reference)</span></span>
<span data-ttu-id="271b6-103">La palabra clave `char` se usa para declarar una instancia de la estructura <xref:System.Char?displayProperty=nameWithType> que .NET Framework usa para representar un carácter Unicode.</span><span class="sxs-lookup"><span data-stu-id="271b6-103">The `char` keyword is used to declare an instance of the <xref:System.Char?displayProperty=nameWithType> structure that the .NET Framework uses to represent a Unicode character.</span></span> <span data-ttu-id="271b6-104">El valor de un objeto `Char` es un valor numérico de 16 bits (ordinal).</span><span class="sxs-lookup"><span data-stu-id="271b6-104">The value of a `Char` object is a 16-bit numeric (ordinal) value.</span></span>  
  
 <span data-ttu-id="271b6-105">Los caracteres Unicode se usan para representar la mayoría de los idiomas escritos del mundo.</span><span class="sxs-lookup"><span data-stu-id="271b6-105">Unicode characters are used to represent most of the written languages throughout the world.</span></span>  
  
|<span data-ttu-id="271b6-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="271b6-106">Type</span></span>|<span data-ttu-id="271b6-107">Intervalo</span><span class="sxs-lookup"><span data-stu-id="271b6-107">Range</span></span>|<span data-ttu-id="271b6-108">Tamaño</span><span class="sxs-lookup"><span data-stu-id="271b6-108">Size</span></span>|<span data-ttu-id="271b6-109">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="271b6-109">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`char`|<span data-ttu-id="271b6-110">U+0000 a U+FFFF</span><span class="sxs-lookup"><span data-stu-id="271b6-110">U+0000 to U+FFFF</span></span>|<span data-ttu-id="271b6-111">Carácter Unicode de 16 bits</span><span class="sxs-lookup"><span data-stu-id="271b6-111">Unicode 16-bit character</span></span>|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="271b6-112">Literales</span><span class="sxs-lookup"><span data-stu-id="271b6-112">Literals</span></span>  
 <span data-ttu-id="271b6-113">Las constantes de tipo `char` pueden escribirse como literales de caracteres, secuencias de escape hexadecimal o representaciones Unicode.</span><span class="sxs-lookup"><span data-stu-id="271b6-113">Constants of the `char` type can be written as character literals, hexadecimal escape sequence, or Unicode representation.</span></span> <span data-ttu-id="271b6-114">También se pueden convertir los códigos de caracteres enteros.</span><span class="sxs-lookup"><span data-stu-id="271b6-114">You can also cast the integral character codes.</span></span> <span data-ttu-id="271b6-115">En el siguiente ejemplo se inicializan cuatro variables `char` con el mismo carácter `X`:</span><span class="sxs-lookup"><span data-stu-id="271b6-115">In the following example four `char` variables are initialized with the same character `X`:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a><span data-ttu-id="271b6-116">Conversiones</span><span class="sxs-lookup"><span data-stu-id="271b6-116">Conversions</span></span>  
 <span data-ttu-id="271b6-117">Un `char` se puede convertir implícitamente a [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) o [decimal](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="271b6-117">A `char` can be implicitly converted to [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span> <span data-ttu-id="271b6-118">En cambio, no hay ninguna conversión implícita de otros tipos al tipo `char`.</span><span class="sxs-lookup"><span data-stu-id="271b6-118">However, there are no implicit conversions from other types to the `char` type.</span></span>  
  
 <span data-ttu-id="271b6-119">El tipo <xref:System.Char?displayProperty=nameWithType> proporciona varios métodos estáticos para trabajar con valores `char`.</span><span class="sxs-lookup"><span data-stu-id="271b6-119">The <xref:System.Char?displayProperty=nameWithType> type provides several static methods for working with `char` values.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="271b6-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="271b6-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="271b6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="271b6-121">See Also</span></span>  
 <xref:System.Char>  
 [<span data-ttu-id="271b6-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="271b6-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="271b6-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="271b6-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="271b6-124">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="271b6-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="271b6-125">Tabla de tipos enteros</span><span class="sxs-lookup"><span data-stu-id="271b6-125">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="271b6-126">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="271b6-126">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="271b6-127">Tabla de conversiones numéricas implícitas</span><span class="sxs-lookup"><span data-stu-id="271b6-127">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="271b6-128">Tabla de conversiones numéricas explícitas</span><span class="sxs-lookup"><span data-stu-id="271b6-128">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="271b6-129">Tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="271b6-129">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 [<span data-ttu-id="271b6-130">Cadenas</span><span class="sxs-lookup"><span data-stu-id="271b6-130">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
