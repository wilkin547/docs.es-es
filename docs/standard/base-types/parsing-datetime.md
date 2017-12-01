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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1beceb2b2d32c500e73cd7786c480fcd84c3001c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Analizar cadenas de fecha y hora en .NET
Métodos de análisis convierten la representación de cadena de una fecha y hora en su equivalente <xref:System.DateTime> objeto. El <xref:System.DateTime.Parse%2A> y <xref:System.DateTime.TryParse%2A> métodos convierten cualquier representación de varias representaciones comunes de una fecha y hora. El <xref:System.DateTime.ParseExact%2A> y <xref:System.DateTime.TryParseExact%2A> métodos convierten una representación de cadena que se ajusta al modelo especificado por una cadena de formato de fecha y hora. (Consulte los temas sobre [cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) y [cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)).  
  
 El análisis se ve influido por las propiedades de un proveedor de formato que proporcione información, como las cadenas usadas para los separadores de fecha y hora, y los nombres de meses, días y eras. El proveedor de formato es la actual <xref:System.Globalization.DateTimeFormatInfo> objeto, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el <xref:System.IFormatProvider> parámetro de un método de análisis. Para el <xref:System.IFormatProvider> parámetro, especifique un <xref:System.Globalization.CultureInfo> objeto, que representa una referencia cultural, o un <xref:System.Globalization.DateTimeFormatInfo> objeto.  
  
 La representación de cadena de una fecha que se vaya a analizar debe incluir el mes y, al menos, un día o año. La representación de cadena de una hora debe incluir la hora y, al menos, los minutos o el designador a. m./p. m. Pero, si es posible, el análisis proporciona valores predeterminados para los componentes omitidos. Si falta una fecha, se usa como valor predeterminado la fecha actual; si falta un año, se usa como valor predeterminado el año actual; si falta un día del mes, se usa como valor predeterminado el primer día del mes; y si falta una hora, se usa como valor predeterminado la medianoche.  
  
 Si la representación de cadena sólo especifica una hora, el análisis devuelve un <xref:System.DateTime> objeto con su <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, y <xref:System.DateTime.Day%2A> se establecen en los valores correspondientes de la <xref:System.DateTime.Today%2A> propiedad. Sin embargo, si la <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> constante se especifica en el método de análisis, el año resultante, mes y día propiedades se establecen en el valor `1`.  
  
 Además de un componente de fecha y hora, la representación de cadena de una fecha y hora puede incluir una diferencia horaria que indica cuánto difiere la hora respecto de la hora universal coordinada (UTC). Por ejemplo, la cadena "14/2/2007 5:32:00 -7:00" define una hora que es siete horas anterior a la hora UTC. Si se omite un desplazamiento de la representación de cadena de una hora, el análisis devuelve un <xref:System.DateTime> objeto con su <xref:System.DateTime.Kind%2A> propiedad establecida en <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Si se especifica un desplazamiento, análisis devuelve un <xref:System.DateTime> objeto con su <xref:System.DateTime.Kind%2A> propiedad establecida en <xref:System.DateTimeKind.Local> y su valor se ajusta a la zona horaria local de su equipo. Puede modificar este comportamiento mediante un <xref:System.Globalization.DateTimeStyles> constante con el método de análisis.  
  
 El proveedor de formato también se usa para interpretar una fecha numérica ambigua. Por ejemplo, no está claro qué componentes de la fecha representada por la cadena "02/03/04" son el mes, el día y el año. En este caso, los componentes se interpretan según el orden de formatos de fecha similares del proveedor de formato.  
  
## <a name="parse"></a>Parse  
 En el ejemplo de código siguiente se muestra el uso de la **analizar** método para convertir una cadena en un **DateTime**. En este ejemplo se usa la referencia cultural asociada al subproceso actual para realizar el análisis. Si el <xref:System.Globalization.CultureInfo> asociada a la actual referencia cultural no puede analizar la cadena de entrada, un <xref:System.FormatException> se produce.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 También puede especificar un **CultureInfo** establecido en una de las referencias culturales definidas por ese objeto, o puede especificar uno de los estándar <xref:System.Globalization.DateTimeFormatInfo> objetos devueltos por la <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> propiedad. En el ejemplo de código siguiente se usa un proveedor de formato para analizar una cadena alemana en un **DateTime**. A **CultureInfo** que representa la referencia cultural de-DE se define y se pasa con la cadena que se está analiza para garantizar el análisis correcto de esta cadena concreta. Esto impide que cualquier otra opción está en el **CurrentCulture** de la **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Sin embargo, aunque puede utilizar las sobrecargas de los <xref:System.DateTime.Parse%2A> método para especificar los proveedores de formato personalizado, el método no admite el uso de proveedores de formato no estándar. Para analizar una fecha y hora expresadas en un formato no estándar, use la <xref:System.DateTime.ParseExact%2A> método en su lugar.  
  
 El siguiente ejemplo de código utiliza el <xref:System.Globalization.DateTimeStyles> enumeración para especificar que la información de fecha y hora actual no debe agregarse a la **DateTime** para los campos que no defina la cadena.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 El <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> método convierte una cadena que se ajusta a un patrón de la cadena especificada para un **DateTime** objeto. Cuando se pasa una cadena que no tiene el formato especificado a este método, un <xref:System.FormatException> se produce. Puede especificar uno de los especificadores de formato de fecha y hora estándar o una combinación limitada de especificadores de formato de fecha y hora personalizados. Con el uso de especificadores de formato personalizados, es posible construir una cadena de reconocimiento personalizada. Para obtener una explicación de los especificadores, consulte los temas sobre [cadenas con formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) y [cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Cada sobrecarga de la <xref:System.DateTime.ParseExact%2A> método también tiene un <xref:System.IFormatProvider> parámetro que normalmente proporciona información específica de la referencia cultural acerca del formato de la cadena. Normalmente, esto <xref:System.IFormatProvider> objeto es un <xref:System.Globalization.CultureInfo> objeto que representa una referencia cultural estándar o un <xref:System.Globalization.DateTimeFormatInfo> objeto devuelto por la <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> propiedad. Sin embargo, a diferencia de la otra fecha y hora funciones de análisis, este método también es compatible con un <xref:System.IFormatProvider> que define una fecha no estándar y el formato de hora.  
  
 En el ejemplo de código siguiente, la **ParseExact** método se pasa un objeto de cadena debe analizar, seguido de un especificador de formato, seguido de un **CultureInfo** objeto. Esto **ParseExact** método sólo puede analizar cadenas que muestren el modelo de fecha larga de la referencia cultural en-US.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 [Analizar cadenas](../../../docs/standard/base-types/parsing-strings.md)  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)  
 [Conversión de tipos en .NET](../../../docs/standard/base-types/type-conversion.md)
