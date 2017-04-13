---
title: "Analizar cadenas de fecha y hora en .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tipos base, analizar cadenas"
  - "cadenas de fecha y hora"
  - "DateTime (objeto)"
  - "enumeraciones [.NET Framework], analizar cadenas"
  - "ParseExact (método)"
  - "analizar cadenas, cadenas de fecha y hora"
  - "cadenas de hora"
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# Analizar cadenas de fecha y hora en .NET Framework
Los métodos de análisis convierten la representación de cadena de una fecha y hora en un objeto <xref:System.DateTime> equivalente.  Los métodos <xref:System.DateTime.Parse%2A> y <xref:System.DateTime.TryParse%2A> convierten cualquier representación de una serie de representaciones comunes de fecha y hora.  Los métodos <xref:System.DateTime.ParseExact%2A> y <xref:System.DateTime.TryParseExact%2A> convierten una representación de cadena que se ajusta al modelo especificado por una cadena de formato de fecha y hora. \(Vea los temas sobre [cadenas de formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) y [cadenas de formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).\)  
  
 El análisis se ve influenciado por las propiedades de un proveedor de formato que proporciona información como, por ejemplo, las cadenas utilizadas para los separadores de fecha y hora y los nombres de los meses, días y eras.  El proveedor de formato es el objeto <xref:System.Globalization.DateTimeFormatInfo> actual, proporcionado implícitamente por la referencia cultural del subproceso actual o explícitamente por el parámetro <xref:System.IFormatProvider> de un método de análisis.  Para el parámetro <xref:System.IFormatProvider>, especifique un objeto <xref:System.Globalization.CultureInfo>, que representa una referencia cultural o un objeto <xref:System.Globalization.DateTimeFormatInfo>.  
  
 La representación de cadena de una fecha que vaya a analizarse deberá incluir el mes y, por lo menos, un día o año.  La representación de cadena de una hora deberá incluir la hora y, por lo menos, los minutos o el designador a.m.\/p.m.  No obstante, si es posible, el análisis proporciona valores predeterminados para los componentes omitidos.  Si falta una fecha, se utiliza el valor predeterminado de fecha actual; si falta un año, el año actual; si falta un día del mes, el primer día del mes; y si falta una hora, la medianoche.  
  
 Si la representación de cadena sólo especifica una hora, el análisis devuelve un objeto <xref:System.DateTime> con las propiedades  <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> y <xref:System.DateTime.Day%2A> establecidas en los valores correspondientes a la propiedad <xref:System.DateTime.Today%2A>.  Sin embargo, si en el método de análisis se especifica la constante <xref:System.Globalization.DateTimeStyles>, las propiedades de año, mes y día resultantes se establecen en el valor `1`.  
  
 Además de un componente de fecha y hora, la representación de cadena de una fecha y una hora puede incluir un desplazamiento que indica la diferencia de la hora con respecto a la hora universal coordinada \(UTC\).  Por ejemplo, la cadena "2\/14\/2007 5:32:00 \-7:00" define una hora que es siete horas más temprano que la hora UTC.  Si en la representación de cadena de una hora se omite la diferencia, el análisis devuelve un objeto <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> está establecida en <xref:System.DateTimeKind?displayProperty=fullName>.  Si se especifica una diferencia, el análisis devuelve un objeto <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> está establecida en <xref:System.DateTimeKind> y cuyo valor está ajustado a la zona horaria local del equipo.  Puede modificar este comportamiento utilizando una constante <xref:System.Globalization.DateTimeStyles> con el método de análisis.  
  
 El proveedor de formato también se utiliza para interpretar una fecha numérica ambigua.  Por ejemplo, no queda claro qué componentes de la fecha representados por la cadena "02\/03\/04" corresponden al mes, al día y al año.  En este caso, los componentes se interpretan según el orden de formatos de fecha similares del proveedor de formato.  
  
## Parse  
 En el ejemplo de código siguiente se ilustra el uso del método **Parse** para convertir una cadena en **DateTime**.  En este ejemplo, para realizar el análisis, se utiliza la referencia cultural asociada al subproceso actual.  Si el objeto <xref:System.Globalization.CultureInfo> asociado a la referencia cultural actual no puede analizar la cadena de entrada, se produce una excepción <xref:System.FormatException>.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 También puede establecer un objeto **CultureInfo** en una de las referencias culturales definidas por ese objeto, o puede especificar uno de los objetos <xref:System.Globalization.DateTimeFormatInfo> estándar devueltos por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  En el ejemplo de código siguiente se utiliza un proveedor de formato para analizar una cadena alemana en un objeto **DateTime**.  Un objeto **CultureInfo** que representa la referencia cultural de\-DE se define y se pasa con la cadena que se está analizando para garantizar el análisis correcto de esta cadena concreta.  Esto descarta el valor que tenga **CurrentCulture** de **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Sin embargo, aunque puede utilizar sobrecargas del método <xref:System.DateTime.Parse%2A> para especificar proveedores de formato personalizado, el método no admite el uso de proveedores de formato no estándar.  Para analizar una fecha y una hora expresadas en un formato no estándar, utilice en su lugar el método <xref:System.DateTime.ParseExact%2A>.  
  
 En el ejemplo de código siguiente se utiliza la enumeración <xref:System.Globalization.DateTimeStyles> para especificar que la información de fecha y hora actual no se debe agregar al objeto **DateTime** en los campos que la cadena no defina.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## ParseExact  
 El método <xref:System.DateTime.ParseExact%2A?displayProperty=fullName> convierte una cadena que se ajusta a un patrón de cadena especificado en un objeto **DateTime**.  Cuando se pasa a este método una cadena que no tiene el formato especificado, se produce una excepción <xref:System.FormatException>.  Se puede definir uno de los especificadores de formato de fecha y hora estándar o una combinación limitada de los especificadores de formato de fecha y hora personalizados.  Si se usan los especificadores de formato personalizados, se puede construir una cadena de reconocimiento personalizada.  Para obtener una explicación de los especificadores, vea los temas sobre [cadenas de formato de fecha y hora estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) y [cadenas de formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Cada sobrecarga del método <xref:System.DateTime.ParseExact%2A> también tiene un parámetro <xref:System.IFormatProvider> que, normalmente, proporciona información específica de la referencia cultural sobre el formato de la cadena.  Normalmente, este objeto <xref:System.IFormatProvider> es un objeto <xref:System.Globalization.CultureInfo> que representa una referencia cultural estándar o un objeto <xref:System.Globalization.DateTimeFormatInfo> devuelto por la propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>.  Sin embargo, a diferencia de las demás funciones de análisis de fecha y hora, este método también admite una interfaz <xref:System.IFormatProvider> que define un formato de fecha y hora no estándar.  
  
 En el ejemplo de código siguiente, se pasa al método **ParseExact** un objeto de cadena que se debe analizar, seguido de un especificador de formato, seguido de un objeto **CultureInfo**.  Este método **ParseExact** sólo puede analizar cadenas que muestren el modelo de fecha larga de la referencia cultural en\-US.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## Vea también  
 [Analizar cadenas](../../../docs/standard/base-types/parsing-strings.md)   
 [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md)   
 [Conversión de tipos en .NET Framework](../../../docs/standard/base-types/type-conversion.md)