---
title: 'Tabla de formatos de presentación para valores numéricos: Referencia de C#'
description: Obtenga información sobre las cadenas de formato numérico estándar de C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: eb93f0a4f3c66e9f7b295366a77b9fb099fc3a1e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713509"
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabla de formatos de presentación para valores numéricos (Referencia de C#)

La siguiente tabla muestra los especificadores de formato admitidos para dar formato a los resultados numéricos. El resultado con formato de la última columna corresponde a la clase <xref:System.Globalization.CultureInfo> "en-US".

|Especificador de formato|Descripción|Ejemplos|Resultado|  
|----------------------|-----------------|--------------|------------|  
|C o c|Moneda|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|\\$2,50<br /><br /> (\\$2,50)|  
|D o d|Decimal|`string s = $"{25:D5}";`|00025|  
|E o e|Exponencial|`string s = $"{250000:E2}";`|2.50E+005|  
|F o f|Punto fijo|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|2.50<br /><br /> 3|  
|G o g|General|`string s = $"{2.5:G}";`|2.5|  
|N o n|Numérica|`string s = $"{2500000:N}";`|2,500,000.00|  
|P o p|Porcentaje|`string s = $"{0.25:P}";`|25.00 %|  
|R o r|Acción de ida y vuelta|`string s = $"{2.5:R}";`|2.5|  
|X o x|Hexadecimal|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|FA<br /><br /> FFFF|  

## <a name="remarks"></a>Comentarios

Use un especificador de formato para crear una cadena de formato. La cadena de formato tiene el siguiente formato: `Axx`, donde

- `A` es el especificador de formato, que controla el tipo de formato aplicado al valor numérico.
- `xx` es el especificador de precisión, que afecta al número de dígitos del resultado con formato. El valor de los intervalos del especificador de precisión comprende de 0 a 99.

Los especificadores de formato decimal ("D" o "d") y hexadecimal ("X" o "x") solo son compatibles con tipos enteros. El especificador de formato del recorrido de ida y vuelta ("R" o "r") solo es compatible para los tipos <xref:System.Single>, <xref:System.Double> y <xref:System.Numerics.BigInteger>.

Las cadenas con formato numérico estándar son compatibles con:

- Algunas sobrecargas del método `ToString` de todos los tipos numéricos. Por ejemplo, se puede proporcionar una cadena de formato numérico a los métodos <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> y <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>.

- La [característica de formato compuesto](../../../standard/base-types/composite-formatting.md) de .NET, que es compatible con el método <xref:System.String.Format%2A?displayProperty=nameWithType>, por ejemplo.

- [Cadenas interpoladas](../tokens/interpolated.md).

Para más información, vea [Cadenas de formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Aplicar formato a tipos](../../../standard/base-types/formatting-types.md)
- [Formatos compuestos](../../../standard/base-types/composite-formatting.md)
- [Interpolación de cadenas](../tokens/interpolated.md)
- [string](../builtin-types/reference-types.md)
