---
title: Procedimiento para mostrar milisegundos en los valores de fecha y hora
description: En este artículo, aprenderá a incluir el componente de milisegundos de un valor de fecha y hora en cadenas de fecha y hora con formato en .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET], milliseconds
- dates [.NET], milliseconds
- milliseconds [.NET]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
ms.openlocfilehash: 722334c324f663ba46a3c861885d4221fc566b8d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681267"
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Procedimiento para mostrar milisegundos en los valores de fecha y hora

Los métodos de formato de fecha y hora predeterminados, como <xref:System.DateTime.ToString?displayProperty=nameWithType>, incluyen las horas, minutos y segundos de un valor de tiempo, pero excluyen el componente correspondiente a los milisegundos. En este tema se muestra cómo se incluye un componente de milisegundos de un valor de fecha y hora en cadenas de fecha y hora con formato.  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Para mostrar el componente de milisegundos de un valor DateTime  
  
1. Cuando trabaje con la representación de cadena de una fecha, conviértala en un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> mediante el método estático <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.  
  
2. Para extraer la representación de cadena del componente de milisegundos de una hora, llame al método <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> o <xref:System.DateTimeOffset.ToString%2A> del valor de fecha y hora y pase el modelo de formato personalizado `fff` o `FFF` en solitario o junto a otros especificadores de formato personalizado como el parámetro `format`.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo se muestra el componente de milisegundos de un valor <xref:System.DateTime> y <xref:System.DateTimeOffset> en la consola en su presentación en solitario e incluido en una cadena de fecha y hora más larga.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 El modelo de formato `fff` incluye todos los ceros finales en el valor de milisegundos. El modelo de formato `FFF` suprime todos estos ceros. En el siguiente ejemplo se ilustra la diferencia.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Un problema que surge al definir un especificador de formato personalizado completo que incluya el componente de milisegundos de un valor de fecha y hora es que éste establece un formato codificado de forma rígida que es posible que no se corresponda con la organización de elementos horarios de la referencia cultural actual de la aplicación. Una alternativa más conveniente consiste en recuperar uno de los modelos de presentación de fecha y hora definidos por el objeto <xref:System.Globalization.DateTimeFormatInfo> de la referencia cultural actual y modificarlo para incluir los milisegundos. En el ejemplo se muestra también este enfoque. En este ejemplo, se recupera el modelo completo de fecha y hora de la referencia cultural actual de la propiedad <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> y, a continuación, se inserta el modelo personalizado `.ffff` tras el segundo modelo. Observe que en el ejemplo se utiliza una expresión regular para realizar esta operación en una única llamada al método.  
  
 También puede utilizar un especificador de formato personalizado para mostrar una fracción de segundo distinta de los milisegundos. Por ejemplo, el especificador de formato personalizado `f` o `F` muestra las décimas de segundo, el especificador de formato personalizado `ff` o `FF` muestra las centésimas de segundo y el especificador de formato personalizado `ffff` o `FFFF` muestra las diezmilésimas de segundo. Las fracciones de milisegundo se truncan en lugar de redondearse en la cadena devuelta. Estos especificadores de formato se utilizan en el ejemplo siguiente.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
> Es posible mostrar unidades fraccionarias de segundo muy pequeñas, como diezmilésimas o cienmilésimas de segundo. Sin embargo, estos valores no suelen ser significativos. La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema. En los sistemas operativos Windows NT 3.5 (y versiones posteriores) y Windows Vista, la resolución del reloj es aproximadamente de 10 a 15 milisegundos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Globalization.DateTimeFormatInfo>
- [Cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md)
