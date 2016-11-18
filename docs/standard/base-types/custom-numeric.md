---
title: "Cadenas con formato numérico personalizado"
description: "Cadenas con formato numérico personalizado"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 7b1c16ee-956f-4e9c-8502-c3dd6598c51d
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 2d5a051efd074d02f2a5e9ff03c11e1d9a202d7f

---

# <a name="custom-numeric-format-strings"></a>Cadenas con formato numérico personalizado

Puede crear una cadena de formato numérico personalizado, formada por uno o varios especificadores numéricos personalizados, para definir cómo debe darse formato a los datos numéricos. Una cadena de formato numérico personalizado es cualquier cadena que no sea una [cadena de formato numérico estándar](standard-numeric.md). 

Algunas sobrecargas del método `ToString` de todos los tipos numéricos admiten las cadenas de formato numérico personalizado. Por ejemplo, puede proporcionar una cadena de formato numérico a los métodos [ToString(String)](xref:System.Int32.ToString(System.String)) y [ToString(String, IFormatProvider)](xref:System.Int32.ToString(System.String,System.IFormatProvider)) del tipo [Int32](xref:System.Int32). La característica de [formato compuesto](composite-format.md) de .NET Framework, que usan algunos métodos `Write` y `WriteLine` de las clases [Console](xref:System.Console) y [StreamWriter](xref:System.IO.StreamWriter), el método [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) y el método [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), admite también cadenas con formato numérico personalizado.

