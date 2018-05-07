---
title: Funciones de conversión de tipos (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-conversion-functions-visual-basic"></a>Funciones de conversión de tipos (Visual Basic)
Estas funciones están compilados de forma alineada, lo que significa que el código de conversión forma parte del código que evalúa la expresión. En ocasiones, no hay ninguna llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento. Cada función convierte una expresión al tipo de datos específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 Requerido. Cualquier expresión del tipo de datos de origen.  
  
## <a name="return-value-data-type"></a>Tipo de datos de valor devuelto  
 El nombre de la función determina el tipo de datos del valor que devuelve, como se muestra en la tabla siguiente.  
  
|Nombre de la función|Tipo de datos devuelto|Intervalo para `expression` argumento|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Cualquier `Char` o `String` o expresión numérica.|  
|`CByte`|[Byte (tipo de datos)](../../../visual-basic/language-reference/data-types/byte-data-type.md)|0 y 255 (sin signo); partes fraccionarias se redondean. <sup>1</sup>|  
|`CChar`|[Char (tipo de datos)](../../../visual-basic/language-reference/data-types/char-data-type.md)|Cualquier `Char` o `String` expresión; sólo primer carácter de un `String` se convierte; puede oscilar entre 0 y 65535 (sin signo).|  
|`CDate`|[Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)|Cualquier representación válida de una fecha y hora.|  
|`CDbl`|[Double (tipos de datos)](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1, 79769313486231570E + 308 a - 4, 94065645841246544E-324 para valores negativos; 4, 94065645841246544E-324 a 1, 79769313486231570E + 308 para valores positivos.|  
|`CDec`|[Decimal (tipo de datos)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+/-79,228,162,514,264,337,593,543,950,335 para números a partir de cero, es decir, números sin decimales. Para números con 28 posiciones decimales, el intervalo es +/-7,9228162514264337593543950335. El menor número posible distinto de cero es 0,0000000000000000000000000001 (+/-1E-28).|  
|`CInt`|[Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)|-2.147.483.648 y 2.147.483.647; partes fraccionarias se redondean. <sup>1</sup>|  
|`CLng`|[Long (tipo de datos)](../../../visual-basic/language-reference/data-types/long-data-type.md)|-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807; partes fraccionarias se redondean. <sup>1</sup>|  
|`CObj`|[Tipo de objeto de datos](../../../visual-basic/language-reference/data-types/object-data-type.md)|Cualquier expresión válida.|  
|`CSByte`|[SByte (tipo de datos)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|-128 a 127; partes fraccionarias se redondean. <sup>1</sup>|  
|`CShort`|[Short (tipo de datos)](../../../visual-basic/language-reference/data-types/short-data-type.md)|-32.768 a 32.767; partes fraccionarias se redondean. <sup>1</sup>|  
|`CSng`|[Single (tipo de datos)](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3, 402823E + 38 a - 1, 401298E-45 para los valores negativos; 1, 401298E-45 a 3, 402823E + 38 para valores positivos.|  
|`CStr`|[String (tipo de datos)](../../../visual-basic/language-reference/data-types/string-data-type.md)|Devuelve para `CStr` dependen de la `expression` argumento. Vea [valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|de 0 a 4.294.967.295 (sin signo); partes fraccionarias se redondean. <sup>1</sup>|  
|`CULng`|[ULong (tipo de datos)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|de 0 a 18.446.744.073.709.551.615 (sin signo); partes fraccionarias se redondean. <sup>1</sup>|  
|`CUShort`|[UShort (tipo de datos)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|de 0 a 65.535 (sin signo); partes fraccionarias se redondean. <sup>1</sup>|  
  
 <sup>1</sup> partes fraccionarias pueden estar sujetas a un tipo especial de redondeo denominado *el redondeo bancario*. Para obtener más información, vea "Comentarios".  
  
## <a name="remarks"></a>Comentarios  
 Como norma, debe utilizar las funciones de conversión de tipo de Visual Basic con preferencia a los métodos de .NET Framework como `ToString()`, ya sea en la <xref:System.Convert> clase o de una clase o estructura individual de tipos. Las funciones de Visual Basic están diseñadas para la interacción óptima con código de Visual Basic, y también hacen que el código fuente más corto y más fácil de leer. Además, los métodos de conversión de .NET Framework no siempre generan los mismos resultados que las funciones de Visual Basic, por ejemplo, al convertir `Boolean` a `Integer`. Para obtener más información, consulte [solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Conversión.** En general, puede utilizar las funciones de conversión de tipo de datos para convertir el resultado de una operación en un tipo de datos concreto en lugar de con el tipo de datos predeterminado. Por ejemplo, utilice `CDec` para forzar la aritmética decimal en los casos donde se haría precisión sencilla, doble precisión o aritmética de enteros.  
  
-   **Error en conversiones.** Si el `expression` pasa a la función es fuera del intervalo del tipo de datos donde es convertir, un <xref:System.OverflowException> se produce.  
  
-   **Partes fraccionarias.** Al convertir un valor no integral a un entero escriba, las funciones de conversión de enteros (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, y `CUShort`) quitar el fracciones de pieza y redondean el valor al entero más próximo.  
  
     Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros de ida y vuelta para el entero par más próximo. Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2. Esto se denomina a veces *el redondeo bancario*, y su finalidad es compensar una tendencia que se podría acumular al sumar muchos de estos números.  
  
     `CInt` y `CLng` diferencian el <xref:Microsoft.VisualBasic.Conversion.Int%2A> y <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funciones, que se truncan en lugar de redondean, la parte fraccionaria de un número. Además, `Fix` y `Int` siempre devuelven un valor del mismo tipo de datos que se pasa.  
  
-   **Conversiones de fecha y hora.** Use la <xref:Microsoft.VisualBasic.Information.IsDate%2A> función para determinar si se puede convertir un valor a una fecha y hora. `CDate` reconoce literales de fecha y literales de tiempo pero no valores numéricos. Para convertir un Visual Basic 6.0 `Date` valor a un `Date` valor en Visual Basic 2005 o versiones posteriores, puede usar el <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> método.  
  
-   **Neutral valores de fecha y hora.** El [tipo de datos Date](../../../visual-basic/language-reference/data-types/date-data-type.md) siempre contiene información de fecha y hora. Para fines de conversión de tipos, Visual Basic considera 1/1/0001 (del 1 de enero del año 1) como un *valor neutral* de fecha y 00:00:00 (medianoche) un valor neutral por vez. Si convierte un `Date` valor en una cadena, `CStr` no incluye valores neutrales en la cadena resultante. Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha. Sin embargo, la información de fecha aún está presente en la versión original `Date` valor y se pueden recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> (función).  
  
-   **Distinción de referencias culturales.** Las funciones de conversión de tipos que implican cadenas realizan conversiones en función de la configuración de referencia cultural actual para la aplicación. Por ejemplo, `CDate` reconoce los formatos de fecha según la configuración regional del sistema. Debe proporcionar el día, mes y año en el orden correcto para la configuración regional o la fecha no se interpreten correctamente. No se reconoce el formato de fecha largo si contiene una cadena de día de la semana, por ejemplo, "Miércoles".  
  
     Si necesita convertir hacia o desde una representación de cadena de un valor en un formato distinto al especificado por la configuración regional, no puede usar las funciones de conversión de tipo de Visual Basic. Para ello, use la `ToString(IFormatProvider)` y `Parse(String, IFormatProvider)` métodos de ese tipo de valor. Por ejemplo, utilice <xref:System.Double.Parse%2A?displayProperty=nameWithType> al convertir una cadena en un `Double`y usar <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en una cadena.  
  
## <a name="ctype-function"></a>CType Function  
 El [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) toma un segundo argumento, `typename`y convierte `expression` a `typename`, donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz a la que existe una conversión válida.  
  
 Para obtener una comparación de `CType` con el otro tipo palabras clave para conversiones, vea [DirectCast (operador)](../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>En el ejemplo se CBool  
 En el ejemplo siguiente se usa el `CBool` función para convertir expresiones de `Boolean` valores. Si una expresión se evalúa como un valor distinto de cero, `CBool` devuelve `True`; en caso contrario, devuelve `False`.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a>En el ejemplo se CByte  
 En el ejemplo siguiente se usa el `CByte` función para convertir una expresión a un `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a>En el ejemplo se CChar  
 En el ejemplo siguiente se usa el `CChar` función para convertir el primer carácter de un `String` expresión a un `Char` tipo.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 El argumento de entrada `CChar` debe ser del tipo de datos `Char` o `String`. No se puede utilizar `CChar` para convertir un número en un carácter, porque `CChar` no acepta un tipo de datos numéricos. En el ejemplo siguiente se obtiene un número que representa un punto de código (código de carácter) y lo convierte en el carácter correspondiente. Usa el <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> función para obtener la cadena de dígitos, `CInt` para convertir la cadena al tipo `Integer`, y `ChrW` para convertir el número que escriba `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a>En el ejemplo se CDate  
 En el ejemplo siguiente se usa el `CDate` función para convertir cadenas a `Date` valores. En general, no se recomienda codificar de forma rígida fechas y horas como cadenas (como se muestra en este ejemplo). Usar literales de fecha y hora, por ejemplo #Feb 12, 1969 # y # 4:45:23 P.M. # en su lugar.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a>En el ejemplo se CDbl  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a>En el ejemplo se CDec  
 En el ejemplo siguiente se usa el `CDec` función para convertir un valor numérico y `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a>En el ejemplo se CInt  
 En el ejemplo siguiente se usa el `CInt` función para convertir un valor a `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a>En el ejemplo se CLng  
 En el ejemplo siguiente se usa el `CLng` función para convertir valores a `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a>En el ejemplo se CObj  
 En el ejemplo siguiente se usa el `CObj` función para convertir un valor numérico y `Object`. El `Object` propia variable contiene sólo un puntero de cuatro bytes, que apunta a la `Double` valor asignado a él.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a>Ejemplo de CSByte  
 En el ejemplo siguiente se usa el `CSByte` función para convertir un valor numérico y `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a>En el ejemplo se CShort  
 En el ejemplo siguiente se usa el `CShort` función para convertir un valor numérico y `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a>En el ejemplo se CSng  
 En el ejemplo siguiente se usa el `CSng` función para convertir valores a `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a>En el ejemplo se CStr  
 En el ejemplo siguiente se usa el `CStr` función para convertir un valor numérico y `String`.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 En el ejemplo siguiente se usa el `CStr` función para convertir `Date` valores `String` valores.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` siempre presenta un `Date` valor en el formato corto estándar de la configuración regional, por ejemplo, "15/6/2003 4:35:47 P.M.". Sin embargo, `CStr` suprime la *valores neutrales* de 1/1/0001 para la fecha y 00:00:00 para la hora.  
  
 Para obtener más detalles sobre los valores devueltos por `CStr`, consulte [valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>Ejemplo de CUInt  
 En el ejemplo siguiente se usa el `CUInt` función para convertir un valor numérico y `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a>Ejemplo de CULng  
 En el ejemplo siguiente se usa el `CULng` función para convertir un valor numérico y `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a>Ejemplo de CUShort  
 En el ejemplo siguiente se usa el `CUShort` función para convertir un valor numérico y `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [Funciones de conversión](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Conversiones de tipos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
