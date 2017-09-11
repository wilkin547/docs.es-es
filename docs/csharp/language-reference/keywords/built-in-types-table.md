---
title: Tabla de tipos integrados (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
caps.latest.revision: 12
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
ms.openlocfilehash: df13a45544491dee9e592a4ab0b90b5235f12abc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="built-in-types-table-c-reference"></a><span data-ttu-id="24650-102">Tabla de tipos integrados (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="24650-102">Built-In Types Table (C# Reference)</span></span>
<span data-ttu-id="24650-103">En la siguiente tabla se muestran las palabras clave para los tipos de C# integrados, que son alias de los tipos predefinidos en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="24650-103">The following table shows the keywords for built-in C# types, which are aliases of predefined types in the <xref:System> namespace.</span></span>  
  
|<span data-ttu-id="24650-104">Tipo de C#</span><span class="sxs-lookup"><span data-stu-id="24650-104">C# Type</span></span>|<span data-ttu-id="24650-105">Tipo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="24650-105">.NET Framework Type</span></span>|  
|--------------|-------------------------|  
|[<span data-ttu-id="24650-106">bool</span><span class="sxs-lookup"><span data-stu-id="24650-106">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)|`System.Boolean`|  
|[<span data-ttu-id="24650-107">byte</span><span class="sxs-lookup"><span data-stu-id="24650-107">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|`System.Byte`|  
|[<span data-ttu-id="24650-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="24650-108">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|`System.SByte`|  
|[<span data-ttu-id="24650-109">char</span><span class="sxs-lookup"><span data-stu-id="24650-109">char</span></span>](../../../csharp/language-reference/keywords/char.md)|`System.Char`|  
|[<span data-ttu-id="24650-110">decimal</span><span class="sxs-lookup"><span data-stu-id="24650-110">decimal</span></span>](../../../csharp/language-reference/keywords/decimal.md)|`System.Decimal`|  
|[<span data-ttu-id="24650-111">double</span><span class="sxs-lookup"><span data-stu-id="24650-111">double</span></span>](../../../csharp/language-reference/keywords/double.md)|`System.Double`|  
|[<span data-ttu-id="24650-112">float</span><span class="sxs-lookup"><span data-stu-id="24650-112">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`System.Single`|  
|[<span data-ttu-id="24650-113">int</span><span class="sxs-lookup"><span data-stu-id="24650-113">int</span></span>](../../../csharp/language-reference/keywords/int.md)|`System.Int32`|  
|[<span data-ttu-id="24650-114">uint</span><span class="sxs-lookup"><span data-stu-id="24650-114">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|`System.UInt32`|  
|[<span data-ttu-id="24650-115">long</span><span class="sxs-lookup"><span data-stu-id="24650-115">long</span></span>](../../../csharp/language-reference/keywords/long.md)|`System.Int64`|  
|[<span data-ttu-id="24650-116">ulong</span><span class="sxs-lookup"><span data-stu-id="24650-116">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|`System.UInt64`|  
|[<span data-ttu-id="24650-117">object</span><span class="sxs-lookup"><span data-stu-id="24650-117">object</span></span>](../../../csharp/language-reference/keywords/object.md)|`System.Object`|  
|[<span data-ttu-id="24650-118">short</span><span class="sxs-lookup"><span data-stu-id="24650-118">short</span></span>](../../../csharp/language-reference/keywords/short.md)|`System.Int16`|  
|[<span data-ttu-id="24650-119">ushort</span><span class="sxs-lookup"><span data-stu-id="24650-119">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|`System.UInt16`|  
|[<span data-ttu-id="24650-120">string</span><span class="sxs-lookup"><span data-stu-id="24650-120">string</span></span>](../../../csharp/language-reference/keywords/string.md)|`System.String`|  
  
## <a name="remarks"></a><span data-ttu-id="24650-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24650-121">Remarks</span></span>  
 <span data-ttu-id="24650-122">A todos los tipos de la tabla, excepto `object` y `string`, se les hace referencia como tipos simples.</span><span class="sxs-lookup"><span data-stu-id="24650-122">All of the types in the table, except `object` and `string`, are referred to as simple types.</span></span>  
  
 <span data-ttu-id="24650-123">Las palabras clave de tipo de C# y sus alias son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="24650-123">The C# type keywords and their aliases are interchangeable.</span></span> <span data-ttu-id="24650-124">Por ejemplo, puede declarar una variable de entero con cualquiera de las siguientes declaraciones:</span><span class="sxs-lookup"><span data-stu-id="24650-124">For example, you can declare an integer variable by using either of the following declarations:</span></span>  
  
```  
int x = 123;  
System.Int32 x = 123;  
```  
  
 <span data-ttu-id="24650-125">Para mostrar el tipo actual de cualquier tipo de C#, use el método del sistema `GetType()`.</span><span class="sxs-lookup"><span data-stu-id="24650-125">To display the actual type for any C# type, use the system method `GetType()`.</span></span> <span data-ttu-id="24650-126">Por ejemplo, la instrucción siguiente muestra el alias de sistema que representa el tipo de `myVariable`:</span><span class="sxs-lookup"><span data-stu-id="24650-126">For example, the following statement displays the system alias that represents the type of `myVariable`:</span></span>  
  
```  
Console.WriteLine(myVariable.GetType());  
```  
  
 <span data-ttu-id="24650-127">También puede usar el operador [typeof](../../../csharp/language-reference/keywords/typeof.md).</span><span class="sxs-lookup"><span data-stu-id="24650-127">You can also use the [typeof](../../../csharp/language-reference/keywords/typeof.md) operator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24650-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="24650-128">See Also</span></span>  
 <span data-ttu-id="24650-129">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="24650-129">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="24650-130">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="24650-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="24650-131">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="24650-131">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="24650-132">[Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="24650-132">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="24650-133">[Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md) </span><span class="sxs-lookup"><span data-stu-id="24650-133">[Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) </span></span>  
 <span data-ttu-id="24650-134">[Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md) </span><span class="sxs-lookup"><span data-stu-id="24650-134">[Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md) </span></span>  
 <span data-ttu-id="24650-135">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="24650-135">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 [<span data-ttu-id="24650-136">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="24650-136">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)