En la tabla siguiente se describen los especificadores de formato numérico personalizado y se muestran las salidas de ejemplo generadas por cada especificador de formato. Consulte la sección [Notas](#notes) para obtener más información sobre cómo usar las cadenas con formato numérico personalizado y la sección [Ejemplo](#example) para ver una ilustración completa de su uso.

Especificador de formato | Name | Descripción | Ejemplos
---------------- | ---- | ----------- | --------
"0" | Marcador de posición cero | Reemplaza el cero con el dígito correspondiente si hay alguno presente; de lo contrario, el cero aparece en la cadena de resultado. | `1234.5678 ("00000") -> 01235`; `0.45678 ("0.00", en-US) -> 0.46`; `0.45678 ("0.00", fr-FR) -> 0,46`
"#" | Marcador de posición de dígito. | Reemplaza el símbolo "#" por el dígito correspondiente si hay alguno presente; de lo contrario, no aparece ningún dígito en la cadena de resultado. Tenga en cuenta que no se mostrará ningún dígito en la cadena de resultado si el dígito que se encuentra en la cadena de entrada es un 0 no significativo. Por ejemplo, 0003 ("####") -> 3. | `1234.5678 ("#####") -> 1235`; `0.45678 ("#.##", en-US) -> .46`; `0.45678 ("#.##", fr-FR) -> ,46`
"." | Separador decimal | Determina la ubicación del separador decimal en la cadena de resultado. | `0.45678 ("0.00", en-US) -> 0.46`; `0.45678 ("0.00", fr-FR) -> 0,46`
"," | Separador de grupos y escala numérica | Actúa como separador de grupos y como especificador de escala numérica. Como separador de grupos, inserta un carácter separador de grupos adaptado entre cada grupo. Como especificador de escala numérica, divide un número por 1000 por cada coma especificada. | Especificador de separador de grupos: `2147483647 ("##,#", en-US) -> 2,147,483,647`; `2147483647 ("##,#", es-ES) -> 2.147.483.647`. Especificador de escala: `2147483647 ("#,#,,", en-US) -> 2,147`; `2147483647 ("#,#,,", es-ES) -> 2.147`
"%" | Marcador de posición de porcentaje. | Multiplica un número por 100 e inserta un símbolo de porcentaje adaptado en la cadena de resultado. | `0.3697 ("%#0.00", en-US) -> %36.97`; `0.3697 ("%#0.00", el-GR) -> %36,97`; `0.3697 ("##.0 %", en-US) -> 37.0 %`; `0.3697 ("##.0 %", el-GR) -> 37,0 %`
"‰" | Marcador de posición de "por mil" | Multiplica un número por 1000 e inserta un símbolo de "por mil" adaptado en la cadena de resultado. | `0.03697 ("#0.00‰", en-US) -> 36.97‰`; `0.03697 ("#0.00‰", ru-RU) -> 36,97‰`
"E0", "E+0", "E-0", "e0", "e+0", "e-0" | Notación exponencial | Si va seguido al menos de un 0 (cero), da formato al resultado usando notación exponencial. El modelo de mayúsculas de "E" o "e" indica el modelo de mayúsculas del símbolo de exponente en la cadena de resultado. El número de ceros que siguen al carácter "E" o "e" determina el número mínimo de dígitos en el exponente. Un signo más (+) indica que un carácter de signo precede siempre al exponente. Un signo menos (-) indica que un carácter de signo solo precede a los exponentes negativos. | `987654 ("#0.0e0") -> 98.8e4`; `1503.92311 ("0.0##e+00") -> 1.504e+03`; `1.8901385E-16 ("0.0e+00") -> 1.9e-16`
\ | Carácter de escape | Hace que el carácter siguiente se interprete como un literal en lugar de como un especificador de formato personalizado. | `987654 ("\###00\#") -> #987654#`
'string', "string" | Delimitador de cadena literal | Indica que los caracteres que encierra se deben copiar en la cadena de resultado sin modificar. | `68 ("# ' degrees'") -> 68 degrees`
; | Separador de secciones | Define secciones con cadenas de formato diferentes para los números positivos, negativos y cero. | `12.345 ("#0.0#;(#0.0#);-\0-") -> 12.35`; `0 ("#0.0#;(#0.0#);-\0-") -> -0-`; `-12.345 ("#0.0#;(#0.0#);-\0-") -> (12.35)`; `12.345 ("#0.0#;(#0.0#)") -> 12.35`; `0 ("#0.0#;(#0.0#)") -> 0.0 ; -12.345 ("#0.0#;(#0.0#)") -> (12.35)`
Otros | Todos los demás caracteres | El carácter se copia en la cadena de resultado sin modificar. | `68 ("# °") -> 68 °`

En las secciones siguientes se proporciona información detallada sobre cada uno de los especificadores de formato numérico personalizado.

## <a name="the-0-custom-specifier"></a>El especificador personalizado "0"

El especificador de formato personalizado "0" actúa como un símbolo de marcador de posición cero. Si el valor al que se está dando formato tiene un dígito en la posición donde aparece el cero en la cadena de formato, se copia ese dígito a la cadena de resultado; de lo contrario, aparecerá un cero en la cadena de resultado. La posición del cero que aparece más a la izquierda antes del separador decimal y la del cero que está más a la derecha después del separador decimal determinan el intervalo de dígitos que están siempre presentes en la cadena de resultado. 

El especificador "00" hace que el valor se redondee al dígito más próximo que precede al decimal, donde siempre se utiliza el redondeo para evitar el cero. Por ejemplo, al aplicar el formato a 34.5 con "00" el resultado del valor es 35.

En el ejemplo siguiente se muestran varios valores a los que se les ha aplicado cadenas de formato personalizado que incluyen marcadores de posición cero.

```csharp
double value;

value = 123;
Console.WriteLine(value.ToString("00000"));
Console.WriteLine(String.Format("{0:00000}", value));
// Displays 00123

value = 1.2;
Console.WriteLine(value.ToString("0.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                "{0:0.00}", value));
// Displays 1.20

Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value));
// Displays 01.20

CultureInfo daDK = CultureInfo.CreateSpecificCulture("da-DK");
Console.WriteLine(value.ToString("00.00", daDK)); 
Console.WriteLine(String.Format(daDK, "{0:00.00}", value));
// Displays 01,20

value = .56;
Console.WriteLine(value.ToString("0.0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.0}", value));
// Displays 0.6

value = 1234567890;
Console.WriteLine(value.ToString("0,0", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0}", value)); 
// Displays 1,234,567,890      

CultureInfo elGR = CultureInfo.CreateSpecificCulture("el-GR");
Console.WriteLine(value.ToString("0,0", elGR)); 
Console.WriteLine(String.Format(elGR, "{0:0,0}", value));   
// Displays 1.234.567.890

value = 1234567890.123456;
Console.WriteLine(value.ToString("0,0.0", CultureInfo.InvariantCulture));   
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.0}", value));   
// Displays 1,234,567,890.1  

value = 1234.567890;
Console.WriteLine(value.ToString("0,0.00", CultureInfo.InvariantCulture));  
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.00}", value));  
// Displays 1,234.57
```

```vb
Dim value As Double

value = 123
Console.WriteLine(value.ToString("00000"))
Console.WriteLine(String.Format("{0:00000}", value))
' Displays 00123

value = 1.2
Console.Writeline(value.ToString("0.00", CultureInfo.InvariantCulture))
Console.Writeline(String.Format(CultureInfo.InvariantCulture, 
                  "{0:0.00}", value))
' Displays 1.20
Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value))
' Displays 01.20
Dim daDK As CultureInfo = CultureInfo.CreateSpecificCulture("da-DK")
Console.WriteLine(value.ToString("00.00", daDK))
Console.WriteLine(String.Format(daDK, "{0:00.00}", value))
' Displays 01,20

value = .56
Console.WriteLine(value.ToString("0.0", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.0}", value))
' Displays 0.6

value = 1234567890
Console.WriteLine(value.ToString("0,0", CultureInfo.InvariantCulture))  
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0}", value))  
' Displays 1,234,567,890      
Dim elGR As CultureInfo = CultureInfo.CreateSpecificCulture("el-GR")
Console.WriteLine(value.ToString("0,0", elGR))
Console.WriteLine(String.Format(elGR, "{0:0,0}", value))    
' Displays 1.234.567.890

value = 1234567890.123456
Console.WriteLine(value.ToString("0,0.0", CultureInfo.InvariantCulture))    
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.0}", value))    
' Displays 1,234,567,890.1  

value = 1234.567890
Console.WriteLine(value.ToString("0,0.00", CultureInfo.InvariantCulture))   
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0,0.00}", value))   
' Displays 1,234.57
```

## <a name="the-custom-specifier"></a>El especificador personalizado "#"

El especificador de formato personalizado "#" actúa como un símbolo de marcador de posición de dígitos. Si el valor al que se está dando formato tiene un dígito en la posición donde aparece el símbolo "#" en la cadena de formato, ese dígito se copia a la cadena de resultado. En caso contrario, no se almacena nada en esa posición de la cadena de resultado. 

Tenga en cuenta que este especificador nunca muestra un cero que no sea un dígito significativo, incluso aunque el cero sea el único dígito de la cadena. Solo mostrará cero si es un dígito significativo del número que se está mostrando. 

La cadena de formato "##" hace que el valor se redondee al dígito más próximo que precede al decimal, donde siempre se utiliza el redondeo para evitar el cero. Por ejemplo, al aplicar el formato a 34.5 con "##" el resultado del valor es 35.

En el ejemplo siguiente se muestran varios valores a los que se les ha aplicado cadenas de formato personalizado que incluyen marcadores de posición de dígitos.

```csharp
double value;

value = 1.2;
Console.WriteLine(value.ToString("#.##", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#.##}", value));
// Displays 1.2

value = 123;
Console.WriteLine(value.ToString("#####"));
Console.WriteLine(String.Format("{0:#####}", value));
// Displays 123

value = 123456;
Console.WriteLine(value.ToString("[##-##-##]"));      
Console.WriteLine(String.Format("{0:[##-##-##]}", value));      
// Displays [12-34-56]

value = 1234567890;
Console.WriteLine(value.ToString("#"));
Console.WriteLine(String.Format("{0:#}", value));
// Displays 1234567890

Console.WriteLine(value.ToString("(###) ###-####"));
Console.WriteLine(String.Format("{0:(###) ###-####}", value));
// Displays (123) 456-7890
```

```vb
Dim value As Double

value = 1.2
Console.WriteLine(value.ToString("#.##", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#.##}", value))
' Displays 1.2

value = 123
Console.WriteLine(value.ToString("#####"))
Console.WriteLine(String.Format("{0:#####}", value))
' Displays 123

value = 123456
Console.WriteLine(value.ToString("[##-##-##]"))      
Console.WriteLine(String.Format("{0:[##-##-##]}", value))      
' Displays [12-34-56]

value = 1234567890
Console.WriteLine(value.ToString("#"))
Console.WriteLine(String.Format("{0:#}", value))
' Displays 1234567890

Console.WriteLine(value.ToString("(###) ###-####"))
Console.WriteLine(String.Format("{0:(###) ###-####}", value))
' Displays (123) 456-7890
```

Para devolver una cadena de resultado en la que los dígitos que faltan o los ceros iniciales se reemplazan por espacios, use la característica de [formato compuesto](composite-format.md) y especifique un ancho de campo, como se muestra en el ejemplo siguiente.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double value = .324;
      Console.WriteLine("The value is: '{0,5:#.###}'", value);
   }
}
// The example displays the following output if the current culture
// is en-US:
//      The value is: ' .324'
```

```vb
Module Example
   Public Sub Main()
      Dim value As Double = .324
      Console.WriteLine("The value is: '{0,5:#.###}'", value)
   End Sub
