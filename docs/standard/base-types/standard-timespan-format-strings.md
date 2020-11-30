---
title: Cadenas de formato TimeSpan estándar
description: Revise las cadenas de formato TimeSpan estándar, que usan un único especificador de formato para definir la representación de texto de un valor TimeSpan en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, standard time interval
- format strings
- standard time interval format strings
- standard format strings, time intervals
- format specifiers, time intervals
- time intervals [.NET], formatting
- time [.NET], formatting
- formatting [.NET], time
- standard TimeSpan format strings
- formatting [.NET], time intervals
ms.assetid: 9f6c95eb-63ae-4dcc-9c32-f81985c75794
ms.openlocfilehash: 251f90e85d037d8cf4f3fd58bc27659c98d04b5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734249"
---
# <a name="standard-timespan-format-strings"></a>Cadenas de formato TimeSpan estándar

Una cadena de formato estándar <xref:System.TimeSpan> usa un único especificador de formato para definir la representación de texto de un valor <xref:System.TimeSpan> resultante de una operación de formato. Cualquier cadena de formato que contenga más de un carácter, incluido el espacio en blanco, se interpreta como una cadena de formato <xref:System.TimeSpan> personalizado. Para más información, consulte [Cadenas de formato TimeSpan personalizadas](custom-timespan-format-strings.md).  
  
 Las representaciones de cadena de los valores <xref:System.TimeSpan> se generan mediante llamadas a las sobrecargas del método <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType>, y también mediante métodos que admiten formatos compuestos, como <xref:System.String.Format%2A?displayProperty=nameWithType>. Para obtener más información, consulte [Aplicar formato a tipos](formatting-types.md) y [Formatos compuestos](composite-formatting.md). En el siguiente ejemplo se muestra el uso de cadenas de formato estándar en operaciones de formato.  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/formatexample1.cs#2)]
 [!code-vb[Conceptual.TimeSpan.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/formatexample1.vb#2)]  
  
 Los métodos <xref:System.TimeSpan> y <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType> también usan cadenas de formato <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType> estándar para definir el formato que deben tener las cadenas de entrada de las operaciones de análisis. (Estas operaciones convierten la representación de cadena de un valor en ese valor.) En el siguiente ejemplo, se muestra el uso de cadenas de formato estándar en operaciones de análisis.  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/parseexample1.cs#3)]
 [!code-vb[Conceptual.TimeSpan.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/parseexample1.vb#3)]  
  
En la tabla siguiente se muestran los especificadores de formato de intervalo de tiempo estándar.  
  
|Especificador de formato|NOMBRE|Descripción|Ejemplos|  
|----------------------|----------|-----------------|--------------|  
|"c"|Formato constante (invariable)|Este especificador no tiene en cuenta la referencia cultural. Toma la forma `[-][d'.']hh':'mm':'ss['.'fffffff]`.<br /><br /> (Las cadenas de formato "t" y "T" producen los mismos resultados).<br /><br /> Más información: [Especificador de formato constante ("c")](#the-constant-c-format-specifier).|`TimeSpan.Zero` -> 00:00:00<br /><br /> `New TimeSpan(0, 0, 30, 0)` -> 00:30:00<br /><br /> `New TimeSpan(3, 17, 25, 30, 500)` -> 3.17:25:30.5000000|  
|"g"|Formato corto general|Este especificador solo genera lo necesario. Tiene en cuenta la referencia cultural y su forma es `[-][d':']h':'mm':'ss[.FFFFFFF]`.<br /><br /> Más información: [Especificador de formato corto general ("g")](#the-general-short-g-format-specifier).|`New TimeSpan(1, 3, 16, 50, 500)` -> 1:3:16:50.5 (en-US)<br /><br /> `New TimeSpan(1, 3, 16, 50, 500)` -> 1:3:16:50,5 (fr-FR)<br /><br /> `New TimeSpan(1, 3, 16, 50, 599)` -> 1:3:16:50.599 (en-US)<br /><br /> `New TimeSpan(1, 3, 16, 50, 599)` -> 1:3:16:50,599 (fr-FR)|  
|"G"|Formato general largo|Este especificador siempre genera días y siete dígitos fraccionarios. Tiene en cuenta la referencia cultural y su forma es `[-]d':'hh':'mm':'ss.fffffff`.<br /><br /> Más información: [Especificador de formato largo general ("G")](#the-general-long-g-format-specifier).|`New TimeSpan(18, 30, 0)` -> 0:18:30:00.0000000 (en-US)<br /><br /> `New TimeSpan(18, 30, 0)` -> 0:18:30:00,0000000 (fr-FR)|  

## <a name="the-constant-c-format-specifier"></a>Especificador de formato constante ("c")  

 El especificador de formato "c" devuelve la representación de cadena de un valor <xref:System.TimeSpan> de la siguiente forma:  
  
 [-][*d*.]*hh*:*mm*:*ss*[.*fffffff*]  
  
 Los elementos de los corchetes ([ y ]) son opcionales. El punto (.) y los dos puntos (:) son símbolos literales. En la siguiente tabla se describen los elementos restantes.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|*-*|Signo negativo opcional, que indica un intervalo de tiempo negativo.|  
|*d*|Número opcional de días, sin ceros a la izquierda.|  
|*hh*|Número de horas, entre "00" y "23".|  
|*mm*|Número de minutos, entre "00" y "59".|  
|*ss*|Número de segundos, entre "00" y "59".|  
|*fffffff*|La parte fraccionaria opcional de un segundo.  Su valor puede oscilar entre "0000001" (un tic o una diez millonésima de segundo) y "9999999" (9.999.999 diez millonésimas de segundo, o un segundo menos un tic).|  
  
 A diferencia de los especificadores de formato de "g" y "G", el especificador de formato "c" no tiene en cuenta la referencia cultural. Genera la representación de cadena de un valor <xref:System.TimeSpan> que es invariable y común a las versiones anteriores a .NET Framework 4. "c" es la cadena de formato <xref:System.TimeSpan> predeterminado; el método <xref:System.TimeSpan.ToString?displayProperty=nameWithType> da formato a un valor de intervalo de tiempo mediante la cadena de formato "c".  
  
> [!NOTE]
> <xref:System.TimeSpan> también admite las cadenas de formato estándar "t" y "T", cuyo comportamiento es idéntico al de la cadena de formato estándar "c".  
  
 En el ejemplo siguiente se crea una instancia de dos objetos <xref:System.TimeSpan>, que se usan para realizar operaciones aritméticas y se muestra el resultado. En cada caso, se utiliza un formato compuesto para mostrar el valor <xref:System.TimeSpan> mediante el especificador de formato "c".  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardc1.cs#1)]
 [!code-vb[Conceptual.TimeSpan.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardc1.vb#1)]  

## <a name="the-general-short-g-format-specifier"></a>Especificador de formato corto general ("g")  

 El especificador de formato <xref:System.TimeSpan> "g" devuelve la representación de cadena de un valor <xref:System.TimeSpan> en una forma compacta, incluyendo únicamente los elementos que sean necesarios. Tiene la forma siguiente:  
  
 [-][*d*:]*h*:*mm*:*ss*[.*FFFFFFF*]  
  
 Los elementos de los corchetes ([ y ]) son opcionales. Los dos puntos (:) son un símbolo literal. En la siguiente tabla se describen los elementos restantes.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|*-*|Signo negativo opcional, que indica un intervalo de tiempo negativo.|  
|*d*|Número opcional de días, sin ceros a la izquierda.|  
|*h*|El número de horas, entre "0" a "23", sin ceros a la izquierda.|  
|*mm*|Número de minutos, entre "00" y "59".|  
|*ss*|Número de segundos, entre "00" y "59".|  
|*.*|Separador de fracciones de segundo. Es equivalente a la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> de la referencia cultural especificada sin invalidaciones del usuario.|  
|*FFFFFFF*|Fracciones de segundo. Se muestra la menor cantidad de dígitos posible.|  
  
 Al igual que el especificador de formato "G", el especificador de formato "g" se localiza. Su separador de fracciones de segundo se basa en la referencia cultural actual o en la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> de una referencia cultural especificada.  
  
 En el ejemplo siguiente se crea una instancia de dos objetos <xref:System.TimeSpan>, que se usan para realizar operaciones aritméticas y se muestra el resultado. En cada caso, se utiliza un formato compuesto para mostrar el valor <xref:System.TimeSpan> mediante el especificador de formato "g". Además, se da formato al valor <xref:System.TimeSpan> mediante las convenciones de formato de la referencia cultural del sistema actual (que, en este caso, es inglés - Estados Unidos o en-US) y la referencia cultural de Francia de francés (fr-FR).  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardshort1.cs#4)]
 [!code-vb[Conceptual.TimeSpan.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardshort1.vb#4)]  

## <a name="the-general-long-g-format-specifier"></a>Especificador de formato largo general ("G")  

 El especificador de formato <xref:System.TimeSpan> "G" devuelve la representación de cadena de un valor <xref:System.TimeSpan> en un formato largo que siempre incluye los días y las fracciones de segundo. La cadena resultante del especificador de formato estándar "G" tiene la forma siguiente:  
  
 [-]*d*:*hh*:*mm*:*ss*.*fffffff*  
  
 Los elementos de los corchetes ([ y ]) son opcionales. Los dos puntos (:) son un símbolo literal. En la siguiente tabla se describen los elementos restantes.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|*-*|Signo negativo opcional, que indica un intervalo de tiempo negativo.|  
|*d*|Número de días, sin ceros a la izquierda.|  
|*hh*|Número de horas, entre "00" y "23".|  
|*mm*|Número de minutos, entre "00" y "59".|  
|*ss*|Número de segundos, entre "00" y "59".|  
|*.*|Separador de fracciones de segundo. Es equivalente a la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> de la referencia cultural especificada sin invalidaciones del usuario.|  
|*fffffff*|Fracciones de segundo.|  
  
 Al igual que el especificador de formato "G", el especificador de formato "g" se localiza. Su separador de fracciones de segundo se basa en la referencia cultural actual o en la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> de una referencia cultural especificada.  
  
 En el ejemplo siguiente se crea una instancia de dos objetos <xref:System.TimeSpan>, que se usan para realizar operaciones aritméticas y se muestra el resultado. En cada caso, se utiliza un formato compuesto para mostrar el valor <xref:System.TimeSpan> mediante el especificador de formato "G". Además, se da formato al valor <xref:System.TimeSpan> mediante las convenciones de formato de la referencia cultural del sistema actual (que, en este caso, es inglés - Estados Unidos o en-US) y la referencia cultural de Francia de francés (fr-FR).  
  
 [!code-csharp[Conceptual.TimeSpan.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.standard/cs/standardlong1.cs#5)]
 [!code-vb[Conceptual.TimeSpan.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.standard/vb/standardlong1.vb#5)]
  
## <a name="see-also"></a>Vea también

- [Aplicación de formato a tipos](formatting-types.md)
- [Cadenas de formato TimeSpan personalizado](custom-timespan-format-strings.md)
- [Analizar cadenas](parsing-strings.md)
