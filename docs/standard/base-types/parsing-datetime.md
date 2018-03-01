---
title: Analizar cadenas de fecha y hora en .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6e3ef01abdb615b2850b5a9d07e1208ee22eda95
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Analizar cadenas de fecha y hora en .NET
Los métodos de análisis convierten la representación de cadena de una fecha y hora en un objeto <xref:System.DateTime> equivalente. Los métodos <xref:System.DateTime.Parse%2A> y <xref:System.DateTime.TryParse%2A> convierten varias representaciones comunes de fecha y hora. Los métodos <xref:System.DateTime.ParseExact%2A> y <xref:System.DateTime.TryParseExact%2A> convierten una representación de cadena que se ajusta al modelo especificado por una cadena de formato de fecha y hora. (Consulte los temas sobre [cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) y [cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)).  
  
 El análisis se ve influido por las propiedades de un proveedor de formato que proporcione información, como las cadenas usadas para los separadores de fecha y hora, y los nombres de meses, días y eras. El proveedor de formato es el objeto <xref:System.Globalization.DateTimeFormatInfo> actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro <xref:System.IFormatProvider> de un método de análisis. Para el parámetro <xref:System.IFormatProvider>, especifique un objeto <xref:System.Globalization.CultureInfo>, que representa una referencia cultural, o un objeto <xref:System.Globalization.DateTimeFormatInfo>.  
  
 La representación de cadena de una fecha que se vaya a analizar debe incluir el mes y, al menos, un día o año. La representación de cadena de una hora debe incluir la hora y, al menos, los minutos o el designador a. m./p. m. Pero, si es posible, el análisis proporciona valores predeterminados para los componentes omitidos. Si falta una fecha, se usa como valor predeterminado la fecha actual; si falta un año, se usa como valor predeterminado el año actual; si falta un día del mes, se usa como valor predeterminado el primer día del mes; y si falta una hora, se usa como valor predeterminado la medianoche.  
  
 Si la representación de cadena solo especifica una hora, el análisis devuelve un objeto <xref:System.DateTime> con sus propiedades <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> y <xref:System.DateTime.Day%2A> establecidas en los valores correspondientes de la propiedad <xref:System.DateTime.Today%2A>. Pero si se especifica la constante <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> en el método de análisis, las propiedades de año, mes y día resultantes se establecen en el valor `1`.  
  
 Además de un componente de fecha y hora, la representación de cadena de una fecha y hora puede incluir una diferencia horaria que indica cuánto difiere la hora respecto de la hora universal coordinada (UTC). Por ejemplo, la cadena "14/2/2007 5:32:00 -7:00" define una hora que es siete horas anterior a la hora UTC. Si se omite la diferencia horaria de la representación de cadena de una hora, el análisis devuelve un objeto <xref:System.DateTime> con su propiedad <xref:System.DateTime.Kind%2A> establecida en <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Si se especifica la diferencia horaria, el análisis devuelve un objeto <xref:System.DateTime> con su propiedad <xref:System.DateTime.Kind%2A> establecida en <xref:System.DateTimeKind.Local> y su valor ajustado a la zona horaria local del equipo. Puede modificar este comportamiento mediante el uso de una constante <xref:System.Globalization.DateTimeStyles> con el método de análisis.  
  
 El proveedor de formato también se usa para interpretar una fecha numérica ambigua. Por ejemplo, no está claro qué componentes de la fecha representada por la cadena "02/03/04" son el mes, el día y el año. En este caso, los componentes se interpretan según el orden de formatos de fecha similares del proveedor de formato.  
  
## <a name="parse"></a>Parse  
 En el ejemplo de código siguiente se muestra el uso del método **Parse** para convertir una cadena en un valor **DateTime**. En este ejemplo se usa la referencia cultural asociada al subproceso actual para realizar el análisis. Si el objeto <xref:System.Globalization.CultureInfo> asociado a la referencia cultural actual no puede analizar la cadena de entrada, se produce una excepción <xref:System.FormatException>.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 También puede especificar un objeto **CultureInfo** establecido en una de las referencias culturales definidas por ese objeto, o puede especificar uno de los objetos <xref:System.Globalization.DateTimeFormatInfo> estándar devueltos por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. En el ejemplo de código siguiente se usa un proveedor de formato para analizar una cadena alemana en un valor **DateTime**. Se define un objeto **CultureInfo** que representa la referencia cultural de-DE y se pasa con la cadena que se está analizando para garantizar el análisis correcto de esta cadena concreta. Esto impide cualquier opción que se encuentre en **CurrentCulture** de **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Pero, aunque puede usar sobrecargas del método <xref:System.DateTime.Parse%2A> para especificar proveedores de formato personalizados, el método no admite el uso de proveedores de formato no estándar. Para analizar una fecha y hora expresadas en un formato no estándar, use en su lugar el método <xref:System.DateTime.ParseExact%2A>.  
  
 En el ejemplo de código siguiente se usa la enumeración <xref:System.Globalization.DateTimeStyles> para especificar que la información de fecha y hora actual no se debe agregar al valor **DateTime** para los campos que la cadena no defina.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 El método <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> convierte una cadena que se ajusta a un modelo de cadena específico para un objeto **DateTime**. Cuando se pasa a este método una cadena que no tiene la forma especificada, se produce una excepción <xref:System.FormatException>. Puede especificar uno de los especificadores de formato de fecha y hora estándar o una combinación limitada de especificadores de formato de fecha y hora personalizados. Con el uso de especificadores de formato personalizados, es posible construir una cadena de reconocimiento personalizada. Para obtener una explicación de los especificadores, consulte los temas sobre [cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) y [cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Cada sobrecarga del método <xref:System.DateTime.ParseExact%2A> también tiene un parámetro <xref:System.IFormatProvider> que normalmente proporciona información específica de la referencia cultural sobre el formato de la cadena. Normalmente, este objeto <xref:System.IFormatProvider> es un objeto <xref:System.Globalization.CultureInfo> que representa una referencia cultural estándar o un objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>. Pero, a diferencia de otras funciones de análisis de fecha y hora, este método también admite un objeto <xref:System.IFormatProvider> que define un formato de fecha y hora no estándar.  
  
 En el ejemplo de código siguiente, se pasa al método **ParseExact** un objeto de cadena para que lo analice, seguido de un especificador de formato, seguido de un objeto **CultureInfo**. Este método **ParseExact** solo puede analizar cadenas que muestren el modelo de fecha larga de la referencia cultural en-US.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)  
 [Conversión de tipos en .NET](../../../docs/standard/base-types/type-conversion.md)
