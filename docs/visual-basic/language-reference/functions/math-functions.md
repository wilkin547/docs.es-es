---
title: Funciones matemáticas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- math functions, Visual Basic
- arithmetic operations, math functions
- math routines
- Atn function
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
ms.openlocfilehash: da0b612feb5b9a479d50f52cf65e38007ab3b196
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44360445"
---
# <a name="math-functions-visual-basic"></a>Funciones matemáticas (Visual Basic)
Los métodos de la <xref:System.Math?displayProperty=nameWithType> clase proporcionar operaciones trigonométricas, logarítmicas y otras funciones matemáticas comunes.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se enumera los métodos de la <xref:System.Math?displayProperty=nameWithType> clase. Puede usar estas opciones en un programa de Visual Basic.  
  
|Método de .NET|Descripción|  
|---------------------------|-----------------|  
|<xref:System.Math.Abs%2A>|Devuelve el valor absoluto de un número.|  
|<xref:System.Math.Acos%2A>|Devuelve el ángulo cuyo coseno es el número especificado.|  
|<xref:System.Math.Asin%2A>|Devuelve el ángulo cuyo seno es el número especificado.|  
|<xref:System.Math.Atan%2A>|Devuelve el ángulo cuya tangente corresponde al número especificado.|  
|<xref:System.Math.Atan2%2A>|Devuelve el ángulo cuya tangente es el cociente de dos números especificados.|  
|<xref:System.Math.BigMul%2A>|Devuelve el producto completo de dos números de 32 bits.|  
|<xref:System.Math.Ceiling%2A>|Devuelve el valor integral más pequeño que es mayor o igual que el especificado `Decimal` o `Double`.|  
|<xref:System.Math.Cos%2A>|Devuelve el coseno del ángulo especificado.|  
|<xref:System.Math.Cosh%2A>|Devuelve el coseno hiperbólico del ángulo especificado.|  
|<xref:System.Math.DivRem%2A>|Devuelve el cociente de dos enteros con signo de 32 bits o 64 bits y también devuelve el resto en un parámetro de salida.|  
|<xref:System.Math.Exp%2A>|Devuelve e (la base de los logaritmos naturales) elevado a la potencia especificada.|  
|<xref:System.Math.Floor%2A>|Devuelve el entero más grande que sea menor o igual que el especificado `Decimal` o `Double` número.|  
|<xref:System.Math.IEEERemainder%2A>|Devuelve el resto resultante de la división de un número especificado por otro número especificado.|  
|<xref:System.Math.Log%2A>|Devuelve el logaritmo natural (base e) de un número especificado o bien el logaritmo de un número especificado en una base especificada.|  
|<xref:System.Math.Log10%2A>|Devuelve el logaritmo en base 10 de un número especificado.|  
|<xref:System.Math.Max%2A>|Devuelve el mayor de dos números.|  
|<xref:System.Math.Min%2A>|Devuelve el menor de dos números.|  
|<xref:System.Math.Pow%2A>|Devuelve un número especificado elevado a la potencia especificada.|  
|<xref:System.Math.Round%2A>|Devuelve un `Decimal` o `Double` valor se redondea al valor entero más próximo o a un número especificado de dígitos fraccionarios.|  
|<xref:System.Math.Sign%2A>|Devuelve un `Integer` valor que indica el signo de un número.|  
|<xref:System.Math.Sin%2A>|Devuelve el seno del ángulo especificado.|  
|<xref:System.Math.Sinh%2A>|Devuelve el seno hiperbólico del ángulo especificado.|  
|<xref:System.Math.Sqrt%2A>|Devuelve la raíz cuadrada de un número especificado.|  
|<xref:System.Math.Tan%2A>|Devuelve la tangente del ángulo especificado.|  
|<xref:System.Math.Tanh%2A>|Devuelve la tangente hiperbólica del ángulo especificado.|  
|<xref:System.Math.Truncate%2A>|Calcula la parte entera de un `Decimal` o `Double` número.|  
  
 Para utilizar estas funciones sin calificación, importe el <xref:System.Math?displayProperty=nameWithType> espacio de nombres en el proyecto, agregue el código siguiente a la parte superior del archivo de origen:  
  
```vb
Imports System.Math  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Abs%2A> método de la <xref:System.Math> clase para calcular el valor absoluto de un número.  
  
```vb
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Atan%2A> método de la <xref:System.Math> clase para calcular el valor de pi.  
  
```vb
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Cos%2A> método de la <xref:System.Math> clase para devolver el coseno de un ángulo.  
  
```vb
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Exp%2A> método de la <xref:System.Math> clase para devolver e elevado a una potencia.  
  
```vb
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Log%2A> método de la <xref:System.Math> clase para devolver el logaritmo natural de un número.  
  
```vb
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Round%2A> método de la <xref:System.Math> clase para redondear un número entero más cercano.  
  
```vb
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Sign%2A> método de la <xref:System.Math> clase para determinar el signo de un número.  
  
```vb
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Sin%2A> método de la <xref:System.Math> clase para devolver el seno de un ángulo.  
  
```vb
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Sqrt%2A> método de la <xref:System.Math> clase para calcular la raíz cuadrada de un número.  
  
```vb
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el <xref:System.Math.Tan%2A> método de la <xref:System.Math> clase para devolver la tangente de un ángulo.  
  
```vb
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## <a name="requirements"></a>Requisitos  
 **Clase:** <xref:System.Math>  
  
 **Namespace:** <xref:System>  
  
 **Ensamblado:** mscorlib (en mscorlib.dll)  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>  
 <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>  
 <xref:System.Double.NaN>  
 [Funciones matemáticas derivadas](../../../visual-basic/language-reference/keywords/derived-math-functions.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
