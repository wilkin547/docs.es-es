---
title: 'Cómo: Convertir una cadena en un número (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 55ff87ef51f00a803276083052d4d86960e702e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>Cómo: Convertir una cadena en un número (Guía de programación de C#)
Puede convertir una [cadena](../../../csharp/language-reference/keywords/string.md) en un número usando métodos en la clase <xref:System.Convert> o usando el método `TryParse` que se ha encontrado en los diversos tipos numéricos (int, long, float, etc.).  
  
 Si tiene una cadena, resulta algo más eficaz y sencillo llamar a un método `TryParse` (por ejemplo, `int.TryParse("11")`).  El uso de un método `Convert` resulta más práctico para objetos generales que implementan <xref:System.IConvertible>.  
  
 Puede usar los métodos `Parse` o `TryParse` en el tipo numérico que espera que la cadena contenga, como el tipo <xref:System.Int32?displayProperty=nameWithType>.  El método <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> utiliza <xref:System.Int32.Parse%2A> internamente.  Si el formato de la cadena no es válido, `Parse` genera una excepción, mientras que `TryParse` devuelve [false](../../../csharp/language-reference/keywords/false.md).  
  
## <a name="example"></a>Ejemplo  
 Los métodos `Parse` y `TryParse` no tienen en cuenta los espacios en blanco al principio y al final de la cadena, pero todos los demás caracteres deben ser caracteres que formen el tipo numérico adecuado (int, long, ulong, float, decimal, etc.).  Si hay un espacio en blanco dentro de los caracteres que forman el número, se producirá un error.  Por ejemplo, puede usar `decimal.TryParse` para analizar "10", "10,3" o "  10  ", pero no para analizar 10 en "10X", "1 0" (advierta el espacio), "10 ,3" (advierta el espacio) o "10e1" (`float.TryParse` funciona aquí), y así sucesivamente.  
  
 En los siguientes ejemplos se muestran llamadas correctas e incorrectas a `Parse` y `TryParse`.  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a>Ejemplo  
 En la siguiente tabla se muestran algunos de los métodos de la clase <xref:System.Convert> que se pueden usar.  
  
|Tipo numérico|Método|  
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
  
 En este ejemplo, se llama al método <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> para convertir una [cadena](../../../csharp/language-reference/keywords/string.md) de entrada en un valor [int](../../../csharp/language-reference/keywords/int.md). El código detecta las dos excepciones más comunes que este método puede generar, <xref:System.FormatException> y <xref:System.OverflowException>. Si se puede incrementar el número sin que se produzca un desbordamiento de la ubicación de almacenamiento de los enteros, el programa agregará 1 al resultado e imprimirá el resultado.  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Tipos](../../../csharp/programming-guide/types/index.md)  
 [Cómo: Determinar si una cadena representa un valor numérico](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)  
 [.NET Framework 4 Formatting Utility](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d) (Utilidad de formato de .NET Framework 4)
