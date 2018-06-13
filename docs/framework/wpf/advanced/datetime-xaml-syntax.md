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
ms.openlocfilehash: 286117cc0cce9fb54ea2c372360b13865fba77ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540568"
---
# <a name="datetime-xaml-syntax"></a>DateTime (Sintaxis XAML)
Algunos controles, como <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker>, tienen propiedades que utilizan el <xref:System.DateTime> tipo. Aunque normalmente se especifica una fecha y hora inicial para estos controles en el código subyacente en tiempo de ejecución, puede especificar una fecha u hora inicial en XAML. El analizador de XAML de WPF controla el análisis de <xref:System.DateTime> valores mediante una sintaxis de texto XAML integrada. Este tema describe los detalles de la <xref:System.DateTime> sintaxis de texto XAML.  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Cuándo usar la sintaxis XAML de DateTime  
 Establecer fechas en XAML no siempre es necesario y puede incluso no ser deseable. Por ejemplo, podría usar la <xref:System.DateTime.Now%2A?displayProperty=nameWithType> propiedad para inicializar una fecha en tiempo de ejecución, o podría hacer todos los ajustes de fecha para un calendario en el código subyacente según proporcionados por el usuario. Sin embargo, hay escenarios donde puede que desee para las fechas de codificar de forma rígida en un <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker> en una plantilla de control. El <xref:System.DateTime> para estos escenarios, se debe emplear la sintaxis XAML.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintaxis XAML de DateTime es un comportamiento nativo  
 <xref:System.DateTime> es una clase que se define en las bibliotecas de clases base de CLR. Debido a cómo se relacionan las bibliotecas de clases base con el resto de CLR, no es posible aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la clase y use un convertidor de tipos para procesar cadenas de XAML y convertirlos a <xref:System.DateTime> en el modelo de objetos de tiempo de ejecución. No existe ninguna clase `DateTimeConverter` que proporcione el comportamiento de conversión; el comportamiento de conversión que se describe en este tema es nativo para el analizador de XAML de WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Cadenas de formato para la sintaxis XAML de DateTime  
 Puede especificar el formato de un <xref:System.DateTime> con una cadena de formato. Las cadenas de formato formalizan la sintaxis de texto que puede usarse para crear un valor. <xref:System.DateTime> los valores de controles de WPF existente generalmente solo utilizan los componentes de fecha de <xref:System.DateTime> y no los componentes de tiempo.  
  
 Al especificar un <xref:System.DateTime> en XAML, puede usar cualquiera de las cadenas de formato indistintamente.  
  
 También puede usar formatos y cadenas de formato que no se muestren específicamente en este tema. Técnicamente, el XAML para cualquier <xref:System.DateTime> valor que se especifica y, a continuación, se analiza el analizador de XAML de WPF utiliza una llamada interna a <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, por lo tanto, podría utilizar cualquier cadena aceptada por <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> para el XAML de entrada. Para obtener más información, consulta <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  La sintaxis de XAML de DateTime siempre utiliza `en-us` como el <xref:System.Globalization.CultureInfo> para su conversión nativa. Esto no se ve influenciado por <xref:System.Windows.FrameworkElement.Language%2A> valor o `xml:lang` valor en el XAML, porque la conversión de tipo de nivel de atributo XAML actúa sin ese contexto. No intente interpolar las cadenas de formato que se muestran aquí debido a las variaciones culturales, como el orden en que aparecen el día y el mes. Las cadenas de formato que se muestran aquí son las cadenas de formato exactas que se usan al analizar el lenguaje XAML, independientemente de otras configuraciones de referencias culturales.  
  
 Las siguientes secciones describen algunos de los comunes <xref:System.DateTime> las cadenas de formato.  
  
### <a name="short-date-pattern-d"></a>Patrón de fecha corta ("d")  
 La siguiente muestra el formato de fecha corta para un <xref:System.DateTime> en XAML:  
  
 `M/d/YYYY`  
  
 Se trata de la forma más simple que especifica toda la información necesaria para los usos típicos de los controles de WPF y no puede verse afectada por desfases accidentales de las zonas horarias en comparación con un componente de tiempo y, por tanto, es preferible a otros formatos.  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena:  
  
 `3/1/2010`  
  
 Para obtener más información, consulta <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Patrón de DateTime ordenable ("s")  
 La continuación muestra el que se puede ordenar <xref:System.DateTime> patrón en XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Patrón RFC1123 ("r")  
 El patrón RFC1123 resulta útil porque podría ser una cadena introducida desde otros generadores de fecha que también usan este patrón por motivos de invariabilidad de referencia cultural. La siguiente muestra el RFC1123 <xref:System.DateTime> patrón en XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Otros formatos y patrones  
 Como se indicó anteriormente, un <xref:System.DateTime> en XAML se puede especificar como una cadena que sea aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Esto incluye otros formatos formalizados (por ejemplo <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) y los formatos que no son formalizados como un determinado <xref:System.Globalization.DateTimeFormatInfo> formulario. Por ejemplo, el formulario `YYYY/mm/dd` es aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. En este tema no se intentan describir todos los formatos posibles que funcionan, sino que se recomienda el patrón de fecha corta como procedimiento estándar.  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
