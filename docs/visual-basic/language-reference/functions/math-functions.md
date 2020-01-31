---
title: Funciones matemáticas
ms.date: 01/27/2020
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: ea30ae3b30484c1a13d6d540f121c03afb30ba26
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794595"
---
# <a name="math-functions-visual-basic"></a>Funciones matemáticas (Visual Basic)

Los métodos de la clase <xref:System.Math?displayProperty=nameWithType> proporcionan funciones trigonométricas, logarítmicas y otras funciones matemáticas comunes.

## <a name="remarks"></a>Notas

En la tabla siguiente se enumeran los métodos de la clase <xref:System.Math?displayProperty=nameWithType>. Puede usarlos en un programa de Visual Basic:
  
|Método .NET|Descripción|
|---------------------------|-----------------|
|<xref:System.Math.Abs%2A>|Devuelve el valor absoluto de un número.|
|<xref:System.Math.Acos%2A>|Devuelve el ángulo cuyo coseno es el número especificado.|
|<xref:System.Math.Asin%2A>|Devuelve el ángulo cuyo seno es el número especificado.|
|<xref:System.Math.Atan%2A>|Devuelve el ángulo cuya tangente corresponde al número especificado.|
|<xref:System.Math.Atan2%2A>|Devuelve el ángulo cuya tangente es el cociente de dos números especificados.|
|<xref:System.Math.BigMul%2A>|Devuelve el producto completo de números de 2 32 bits.|
|<xref:System.Math.Ceiling%2A>|Devuelve el valor integral más pequeño que es mayor o igual que el `Decimal` o `Double`especificado.|
|<xref:System.Math.Cos%2A>|Devuelve el coseno del ángulo especificado.|
|<xref:System.Math.Cosh%2A>|Devuelve el coseno hiperbólico del ángulo especificado.|
|<xref:System.Math.DivRem%2A>|Devuelve el cociente de los enteros con signo de 2 32 bits o 64 bits y también devuelve el resto en un parámetro de salida.|
|<xref:System.Math.Exp%2A>|Devuelve e (la base de los logaritmos naturales) elevado a la potencia especificada.|
|<xref:System.Math.Floor%2A>|Devuelve el entero más grande que es menor o igual que el `Decimal` o el número de `Double` especificados.|
|<xref:System.Math.IEEERemainder%2A>|Devuelve el resto que es el resultado de la división de un número especificado por otro número especificado.|
|<xref:System.Math.Log%2A>|Devuelve el logaritmo natural (base e) de un número especificado o el logaritmo de un número especificado en una base especificada.|
|<xref:System.Math.Log10%2A>|Devuelve el logaritmo en base 10 de un número especificado.|
|<xref:System.Math.Max%2A>|Devuelve el mayor de dos números.|
|<xref:System.Math.Min%2A>|Devuelve el menor de dos números.|
|<xref:System.Math.Pow%2A>|Devuelve un número especificado elevado a la potencia especificada.|
|<xref:System.Math.Round%2A>|Devuelve un valor `Decimal` o `Double` redondeado al valor entero más próximo o a un número especificado de dígitos fraccionarios.|
|<xref:System.Math.Sign%2A>|Devuelve un valor `Integer` que indica el signo de un número.|
|<xref:System.Math.Sin%2A>|Devuelve el seno del ángulo especificado.|
|<xref:System.Math.Sinh%2A>|Devuelve el seno hiperbólico del ángulo especificado.|
|<xref:System.Math.Sqrt%2A>|Devuelve la raíz cuadrada de un número especificado.|
|<xref:System.Math.Tan%2A>|Devuelve la tangente del ángulo especificado.|
|<xref:System.Math.Tanh%2A>|Devuelve la tangente hiperbólica del ángulo especificado.|
|<xref:System.Math.Truncate%2A>|Calcula la parte entera de una `Decimal` o un número de `Double` especificados.|

En la tabla siguiente se enumeran los métodos de la clase <xref:System.Math?displayProperty=nameWithType> que no existen en .NET Framework pero que se agregan en .NET Standard o .NET Core:

|Método .NET|Descripción|Disponible en|
|---------------------------|-----------------|-----------|
|<xref:System.Math.Acosh%2A>|Devuelve el ángulo cuyo coseno hiperbólico es el número especificado.|A partir de .NET Core 2,1 y .NET Standard 2,1|
|<xref:System.Math.Asinh%2A>|Devuelve el ángulo cuyo seno hiperbólico es el número especificado.|A partir de .NET Core 2,1 y .NET Standard 2,1|
|<xref:System.Math.Atanh%2A>|Devuelve el ángulo cuya tangente hiperbólica es el número especificado.|A partir de .NET Core 2,1 y .NET Standard 2,1|
|<xref:System.Math.BitDecrement%2A>|Devuelve el siguiente valor más pequeño menor que `x`.|A partir de .NET Core 3,0|
|<xref:System.Math.BitIncrement%2A>|Devuelve el siguiente valor más grande mayor que `x`.|A partir de .NET Core 3,0|
|<xref:System.Math.Cbrt%2A>|Devuelve la raíz cúbica de un número especificado.|A partir de .NET Core 2,1 y .NET Standard 2,1|
|<xref:System.Math.Clamp%2A>|Devuelve un elemento `value` fijado al rango inclusivo de `min` y `max`.|A partir de .NET Core 2,0 y .NET Standard 2,1|
|<xref:System.Math.CopySign%2A>|Devuelve un valor con la magnitud de `x` y el signo de `y`.|A partir de .NET Core 3,0|
|<xref:System.Math.FusedMultiplyAdd%2A>|Devuelve (x \* y) + z, redondeado como una operación ternaria.|A partir de .NET Core 3,0|
|<xref:System.Math.ILogB%2A>|Devuelve el logaritmo de entero en base 2 de un número especificado.|A partir de .NET Core 3,0|
|<xref:System.Math.Log2%2A>|Devuelve el logaritmo en base 2 de un número especificado.|A partir de .NET Core 3,0|
|<xref:System.Math.MaxMagnitude%2A>|Devuelve la magnitud mayor de dos números de punto flotante de precisión doble.|A partir de .NET Core 3,0|
|<xref:System.Math.MinMagnitude%2A>|Devuelve la magnitud menor de dos números de punto flotante de precisión doble.|A partir de .NET Core 3,0|
|<xref:System.Math.ScaleB%2A>|Devuelve la x \* 2 ^ n calculada de forma eficaz.|A partir de .NET Core 3,0|

