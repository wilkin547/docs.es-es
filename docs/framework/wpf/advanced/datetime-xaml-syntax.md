---
title: DateTime (Sintaxis XAML)
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: d7fe5f15f79ab068e88c3fb6f7b7cac0986aa636
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052929"
---
# <a name="datetime-xaml-syntax"></a>DateTime (Sintaxis XAML)
Algunos controles, como <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker>, tienen propiedades que usan el <xref:System.DateTime> tipo. Aunque normalmente se especifica una fecha y hora inicial para estos controles en el código subyacente en tiempo de ejecución, puede especificar una fecha u hora inicial en XAML. El analizador de WPF XAML controla el análisis de <xref:System.DateTime> valores mediante una sintaxis de texto XAML integrada. En este tema se describe los detalles de la <xref:System.DateTime> sintaxis de texto XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Cuándo usar la sintaxis XAML de DateTime  
 Establecer fechas en XAML no siempre es necesario y puede incluso no ser deseable. Por ejemplo, podría utilizar el <xref:System.DateTime.Now%2A?displayProperty=nameWithType> propiedad para inicializar una fecha en tiempo de ejecución, o podría hacer todos los ajustes de fecha de un calendario en el código subyacente en función de entrada del usuario. Sin embargo, hay escenarios donde es posible que desee fechas de codificar de forma rígida en un <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker> en una plantilla de control. El <xref:System.DateTime> deben utilizarse la sintaxis XAML para estos escenarios.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintaxis XAML de DateTime es un comportamiento nativo  
 <xref:System.DateTime> es una clase que se define en las bibliotecas de clases base de CLR. Debido a cómo se relacionan las bibliotecas de clases base con el resto de CLR, no es posible aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la clase y el uso de un convertidor de tipos para procesar cadenas de XAML y convertirlas a <xref:System.DateTime> en el modelo de objetos de tiempo de ejecución. No existe ninguna clase `DateTimeConverter` que proporcione el comportamiento de conversión; el comportamiento de conversión que se describe en este tema es nativo para el analizador de XAML de WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Cadenas de formato para la sintaxis XAML de DateTime  
 Puede especificar el formato de un <xref:System.DateTime> con una cadena de formato. Las cadenas de formato formalizan la sintaxis de texto que puede usarse para crear un valor. <xref:System.DateTime> los valores de los controles de WPF existente generalmente solo utilizan los componentes de fecha de <xref:System.DateTime> y no los componentes de tiempo.  
  
 Al especificar un <xref:System.DateTime> en XAML, puede usar cualquiera de las cadenas de formato indistintamente.  
  
 También puede usar formatos y cadenas de formato que no se muestren específicamente en este tema. Técnicamente, el XAML para cualquier <xref:System.DateTime> valor especificado y, a continuación, analice el analizador de WPF XAML usa una llamada interna a <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, por lo tanto, podría utilizar cualquier cadena aceptado por <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> para el XAML de entrada. Para obtener más información, consulta <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  La sintaxis XAML DateTime siempre usa `en-us` como el <xref:System.Globalization.CultureInfo> para su conversión nativa. Esto no se ve influenciado por <xref:System.Windows.FrameworkElement.Language%2A> valor o `xml:lang` valor en el XAML, porque la conversión de tipo de nivel de atributo XAML actúa sin ese contexto. No intente interpolar las cadenas de formato que se muestran aquí debido a las variaciones culturales, como el orden en que aparecen el día y el mes. Las cadenas de formato que se muestran aquí son las cadenas de formato exactas que se usan al analizar el lenguaje XAML, independientemente de otras configuraciones de referencias culturales.  
  
 Las secciones siguientes describen algunos de los comunes <xref:System.DateTime> cadenas con formato.  
  
### <a name="short-date-pattern-d"></a>Patrón de fecha corta ("d")  
 La siguiente muestra el formato de fecha corta para un <xref:System.DateTime> en XAML:  
  
 `M/d/YYYY`  
  
 Se trata de la forma más simple que especifica toda la información necesaria para los usos típicos de los controles de WPF y no puede verse afectada por desfases accidentales de las zonas horarias en comparación con un componente de tiempo y, por tanto, es preferible a otros formatos.  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena:  
  
 `3/1/2010`  
  
 Para obtener más información, consulta <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Patrón de DateTime ordenable ("s")  
 La siguiente muestra la que se puede ordenar <xref:System.DateTime> patrón en XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Patrón RFC1123 ("r")  
 El patrón RFC1123 resulta útil porque podría ser una cadena introducida desde otros generadores de fecha que también usan este patrón por motivos de invariabilidad de referencia cultural. La siguiente muestra el valor de RFC1123 <xref:System.DateTime> patrón en XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Otros formatos y patrones  
 Como se indicó anteriormente, un <xref:System.DateTime> en XAML se puede especificar como cualquier cadena que es aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Esto incluye otros formatos formalizados (por ejemplo <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) y formatos no formalizados como un determinado <xref:System.Globalization.DateTimeFormatInfo> formulario. Por ejemplo, el formulario `YYYY/mm/dd` es aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. En este tema no se intentan describir todos los formatos posibles que funcionan, sino que se recomienda el patrón de fecha corta como procedimiento estándar.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
