---
title: "Cómo: Rellenar un número con ceros a la izquierda"
description: "Cómo rellenar un número con ceros a la izquierda"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: a517c066-b11e-4815-826b-9262611eac40
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 0a136d88dfbc83d40ff8a204f275537c24f9748b

---

# <a name="how-to-pad-a-number-with-leading-zeros"></a>Cómo: Rellenar un número con ceros a la izquierda

Si quiere agregar ceros a la izquierda de un entero, puede hacerlo mediante la [cadena de formato numérico estándar](standard-numeric.md) "D" con un especificador de precisión. Para agregar ceros a la izquierda tanto de enteros como de números de punto flotante, use una [cadena de formato numérico personalizada](custom-numeric.md). En este tema se explica cómo usar ambos métodos para rellenar un número con ceros a la izquierda.

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>Para rellenar un entero con ceros a la izquierda hasta una longitud concreta

1. Determine el número mínimo de dígitos que desea que muestre el valor entero. Incluya los dígitos a la izquierda en este número.

2. Determine si desea mostrar el entero como valor decimal o hexadecimal.

    * Para mostrar el entero como valor decimal, llame a su método `ToString(String)` y pase la cadena "D*n*" como valor del parámetro format, donde *n* representa la longitud mínima de la cadena.
    
    * Para mostrar el entero como valor hexadecimal, llame a su método `ToString(String)` y pase la cadena "X*n*" como valor del parámetro format, donde *n* representa la longitud mínima de la cadena.
    
  También puede usar la cadena de formato en un método como [Console.WriteLine](xref:System.Console.WriteLine) o [String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)), que usan [formato compuesto](composite-format.md).  
  
En el ejemplo siguiente se aplica formato a varios valores enteros con ceros a la izquierda de modo que la longitud mínima total del número con formato sea de ocho caracteres.

```csharp
byte byteValue = 254;
short shortValue = 10342;
int intValue = 1023983;
long lngValue = 6985321;               
ulong ulngValue = UInt64.MaxValue;

// Display integer values by calling the ToString method.
Console.WriteLine("{0,22} {1,22}", byteValue.ToString("D8"), byteValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", shortValue.ToString("D8"), shortValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", intValue.ToString("D8"), intValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", lngValue.ToString("D8"), lngValue.ToString("X8"));
Console.WriteLine("{0,22} {1,22}", ulngValue.ToString("D8"), ulngValue.ToString("X8"));
Console.WriteLine();

// Display the same integer values by using composite formatting.
Console.WriteLine("{0,22:D8} {0,22:X8}", byteValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", shortValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", intValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", lngValue);
Console.WriteLine("{0,22:D8} {0,22:X8}", ulngValue);
// The example displays the following output:
//                     00000254               000000FE
//                     00010342               00002866
//                     01023983               000F9FEF
//                     06985321               006A9669
//         18446744073709551615       FFFFFFFFFFFFFFFF
//       
//                     00000254               000000FE
//                     00010342               00002866
//                     01023983               000F9FEF
//                     06985321               006A9669
//         18446744073709551615       FFFFFFFFFFFFFFFF
//         18446744073709551615       FFFFFFFFFFFFFFFF
```

```vb
Dim byteValue As Byte = 254
Dim shortValue As Short = 10342
Dim intValue As Integer = 1023983
Dim lngValue As Long = 6985321               
Dim ulngValue As ULong = UInt64.MaxValue

' Display integer values by calling the ToString method.
Console.WriteLine("{0,22} {1,22}", byteValue.ToString("D8"), byteValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", shortValue.ToString("D8"), shortValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", intValue.ToString("D8"), intValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", lngValue.ToString("D8"), lngValue.ToString("X8"))
Console.WriteLine("{0,22} {1,22}", ulngValue.ToString("D8"), ulngValue.ToString("X8"))
Console.WriteLine()

' Display the same integer values by using composite formatting.
Console.WriteLine("{0,22:D8} {0,22:X8}", byteValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", shortValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", intValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", lngValue)
Console.WriteLine("{0,22:D8} {0,22:X8}", ulngValue)
' The example displays the following output:
'                     00000254               000000FE
'                     00010342               00002866
'                     01023983               000F9FEF
'                     06985321               006A9669
'         18446744073709551615       FFFFFFFFFFFFFFFF
'       
'                     00000254               000000FE
'                     00010342               00002866
'                     01023983               000F9FEF
'                     06985321               006A9669
'         18446744073709551615       FFFFFFFFFFFFFFFF
```

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>Para rellenar un entero con una determinada cantidad de ceros a la izquierda

