---
title: "Funciones de conversi&#243;n de tipos (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CUShort"
  - "vb.csng"
  - "vb.CDate"
  - "CByte"
  - "CSng"
  - "vb.CDec"
  - "CBool"
  - "CStr"
  - "vb.CULng"
  - "CDec"
  - "CVErr"
  - "CDbl"
  - "CShort"
  - "vb.CObj"
  - "vb.CVErr"
  - "CULng"
  - "vb.cdbl"
  - "vb.cbool"
  - "CObj"
  - "CDate"
  - "CLng"
  - "vb.cstr"
  - "vb.cbyte"
  - "vb.clng"
  - "vb.CChar"
  - "CUShort"
  - "vb.CUInt"
  - "vb.cint"
  - "vb.CShort"
  - "CInt"
  - "CUInt"
  - "CChar"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "redondeo bancario"
  - "Boolean (tipo de datos), convertir"
  - "Byte (tipo de datos), convertir"
  - "CBool (función)"
  - "CByte (función)"
  - "CChar (función)"
  - "CDate (función)"
  - "CDbl (función)"
  - "CDec (función)"
  - "Char (tipo de datos), convertir"
  - "CInt (función)"
  - "CLng (función)"
  - "conversiones, funciones de conversión de tipos"
  - "CSByte (función)"
  - "CSng (función)"
  - "CStr (función)"
  - "CUInt (función)"
  - "CULng (función)"
  - "Currency (tipo de datos), funciones de conversión"
  - "CUShort (función)"
  - "conversión de tipos de datos, funciones para"
  - "tipos de datos [Visual Basic], convertir"
  - "Date (tipo de datos), convertir"
  - "fechas, convertir"
  - "Decimal (tipo de datos), convertir"
  - "Double (tipo de datos), convertir"
  - "números de precisión doble"
  - "fracciones"
  - "Integer (tipo de datos), convertir"
  - "enteros, funciones de conversión de tipos"
  - "Long (tipo de datos), convertir"
  - "números, convertir"
  - "números, redondeo"
  - "valores devueltos, tipos de datos"
  - "redondear números, redondeo bancario"
  - "redondear números, conversión de tipos"
  - "Short (tipo de datos), convertir"
  - "Single (tipo de datos), convertir"
  - "números de precisión sencilla, convertir"
  - "conversión de cadenas, funciones de conversión"
  - "String (tipo de datos), convertir"
  - "texto, convertir"
  - "horas, convertir"
  - "conversión de tipos, funciones para"
  - "conversión de tipos, Visual Basic y .NET Framework"
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Funciones de conversi&#243;n de tipos (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Estas funciones se compilan en línea, es decir, el código de conversión forma parte del código que evalúa la expresión.  A veces no se produce una llamada a un procedimiento para realizar la conversión, lo que mejora el rendimiento.  Cada función convierte una expresión a un tipo de datos específico.  
  
## Sintaxis  
  
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
  
## Parte  
 `expression`  
 Obligatorio.  Cualquier expresión del tipo de datos de origen.  
  
## Tipo de datos del valor devuelto  
 El nombre de función determina el tipo de datos del valor devuelto, como se muestra en la tabla siguiente.  
  
