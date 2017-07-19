---
title: "Analizar cadenas num&#233;ricas en .NET Framework | Microsoft Docs"
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
  - "analizar cadenas, cadenas numéricas"
  - "cadenas numéricas"
  - "enumeraciones [.NET Framework], cadenas de análisis"
  - "tipos base, analizar cadenas"
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Analizar cadenas num&#233;ricas en .NET Framework
Todos los tipos numéricos tienen dos métodos estáticos de análisis, `Parse` y `TryParse`, que puede usar para convertir la representación de cadena de un número en un tipo numérico.  Estos métodos permiten analizar cadenas que se generaron mediante las cadenas de formato documentadas en [Cadenas con formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md) y [Cadenas con formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md).  De forma predeterminada, los métodos `Parse` y `TryParse` pueden convertir correctamente cadenas que contienen dígitos decimales enteros únicamente a valores enteros.  Pueden convertir correctamente cadenas que contienen dígitos decimales enteros y fraccionarios, separadores de grupo y un separador decimal en valores de punto flotante.  El método `Parse` produce una excepción si se produce un error en la operación, mientras que el método `TryParse` devuelve `false`.  
  
## Análisis y proveedores de formato  
 Normalmente, las representaciones de cadena de los valores numéricos difieren según la referencia cultural.  Los elementos de cadenas numéricas como símbolos de moneda, separadores de grupo \(o miles\), y separadores decimales varían según la referencia cultural.  Los métodos de análisis usan implícita o explícitamente un proveedor de formato que reconoce estas variaciones específicas de la referencia cultural.  Si no se especifica ningún proveedor de formato en una llamada al método `Parse` o `TryParse`, se usará el proveedor de formato asociado a la referencia cultural del subproceso actual \(el objeto <xref:System.Globalization.NumberFormatInfo> devuelto por la propiedad <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=fullName>\).  
  
 Un proveedor de formato se representa mediante una implementación de <xref:System.IFormatProvider>.  Esta interfaz tiene un solo miembro, el método <xref:System.IFormatProvider.GetFormat%2A>, cuyo único parámetro es un objeto <xref:System.Type> que representa el tipo al que se va a dar formato.  Este método devuelve el objeto que proporciona información de formato.  .NET Framework admite las dos implementaciones siguientes de <xref:System.IFormatProvider> para analizar cadenas numéricas:  
  
-   Un objeto <xref:System.Globalization.CultureInfo> cuyo método <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=fullName> devuelve un objeto <xref:System.Globalization.NumberFormatInfo> que proporciona información de formato específica de la referencia cultural.  
  
-   Un objeto <xref:System.Globalization.NumberFormatInfo> cuyo método <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=fullName> se devuelve a sí mismo.  
  
 En el ejemplo siguiente se intenta convertir cada cadena de una matriz a un valor de tipo <xref:System.Double>.  Primero se intenta analizar la cadena usando un proveedor de formato que refleje las convenciones de la referencia cultural Inglés \(Estados Unidos\).  Si esta operación produce <xref:System.FormatException>, se intenta analizar la cadena usando un proveedor de formato que refleje las convenciones de la referencia cultural Francés \(Francia\).  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## Análisis y valores NumberStyles  
 Los elementos de estilo \(como espacio en blanco, separadores de grupos y separador decimal\) que la operación de análisis puede tratar están definidos por un valor de la enumeración <xref:System.Globalization.NumberStyles>.  De forma predeterminada, las cadenas que representan valores enteros se analizan usando el valor de <xref:System.Globalization.NumberStyles?displayProperty=fullName>, que solo permite dígitos numéricos, espacio en blanco inicial y final, y un signo inicial.  Las cadenas que representan valores de punto flotante se analizan mediante una combinación de los valores de <xref:System.Globalization.NumberStyles?displayProperty=fullName> y <xref:System.Globalization.NumberStyles?displayProperty=fullName>; este estilo compuesto permite dígitos decimales junto con espacios en blanco iniciales y finales, un signo inicial, un separador decimal, un separador de grupos y un exponente.  Llamando a una sobrecarga del método `Parse` o `TryParse` que incluye un parámetro de tipo <xref:System.Globalization.NumberStyles> y estableciendo una o más marcas de <xref:System.Globalization.NumberStyles>, puede controlar los elementos de estilo que pueden estar presentes en la cadena para que la operación de análisis se realice correctamente.  
  
 Por ejemplo, una cadena que contiene un separador de grupos no se puede convertir en un valor de <xref:System.Int32> utilizando el método de <xref:System.Int32.Parse%28System.String%29?displayProperty=fullName> .  Sin embargo, la conversión se realiza correctamente si utiliza el indicador de <xref:System.Globalization.NumberStyles?displayProperty=fullName> , como muestra el ejemplo siguiente.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  La operación de análisis usa siempre las convenciones de formato de una referencia cultural determinada.  Si no especifica una referencia cultural pasando un objeto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo>, se usará la referencia cultural asociada al subproceso actual.  
  
 En la tabla siguiente se muestran los miembros de la enumeración <xref:System.Globalization.NumberStyles> y se describe el efecto que tienen sobre la operación de análisis.  
  
