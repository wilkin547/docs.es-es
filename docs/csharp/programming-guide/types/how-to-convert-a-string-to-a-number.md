---
title: 'Procedimiento Convertir una cadena en un número: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: a75d6dd5fdb74ca3cb6fe28db7415aeb478e2237
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243223"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="82860-102">Procedimiento Convertir una cadena en un número (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="82860-102">How to: Convert a String to a Number (C# Programming Guide)</span></span>
<span data-ttu-id="82860-103">Puede convertir una [cadena](../../../csharp/language-reference/keywords/string.md) en un número usando métodos en la clase <xref:System.Convert> o usando el método `TryParse` que se ha encontrado en los diversos tipos numéricos (int, long, float, etc.).</span><span class="sxs-lookup"><span data-stu-id="82860-103">You can convert a [string](../../../csharp/language-reference/keywords/string.md) to a number by using methods in the <xref:System.Convert> class or by using the `TryParse` method found on the various numeric types (int, long, float, etc.).</span></span>  
  
 <span data-ttu-id="82860-104">Si tiene una cadena, resulta algo más eficaz y sencillo llamar a un método `TryParse` (por ejemplo, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span><span class="sxs-lookup"><span data-stu-id="82860-104">If you have a string, it is slightly more efficient and straightforward to call a `TryParse` method (for example, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)).</span></span>  <span data-ttu-id="82860-105">El uso de un método <xref:System.Convert> resulta más práctico para objetos generales que implementan <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="82860-105">Using a <xref:System.Convert> method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="82860-106">Puede usar los métodos `Parse` o `TryParse` en el tipo numérico que espera que la cadena contenga, como el tipo <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="82860-106">You can use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=nameWithType> type.</span></span>  <span data-ttu-id="82860-107">El método <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> utiliza <xref:System.Int32.Parse%2A> internamente.</span><span class="sxs-lookup"><span data-stu-id="82860-107">The <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="82860-108">Si el formato de la cadena no es válido, `Parse` genera una excepción, mientras que `TryParse` devuelve [false](../../../csharp/language-reference/keywords/false.md).</span><span class="sxs-lookup"><span data-stu-id="82860-108">If the string is not in a valid format, `Parse` throws an exception whereas `TryParse` returns [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82860-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82860-109">Example</span></span>  
 <span data-ttu-id="82860-110">Los métodos `Parse` y `TryParse` no tienen en cuenta los espacios en blanco al principio y al final de la cadena, pero todos los demás caracteres deben ser caracteres que formen el tipo numérico adecuado (int, long, ulong, float, decimal, etc.).</span><span class="sxs-lookup"><span data-stu-id="82860-110">The `Parse` and `TryParse` methods ignore white space at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (int, long, ulong, float, decimal, etc.).</span></span>  <span data-ttu-id="82860-111">Si hay un espacio en blanco dentro de los caracteres que forman el número, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="82860-111">Any white space within the characters that form the number cause an error.</span></span>  <span data-ttu-id="82860-112">Por ejemplo, puede usar `decimal.TryParse` para analizar "10", "10,3" o "  10  ", pero no para analizar 10 en "10X", "1 0" (advierta el espacio), "10 ,3" (advierta el espacio) o "10e1" (`float.TryParse` funciona aquí), y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="82860-112">For example, you can use `decimal.TryParse` to parse "10", "10.3", "  10  ", but you cannot use this method to parse 10 from "10X", "1 0" (note space), "10 .3" (note space), "10e1" (`float.TryParse` works here), and so on.</span></span>  
  
 <span data-ttu-id="82860-113">En los siguientes ejemplos se muestran llamadas correctas e incorrectas a `Parse` y `TryParse`.</span><span class="sxs-lookup"><span data-stu-id="82860-113">The examples below demonstrate both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a><span data-ttu-id="82860-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="82860-114">Example</span></span>  
 <span data-ttu-id="82860-115">En la siguiente tabla se muestran algunos de los métodos de la clase <xref:System.Convert> que se pueden usar.</span><span class="sxs-lookup"><span data-stu-id="82860-115">The following table lists some of the methods from the <xref:System.Convert> class that you can use.</span></span>  
  
|<span data-ttu-id="82860-116">Tipo numérico</span><span class="sxs-lookup"><span data-stu-id="82860-116">Numeric Type</span></span>|<span data-ttu-id="82860-117">Método</span><span class="sxs-lookup"><span data-stu-id="82860-117">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="82860-118">En este ejemplo, se llama al método <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> para convertir una [cadena](../../../csharp/language-reference/keywords/string.md) de entrada en un valor [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="82860-118">This example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> method to convert an input [string](../../../csharp/language-reference/keywords/string.md) to an [int](../../../csharp/language-reference/keywords/int.md) .</span></span> <span data-ttu-id="82860-119">El código detecta las dos excepciones más comunes que este método puede generar, <xref:System.FormatException> y <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="82860-119">The code catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="82860-120">Si se puede incrementar el número sin que se produzca un desbordamiento de la ubicación de almacenamiento de los enteros, el programa agregará 1 al resultado e imprimirá el resultado.</span><span class="sxs-lookup"><span data-stu-id="82860-120">If the number can be incremented without overflowing the integer storage location, the program adds 1 to the result and prints the output.</span></span>  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="82860-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="82860-121">See Also</span></span>

- [<span data-ttu-id="82860-122">Tipos</span><span class="sxs-lookup"><span data-stu-id="82860-122">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
- [<span data-ttu-id="82860-123">Cómo: Determinar si una cadena representa un valor numérico</span><span class="sxs-lookup"><span data-stu-id="82860-123">How to: Determine Whether a String Represents a Numeric Value</span></span>](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)  
- <span data-ttu-id="82860-124">[.NET Framework 4 Formatting Utility](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d) (Utilidad de formato de .NET Framework 4)</span><span class="sxs-lookup"><span data-stu-id="82860-124">[.NET Framework 4 Formatting Utility](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)</span></span>
