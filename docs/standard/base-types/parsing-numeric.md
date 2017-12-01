---
title: "Analizar cadenas numéricas en .NET"
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
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c9bb58b0d7b45ca197653742844be01ac3bbe41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-numeric-strings-in-net"></a>Analizar cadenas numéricas en la red
Todos los tipos numéricos tienen dos métodos de análisis estáticos, `Parse` y `TryParse`, que puede usar para convertir la representación de cadena de un número en un tipo numérico. Estos métodos permiten analizar cadenas generadas mediante el uso de las cadenas de formato que se documentan en [Cadenas con formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md) y [Cadenas con formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md). De forma predeterminada, los métodos `Parse` y `TryParse` pueden convertir correctamente las cadenas que contienen dígitos decimales enteros solo en valores enteros. Pueden convertir correctamente las cadenas que contienen dígitos decimales enteros y fraccionarios, separadores de grupos y un separador decimal en valores de punto flotante. El método `Parse` produce una excepción si se produce un error en la operación, mientras que el método `TryParse` devuelve `false`.  
  
## <a name="parsing-and-format-providers"></a>Análisis y proveedores de formato  
 Normalmente, las representaciones de cadena de valores numéricos se diferencian en la referencia cultural. Todos los elementos de las cadenas numéricas, como los símbolos de moneda, los separadores de grupo (o millares) y los separadores decimales, varían según la referencia cultural. Los métodos de análisis usan implícita o explícitamente un proveedor de formato que reconoce estas variaciones específicas de la referencia cultural. Si no hay ningún proveedor de formato se especifica en una llamada a la `Parse` o `TryParse` /método siguiente, el proveedor de formato asociado a la referencia cultural del subproceso actual (la <xref:System.Globalization.NumberFormatInfo> objeto devuelto por la <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType> propiedad) se utiliza.  
  
 Un proveedor de formato se representa mediante un <xref:System.IFormatProvider> implementación. Esta interfaz tiene un solo miembro, el <xref:System.IFormatProvider.GetFormat%2A> método cuyo parámetro único es un <xref:System.Type> objeto que representa el tipo de formato. Este método devuelve el objeto que proporciona información de formato. .NET es compatible con las dos siguientes <xref:System.IFormatProvider> implementaciones para analizar cadenas numéricas:  
  
-   A <xref:System.Globalization.CultureInfo> cuyos <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> método devuelve un <xref:System.Globalization.NumberFormatInfo> objeto que proporciona información de formato específica de la referencia cultural.  
  
-   A <xref:System.Globalization.NumberFormatInfo> cuyos <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> método devuelve a sí mismo.  
  
 En el ejemplo siguiente se intenta convertir cada cadena en una matriz a un <xref:System.Double> valor. Primero se intenta analizar la cadena mediante un proveedor de formato que refleja las convenciones de la referencia cultural Inglés (Estados Unidos). Si esta operación produce un <xref:System.FormatException>, intenta analizar la cadena utilizando un proveedor de formato que refleja las convenciones de la referencia cultural Francés (Francia).  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Análisis y valores NumberStyles  
 Los elementos de estilo (como espacios en blanco, separadores de grupos y separador decimal) que puede controlar la operación de análisis se definen mediante un <xref:System.Globalization.NumberStyles> valor de enumeración. De forma predeterminada, se analizan cadenas que representan valores enteros utilizando el <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType> valor, que permite solo dígitos numéricos, el espacio en blanco inicial y final y un signo inicial. Cadenas que representan los valores de punto flotante se analizan mediante una combinación de la <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> valores; este estilo compuesto permite decimales junto con iniciales y finales de los espacios en blanco, un inicio de sesión inicial, un separador decimal, un grupo separador y un exponente. Mediante una llamada a una sobrecarga de la `Parse` o `TryParse` método que incluya un parámetro de tipo <xref:System.Globalization.NumberStyles> y configuración de uno o más <xref:System.Globalization.NumberStyles> marcas, puede controlar los elementos de estilo que pueden estar presentes en la cadena para la operación de análisis se realizan correctamente.  
  
 Por ejemplo, una cadena que contiene un separador de grupo no se puede convertir a un <xref:System.Int32> valor mediante el uso de la <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType> método. Sin embargo, la conversión se realiza correctamente si usas el <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> marca, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  La operación de análisis siempre usa las convenciones de formato de una referencia cultural determinada. Si no especifica una referencia cultural pasando un <xref:System.Globalization.CultureInfo> o <xref:System.Globalization.NumberFormatInfo> del objeto, se usa la referencia cultural asociada al subproceso actual.  
  
 En la tabla siguiente se enumera los miembros de la <xref:System.Globalization.NumberStyles> enumeración y se describe el efecto que tienen en la operación de análisis.  
  