End Module
' The example displays the following output if the current culture
' is en-US:
'      The value is: ' .324'
```

## <a name="the-custom-specifier"></a>El especificador personalizado "."

El especificador de formato personalizado "." inserta un separador decimal localizado en la cadena del resultado. El primer punto de la cadena de formato determina la ubicación del separador decimal en el valor con formato y se omite cualquier punto adicional. 

El carácter que se usa como separador decimal en la cadena de resultado no es siempre un punto; viene determinado por la propiedad [NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que controla la aplicación de formato.

En el ejemplo siguiente se utiliza el especificador de formato "." para definir la ubicación del separador decimal en varias cadenas de resultado.

```csharp
double value;

value = 1.2;
Console.WriteLine(value.ToString("0.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.00}", value));
// Displays 1.20

Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:00.00}", value));
// Displays 01.20

Console.WriteLine(value.ToString("00.00", 
                CultureInfo.CreateSpecificCulture("da-DK")));
Console.WriteLine(String.Format(CultureInfo.CreateSpecificCulture("da-DK"),
                "{0:00.00}", value));
// Displays 01,20

value = .086;
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value)); 
// Displays 8.6%

value = 86000;
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                "{0:0.###E+0}", value));
// Displays 8.6E+4
```

```vb
Dim value As Double

  value = 1.2
  Console.Writeline(value.ToString("0.00", CultureInfo.InvariantCulture))
  Console.Writeline(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:0.00}", value))
  ' Displays 1.20

  Console.WriteLine(value.ToString("00.00", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:00.00}", value))
  ' Displays 01.20

  Console.WriteLine(value.ToString("00.00", _
                    CultureInfo.CreateSpecificCulture("da-DK")))
  Console.WriteLine(String.Format(CultureInfo.CreateSpecificCulture("da-DK"),
                    "{0:00.00}", value))
  ' Displays 01,20

  value = .086
  Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture)) 
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#0.##%}", value)) 
  ' Displays 8.6%

  value = 86000
  Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                    "{0:0.###E+0}", value))