1. Determine cuántos ceros a la izquierda desea que muestre el valor entero.

2. Determine si desea mostrar el entero como valor decimal o hexadecimal. Para aplicar el formato de valor decimal hay que usar el especificador de formato estándar “D”, mientras que para el valor hexadecimal hay que usar el especificador de formato estándar “X”.

3. Determine la longitud de la cadena numérica sin rellenar mediante una llamada a los métodos `ToString("D").Length` o `ToString("X").Length` del valor entero. 

4. Agregue el número de ceros a la izquierda que desea incluir en la cadena con formato a la longitud de la cadena numérica sin rellenar. Esto define la longitud total de la cadena rellenada.

5. Llame al método `ToString(String)` del valor entero y pase la cadena "D*n*" para cadenas decimales y "X*n*" para cadenas hexadecimales, donde *n* representa la longitud total de la cadena rellenada. También puede usar la cadena de formato "D*n*" o "X*n*" en un método que admita formato compuesto.

En el ejemplo siguiente se rellena un valor entero con cinco ceros a la izquierda.

```csharp
int value = 160934;
int decimalLength = value.ToString("D").Length + 5;
int hexLength = value.ToString("X").Length + 5;
Console.WriteLine(value.ToString("D" + decimalLength.ToString()));
Console.WriteLine(value.ToString("X" + hexLength.ToString()));
// The example displays the following output:
//       00000160934
//       00000274A6
```

```vb
Dim value As Integer = 160934
Dim decimalLength As Integer = value.ToString("D").Length + 5
Dim hexLength As Integer = value.ToString("X").Length + 5
Console.WriteLine(value.ToString("D" + decimalLength.ToString()))
Console.WriteLine(value.ToString("X" + hexLength.ToString()))
' The example displays the following output:
'       00000160934
'       00000274A6 
```

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>Para rellenar un valor numérico con ceros a la izquierda hasta una longitud concreta

1. Determine con cuántos dígitos a la izquierda del decimal desea que se represente la cadena del número. Incluya los ceros a la izquierda en este número total de dígitos.

2. Defina una cadena de formato numérico personalizado en la que se use el marcador de posición cero (“0”) para representar el número mínimo de ceros.

3. Llame al método `ToString(String)` del número y pase la cadena de formato personalizado. También puede usar la cadena de formato personalizado con un método que admita formato compuesto.

En el ejemplo siguiente se aplica formato a varios valores numéricos con ceros a la izquierda de modo que la longitud total del número con formato sea de al menos ocho dígitos a la izquierda del decimal.

```csharp
string fmt = "00000000.##";
int intValue = 1053240;
decimal decValue = 103932.52m;
float sngValue = 1549230.10873992f;
double dblValue = 9034521202.93217412;

// Display the numbers using the ToString method.
Console.WriteLine(intValue.ToString(fmt));
Console.WriteLine(decValue.ToString(fmt));           
Console.WriteLine(sngValue.ToString(fmt));
Console.WriteLine(dblValue.ToString(fmt));           
Console.WriteLine();

// Display the numbers using composite formatting.
string formatString = " {0,15:" + fmt + "}";
Console.WriteLine(formatString, intValue);      
Console.WriteLine(formatString, decValue);      
Console.WriteLine(formatString, sngValue);      
Console.WriteLine(formatString, dblValue);      
// The example displays the following output:
//       01053240
//       00103932.52
//       01549230
//       9034521202.93
//       
//               01053240
//            00103932.52
//               01549230
//          9034521202.93  
```