|Valor NumberStyles|Efecto en la cadena que se va a analizar|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Solo se permiten los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Se permiten el separador decimal y los dígitos fraccionarios. En el caso de los valores enteros, solo se permite cero como dígito fraccionario. Separadores decimales válidos vienen determinados por la <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType> propiedad.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Se puede usar el carácter "e" o "E" para indicar la notación exponencial. Consulte <xref:System.Globalization.NumberStyles> para obtener información adicional.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|Se permite el espacio en blanco inicial.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|Se permite el espacio en blanco final.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Un signo positivo o negativo puede preceder a los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Un signo positivo o negativo puede seguir a los dígitos numéricos.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Se pueden usar paréntesis para indicar valores negativos.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|Se permite el separador de grupos. El carácter de separador de grupo viene determinado por la <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> o <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType> propiedad.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|Se permite el símbolo de moneda. El símbolo de moneda se define mediante el <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType> propiedad.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|La cadena que se va a analizar se interpreta como un número hexadecimal. Puede incluir los dígitos hexadecimales 0-9, A-F y a-f. Esta marca solo se puede usar para analizar valores enteros.|  
  
 Además, el <xref:System.Globalization.NumberStyles> enumeración proporciona los siguientes estilos compuestos, que incluyen varios <xref:System.Globalization.NumberStyles> marcas.  
  
|Valor NumberStyles compuestos|Miembros que incluye|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Incluye el <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, y <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType> estilos. Este es el estilo predeterminado que se usa para analizar valores enteros.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Incluye el <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, y <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> estilos.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Incluye el <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, y <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> estilos.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Incluye todos los estilos excepto <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> y <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Incluye todos los estilos excepto <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Incluye el <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, y <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType> estilos.|  
  
## <a name="parsing-and-unicode-digits"></a>Análisis y dígitos Unicode  
 El estándar Unicode define puntos de código para dígitos de diferentes sistemas de escritura. Por ejemplo, los puntos de código de U+0030 a U+0039 representan los dígitos latinos básicos del 0 al 9, los puntos de código de U+09E6 a U+09EF representan los dígitos de bangla del 0 al 9, y los puntos de código de U+FF10 a U+FF19 representan los dígitos de ancho completo del 0 al 9. Pero los únicos dígitos numéricos que reconocen los métodos de análisis son los dígitos latinos básicos del 0 al 9 con puntos de código de U+0030 a U+0039. Si un valor numérico al analizar el método se pasa una cadena que contiene cualquier otro dígito, el método produce una <xref:System.FormatException>.  
  
 En el ejemplo siguiente se usa el <xref:System.Int32.Parse%2A?displayProperty=nameWithType> método para analizar cadenas que se componen de dígitos en diferentes sistemas de escritura. Como muestra la salida del ejemplo, el intento de analizar los dígitos latinos básicos se realiza correctamente, pero se produce un error en el intento de analizar los dígitos de ancho completo, árabe-hindús y de bangla.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Globalization.NumberStyles>  
 [Analizar cadenas](../../../docs/standard/base-types/parsing-strings.md)  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)