Para usar estas funciones sin calificación, importe el espacio de nombres <xref:System.Math?displayProperty=nameWithType> en el proyecto agregando el código siguiente a la parte superior del archivo de código fuente:

```vb
Imports System.Math
```

## <a name="example---abs"></a>Ejemplo: ABS

En este ejemplo se usa el método <xref:System.Math.Abs%2A> de la clase <xref:System.Math> para calcular el valor absoluto de un número.

```vb
Dim x As Double = Math.Abs(50.3)
Dim y As Double = Math.Abs(-50.3)
Console.WriteLine(x)
Console.WriteLine(y)
' This example produces the following output:
' 50.3
' 50.3
```  

## <a name="example---atan"></a>Ejemplo: atan

En este ejemplo se usa el método <xref:System.Math.Atan%2A> de la clase <xref:System.Math> para calcular el valor de PI.

```vb
Public Function GetPi() As Double
    ' Calculate the value of pi.
    Return 4.0 * Math.Atan(1.0)
End Function
```

> [!NOTE]
> La clase <xref:System.Math?displayProperty=nameWithType> contiene <xref:System.Math.PI?displayProperty=nameWithType> campo constante. Puede utilizarlo en lugar de calcularlo.

## <a name="example---cos"></a>Ejemplo: cos

En este ejemplo se usa el método <xref:System.Math.Cos%2A> de la clase <xref:System.Math> para devolver el coseno de un ángulo.

```vb
Public Function Sec(angle As Double) As Double
    ' Calculate the secant of angle, in radians.
    Return 1.0 / Math.Cos(angle)
End Function
```

## <a name="example---exp"></a>Ejemplo: EXP

En este ejemplo se usa el método <xref:System.Math.Exp%2A> de la clase <xref:System.Math> para devolver e elevado a una potencia.

```vb
Public Function Sinh(angle As Double) As Double
    ' Calculate hyperbolic sine of an angle, in radians.
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0
End Function
```

## <a name="example---log"></a>Registro de ejemplo

En este ejemplo se usa el método <xref:System.Math.Log%2A> de la clase <xref:System.Math> para devolver el logaritmo natural de un número.

```vb
Public Function Asinh(value As Double) As Double
    ' Calculate inverse hyperbolic sine, in radians.
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))
End Function
```

## <a name="example---round"></a>Ejemplo: redondeo

En este ejemplo se usa el método <xref:System.Math.Round%2A> de la clase <xref:System.Math> para redondear un número al entero más próximo.

```vb
Dim myVar2 As Double = Math.Round(2.8)
Console.WriteLine(myVar2)
' The code produces the following output:
' 3
```

## <a name="example---sign"></a>Ejemplo: Sign

En este ejemplo se usa el método <xref:System.Math.Sign%2A> de la clase <xref:System.Math> para determinar el signo de un número.

```vb
Dim mySign1 As Integer = Math.Sign(12)
Dim mySign2 As Integer = Math.Sign(-2.4)
Dim mySign3 As Integer = Math.Sign(0)
Console.WriteLine(mySign1)
Console.WriteLine(mySign2)
Console.WriteLine(mySign3)
' The code produces the following output:
' 1
' -1
' 0
```

## <a name="example---sin"></a>Ejemplo: sin

En este ejemplo se usa el método <xref:System.Math.Sin%2A> de la clase <xref:System.Math> para devolver el seno de un ángulo.

```vb
Public Function Csc(angle As Double) As Double
    ' Calculate cosecant of an angle, in radians.
    Return 1.0 / Math.Sin(angle)
End Function
```

## <a name="example---sqrt"></a>Ejemplo: sqrt

En este ejemplo se usa el método <xref:System.Math.Sqrt%2A> de la clase <xref:System.Math> para calcular la raíz cuadrada de un número.

```vb
Dim mySqrt1 As Double = Math.Sqrt(4)
Dim mySqrt2 As Double = Math.Sqrt(23)
Dim mySqrt3 As Double = Math.Sqrt(0)
Dim mySqrt4 As Double = Math.Sqrt(-4)
Console.WriteLine(mySqrt1)
Console.WriteLine(mySqrt2)
Console.WriteLine(mySqrt3)
Console.WriteLine(mySqrt4)
' The code produces the following output:
' 2
' 4.79583152331272
' 0
' NaN
```

## <a name="example---tan"></a>Ejemplo: tan

En este ejemplo se usa el método <xref:System.Math.Tan%2A> de la clase <xref:System.Math> para devolver la tangente de un ángulo.

```vb
Public Function Ctan(angle As Double) As Double
    ' Calculate cotangent of an angle, in radians.
    Return 1.0 / Math.Tan(angle)
End Function
```

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>
- <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>
- <xref:System.Double.NaN>
- [Funciones matemáticas derivadas](../keywords/derived-math-functions.md)
- [Operadores aritméticos](../operators/arithmetic-operators.md)