' Displays 8.6E+4
```

## <a name="the-custom-specifier"></a>El especificador personalizado ","

El carácter "," actúa como separador de grupos y como especificador de escala numérica. 

* Separador de grupos: si se especifican una o varias comas dos marcadores de posición de dígitos (0 ó #) que dan formato a los dígitos enteros de un número, se insertará un carácter separador de grupos entre cada grupo de números en la parte entera de la salida. 

  Las propiedades [NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) y [NumberGroupSizes](xref:System.Globalization.NumberFormatInfo.NumberGroupSizes) del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual determinan el carácter usado como separador de grupos de números y el tamaño de cada grupo de números. Por ejemplo, si se utiliza la cadena "#,#" y la referencia cultural de todos los idiomas para dar formato al número 1000, el resultado será "1,000".
  
* Especificador de escala numérica: si se especifican una o varias comas inmediatamente a la izquierda del punto decimal explícito o implícito, el número al que se va a dar formato se divide por 1000 por cada coma. Por ejemplo, si se utiliza la cadena "0,," para dar formato al número 100 millones, el resultado será "100". 

Puede usar especificadores de separador de grupos y de escala numérica en la misma cadena de formato. Por ejemplo, si se utiliza la cadena "#,0,," y la referencia cultural de todos los idiomas para dar formato al número mil millones, el resultado será "1,000". 

En el ejemplo siguiente se muestra el uso de la coma como separador de grupos.

```csharp
double value = 1234567890;
Console.WriteLine(value.ToString("#,#", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,#}", value));
// Displays 1,234,567,890      

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value));
// Displays 1,235
```

```vb
Dim value As Double = 1234567890
Console.WriteLine(value.ToString("#,#", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,#}", value))
' Displays 1,234,567,890      

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value))
' Displays 1,235
```

En el ejemplo siguiente se muestra el uso de la coma como especificador de escala numérica.

```csharp
double value = 1234567890;
Console.WriteLine(value.ToString("#,,", CultureInfo.InvariantCulture)); 
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,,}", value)); 
// Displays 1235   

