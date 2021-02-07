---
description: 'Más información sobre: funciones de conversión de tipos (Visual Basic)'
title: Type Conversion Functions
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c2e701b522bbeb32f4f6f448acd78e09b0616f46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731089"
---
# <a name="type-conversion-functions-visual-basic"></a>Funciones de conversión de tipos (Visual Basic)

Estas funciones se compilan en línea, lo que significa que el código de conversión forma parte del código que evalúa la expresión. A veces no hay ninguna llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento. Cada función convierte una expresión en un tipo de datos específico.

## <a name="syntax"></a>Sintaxis

```vb
CBool(expression)
CByte(expression)
CChar(expression)
CDate(expression)
CDbl(expression)
CDec(expression)
CInt(expression)
CLng(expression)
CObj(expression)
CSByte(expression)
CShort(expression)
CSng(expression)
CStr(expression)
CUInt(expression)
CULng(expression)
CUShort(expression)
```

## <a name="part"></a>Parte

`expression`  
Necesario. Cualquier expresión del tipo de datos de origen.

## <a name="return-value-data-type"></a>Tipo de datos de valor devuelto

El nombre de la función determina el tipo de datos del valor que devuelve, tal y como se muestra en la tabla siguiente.

|Nombre de la función|Tipo de datos devuelto|Intervalo para el `expression` argumento|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[Tipo de datos Boolean](../data-types/boolean-data-type.md)|Cualquier `Char` expresión válida o `String` numérica.|
|`CByte`|[Tipo de datos Byte](../data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> (0) a <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a byte con la `CByte` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|
|`CChar`|[Tipo de datos Char](../data-types/char-data-type.md)|Cualquier `Char` expresión o válida `String` ; solo se convierte el primer carácter de un `String` ; el valor puede ser de 0 a 65535 (sin signo).|
|`CDate`|[Tipo de datos Date](../data-types/date-data-type.md)|Cualquier representación válida de una fecha y hora.|
|`CDbl`|[Tipo de datos Double](../data-types/double-data-type.md)|-1.79769313486231570 e + 308 a-4.94065645841246544 E-324 para los valores negativos; 4.94065645841246544 e-324 a 1.79769313486231570 E + 308 para los valores positivos.|
|`CDec`|[Tipo de datos Decimal](../data-types/decimal-data-type.md)|+/-79.228.162.514.264.337.593.543.950.335 para números con escala cero, es decir, números sin decimales. En el caso de números con 28 posiciones decimales, el intervalo es +/-7,9228162514264337593543950335. El número más pequeño posible distinto de cero es 0,0000000000000000000000000001 (+/-1E-28).|
|`CInt`|[Tipo de datos Integer](../data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) a <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); las partes fraccionarias se redondean.<sup> 1</sup> <br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a entero con la `CInt` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo. |
|`CLng`|[Tipo de datos Long](../data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) a <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); las partes fraccionarias se redondean.<sup> 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a 64 bits con la `CLng` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|
|`CObj`|[Object Data Type](../data-types/object-data-type.md)|Cualquier expresión válida.|
|`CSByte`|[Tipo de datos SByte](../data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) a <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); las partes fraccionarias se redondean.<sup> 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de bytes de punto flotante a firma con la `CSByte` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|
|`CShort`|[Tipo de datos Short](../data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) a <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); las partes fraccionarias se redondean.<sup> 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a 16 bits con la `CShort` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|
|`CSng`|[Tipo de datos Single](../data-types/single-data-type.md)|-3.402823 e + 38 a-401298e E-45 para los valores negativos; 401298e e-45 a 3.402823 E + 38 para los valores positivos.|
|`CStr`|[String (Tipo de datos)](../data-types/string-data-type.md)|Returns para `CStr` dependen del `expression` argumento. Vea [valores devueltos para la función CSTR](return-values-for-the-cstr-function.md).|
|`CUInt`|[Tipo de datos UInteger](../data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) a <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a sin signo con la `CUInt` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|
|`CULng`|[Tipo de datos ULong](../data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) a <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de punto flotante a entero largo sin signo con la `CULng` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|
|`CUShort`|[Tipo de datos UShort](../data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) a <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (sin signo); las partes fraccionarias se redondean<sup> . 1</sup><br/><br/>A partir de Visual Basic 15,8, Visual Basic optimiza el rendimiento de la conversión de enteros de punto flotante a sin signo de 16 bits con la `CUShort` función; vea la sección [comentarios](#remarks) para obtener más información. Vea la sección [ejemplo de cint](#cint-example) para obtener un ejemplo.|

<sup>1</sup> las partes fraccionarias pueden estar sujetas a un tipo especial de redondeo denominado *redondeo bancario*. Vea "Comentarios" para obtener más información.

## <a name="remarks"></a>Observaciones

Como norma general, debe usar las funciones de conversión de tipo Visual Basic en preferencia a los métodos de .NET Framework como `ToString()` , ya sea en la <xref:System.Convert> clase o en una estructura o clase de tipo individual. Las funciones de Visual Basic están diseñadas para una interacción óptima con el código Visual Basic y también hacen que el código fuente sea más corto y más fácil de leer. Además, los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las funciones de Visual Basic, por ejemplo, al convertir `Boolean` a `Integer` . Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

A partir de Visual Basic 15,8, el rendimiento de la conversión de punto flotante a entero se optimiza al pasar el <xref:System.Single> <xref:System.Double> valor o devuelto por los métodos siguientes a una de las funciones de conversión de enteros ( `CByte` , `CShort` , `CInt` , `CLng` , `CSByte` , `CUShort` , `CUInt` , `CULng` ):

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Esta optimización permite que el código que realiza un gran número de conversiones de enteros se ejecute hasta dos veces más rápido. En el ejemplo siguiente se muestran estas conversiones optimizadas de punto flotante a entero:

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>Comportamiento

- **Conversión.** En general, puede utilizar las funciones de conversión de tipos de datos para convertir el resultado de una operación en un tipo de datos determinado en lugar del tipo de datos predeterminado. Por ejemplo, use `CDec` para forzar la aritmética decimal en los casos en los que normalmente tendría lugar la aritmética de precisión sencilla, doble precisión o entero.

- **Conversiones con errores.** Si el que se `expression` pasa a la función está fuera del intervalo del tipo de datos al que se va a convertir, <xref:System.OverflowException> se produce una.

- **Partes fraccionarias.** Cuando se convierte un valor no entero en un tipo entero, las funciones de conversión de enteros ( `CByte` , `CInt` , `CLng` , `CSByte` , `CShort` , `CUInt` , `CULng` y `CUShort` ) quitan la parte fraccionaria y redondean el valor al entero más cercano.

     Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros lo redondean al entero par más cercano. Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2. A veces, esto se denomina *redondeo bancario* y su finalidad es compensar una diferencia que podría acumularse al agregar muchos de estos números juntos.

     `CInt` y `CLng` difieren de las <xref:Microsoft.VisualBasic.Conversion.Int%2A> <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funciones y, que truncan, en lugar de redondear, la parte fraccionaria de un número. Además, `Fix` y `Int` siempre devuelven un valor del mismo tipo de datos que se pasa.

- **Conversiones de fecha y hora.** Use la <xref:Microsoft.VisualBasic.Information.IsDate%2A> función para determinar si un valor se puede convertir en una fecha y hora. `CDate` reconoce los literales de fecha y los literales de hora, pero no los valores numéricos. Para convertir un valor Visual Basic 6,0 en `Date` un `Date` valor de Visual Basic 2005 o versiones posteriores, puede utilizar el <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> método.

- **Valores de fecha y hora neutros.** El [tipo de datos Date](../data-types/date-data-type.md) siempre contiene información de fecha y hora. A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo. Si convierte un `Date` valor en una cadena, no `CStr` incluye valores neutros en la cadena resultante. Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha. Sin embargo, la información de fecha todavía está presente en el `Date` valor original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.

- **Confidencialidad de la referencia cultural.** Las funciones de conversión de tipos que implican cadenas realizan conversiones basadas en la configuración de la referencia cultural actual de la aplicación. Por ejemplo, `CDate` reconoce los formatos de fecha según la configuración regional del sistema. Debe proporcionar el día, el mes y el año en el orden correcto de la configuración regional, o la fecha podría no interpretarse correctamente. No se reconoce el formato de fecha larga si contiene una cadena de día de la semana, como "miércoles".

     Si necesita convertir a o desde una representación de cadena de un valor en un formato distinto del especificado por la configuración regional, no puede usar las funciones de conversión de tipo Visual Basic. Para ello, use los `ToString(IFormatProvider)` métodos y `Parse(String, IFormatProvider)` del tipo de ese valor. Por ejemplo, <xref:System.Double.Parse%2A?displayProperty=nameWithType> se usa al convertir una cadena en un `Double` y se usa <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en una cadena.

## <a name="ctype-function"></a>CType Function

La [función ctype](ctype-function.md) toma un segundo argumento, `typename` , y se convierte `expression` en `typename` , donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz a la que exista una conversión válida.

Para obtener una comparación de `CType` con las otras palabras clave de conversión de tipos, vea operador [DirectCast](../operators/directcast-operator.md) y [operador TryCast](../operators/trycast-operator.md).

## <a name="cbool-example"></a>Ejemplo de CBool

En el ejemplo siguiente se utiliza la `CBool` función para convertir expresiones en `Boolean` valores. Si una expresión se evalúa como un valor distinto de cero, `CBool` devuelve `True` ; de lo contrario, devuelve `False` .

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a>Ejemplo de CByte

En el ejemplo siguiente se utiliza la `CByte` función para convertir una expresión en `Byte` .

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a>Ejemplo de CChar

En el ejemplo siguiente se utiliza la `CChar` función para convertir el primer carácter de una `String` expresión a un `Char` tipo.

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

El argumento de entrada de `CChar` debe ser de tipo de datos `Char` o `String` . No se puede usar `CChar` para convertir un número en un carácter, porque `CChar` no puede aceptar un tipo de datos numérico. En el ejemplo siguiente se obtiene un número que representa un punto de código (código de carácter) y lo convierte en el carácter correspondiente. Usa la <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> función para obtener la cadena de dígitos, `CInt` convertir la cadena al tipo `Integer` y `ChrW` convertir el número al tipo `Char` .

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a>Ejemplo de CDate

En el ejemplo siguiente se utiliza la `CDate` función para convertir cadenas en `Date` valores. En general, no se recomienda codificar las fechas y horas de forma rígida como cadenas (como se muestra en este ejemplo). Utilice literales de fecha y literales de hora, como #Feb 12, 1969 # y #4:45:23 PM #, en su lugar.

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a>Ejemplo de CDbl

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a>Ejemplo de CDec

En el ejemplo siguiente se utiliza la `CDec` función para convertir un valor numérico en `Decimal` .

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a>Ejemplo de CInt

En el ejemplo siguiente se utiliza la `CInt` función para convertir un valor en `Integer` .

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a>Ejemplo de CLng

En el ejemplo siguiente se utiliza la `CLng` función para convertir valores en `Long` .

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a>Ejemplo de CObj

En el ejemplo siguiente se utiliza la `CObj` función para convertir un valor numérico en `Object` . La `Object` propia variable solo contiene un puntero de cuatro bytes, que señala al `Double` valor que se le ha asignado.

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a>Ejemplo de CSByte

En el ejemplo siguiente se utiliza la `CSByte` función para convertir un valor numérico en `SByte` .

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a>Ejemplo de CShort

En el ejemplo siguiente se utiliza la `CShort` función para convertir un valor numérico en `Short` .

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a>Ejemplo de CSng

En el ejemplo siguiente se utiliza la `CSng` función para convertir valores en `Single` .

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a>Ejemplo de CStr

En el ejemplo siguiente se utiliza la `CStr` función para convertir un valor numérico en `String` .

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

En el ejemplo siguiente se utiliza la `CStr` función para convertir `Date` valores en `String` valores.

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

`CStr` siempre representa un `Date` valor en el formato corto estándar para la configuración regional actual, por ejemplo, "6/15/2003 4:35:47 PM". Sin embargo, `CStr` suprime los *valores neutros* de 1/1/0001 para la fecha y 00:00:00 para la hora.

Para obtener más información sobre los valores devueltos por `CStr` , vea [valores devueltos para la función CSTR](return-values-for-the-cstr-function.md).

## <a name="cuint-example"></a>Ejemplo de CUInt

En el ejemplo siguiente se utiliza la `CUInt` función para convertir un valor numérico en `UInteger` .

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a>Ejemplo de CULng

En el ejemplo siguiente se utiliza la `CULng` función para convertir un valor numérico en `ULong` .

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a>Ejemplo de CUShort

En el ejemplo siguiente se utiliza la `CUShort` función para convertir un valor numérico en `UShort` .

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Funciones de conversión](conversion-functions.md)
- [Conversiones de tipos en Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
