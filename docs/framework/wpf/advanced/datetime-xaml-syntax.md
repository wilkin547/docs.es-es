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
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186328"
---
# <a name="datetime-xaml-syntax"></a>DateTime (Sintaxis XAML)
Algunos controles, <xref:System.Windows.Controls.Calendar> como <xref:System.Windows.Controls.DatePicker>y , tienen <xref:System.DateTime> propiedades que usan el tipo. Aunque normalmente se especifica una fecha y hora inicial para estos controles en el código subyacente en tiempo de ejecución, puede especificar una fecha u hora inicial en XAML. El analizador XAML de WPF <xref:System.DateTime> controla el análisis de valores mediante una sintaxis de texto XAML integrada. En este tema se describen los detalles de la <xref:System.DateTime> sintaxis de texto XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a>Cuándo usar la sintaxis XAML de DateTime  
 Establecer fechas en XAML no siempre es necesario y puede incluso no ser deseable. Por ejemplo, podría <xref:System.DateTime.Now%2A?displayProperty=nameWithType> usar la propiedad para inicializar una fecha en tiempo de ejecución, o podría realizar todos los ajustes de fecha para un calendario en el código subyacente en función de la entrada del usuario. Sin embargo, hay escenarios en los que <xref:System.Windows.Controls.Calendar> es <xref:System.Windows.Controls.DatePicker> posible que desee codificar de forma rígida las fechas en a y en una plantilla de control. La <xref:System.DateTime> sintaxis XAML se debe usar para estos escenarios.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintaxis XAML de DateTime es un comportamiento nativo  
 <xref:System.DateTime>es una clase que se define en las bibliotecas de clases base de CLR. Debido a cómo se relacionan las bibliotecas de clases base <xref:System.ComponentModel.TypeConverterAttribute> con el resto de CLR, no es posible <xref:System.DateTime> aplicar a la clase y usar un convertidor de tipos para procesar cadenas desde XAML y convertirlas en el modelo de objetos en tiempo de ejecución. No existe ninguna clase `DateTimeConverter` que proporcione el comportamiento de conversión; el comportamiento de conversión que se describe en este tema es nativo para el analizador de XAML de WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a>Cadenas de formato para la sintaxis XAML de DateTime  
 Puede especificar el formato <xref:System.DateTime> de a con una cadena de formato. Las cadenas de formato formalizan la sintaxis de texto que puede usarse para crear un valor. <xref:System.DateTime>Los valores de los controles WPF existentes <xref:System.DateTime> generalmente solo usan los componentes de fecha de los componentes de tiempo y no los.  
  
 Al especificar <xref:System.DateTime> un en XAML, puede usar cualquiera de las cadenas de formato indistintamente.  
  
 También puede usar formatos y cadenas de formato que no se muestren específicamente en este tema. Técnicamente, el XAML <xref:System.DateTime> para cualquier valor especificado y, a continuación, analizado <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>por el analizador XAML de <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> WPF usa una llamada interna a , por lo tanto, podría usar cualquier cadena aceptada por la entrada XAML. Para más información, consulte <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> La sintaxis XAML `en-us` DateTime <xref:System.Globalization.CultureInfo> siempre usa como para su conversión nativa. Esto no se <xref:System.Windows.FrameworkElement.Language%2A> ve `xml:lang` influenciado por el valor o el valor en el XAML, porque la conversión de tipos de nivel de atributo XAML actúa sin ese contexto. No intente interpolar las cadenas de formato que se muestran aquí debido a las variaciones culturales, como el orden en que aparecen el día y el mes. Las cadenas de formato que se muestran aquí son las cadenas de formato exactas que se usan al analizar el lenguaje XAML, independientemente de otras configuraciones de referencias culturales.  
  
 En las secciones siguientes <xref:System.DateTime> se describen algunas de las cadenas de formato comunes.  
  
### <a name="short-date-pattern-d"></a>Patrón de fecha corta ("d")  
 A continuación se muestra el <xref:System.DateTime> formato de fecha corta para un en XAML:  
  
 `M/d/YYYY`  
  
 Se trata de la forma más simple que especifica toda la información necesaria para los usos típicos de los controles de WPF y no puede verse afectada por desfases accidentales de las zonas horarias en comparación con un componente de tiempo y, por tanto, es preferible a otros formatos.  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena:  
  
 `3/1/2010`  
  
 Para más información, consulte <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Patrón de DateTime ordenable ("s")  
 A continuación se muestra <xref:System.DateTime> el patrón que se puede ordenar en XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Patrón RFC1123 ("r")  
 El patrón RFC1123 resulta útil porque podría ser una cadena introducida desde otros generadores de fecha que también usan este patrón por motivos de invariabilidad de referencia cultural. A continuación se muestra el <xref:System.DateTime> patrón RFC1123 en XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Otros formatos y patrones  
 Como se indicó anteriormente, un <xref:System.DateTime> en XAML se puede <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>especificar como cualquier cadena que sea aceptable como entrada para . Esto incluye otros formatos <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>formalizados (por ejemplo) y <xref:System.Globalization.DateTimeFormatInfo> formatos que no se formalizan como un formulario determinado. Por ejemplo, `YYYY/mm/dd` el formulario es <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>aceptable como entrada para . En este tema no se intentan describir todos los formatos posibles que funcionan, sino que se recomienda el patrón de fecha corta como procedimiento estándar.  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
