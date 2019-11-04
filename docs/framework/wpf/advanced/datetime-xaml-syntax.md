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
ms.openlocfilehash: c9fb030e6f819b1ca463199a76acd32cb1865f33
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458938"
---
# <a name="datetime-xaml-syntax"></a>DateTime (Sintaxis XAML)
Algunos controles, como <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker>, tienen propiedades que usan el tipo de <xref:System.DateTime>. Aunque normalmente se especifica una fecha y hora inicial para estos controles en el código subyacente en tiempo de ejecución, puede especificar una fecha u hora inicial en XAML. El analizador de XAML de WPF controla el análisis de valores de <xref:System.DateTime> mediante una sintaxis de texto XAML integrada. En este tema se describen los detalles de la sintaxis de texto XAML de <xref:System.DateTime>.  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Cuándo usar la sintaxis XAML de DateTime  
 Establecer fechas en XAML no siempre es necesario y puede incluso no ser deseable. Por ejemplo, puede usar la propiedad <xref:System.DateTime.Now%2A?displayProperty=nameWithType> para inicializar una fecha en tiempo de ejecución, o puede realizar todos los ajustes de fecha de un calendario en el código subyacente en función de los datos proporcionados por el usuario. Sin embargo, hay escenarios en los que es posible que desee codificar las fechas en un <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker> en una plantilla de control. La sintaxis XAML de <xref:System.DateTime> debe usarse para estos escenarios.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintaxis XAML de DateTime es un comportamiento nativo  
 <xref:System.DateTime> es una clase que se define en las bibliotecas de clases base de CLR. Debido al modo en que las bibliotecas de clases base se relacionan con el resto de CLR, no es posible aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la clase y usar un convertidor de tipos para procesar cadenas de XAML y convertirlas en <xref:System.DateTime> en el modelo de objetos de tiempo de ejecución. No existe ninguna clase `DateTimeConverter` que proporcione el comportamiento de conversión; el comportamiento de conversión que se describe en este tema es nativo para el analizador de XAML de WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Cadenas de formato para la sintaxis XAML de DateTime  
 Puede especificar el formato de una <xref:System.DateTime> con una cadena de formato. Las cadenas de formato formalizan la sintaxis de texto que puede usarse para crear un valor. los valores de <xref:System.DateTime> de los controles de WPF existentes generalmente solo utilizan los componentes de fecha de <xref:System.DateTime> y no los componentes de hora.  
  
 Al especificar una <xref:System.DateTime> en XAML, puede utilizar cualquiera de las cadenas de formato indistintamente.  
  
 También puede usar formatos y cadenas de formato que no se muestren específicamente en este tema. Técnicamente, el XAML de cualquier valor <xref:System.DateTime> que se especifica y, a continuación, lo analiza el analizador XAML de WPF usa una llamada interna a <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, por lo tanto, puede usar cualquier cadena aceptada por <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> para la entrada XAML. Para obtener más información, vea <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> La sintaxis XAML de DateTime siempre usa `en-us` como <xref:System.Globalization.CultureInfo> para su conversión nativa. Esto no se ve afectado por <xref:System.Windows.FrameworkElement.Language%2A> valor o `xml:lang` valor en el código XAML, ya que la conversión de tipos de nivel de atributo de XAML actúa sin ese contexto. No intente interpolar las cadenas de formato que se muestran aquí debido a las variaciones culturales, como el orden en que aparecen el día y el mes. Las cadenas de formato que se muestran aquí son las cadenas de formato exactas que se usan al analizar el lenguaje XAML, independientemente de otras configuraciones de referencias culturales.  
  
 En las secciones siguientes se describen algunas de las cadenas de formato de <xref:System.DateTime> comunes.  
  
### <a name="short-date-pattern-d"></a>Patrón de fecha corta ("d")  
 A continuación se muestra el formato de fecha corta para un <xref:System.DateTime> en XAML:  
  
 `M/d/YYYY`  
  
 Se trata de la forma más simple que especifica toda la información necesaria para los usos típicos de los controles de WPF y no puede verse afectada por desfases accidentales de las zonas horarias en comparación con un componente de tiempo y, por tanto, es preferible a otros formatos.  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena:  
  
 `3/1/2010`  
  
 Para obtener más información, vea <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Patrón de DateTime ordenable ("s")  
 A continuación se muestra el patrón de <xref:System.DateTime> ordenable en XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Patrón RFC1123 ("r")  
 El patrón RFC1123 resulta útil porque podría ser una cadena introducida desde otros generadores de fecha que también usan este patrón por motivos de invariabilidad de referencia cultural. A continuación se muestra el patrón de <xref:System.DateTime> de RFC1123 en XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Otros formatos y patrones  
 Como se indicó anteriormente, se puede especificar un <xref:System.DateTime> en XAML como cualquier cadena que sea aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Esto incluye otros formatos formalizados (por ejemplo <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) y formatos no formalizados como un formulario de <xref:System.Globalization.DateTimeFormatInfo> determinado. Por ejemplo, el formulario `YYYY/mm/dd` es aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. En este tema no se intentan describir todos los formatos posibles que funcionan, sino que se recomienda el patrón de fecha corta como procedimiento estándar.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