|Nombre de la función|Tipo de datos devuelto|Intervalo de valores del argumento `expression`|  
|--------------------------|----------------------------|-----------------------------------------------------|  
|`CBool`|[Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Cualquier expresión numérica, `Char` o `String` válida.|  
|`CByte`|[Byte \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/byte-data-type.md)|0 a 255 \(sin signo\); las partes fraccionarias se redondean.<sup>1</sup>|  
|`CChar`|[Char \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/char-data-type.md)|Cualquier expresión `Char` o `String` válida; sólo se convierte el primer carácter de `String`; el valor puede estar comprendido entre 0 y 65535 \(sin signo\).|  
|`CDate`|[Date \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/date-data-type.md)|Cualquier representación válida de fecha y hora.|  
|`CDbl`|[Double \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/double-data-type.md)|de \-1,79769313486231570E\+308 a \-4,94065645841246544E\-324 para valores negativos; de 4,94065645841246544E\-324 a 1,79769313486231570E\+308 para valores positivos.|  
|`CDec`|[Decimal \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|\+\/\-79.228.162.514.264.337.593.543.950.335 para números a partir de cero, es decir, números sin decimales.  Para números con 28 posiciones decimales, el intervalo es  \+\/\-7,9228162514264337593543950335.  El menor número posible distinto de cero es 0,0000000000000000000000000001 \(\+\/\-1E\-28\).|  
|`CInt`|[Integer \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/integer-data-type.md)|de \-2.147.483.648 a 2.147.483.647; las partes fraccionarias se redondean.<sup>1</sup>|  
|`CLng`|[Long \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/long-data-type.md)|de \-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807; las partes fraccionarias se redondean.<sup>1</sup>|  
|`CObj`|[Object \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/object-data-type.md)|Cualquier expresión válida.|  
|`CSByte`|[SByte \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|de \-128 a 127; las partes fraccionarias se redondean.<sup>1</sup>|  
|`CShort`|[Short \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/short-data-type.md)|de \-32.768 a 32.767; las partes fraccionarias se redondean.<sup>1</sup>|  
|`CSng`|[Single \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/single-data-type.md)|De \-3,402823E\+38 a –1,401298E\-45 para valores negativos; de 1,401298E\-45 a 3,402823E\+38 para valores positivos.|  
|`CStr`|[String \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/string-data-type.md)|Los valores devueltos para `CStr` dependen del argumento `expression`.  Vea [Valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[UInteger \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|de 0 a 4.294.967.295 \(sin signo\); las partes fraccionarias se redondean.<sup>1</sup>|  
|`CULng`|[ULong \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|de 0 a 18.446.744.073.709.551.615 \(sin signo\); las partes fraccionarias se redondean.<sup>1</sup>|  
|`CUShort`|[UShort \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|de 0 a 65.535 \(sin signo\); las partes fraccionarias se redondean.<sup>1</sup>|  
  
 <sup>1</sup> Las partes fraccionarias pueden estar sujetas a un tipo especial de redondeo denominado *redondeo bancario*.  Vea "Comentarios" para obtener más información.  
  
## Comentarios  
 Por regla general, debe utilizar preferentemente las funciones de conversión de tipos de Visual Basic que los métodos de .NET Framework, como `ToString()`, en la clase <xref:System.Convert> o en una clase o estructura individual de tipos.  Las funciones de Visual Basic se han diseñado para que interactúen de forma óptima con el código de Visual Basic; además hacen que el código fuente sea más corto y fácil de leer.  Asimismo, los métodos de conversión de .NET Framework no siempre producen los mismos resultados que las funciones de Visual Basic, por ejemplo cuando se convierte de `Boolean` a `Integer`.  Para obtener más información, vea [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Comportamiento  
  
-   **Conversión.** En general, puede utilizar las funciones de conversión de tipos de datos para convertir el resultado de una operación a un tipo de datos concreto en vez de al tipo de datos predeterminado.  Por ejemplo, utilice `CDec` para forzar la ejecución de operaciones con aritmética decimal en los casos en los que se haría con precisión sencilla, doble precisión o aritmética de enteros.  
  
-   **Conversiones incorrectas.** Si el argumento `expression` transferido a la función está fuera del intervalo de valores del tipo de datos al que se va a convertir, se inicia una excepción <xref:System.OverflowException>.  
  
-   **Partes fraccionarias.** Cuando un valor no integral se convierte a un tipo entero, las funciones de conversión de enteros \(`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng` y `CUShort`\) quitan la parte fraccionaria y redondean el valor al entero más próximo.  
  
     Si la parte fraccionaria es exactamente 0,5, las funciones de conversión de enteros lo rodean al entero par más próximo.  Por ejemplo, 0,5 se redondea a 0 y 1,5 y 2,5 se redondean a 2.  Esto se denomina *redondeo bancario* a veces y su propósito es compensar una tendencia que se podría acumular al sumar muchos de estos números.  
  
     `CInt` y `CLng` difieren de las funciones <xref:Microsoft.VisualBasic.Conversion.Int%2A> y <xref:Microsoft.VisualBasic.Conversion.Fix%2A>, en que, en lugar de redondear, truncan la parte fraccionaria de un número.  Además, `Fix` e `Int` siempre devuelven un valor del mismo tipo de datos que reciben.  
  
-   **Conversiones de fecha y hora.** Utilice la función <xref:Microsoft.VisualBasic.Information.IsDate%2A> para determinar si un valor se puede convertir en una fecha y hora.  `CDate` reconoce literales de fecha y literales de tiempo pero no valores numéricos.  Para convertir un valor `Date` de Visual Basic 6.0 en un valor  `Date` en Visual Basic 2005 o versiones posteriores, puede utilizar el método <xref:System.DateTime.FromOADate%2A?displayProperty=fullName>.  
  
-   **Valores de fecha u hora neutrales.** El tipo de datos [Date \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/date-data-type.md) contiene siempre información de fecha y hora.  Para la conversión de tipos, Visual Basic considera 1\/1\/0001 \(1 de enero del año 1\) un *valor neutral* de fecha y 00:00:00 \(medianoche\) un valor neutral de hora.  Si se convierte un valor `Date` a una cadena, `CStr` no incluye valores neutrales en la cadena resultante.  Por ejemplo, si se convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado sería "9:30:00 a.m.", ya que la información de fecha se omite.  Sin embargo, la información de fecha permanece presente en el valor de `Date` original y se puede recuperar mediante funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
-   **Distinción de referencias culturales.** Las funciones de conversión de tipos que implican cadenas realizan las conversiones en función de la configuración de la referencia cultural actual de la aplicación.  Por ejemplo, `CDate` reconoce formatos de fecha de acuerdo con la configuración regional del sistema.  Debe suministrar el día, mes y año en el orden correcto para la configuración regional; de no hacerlo así, es posible que la fecha no se interprete de forma correcta.  No se puede reconocer un formato de fecha largo si contiene la cadena del día de la semana, por ejemplo “Miércoles”.  
  
     Si necesita convertir una representación de cadena de un valor en un formato diferente al especificado por la configuración regional, no puede utilizar las funciones de conversión de tipos de Visual Basic.  Para ello, utilice los métodos `ToString(IFormatProvider)` y `Parse(String, IFormatProvider)` de ese tipo de valor.  Por ejemplo, utilice <xref:System.Double.Parse%2A?displayProperty=fullName> cuando convierte una cadena a un valor de tipo `Double` y utilice <xref:System.Double.ToString%2A?displayProperty=fullName> cuando convierta un valor de tipo `Double` en una cadena.  
  
## CType \(Función\)  
 La [función CType](../../../visual-basic/language-reference/functions/ctype-function.md) toma un segundo argumento, `typename`, y convierte `expression` en `typename`, donde `typename` puede ser cualquier tipo de datos, estructura, clase o interfaz para la que exista una conversión válida.  
  
 Para una comparación de `CType` con las otras palabras clave de conversión de tipos, vea [DirectCast \(Operador\)](../../../visual-basic/language-reference/operators/directcast-operator.md) y [TryCast \(Operador\)](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## Ejemplo de la función CBool  
 En este ejemplo se utiliza la función `CBool` para convertir expresiones en valores `Boolean`.  Si una expresión se evalúa en  un valor distinto de cero, `CBool` devuelve `True`; en caso contrario, devuelve `False`.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## Ejemplo de la función CByte  
 En este ejemplo se utiliza la función `CByte` para convertir expresiones en `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## Ejemplo de la función CChar  
 En el ejemplo siguiente se utiliza la función `CChar` para convertir el primer carácter de una expresión `String` en un tipo `Char`.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 El argumento de entrada para `CChar` debe pertenecer al tipo de datos `Char` o `String`.  No puede utilizar `CChar` para convertir un número en un carácter, porque `CChar` no acepta un tipo de datos numéricos.  En el ejemplo siguiente se obtiene un número que representa un punto de código \(código de carácter\) y se convierte al carácter correspondiente.  En el ejemplo se utiliza la función <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> para obtener la cadena de dígitos, `CInt` para convertir la cadena en el tipo `Integer` y `ChrW` para convertir el número en el tipo `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## Ejemplo de la función CDate  
 En este ejemplo se utiliza la función `CDate` para convertir cadenas en valores `Date`.  En general, no se recomienda especificar las fechas y horas como cadenas en el código, tal y como se puede ver en este ejemplo.  Utilice literales de fecha y hora, por ejemplo \#Feb 12, 1969\# y \#4:45:233 p.m.\#.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## Ejemplo del algoritmo CDbl  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## Ejemplo de la función CDec  
 En el siguiente ejemplo se utiliza la función `CDec` para convertir un valor numérico en `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## Ejemplo de la función CInt  
 En este ejemplo se utiliza la función `CInt` para convertir un valor a `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## Ejemplo del algoritmo CLng  
 En el ejemplo siguiente se utiliza la función `CLng` para convertir valores a `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## Ejemplo de la función CObj  
 En el siguiente ejemplo se utiliza la función `CObj` para convertir un valor numérico en `Object`.  La variable `Object` en sí contiene sólo un puntero de cuatro bytes, que señala al valor `Double` que tiene asignado.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## Ejemplo de CSByte  
 En el siguiente ejemplo se utiliza la función `CSByte` para convertir un valor numérico en `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## Ejemplo de la función CShort  
 En el siguiente ejemplo se utiliza la función `CShort` para convertir un valor numérico en `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## Ejemplo del algoritmo CSng  
 En el ejemplo siguiente se utiliza la función `CSng` para convertir valores a `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## Ejemplo del algoritmo CStr  
 En el siguiente ejemplo se utiliza la función `CStr` para convertir un valor numérico en `String`.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 En el ejemplo siguiente se utiliza la función `CStr` para convertir valores `Date` en valores `String`.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` siempre representa un valor `Date` en el formato corto estándar de la configuración regional actual, por ejemplo, "15\/6\/2003 4:35:47 p.m.".  Sin embargo, `CStr` suprime los *valores neutrales* 1\/1\/0001 para la fecha y 00:00:00 para la hora.  
  
 Para obtener información detallada sobre los valores devueltos por `CStr`, vea [Valores devueltos para la función CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## Ejemplo de CUInt  
 En el siguiente ejemplo se utiliza la función `CUInt` para convertir un valor numérico en `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## Ejemplo de CULng  
 En el siguiente ejemplo se utiliza la función `CULng` para convertir un valor numérico en `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## Ejemplo de CUShort  
 En el siguiente ejemplo se utiliza la función `CUShort` para convertir un valor numérico en `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## Vea también  
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