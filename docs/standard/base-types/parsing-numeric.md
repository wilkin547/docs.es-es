---
title: Analizar cadenas numéricas en .NET
description: Descubra el análisis de cadenas numéricas en .NET. Aprenda a analizar con proveedores de formato, valores de enumeración NumberStyles y dígitos Unicode.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
ms.openlocfilehash: 1339301786ed0f7ddd41565ca3fc64c2a859b3f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683763"
---
# <a name="parsing-numeric-strings-in-net"></a>Analizar cadenas numéricas en .NET

Todos los tipos numéricos tienen dos métodos de análisis estáticos, `Parse` y `TryParse`, que puede usar para convertir la representación de cadena de un número en un tipo numérico. Estos métodos permiten analizar cadenas generadas mediante el uso de las cadenas de formato que se documentan en [Cadenas con formato numérico estándar](standard-numeric-format-strings.md) y [Cadenas con formato numérico personalizado](custom-numeric-format-strings.md). De forma predeterminada, los métodos `Parse` y `TryParse` pueden convertir correctamente las cadenas que contienen dígitos decimales enteros solo en valores enteros. Pueden convertir correctamente las cadenas que contienen dígitos decimales enteros y fraccionarios, separadores de grupos y un separador decimal en valores de punto flotante. El método `Parse` produce una excepción si se produce un error en la operación, mientras que el método `TryParse` devuelve `false`.  
  
## <a name="parsing-and-format-providers"></a>Análisis y proveedores de formato  

 Normalmente, las representaciones de cadena de valores numéricos se diferencian en la referencia cultural. Todos los elementos de las cadenas numéricas, como los símbolos de moneda, los separadores de grupo (o millares) y los separadores decimales, varían según la referencia cultural. Los métodos de análisis usan implícita o explícitamente un proveedor de formato que reconoce estas variaciones específicas de la referencia cultural. Si no se especifica ningún proveedor de formato en una llamada al método `Parse` o `TryParse`, se usa el proveedor de formato asociado a la referencia cultural del subproceso actual (el objeto <xref:System.Globalization.NumberFormatInfo> devuelto por la propiedad <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType>).  
  
 Un proveedor de formato se representa mediante una implementación <xref:System.IFormatProvider>. Esta interfaz tiene un solo miembro, el método <xref:System.IFormatProvider.GetFormat%2A>, cuyo único parámetro es un objeto <xref:System.Type> que representa el tipo al que se va a dar formato. Este método devuelve el objeto que proporciona información de formato. .NET es compatible con las dos implementaciones <xref:System.IFormatProvider> siguientes para analizar cadenas numéricas:  
  
- Un objeto <xref:System.Globalization.CultureInfo> cuyo método <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Globalization.NumberFormatInfo> que proporciona información de formato específica de la referencia cultural.  
  
- Un objeto <xref:System.Globalization.NumberFormatInfo> cuyo método <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> se devuelve a sí mismo.  
  
 En el ejemplo siguiente se intenta convertir cada cadena de una matriz en un valor <xref:System.Double>. Primero se intenta analizar la cadena mediante un proveedor de formato que refleja las convenciones de la referencia cultural Inglés (Estados Unidos). Si esta operación produce una excepción <xref:System.FormatException>, se intenta analizar la cadena mediante un proveedor de formato que refleja las convenciones de la referencia cultural Francés (Francia).  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Análisis y valores NumberStyles  

 Los elementos de estilo (como espacio en blanco, separadores de grupos y separador decimal) que la operación de análisis puede controlar se definen mediante un valor de enumeración <xref:System.Globalization.NumberStyles>. De forma predeterminada, las cadenas que representan valores enteros se analizan mediante el valor <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>, que solo permite dígitos numéricos, espacio en blanco inicial y final, y un signo inicial. Las cadenas que representan valores de punto flotante se analizan mediante una combinación de valores <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>. Este estilo compuesto permite dígitos decimales junto con un espacio en blanco inicial y final, un signo inicial, un separador decimal, separador de grupos y un exponente. Al llamar a una sobrecarga del método `Parse` o `TryParse` que incluya un parámetro de tipo <xref:System.Globalization.NumberStyles> y configurar una o más marcas <xref:System.Globalization.NumberStyles>, puede controlar los elementos de estilo que pueden estar presentes en la cadena para que la operación de análisis se realice correctamente.  
  
 Por ejemplo, una cadena que contiene un separador de grupos no puede convertirse en un valor <xref:System.Int32> mediante el método <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType>. Pero la conversión se realiza correctamente si usa la marca <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
