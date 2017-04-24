---
title: "DateTime (Sintaxis XAML) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DateTime (sintaxis XAML) [WPF]"
  - "DateTime (sintaxis XAML) [WPF], cadenas de formato para"
  - "DateTime (sintaxis XAML) [WPF], cadenas para"
  - "DateTime (sintaxis XAML) [WPF], dónde se usa"
  - "DateTime (texto XAML) [WPF]"
  - "formato de fecha corta [WPF], DateTime"
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DateTime (Sintaxis XAML)
Algunos controles, como <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker> tienen propiedades que usan el tipo <xref:System.DateTime>.  Aunque normalmente se especifica una fecha u hora inicial para estos controles en el código subyacente en tiempo de ejecución, puede especificar una fecha u hora inicial en XAML.  El analizador XAML de WPF controla el análisis de los valores <xref:System.DateTime> utilizando una sintaxis de texto de XAML integrada.  En este tema se describen las características específicas de la sintaxis de texto XAML <xref:System.DateTime>  
  
   
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## Cuándo utilizar la sintaxis XAML de DateTime  
 No siempre es necesario establecer las fechas en XAML, e incluso puede que no se desee.  Por ejemplo, puede usar la propiedad <xref:System.DateTime.Now%2A?displayProperty=fullName> para inicializar una fecha en tiempo de ejecución o podría hacer todos los ajustes de fecha para un calendario en el archivo de código subyacente basándose en los datos proporcionados por el usuario.  Sin embargo, hay escenarios en los que puede resultar conveniente integrar las fechas en <xref:System.Windows.Controls.Calendar> y <xref:System.Windows.Controls.DatePicker> en una plantilla de control.  La sintaxis XAML <xref:System.DateTime> debe utilizarse para estos escenarios.  
  
### La sintaxis XAML de DateTime es un comportamiento nativo  
 <xref:System.DateTime> es una clase que se define en las bibliotecas de clases base de CLR.  Debido al modo en que se relacionan las bibliotecas de clases base con el resto de CLR, no es posible aplicar <xref:System.ComponentModel.TypeConverterAttribute> a la clase y utilizar un convertidor de tipos para procesar cadenas de XAML y convertirlas en <xref:System.DateTime> en el modelo de objetos en tiempo de ejecución.  No hay ninguna clase `DateTimeConverter` que proporcione el comportamiento de conversión; dicho comportamiento, descrito en este tema, es un comportamiento nativo del analizador XAML de WPF.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## Cadenas de formato para la sintaxis XAML de DateTime  
 Puede especificar el formato de un objeto <xref:System.DateTime> con una cadena de formato.  Las cadenas de formato formalizan la sintaxis de texto que se puede utilizar para crear un valor.  Los valores <xref:System.DateTime> de los controles de WPF existentes generalmente solo utilizan los componentes de fecha de <xref:System.DateTime> y no los componentes horarios.  
  
 Al especificar <xref:System.DateTime> en XAML, puede utilizar cualquiera de las cadenas de formato de forma intercambiable.  
  
 También puede utilizar los formatos y cadenas de formato que no se muestran específicamente en este tema.  Técnicamente, el XAML de cualquier valor <xref:System.DateTime> que es especificado y, a continuación, analizado por el analizador XAML de WPF utiliza una llamada interna a <xref:System.DateTime.Parse%2A?displayProperty=fullName>, por consiguiente, podría utilizar cualquier cadena aceptada por <xref:System.DateTime.Parse%2A?displayProperty=fullName> para su entrada XAML.  Para obtener más información, vea <xref:System.DateTime.Parse%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  La sintaxis de XAML de DateTime siempre utiliza `en-us` como <xref:System.Globalization.CultureInfo> para su conversión nativa.  Esto no se ve influido por el valor <xref:System.Windows.FrameworkElement.Language%2A> o el valor `xml:lang` en el XAML, porque la conversión de tipos en el nivel de atributo XAML actúa sin ese contexto.  No intente interpolar las cadenas de formato mostradas aquí debido a las variaciones culturales, como el orden en el que aparecen el día y mes.  Las cadenas de formato mostradas aquí son las cadenas de formato exactas utilizadas en el análisis de XAML sin tener en cuenta otra configuración de referencia cultural.  
  
 En las secciones siguientes se describen algunas de las cadenas de formato habituales de <xref:System.DateTime>.  
  
### Modelo de fecha corta \("d"\)  
 El ejemplo siguiente muestra el formato de fecha corta para <xref:System.DateTime> en XAML:  
  
 `M/d/YYYY`  
  
 Este es el formato más simple que especifica toda la información necesaria para los usos típicos de los controles de WPF, y no puede verse influenciado por desplazamientos accidentales de la zona horaria frente a un componente horario y, por consiguiente, se recomienda sobre los otros formatos.  
  
 Por ejemplo, para especificar la fecha del 1 de junio de 2010, utilice la cadena siguiente:  
  
 `3/1/2010`  
  
 Para obtener más información, vea <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=fullName>.  
  
### Modelo de DateTime que se puede ordenar \("s"\)  
 A continuación se muestra el modelo <xref:System.DateTime> ordenable en XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Por ejemplo, para especificar la fecha del 1 de junio de 2010, utilice la cadena siguiente \(todos los componentes horarios se escriben como 0\):  
  
 `2010-06-01T000:00:00`  
  
### Modelo RFC1123 \("r"\)  
 El modelo RFC1123 es útil porque podría ser una entrada de cadena de otros generadores de fechas que también utilicen el modelo RFC1123 porque la referencia cultural sirva para todos los idiomas.  A continuación se muestra el modelo <xref:System.DateTime> RFC1123 en XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Por ejemplo, para especificar la fecha del 1 de junio de 2010, utilice la cadena siguiente \(todos los componentes horarios se escriben como 0\):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### Otros formatos y modelos  
 Como se indicó previamente, <xref:System.DateTime> en XAML se puede especificar como cualquier cadena que sea aceptable como entrada para <xref:System.DateTime.Parse%2A?displayProperty=fullName>.  Esto incluye otros formatos formalizados \(por ejemplo <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>\) y formatos que no están formalizados como un formulario <xref:System.Globalization.DateTimeFormatInfo> determinado.  Por ejemplo, el formulario `YYYY/mm/dd` es aceptable cuando la entrada para <xref:System.DateTime.Parse%2A?displayProperty=fullName>.  Este tema no intenta describir todos los posibles formatos que funcionan, en su lugar recomienda el modelo de fecha corta como un ejercicio estándar.  
  
## Vea también  
 [Información general sobre XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)