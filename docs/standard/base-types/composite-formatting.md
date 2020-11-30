---
title: Formatos compuestos
description: Conozca el formato compuesto de .NET, que toma como entrada una lista de objetos y una cadena de formato compuesto, que contiene texto fijo con marcadores de posición indexados.
ms.date: 10/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parameter specifiers
- strings [.NET], alignment
- format specifiers, composite formatting
- strings [.NET], composite
- composite formatting
- objects [.NET], formatting multiple objects
ms.assetid: 87b7d528-73f6-43c6-b71a-f23043039a49
ms.openlocfilehash: a0252d013ee6cf7cba7f953fc8a1e2c66c510ca7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683958"
---
# <a name="composite-formatting"></a>Formatos compuestos

La característica de formato compuesto de .NET toma una lista de objetos y una cadena de formato compuesto como entrada. Una cadena de formato compuesto está formada por texto fijo combinado con marcadores de posición indizados, que reciben el nombre de elementos de formato, y que se corresponden con los objetos de la lista. La operación de formato genera una cadena de resultado compuesta por el texto fijo original combinado con la representación de cadena de los objetos de la lista.  
  
> [!IMPORTANT]
> En lugar de usar cadenas de formato compuesto, puede usar *cadenas interpoladas* si el idioma y la versión de idioma que está usando son compatibles con ellos. Una cadena interpolada es una cadena que contiene *expresiones interpoladas*. Cada expresión interpolada se resuelve con el valor de la expresión y se incluye en la cadena de resultado cuando se asigna la cadena. Para obtener más información, vea [Interpolación de cadenas (Referencia de C#)](../../csharp/language-reference/tokens/interpolated.md) y [Cadenas interpoladas (referencia de Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).

La característica de formato compuesto se admite mediante métodos como los siguientes:  
  
- <xref:System.String.Format%2A?displayProperty=nameWithType>, que devuelve una cadena de resultado con formato.  
  
- <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>, que anexa una cadena de resultado con formato a un objeto <xref:System.Text.StringBuilder>.
- Algunas sobrecargas del método <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, que muestran una cadena de resultado con formato en la consola.  
  
- Algunas sobrecargas del método <xref:System.IO.TextWriter.WriteLine%2A?displayProperty=nameWithType>, que escriben la cadena de resultado con formato en una secuencia o un archivo. Las clases derivadas de <xref:System.IO.TextWriter>, como <xref:System.IO.StreamWriter> y <xref:System.Web.UI.HtmlTextWriter>, también comparten esta funcionalidad.  
  
- <xref:System.Diagnostics.Debug.WriteLine%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, que genera un mensaje con formato para los agentes de escucha de traza.  
  
- Los métodos <xref:System.Diagnostics.Trace.TraceError%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace.TraceWarning%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, que generan mensajes con formato para los agentes de escucha de traza.  
  
- El método <xref:System.Diagnostics.TraceSource.TraceInformation%28System.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>, que escribe un método informativo para los agentes de escucha de traza.  
  
## <a name="composite-format-string"></a>Cadena de formato compuesto  

 Los métodos compatibles con la característica de formato compuesto utilizan como argumentos una cadena de formato compuesto y una lista de objetos. Una cadena de formato compuesto consta de cero o más ejecuciones de texto fijo combinadas con uno o varios elementos de formato. El texto fijo es cualquier cadena que elija y cada elemento de formato se corresponde con un objeto o estructura de conversión boxing de la lista. La característica de formato compuesto devuelve una nueva cadena de resultado donde cada elemento de formato se reemplaza por la representación de cadena del objeto correspondiente de la lista.  
  
 Observe el siguiente fragmento de código <xref:System.String.Format%2A>.  
  
 [!code-csharp[Formatting.Composite#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#1)]
 [!code-vb[Formatting.Composite#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#1)]  
  
 El texto fijo es "`Name =`" y "`, hours =`". Los elementos de formato son "`{0}`", cuyo índice es 0, que corresponde al objeto `name`, y "`{1:hh}`", cuyo índice es 1, que corresponde al objeto `DateTime.Now`.  
  
## <a name="format-item-syntax"></a>Sintaxis de elemento de formato  

 Cada elemento de formato presenta la siguiente sintaxis, formada por los siguientes componentes:  
  
 `{` *index*[`,`*alignment*][`:`*formatString*]`}`  
  
 Las llaves ("{" y "}") son necesarias.  
  
### <a name="index-component"></a>Index (Componente)  

 El componente *index* obligatorio, denominado también especificador de parámetros, es un número que empieza por 0 que identifica un elemento correspondiente de la lista de objetos. O sea, el elemento de formato cuyo especificador de parámetro es 0 da formato al primer objeto de la lista, el elemento de formato cuyo especificador de parámetro es 1 da formato al segundo objeto de la lista, etc. En el ejemplo siguiente se incluyen cuatro especificadores de parámetros, numerados del cero al tres, para representar números primos menores que diez:  
  
 [!code-csharp[Formatting.Composite#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#7)]
 [!code-vb[Formatting.Composite#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#7)]  
  
 Los elementos de formato múltiple se pueden referir al mismo elemento de la lista de objetos mediante la especificación del mismo especificador de parámetro. Por ejemplo, se puede dar formato al mismo valor numérico en formato hexadecimal, científico y de número mediante la especificación de una cadena de formato compuesto como esta: "0x{0:X} {0:E} {0:N}", como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Formatting.Composite#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/index1.cs#10)]
 [!code-vb[Formatting.Composite#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/index1.vb#10)]  
  
 Cada elemento de formato puede hacer referencia a cualquier objeto de la lista. Por ejemplo, si existen tres objetos, se puede dar formato al segundo, primero y tercer objeto mediante la especificación de una cadena de formato compuesto como esta: "{1} {0} {2}". Un objeto al que no hace referencia ningún elemento de formato se omite. Se produce una excepción de tipo <xref:System.FormatException> en tiempo de ejecución si un especificador de parámetro designa un elemento fuera de los límites de la lista de objetos.  
  
### <a name="alignment-component"></a>Alignment (Componente)  

 El componente opcional *alignment* es un entero con signo que indica el ancho de campo con formato preferido. Si el valor de *alignment* es menor que la longitud de la cadena con formato, se omite *alignment* y se usa la longitud de la cadena con formato como el ancho de campo. Los datos con formato del campo están alineados a la derecha si *alignment* es positivo y a la izquierda si *alignment* es negativo. Si hace falta relleno, se utiliza un espacio en blanco. Si se especifica *alignment*, es necesaria la coma.  
  
 El siguiente ejemplo define dos matrices, que contiene los nombres de empleados y otra contiene las horas que han trabajado en un período de dos semanas. La cadena de formato compuesto alinea a la izquierda los nombres en un campo de 20 caracteres y alinea a la derecha las horas en un campo de 5 caracteres. Tenga en cuenta que la cadena de formato estándar "N1" también se usa para dar formato a las horas con un dígito fraccionario.  
  
 [!code-csharp[Formatting.Composite#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/alignment1.cs#8)]
 [!code-vb[Formatting.Composite#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/alignment1.vb#8)]  
  
### <a name="format-string-component"></a>Format String (Componente)  

 El componente *formatString* opcional es una cadena de formato adecuada para el tipo de objeto al que se da formato. Especifique una cadena de formato numérico estándar o personalizado si el objeto correspondiente es un valor numérico, una cadena de formato de fecha y hora estándar o personalizado si el objeto correspondiente es un objeto <xref:System.DateTime>, o una [cadena de formato de enumeración](enumeration-format-strings.md) si el objeto correspondiente es un valor de enumeración. Si no se especifica *formatString*, se usa el especificador de formato general ("G") para un tipo numérico, de fecha y hora o de enumeración. Si se especifica *formatString*, son necesarios los dos puntos.  
  
 En la tabla siguiente se enumeran los tipos o las categorías de tipos de la biblioteca de clases de .NET que admiten un conjunto predefinido de cadenas de formato, y se proporcionan vínculos a temas en los que se muestran las cadenas de formato admitidas. Observe que la asignación de formato a cadenas es un mecanismo extensible que permite definir cadenas de formato nuevas para todos los tipos existentes, así como definir un conjunto de cadenas de formato admitidas por un tipo definido por la aplicación. Para obtener más información, consulte los temas sobre las interfaces <xref:System.IFormattable> y <xref:System.ICustomFormatter>.  
  
|Tipo o categoría de tipo|Vea|  
|---------------------------|---------|  
|Tipos de fecha y hora (<xref:System.DateTime>, <xref:System.DateTimeOffset>)|[Cadenas con formato de fecha y hora estándar](standard-date-and-time-format-strings.md)<br /><br /> [Cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md)|  
|Tipos de enumeración (todos los tipos derivados de <xref:System.Enum?displayProperty=nameWithType>)|[Cadenas de formato de enumeración](enumeration-format-strings.md)|  
|Tipos numéricos (<xref:System.Numerics.BigInteger>, <xref:System.Byte>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>)|[Cadenas con formato numérico estándar](standard-numeric-format-strings.md)<br /><br /> [Cadenas con formato numérico personalizado](custom-numeric-format-strings.md)|  
|<xref:System.Guid>|<xref:System.Guid.ToString%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.TimeSpan>|[Cadenas de formato TimeSpan estándar](standard-timespan-format-strings.md)<br /><br /> [Cadenas de formato TimeSpan personalizado](custom-timespan-format-strings.md)|  
  
### <a name="escaping-braces"></a>Llaves de escape  

 Las llaves de apertura y de cierre se interpretan como el inicio y el final de un elemento de formato. Por lo tanto, debe utilizar una secuencia de escape para que se muestre una llave de apertura o de cierre literal. Especifique dos llaves de apertura ("{{") en el texto fijo para que se muestre una llave de apertura ("{"), o dos llaves de cierre ("}}") para que se muestre una llave de cierre ("}"). Las llaves de un elemento de formato se interpretan secuencialmente, en el orden en que se encuentran. No se admite la interpretación de llaves anidadas.  
  
 El modo de interpretar las llaves de escape puede dar lugar a resultados inesperados. Tomemos como ejemplo el elemento de formato "{{{0:D}}}", cuyo propósito es mostrar una llave de apertura, un valor numérico con formato de número decimal y una llave de cierre; pero que, en la práctica, se interpreta de la siguiente forma:  
  
1. Las dos primeras llaves de apertura ("{{") son llaves de escape y dan lugar a en una llave de apertura.  
  
2. Los tres caracteres siguientes ("{0:") se interpretan como el inicio de un elemento de formato.  
  
3. El siguiente carácter ("D") se interpretaría como el especificador de formato numérico estándar decimal, pero las dos llaves de escape siguientes ("}}") dan lugar a una única llave. Como la cadena resultante ("D}") no es un especificador de formato numérico estándar, se interpreta como una cadena de formato personalizado que significa que debe mostrarse la cadena literal "D}".  
  
4. La última llave ("}") se interpreta como el final del elemento de formato.  
  
5. Como resultado final, se muestra la cadena literal "{D}". No se muestra el valor numérico al que se debía dar formato.  
  
 Una forma de escribir código e impedir que las llaves de escape y los elementos de formato se malinterpreten consiste en dar formato a las llaves y elementos de formato por separado. Es decir, en la primera operación de formato mostrar una llave de apertura literal, en la siguiente operación mostrar el resultado del elemento de formato y, por último, en la operación final mostrar una llave de cierre literal. En el ejemplo siguiente se muestra este enfoque.  
  
 [!code-csharp[Formatting.Composite#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Escaping1.cs#2)]
 [!code-vb[Formatting.Composite#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Escaping1.vb#2)]  
  
### <a name="processing-order"></a>Orden de procesamiento  

 Si la llamada al método de formato compuesto incluye un argumento <xref:System.IFormatProvider> cuyo valor no es `null`, el runtime llama al método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> para solicitar una implementación de <xref:System.ICustomFormatter>. Si el método es capaz de devolver una implementación de <xref:System.ICustomFormatter>, se almacena en caché el tiempo que dure la llamada de método de formato compuesto.
  
 Cada valor de la lista de parámetros que se corresponda con un elemento de formato se convierte en una cadena del siguiente modo:  
  
1. Si el valor al que se va a dar formato es `null`, se devuelve una cadena vacía <xref:System.String.Empty?displayProperty=nameWithType>.  
  
2. Si hay disponible una implementación de <xref:System.ICustomFormatter>, el runtime llama al método <xref:System.ICustomFormatter.Format%2A>. Pasa al método el valor *formatString* del elemento de formato, si hay alguno, o `null` si no lo hay, junto con la implementación de <xref:System.IFormatProvider>. Si la llamada al método <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> devuelve `null`, la ejecución avanza al siguiente paso; en caso contrario, se devuelve el resultado de la llamada a <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType>.
  
3. Si el valor implementa la interfaz <xref:System.IFormattable>, se llama al método <xref:System.IFormattable.ToString%28System.String%2CSystem.IFormatProvider%29> de esta. Se pasa al método el valor *formatString*, si hubiera uno presente en el elemento de formato, o `null` si no lo hubiera. El argumento <xref:System.IFormatProvider> se determina de la siguiente forma:  
  
    - Para un valor numérico, si se llama a un método de formato compuesto con un argumento <xref:System.IFormatProvider> que no sea null, el runtime solicita un objeto <xref:System.Globalization.NumberFormatInfo> a su método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. En caso de no poder proporcionar uno, si el valor del argumento es `null`, o si el método de formato compuesto no tiene un parámetro <xref:System.IFormatProvider>, se usa el objeto <xref:System.Globalization.NumberFormatInfo> para la referencia cultural del subproceso actual.  
  
    - Para un valor de fecha y hora, si se llama a un método de formato compuesto con un argumento <xref:System.IFormatProvider> que no sea nulo, el runtime solicita un objeto <xref:System.Globalization.DateTimeFormatInfo> a su método <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>. En caso de no poder proporcionar uno, si el valor del argumento es `null`, o si el método de formato compuesto no tiene un parámetro <xref:System.IFormatProvider>, se usa el objeto <xref:System.Globalization.DateTimeFormatInfo> para la referencia cultural del subproceso actual.  
  
    - Para objetos de otros tipos, si se llama a un formato compuesto con un argumento <xref:System.IFormatProvider>, su valor se pasa directamente a la implementación <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>. En caso contrario, `null` se pasa a la implementación <xref:System.IFormattable.ToString%2A?displayProperty=nameWithType>.  
  
4. Se llama al método sin parámetros `ToString` del tipo, que reemplaza a <xref:System.Object.ToString?displayProperty=nameWithType> o hereda el comportamiento de su clase base. En este caso, se omite la cadena de formato especificada por el componente *formatString* en el elemento de formato, si estuviera presente.  
  
 La alineación se aplica después de que se hayan realizado los pasos anteriores.  
  
## <a name="code-examples"></a>Ejemplos de código  

 En el ejemplo siguiente se muestra una cadena creada mediante formato compuesto y otra creada mediante el método `ToString` de un objeto. Los dos tipos de formato producen resultados equivalentes.  
  
 [!code-csharp[Formatting.Composite#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#3)]
 [!code-vb[Formatting.Composite#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#3)]  
  
 Si tomamos como día actual un jueves del mes de mayo, el valor de ambas cadenas del ejemplo anterior será `Thursday May` para la referencia cultural Inglés (Estados Unidos).  
  
 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> expone la misma funcionalidad que <xref:System.String.Format%2A?displayProperty=nameWithType>. La única diferencia que existe entre estos dos métodos es que <xref:System.String.Format%2A?displayProperty=nameWithType> devuelve el resultado como una cadena, mientras que <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> escribe el resultado en el flujo de salida asociado al objeto <xref:System.Console>. En el ejemplo siguiente se usa el método <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> para dar formato al valor de `MyInt` como un valor de divisa.  
  
 [!code-csharp[Formatting.Composite#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#4)]
 [!code-vb[Formatting.Composite#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#4)]  
  
 En el siguiente ejemplo se muestra la aplicación de formato a objetos múltiples, incluida la aplicación de formato a un objeto de dos formas diferentes.  
  
 [!code-csharp[Formatting.Composite#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#5)]
 [!code-vb[Formatting.Composite#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#5)]  
  
 En el ejemplo siguiente se muestra el uso de la alineación en la aplicación de formato. Los argumentos a los que se da formato se colocan entre caracteres verticales (&#124;) para resaltar la alineación resultante.  
  
 [!code-csharp[Formatting.Composite#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Composite/cs/Composite1.cs#6)]
 [!code-vb[Formatting.Composite#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Composite/vb/Composite1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Console.WriteLine%2A>
- <xref:System.String.Format%2A?displayProperty=nameWithType>
- [Interpolación de cadenas en C#](../../csharp/language-reference/tokens/interpolated.md)
- [Cadenas interpoladas (referencia de Visual Basic)](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md)
- [Aplicación de formato a tipos](formatting-types.md)
- [Cadenas con formato numérico estándar](standard-numeric-format-strings.md)
- [Cadenas con formato numérico personalizado](custom-numeric-format-strings.md)
- [Cadenas con formato de fecha y hora estándar](standard-date-and-time-format-strings.md)
- [Cadenas con formato de fecha y hora personalizado](custom-date-and-time-format-strings.md)
- [Cadenas de formato TimeSpan estándar](standard-timespan-format-strings.md)
- [Cadenas de formato TimeSpan personalizado](custom-timespan-format-strings.md)
- [Cadenas de formato de enumeración](enumeration-format-strings.md)