> La operación de análisis siempre usa las convenciones de formato de una referencia cultural determinada. Si no pasa un objeto <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> para especificar una referencia cultural, se usa la referencia cultural asociada al subproceso actual.  
  
 En la tabla siguiente se enumeran los miembros de la enumeración <xref:System.Globalization.NumberStyles> y se describe el efecto que tienen en la operación de análisis.  
  
|Valor NumberStyles|Efecto en la cadena que se va a analizar|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Solo se permiten los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Se permiten el separador decimal y los dígitos fraccionarios. En el caso de los valores enteros, solo se permite cero como dígito fraccionario. La propiedad <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType> determina los separadores decimales válidos.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Se puede usar el carácter "e" o "E" para indicar la notación exponencial. Vea <xref:System.Globalization.NumberStyles> para obtener información adicional.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|Se permite el espacio en blanco inicial.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|Se permite el espacio en blanco final.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Un signo positivo o negativo puede preceder a los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Un signo positivo o negativo puede seguir a los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Se pueden usar paréntesis para indicar valores negativos.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|Se permite el separador de grupos. El carácter de separador de grupo viene determinado por la propiedad <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|Se permite el símbolo de moneda. El símbolo de moneda se define mediante la propiedad <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|La cadena que se va a analizar se interpreta como un número hexadecimal. Puede incluir los dígitos hexadecimales 0-9, A-F y a-f. Esta marca solo se puede usar para analizar valores enteros.|  
  
 Además, la enumeración <xref:System.Globalization.NumberStyles> proporciona los siguientes estilos compuestos, que incluyen varias marcas <xref:System.Globalization.NumberStyles>.  
  
|Valor NumberStyles compuestos|Miembros que incluye|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Incluye los estilos <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>. Este es el estilo predeterminado que se usa para analizar valores enteros.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Incluye los estilos <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Incluye los estilos <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Incluye todos los estilos excepto <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Incluye todos los estilos excepto <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Incluye los estilos <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
  
## <a name="parsing-and-unicode-digits"></a>Análisis y dígitos Unicode  

 El estándar Unicode define puntos de código para dígitos de diferentes sistemas de escritura. Por ejemplo, los puntos de código de U+0030 a U+0039 representan los dígitos latinos básicos del 0 al 9, los puntos de código de U+09E6 a U+09EF representan los dígitos de bengalí del 0 al 9, y los puntos de código de U+FF10 a U+FF19 representan los dígitos de ancho completo del 0 al 9. Pero los únicos dígitos numéricos que reconocen los métodos de análisis son los dígitos latinos básicos del 0 al 9 con puntos de código de U+0030 a U+0039. Si se pasa a un método de análisis numérico una cadena que contenga cualquier otro dígito, el método producirá una excepción <xref:System.FormatException>.  
  
 En el ejemplo siguiente se usa el método <xref:System.Int32.Parse%2A?displayProperty=nameWithType> para analizar las cadenas que se componen de dígitos en sistemas de escritura diferentes. Como muestra la salida del ejemplo, el intento de analizar los dígitos latinos básicos se realiza correctamente, pero se produce un error en el intento de analizar los dígitos de ancho completo, árabe-hindús y de bengalí.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Globalization.NumberStyles>
- [Analizar cadenas](parsing-strings.md)
- [Aplicación de formato a tipos](formatting-types.md)
