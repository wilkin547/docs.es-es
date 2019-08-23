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
ms.openlocfilehash: 36066d6b2405051a3d35befffe53af8895e26220
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964830"
---
# <a name="datetime-xaml-syntax"></a>DateTime (Sintaxis XAML)
Algunos controles, <xref:System.Windows.Controls.Calendar> como y <xref:System.Windows.Controls.DatePicker>, tienen propiedades que usan el <xref:System.DateTime> tipo. Aunque normalmente se especifica una fecha y hora inicial para estos controles en el código subyacente en tiempo de ejecución, puede especificar una fecha u hora inicial en XAML. El analizador XAML de WPF controla el <xref:System.DateTime> análisis de valores mediante una sintaxis de texto XAML integrada. En este tema se describen los detalles de <xref:System.DateTime> la sintaxis de texto XAML.  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Cuándo usar la sintaxis XAML de DateTime  
 Establecer fechas en XAML no siempre es necesario y puede incluso no ser deseable. Por ejemplo, puede utilizar la <xref:System.DateTime.Now%2A?displayProperty=nameWithType> propiedad para inicializar una fecha en tiempo de ejecución, o puede realizar todos los ajustes de fecha de un calendario en el código subyacente en función de los datos proporcionados por el usuario. Sin embargo, hay escenarios en los que es posible que desee codificar las fechas <xref:System.Windows.Controls.Calendar> en <xref:System.Windows.Controls.DatePicker> un y en una plantilla de control. La <xref:System.DateTime> sintaxis XAML se debe usar en estos escenarios.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>La sintaxis XAML de DateTime es un comportamiento nativo  
 <xref:System.DateTime>es una clase que se define en las bibliotecas de clases base de CLR. Debido al modo en que las bibliotecas de clases base se relacionan con el resto de CLR, no es <xref:System.ComponentModel.TypeConverterAttribute> posible aplicar a la clase y usar un convertidor de tipos para procesar cadenas de XAML y <xref:System.DateTime> convertirlas en en el modelo de objetos de tiempo de ejecución. No existe ninguna clase `DateTimeConverter` que proporcione el comportamiento de conversión; el comportamiento de conversión que se describe en este tema es nativo para el analizador de XAML de WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Cadenas de formato para la sintaxis XAML de DateTime  
 Puede especificar el formato de <xref:System.DateTime> con una cadena de formato. Las cadenas de formato formalizan la sintaxis de texto que puede usarse para crear un valor. <xref:System.DateTime>los valores de los controles de WPF existentes generalmente solo utilizan los componentes <xref:System.DateTime> de fecha de y no los componentes de hora.  
  
 Al especificar un <xref:System.DateTime> en XAML, puede usar cualquiera de las cadenas de formato indistintamente.  
  
 También puede usar formatos y cadenas de formato que no se muestren específicamente en este tema. Técnicamente, el XAML para cualquier <xref:System.DateTime> valor que se especifica y, a continuación, lo analiza el analizador XAML de WPF usa una <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>llamada interna a, por lo que puede usar <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> cualquier cadena aceptada por para la entrada XAML. Para obtener más información, consulta <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> La sintaxis XAML <xref:System.Globalization.CultureInfo> de DateTime siempre `en-us` usa como para su conversión nativa. Esto no se ve afectado <xref:System.Windows.FrameworkElement.Language%2A> por valor `xml:lang` o valor en el código XAML, ya que la conversión de tipos de nivel de atributo de XAML actúa sin ese contexto. No intente interpolar las cadenas de formato que se muestran aquí debido a las variaciones culturales, como el orden en que aparecen el día y el mes. Las cadenas de formato que se muestran aquí son las cadenas de formato exactas que se usan al analizar el lenguaje XAML, independientemente de otras configuraciones de referencias culturales.  
  
 En las secciones siguientes se describen algunas de <xref:System.DateTime> las cadenas de formato comunes.  
  
### <a name="short-date-pattern-d"></a>Patrón de fecha corta ("d")  
 A continuación se muestra el formato de fecha corta <xref:System.DateTime> para un en XAML:  
  
 `M/d/YYYY`  
  
 Se trata de la forma más simple que especifica toda la información necesaria para los usos típicos de los controles de WPF y no puede verse afectada por desfases accidentales de las zonas horarias en comparación con un componente de tiempo y, por tanto, es preferible a otros formatos.  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena:  
  
 `3/1/2010`  
  
 Para obtener más información, consulta <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Patrón de DateTime ordenable ("s")  
 A continuación se muestra el <xref:System.DateTime> patrón de ordenación en XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>Patrón RFC1123 ("r")  
 El patrón RFC1123 resulta útil porque podría ser una cadena introducida desde otros generadores de fecha que también usan este patrón por motivos de invariabilidad de referencia cultural. A continuación se muestra el <xref:System.DateTime> patrón RFC1123 en XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Por ejemplo, para especificar la fecha 1 de junio de 2010, use la siguiente cadena (todos los componentes de tiempo se especifican como 0):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Otros formatos y patrones  
 Como se indicó anteriormente, <xref:System.DateTime> se puede especificar un en XAML como cualquier cadena que sea aceptable como entrada <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>para. Esto incluye otros formatos formalizados (por ejemplo <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) y formatos no formalizados como un formulario determinado. <xref:System.Globalization.DateTimeFormatInfo> Por ejemplo, el formulario `YYYY/mm/dd` es aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. En este tema no se intentan describir todos los formatos posibles que funcionan, sino que se recomienda el patrón de fecha corta como procedimiento estándar.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre XAML (WPF)](xaml-overview-wpf.md)