|Valor de NumberStyles|Efecto sobre la cadena que se va a analizar|  
|---------------------------|-------------------------------------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Solo se permiten dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se permiten el separador decimal y dígitos fraccionarios.  Para los valores enteros, solo se permite cero como dígito fraccionario.  Los separadores decimales válidos se determinan mediante la propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=fullName> o <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se puede usar el carácter "e" o "E" para indicar la notación exponencial.  Vea <xref:System.Globalization.NumberStyles> para obtener información adicional.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se permite el espacio en blanco inicial.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se permite el espacio en blanco final.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Un signo positivo o negativo puede preceder a los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Un signo positivo o negativo puede seguir a los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se pueden usar paréntesis para indicar valores negativos.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se permite el separador de grupos.  El carácter separador de grupos viene determinado por la propiedad <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=fullName> o <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Se permite el símbolo de moneda.  El símbolo de moneda está definido por la propiedad <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|La cadena que se va a analizar se interpreta como un número hexadecimal.  Puede incluir los dígitos hexadecimales 0\-9, A\-F y a\-f.  Esta marca solo se puede usar para analizar valores enteros.|  
  
 Además, la enumeración <xref:System.Globalization.NumberStyles> proporciona los estilos compuestos siguientes, que incluyen varias marcas de <xref:System.Globalization.NumberStyles>.  
  
|Valor compuesto de NumberStyles|Incluye miembros|  
|-------------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Incluye los estilos <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> y <xref:System.Globalization.NumberStyles?displayProperty=fullName>.  Este es el estilo predeterminado empleado para analizar valores enteros.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Incluye los estilos <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> y <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Incluye los estilos <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> y <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Incluye todos los estilos excepto <xref:System.Globalization.NumberStyles?displayProperty=fullName> y <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Incluye todos los estilos excepto <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Incluye los estilos <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> y <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
  
## Análisis y dígitos Unicode  
 El estándar Unicode define puntos de código para los dígitos en diversos sistemas de escritura.  Por ejemplo, los puntos de código de U\+0030 a U\+0039 representan los dígitos latinos básicos 0 a 9, los puntos de código de U\+09E6 a U\+09EF representan, los dígitos de 0 a 9 de Bangla y los puntos de código de U\+FF10 a U\+FF19 representan los dígitos 0 a 9. de ancho completo.  Sin embargo, los únicos dígitos numéricos reconocidos por los métodos de análisis son los dígitos latinos básicos 0\-9 con los puntos de código de U\+0030 a U\+0039.  Si a un método de análisis numérico se le pasa una cadena que contiene cualquier otro dígito, el método produce una excepción <xref:System.FormatException>.  
  
 En el ejemplo siguiente se usa el método <xref:System.Int32.Parse%2A?displayProperty=fullName> para analizar cadenas que constan de dígitos en diferentes sistemas de escritura.  Como el resultado del ejemplo, el intento de analizar los dígitos latinos básicos se realiza correctamente, pero el intento de analizar los dígitos de ancho completo, Árabe\- índicos, y de Bangla falla.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## Vea también  
 <xref:System.Globalization.NumberStyles>   
 [Analizar cadenas](../../../docs/standard/base-types/parsing-strings.md)   
 [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md)