```vb
Dim fmt As String = "00000000.##"
Dim intValue As Integer = 1053240
Dim decValue As Decimal = 103932.52d
Dim sngValue As Single = 1549230.10873992
Dim dblValue As Double = 9034521202.93217412

' Display the numbers using the ToString method.
Console.WriteLine(intValue.ToString(fmt))
Console.WriteLine(decValue.ToString(fmt))            
Console.WriteLine(sngValue.ToString(fmt))
Console.WriteLine(dblValue.ToString(fmt))            
Console.WriteLine()

' Display the numbers using composite formatting.
Dim formatString As String = " {0,15:" + fmt + "}"
Console.WriteLine(formatString, intValue)      
Console.WriteLine(formatString, decValue)      
Console.WriteLine(formatString, sngValue)      
Console.WriteLine(formatString, dblValue)      
' The example displays the following output:
'       01053240
'       00103932.52
'       01549230
'       9034521202.93
'       
'               01053240
'            00103932.52
'               01549230
'          9034521202.93
```

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>Para rellenar un valor numérico con una determinada cantidad de ceros a la izquierda

1. Determine cuántos ceros a la izquierda desea que tenga el valor numérico.

2. Determine el número de dígitos a la izquierda del decimal que tendrá la cadena numérica sin rellenar. Para hacerlo:

    a. Determine si la representación de cadena de un número incluye un símbolo de separador decimal.
    
    b. Si incluye un símbolo de separador decimal, determine el número de caracteres a la izquierda del separador decimal.       
    
    O bien
       
    Si no incluye un símbolo de separador decimal, determine la longitud de la cadena. 
       
3. Cree una cadena de formato personalizado en la que se use el marcador de posición cero (“0”) para cada uno de los ceros a la izquierda que aparecen en la cadena, y en la que se use también el marcador de posición cero o el marcador de posición de dígitos (“#”) para representar cada uno de los dígitos de la cadena predeterminada. 

4. Proporcione la cadena de formato personalizado como un parámetro bien al método ToString(String) del número, bien a un método que admita el formato compuesto.

En el ejemplo siguiente se rellenan dos valores [Double](xref:System.Double) con cinco ceros a la izquierda.

```csharp
double[] dblValues = { 9034521202.93217412, 9034521202 };
foreach (double dblValue in dblValues)
{
   string decSeparator = System.Globalization.NumberFormatInfo.CurrentInfo.NumberDecimalSeparator;
   string fmt, formatString;

   if (dblValue.ToString().Contains(decSeparator))
   {
      int digits = dblValue.ToString().IndexOf(decSeparator);
      fmt = new String('0', 5) + new String('#', digits) + ".##";
   }
   else
   {
      fmt = new String('0', dblValue.ToString().Length);   
   }
   formatString = "{0,20:" + fmt + "}";

   Console.WriteLine(dblValue.ToString(fmt));
   Console.WriteLine(formatString, dblValue);
}
// The example displays the following output:
//       000009034521202.93
//         000009034521202.93
//       9034521202
//                 9034521202 
```

```vb
Dim dblValues() As Double = { 9034521202.93217412, 9034521202 }
For Each dblValue As Double In dblValues
   Dim decSeparator As String = System.Globalization.NumberFormatInfo.CurrentInfo.NumberDecimalSeparator
   Dim fmt, formatString As String

   If dblValue.ToString.Contains(decSeparator) Then
      Dim digits As Integer = dblValue.ToString().IndexOf(decSeparator)
      fmt = New String("0"c, 5) + New String("#"c, digits) + ".##"
   Else
      fmt = New String("0"c, dblValue.ToString.Length)   
   End If
   formatString = "{0,20:" + fmt + "}"

   Console.WriteLine(dblValue.ToString(fmt))
   Console.WriteLine(formatString, dblValue)
Next
' The example displays the following output:
'       000009034521202.93
'         000009034521202.93
'       9034521202
'                 9034521202
```

## <a name="see-also"></a>Vea también

[Cadenas con formato numérico estándar](standard-numeric.md)

[Cadenas con formato numérico personalizado](custom-numeric.md)

[Formatos compuestos](composite-format.md)




<!--HONumber=Nov16_HO3-->


