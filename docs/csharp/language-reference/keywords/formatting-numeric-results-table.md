---
title: Tabla de formatos de presentación para valores numéricos (Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 8d034955d5d5d31788eafc0c21246451d7fd1f35
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43474299"
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabla de formatos de presentación para valores numéricos (Referencia de C#)
Se puede aplicar formato a los resultados numéricos mediante el método <xref:System.String.Format%2A?displayProperty=nameWithType>, o con los métodos <xref:System.Console.Write%2A?displayProperty=nameWithType> o <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> que realizan una llamada a `String.Format`, o usando la [interpolación de cadenas](../tokens/interpolated.md). El formato se especifica mediante cadenas de formato. La tabla siguiente contiene las cadenas de formato estándar admitidas. La cadena de formato toma la siguiente forma: `Axx`, donde `A` es el especificador de formato y `xx` es el especificador de precisión. El especificador de formato controla el tipo de formato aplicado al valor numérico, mientras que el especificador de precisión controla el número de dígitos significativos o posiciones decimales del resultado. El valor de los intervalos del especificador de precisión comprende de 0 a 99.  
  
 Para obtener más información sobre cadenas de formato estándar y personalizadas, vea [Aplicación de formato a tipo](../../../standard/base-types/formatting-types.md).
  
|Especificador de formato|Descripción|Ejemplos|Salida|  
|----------------------|-----------------|--------------|------------|  
|C o c|Moneda|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
|D o d|Decimal|Console.Write("{0:D5}", 25);|00025|  
|E o e|Científica|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F o f|Punto fijo|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G o g|General|Console.Write("{0:G}", 2.5);|2.5|  
|N o n|número|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X o x|Hexadecimal|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Cadenas con formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md)  
- [Tablas de referencia para tipos](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
- [string](../../../csharp/language-reference/keywords/string.md)