Console.WriteLine(value.ToString("#,,,", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,,,}", value));
// Displays 1  

Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture));       
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#,##0,,}", value));       
// Displays 1,235
```  

```vb
Dim value As Double = 1234567890
  Console.WriteLine(value.ToString("#,,", CultureInfo.InvariantCulture))    
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, "{0:#,,}", value))  
  ' Displays 1235   

  Console.WriteLine(value.ToString("#,,,", CultureInfo.InvariantCulture))
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#,,,}", value))
' Displays 1  

  Console.WriteLine(value.ToString("#,##0,,", CultureInfo.InvariantCulture))       
  Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                  "{0:#,##0,,}", value))       
' Displays 1,235
```

## <a name="the-custom-specifier"></a>El especificador personalizado "%"

Un signo de porcentaje (%) en una cadena de formato hace que se multiplique un número por 100 antes de darle formato. El símbolo de porcentaje adaptado se inserta en el número en la ubicación donde aparece % en la cadena de formato. La propiedad [PercentSymbol](xref:System.Globalization.NumberFormatInfo.PercentSymbol) del objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) actual define el carácter de porcentaje empleado.

En el ejemplo siguiente se definen varias cadenas de formato personalizado que incluyen el especificador personalizado "%".

```csharp
double value = .086;
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value));
// Displays 8.6%     
```

```vb
Dim value As Double = .086
Console.WriteLine(value.ToString("#0.##%", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:#0.##%}", value))
' Displays 8.6% 
```

## <a name="the-custom-specifier"></a>El especificador personalizado "‰"

Un carácter de "por mil" (‰ o \u2030) en una cadena de formato hace que un número se multiplique por 1000 antes de darle formato. El símbolo de "por mil" adecuado se inserta en la cadena devuelta, en la ubicación de la cadena de formato en la que aparece el símbolo ‰. La propiedad [NumberFormatInfo.PerMilleSymbol](xref:System.Globalization.NumberFormatInfo.PerMilleSymbol) del objeto que proporciona la información de formato específica de la referencia cultural es la que determina el carácter de "por mil" que se usa.

En el ejemplo siguiente se define una cadena de formato personalizado que incluye el especificador personalizado "‰".

```csharp
double value = .00354;
string perMilleFmt = "#0.## " + '\u2030';
Console.WriteLine(value.ToString(perMilleFmt, CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:" + perMilleFmt + "}", value));
// Displays 3.54‰   
```

```vb
Dim value As Double = .00354
Dim perMilleFmt As String = "#0.## " & ChrW(&h2030)
Console.WriteLine(value.ToString(perMilleFmt, CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:" + perMilleFmt + "}", value))
' Displays 3.54 ‰
```

## <a name="the-e-and-e-custom-specifiers"></a>Los especificadores personalizados "E" y "e"

Si alguna de las cadenas "E", "E+", "E-", "e", "e+", o "e-" está presente en la cadena de formato y va seguida inmediatamente de al menos un cero, se da formato al número mediante notación científica con una 'E' o una 'e' insertadas entre el número y el exponente. El número de ceros que hay a continuación del indicador de notación científica determina el número mínimo de dígitos para el exponente. Los formatos 'E+' y 'e+' indican que un signo más o un signo menos debe preceder siempre al exponente. Los formatos 'E', 'E-', 'e' o 'e-' indican que un carácter de signo debe preceder solo a exponentes negativos.

En el ejemplo siguiente se da formato a varios valores numéricos utilizando los especificadores de notación científica.

```csharp
double value = 86000;
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+0}", value));
// Displays 8.6E+4

Console.WriteLine(value.ToString("0.###E+000", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+000}", value));
// Displays 8.6E+004

Console.WriteLine(value.ToString("0.###E-000", CultureInfo.InvariantCulture));
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E-000}", value));
// Displays 8.6E004
```

```vb
Dim value As Double = 86000
Console.WriteLine(value.ToString("0.###E+0", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+0}", value))
' Displays 8.6E+4

Console.WriteLine(value.ToString("0.###E+000", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E+000}", value))
' Displays 8.6E+004

Console.WriteLine(value.ToString("0.###E-000", CultureInfo.InvariantCulture))
Console.WriteLine(String.Format(CultureInfo.InvariantCulture, 
                                "{0:0.###E-000}", value))
' Displays 8.6E004
```

## <a name="the-escape-character"></a>El carácter de escape "\"

Los símbolos "#", "0", ".", ",", "%" y "‰" en una cadena de formato se interpretan como especificadores de formato en lugar de como caracteres literales. Dependiendo de su posición en una cadena de formato personalizado, la "E" en mayúsculas y minúsculas así como los símbolos + y - también se pueden interpretar como especificadores de formato. 

Para evitar que un carácter se interprete como un especificador de formato, puede precederlo con una barra diagonal inversa, que es el carácter de escape. El carácter de escape significa que el siguiente carácter es un carácter literal que se debe incluir en la cadena de resultado sin modificar.

Para incluir una barra diagonal inversa en una cadena de resultado, debe indicar su secuencia de escape con otra barra diagonal inversa (\\). 

> [!NOTE]
> Algunos compiladores, como el compilador de C#, también pueden interpretar un único carácter de barra diagonal inversa como un carácter de escape. Para asegurarse de que una cadena se interpreta correctamente al darle formato, puede usar el carácter literal de cadena textual (el carácter @) antes de la cadena en C# o puede agregar otro carácter de barra diagonal inversa delante de cada barra diagonal inversa. En el siguiente ejemplo de C# se muestran ambos enfoques.

En el ejemplo siguiente se usa el carácter de escape para evitar que la operación de formato interprete los caracteres "#", "0" y "\" como caracteres de escape o especificadores de formato. En el ejemplo se usa una barra diagonal inversa adicional para asegurarse de que una barra diagonal inversa se interprete como un carácter literal.

```csharp
int value = 123;
Console.WriteLine(value.ToString("\\#\\#\\# ##0 dollars and \\0\\0 cents \\#\\#\\#"));
Console.WriteLine(String.Format("{0:\\#\\#\\# ##0 dollars and \\0\\0 cents \\#\\#\\#}",
                                value));
// Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString(xref:"\#\#\# ##0 dollars and \0\0 cents \#\#\#"));
Console.WriteLine(String.Format(xref:"{0:\#\#\# ##0 dollars and \0\0 cents \#\#\#}",
                                value));
// Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString("\\\\\\\\\\\\ ##0 dollars and \\0\\0 cents \\\\\\\\\\\\"));
Console.WriteLine(String.Format("{0:\\\\\\\\\\\\ ##0 dollars and \\0\\0 cents \\\\\\\\\\\\}",
                                value));
// Displays \\\ 123 dollars and 00 cents \\\

Console.WriteLine(value.ToString(xref:"\\\\\\ ##0 dollars and \0\0 cents \\\\\\"));
Console.WriteLine(String.Format(xref:"{0:\\\\\\ ##0 dollars and \0\0 cents \\\\\\}",
                                value));
// Displays \\\ 123 dollars and 00 cents \\\
```

```vb
Dim value As Integer = 123
Console.WriteLine(value.ToString("\#\#\# ##0 dollars and \0\0 cents \#\#\#"))
Console.WriteLine(String.Format("{0:\#\#\# ##0 dollars and \0\0 cents \#\#\#}", 
                                value))
' Displays ### 123 dollars and 00 cents ###

Console.WriteLine(value.ToString("\\\\\\ ##0 dollars and \0\0 cents \\\\\\"))
Console.WriteLine(String.Format("{0:\\\\\\ ##0 dollars and \0\0 cents \\\\\\}", 
                                value))
' Displays \\\ 123 dollars and 00 cents \\\
```

## <a name="the-section-separator"></a>El separador de secciones ";"

El punto y coma (;) es un especificador de formato condicional que aplica distinto formato a un número dependiendo de si su valor es positivo, negativo o cero. Para generar este comportamiento, una cadena de formato personalizado puede contener hasta tres secciones separadas por signos de punto y coma. Estas secciones se describen en la siguiente tabla. 

Número de secciones | Descripción
------------------ | -----------
Una sección | La cadena de formato se aplica a todos los valores.
Dos secciones | La primera sección se aplica a valores positivos y ceros, y la segunda, sólo a valores negativos. Si el número al que se va a dar formato es negativo, pero se convierte en cero después de redondearlo según el formato de la segunda sección, se da formato al cero resultante según la primera sección.
Tres secciones. | La primera sección se aplica a valores positivos y ceros, la segunda, sólo a valores negativos, y la tercera, a ceros. La segunda sección se puede dejar vacía (no dejando nada entre los signos de punto y coma) y, en ese caso, la primera sección se aplica a los valores distintos de cero. Si el número al que se va a dar formato es distinto de cero, pero se convierte en cero después de redondearlo según el formato de la primera o la segunda sección, se da formato al cero resultante según la tercera sección.

Los separadores de sección omiten cualquier formato preexistente asociado a un número al dar formato al valor final. Por ejemplo, los valores negativos se muestran siempre con signo menos cuando se utilizan separadores de sección. Si se desea que el valor con formato final tenga un signo menos, debe incluir explícitamente el signo menos como parte del especificador de formato personalizado. 

En el ejemplo siguiente se usa el especificador de formato ";" para aplicar un formato diferente a los números positivos, negativos y cero.

```csharp
double posValue = 1234;
double negValue = -1234;
double zeroValue = 0;

string fmt2 = "##;(##)";
string fmt3 = "##;(##);**Zero**";

Console.WriteLine(posValue.ToString(fmt2));  
Console.WriteLine(String.Format("{0:" + fmt2 + "}", posValue));    
// Displays 1234

Console.WriteLine(negValue.ToString(fmt2));  
Console.WriteLine(String.Format("{0:" + fmt2 + "}", negValue));    
// Displays (1234)

Console.WriteLine(zeroValue.ToString(fmt3)); 
Console.WriteLine(String.Format("{0:" + fmt3 + "}", zeroValue));
// Displays **Zero**
```

```vb
Dim posValue As Double = 1234
Dim negValue As Double = -1234
Dim zeroValue As Double = 0

Dim fmt2 As String = "##;(##)"
Dim fmt3 As String = "##;(##);**Zero**"

Console.WriteLine(posValue.ToString(fmt2))   
Console.WriteLine(String.Format("{0:" + fmt2 + "}", posValue))    
' Displays 1234

Console.WriteLine(negValue.ToString(fmt2))   
Console.WriteLine(String.Format("{0:" + fmt2 + "}", negValue))    
' Displays (1234)

Console.WriteLine(zeroValue.ToString(fmt3))  
Console.WriteLine(String.Format("{0:" + fmt3 + "}", zeroValue))
' Displays **Zero**
```

## <a name="notes"></a>Notas

### <a name="floatingpoint-infinities-and-nan"></a>Infinitos de punto flotante y NaN

Independientemente de la cadena de formato, si el valor de un tipo de punto flotante [Single](xref:System.Single) o [Double](xref:System.Double) es infinito positivo, infinito negativo o NaN (Not a Number, no es un número), la cadena con formato será el valor de la propiedad [PositiveInfinitySymbol](xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol), [NegativeInfinitySymbol](xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol) o [NaNSymbol](xref:System.Globalization.NumberFormatInfo.NaNSymbol) respectiva especificada por el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) aplicable actualmente. 

### <a name="rounding-and-fixedpoint-format-strings"></a>Cadenas de formato de punto fijo y redondeo

Para las cadenas de formato de punto fijo (es decir, las cadenas de formato que no contienen caracteres de formato de notación científica), los números se redondean hasta tantos decimales como marcadores de posición de dígitos haya a la derecha del separador decimal. Si la cadena de formato no contiene ningún separador decimal, el número se redondea al entero más próximo. Si el número tiene más dígitos que marcadores de posición de dígitos a la izquierda del separador decimal, los dígitos adicionales se copian en la cadena de resultado justo antes del primer marcador de posición de dígitos.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestran dos cadenas de formato numérico personalizado. En ambos casos, el marcador de posición de dígitos (#) muestra los datos numéricos, y todos los demás caracteres se copian en la cadena de resultado.

```csharp
double number1 = 1234567890;
string value1 = number1.ToString("(###) ###-####");
Console.WriteLine(value1);

int number2 = 42;
string value2 = number2.ToString("My Number = #");
Console.WriteLine(value2);
// The example displays the following output:
//       (123) 456-7890
//       My Number = 42
```

```vb
Dim number1 As Double = 1234567890
Dim value1 As String = number1.ToString("(###) ###-####")
Console.WriteLine(value1)

Dim number2 As Integer = 42
Dim value2 As String = number2.ToString("My Number = #")
Console.WriteLine(value2)
' The example displays the following output:
'       (123) 456-7890
'       My Number = 42
```

## <a name="see-also"></a>Vea también

[System.Globalization.NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)

[Aplicar formato a tipos](formatting-types.md)

[Cadenas con formato numérico estándar](standard-numeric.md)

[Cómo: Rellenar un número con ceros a la izquierda](pad-number.md)

[Formatos compuestos](composite-format.md)




<!--HONumber=Nov16_HO3-->


