---
title: "Funciones matem&#225;ticas (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "funciones matemáticas, Visual Basic"
  - "operaciones aritméticas, funciones matemáticas"
  - "rutinas matemáticas"
  - "Atn (función)"
ms.assetid: 4d2d82e7-6924-42fe-a4a7-b4dd5bebbd0c
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Funciones matem&#225;ticas (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los métodos de la clase de <xref:System.Math?displayProperty=fullName> proporcionan funciones matemáticas trigonométricas, logarítmicas, y otras comunes.  
  
## Comentarios  
 La tabla siguiente se enumeran los métodos de la clase de <xref:System.Math?displayProperty=fullName>.  Puede usar estas en un programa de Visual Basic.  
  
|Método en .NET Framework|Descripción|  
|------------------------------|-----------------|  
|<xref:System.Math.Abs%2A>|Devuelve el valor absoluto de un número.|  
|<xref:System.Math.Acos%2A>|Devuelve el ángulo cuyo coseno es el número especificado.|  
|<xref:System.Math.Asin%2A>|Devuelve el ángulo cuyo seno es el número especificado.|  
|<xref:System.Math.Atan%2A>|Devuelve el ángulo cuya tangente corresponde al número especificado.|  
|<xref:System.Math.Atan2%2A>|Devuelve el ángulo cuya tangente es el cociente de dos números especificados.|  
|<xref:System.Math.BigMul%2A>|Devuelve el producto completo de dos números de 32 bits.|  
|<xref:System.Math.Ceiling%2A>|Devuelve el valor entero más pequeño que es mayor o igual `Decimal` especificado o `Double`.|  
|<xref:System.Math.Cos%2A>|Devuelve el coseno del ángulo especificado.|  
|<xref:System.Math.Cosh%2A>|Devuelve el coseno hiperbólico del ángulo especificado.|  
|<xref:System.Math.DivRem%2A>|Devuelve el cociente de dos de 32 bits o de enteros con signo de 64 bits, y también devuelve el resto de un parámetro de salida.|  
|<xref:System.Math.Exp%2A>|Devuelve e \(base de los logaritmos naturales\) se produce a la potencia especificado.|  
|<xref:System.Math.Floor%2A>|Devuelve el entero más grande que sea menor o igual que `Decimal` o el número especificado de `Double`.|  
|<xref:System.Math.IEEERemainder%2A>|Devuelve el resto que es el resultado de la división de un número especificado por otro número especificado.|  
|<xref:System.Math.Log%2A>|Devuelve el logaritmo natural \(de e base\) de un número especificado o el logaritmo de un número especificado en una base especificada.|  
|<xref:System.Math.Log10%2A>|Devuelve el logaritmo en base 10 de un número especificado.|  
|<xref:System.Math.Max%2A>|Devuelve el mayor de dos números.|  
|<xref:System.Math.Min%2A>|Devuelve el menor de dos números.|  
|<xref:System.Math.Pow%2A>|Devuelve un número especificado elevado a la potencia especificada.|  
|<xref:System.Math.Round%2A>|Devuelve un valor de `Decimal` o de `Double` redondeado al valor entero más cercano o a un número especificado de dígitos fraccionarios.|  
|<xref:System.Math.Sign%2A>|Devuelve un valor `Integer` que indica el signo de un número.|  
|<xref:System.Math.Sin%2A>|Devuelve el seno del ángulo especificado.|  
|<xref:System.Math.Sinh%2A>|Devuelve el seno hiperbólico del ángulo especificado.|  
|<xref:System.Math.Sqrt%2A>|Devuelve la raíz cuadrada de un número especificado.|  
|<xref:System.Math.Tan%2A>|Devuelve la tangente del ángulo especificado.|  
|<xref:System.Math.Tanh%2A>|Devuelve la tangente hiperbólica del ángulo especificado.|  
|<xref:System.Math.Truncate%2A>|Calcula la parte entera de `Decimal` o un número especificado de `Double`.|  
  
 Para utilizar estas funciones sin calificación, importe el espacio de nombres <xref:System.Math?displayProperty=fullName> en el proyecto agregando el código siguiente en la parte superior del archivo de código fuente:  
  
```  
Imports System.Math  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Abs%2A> de la clase <xref:System.Math> para calcular el valor absoluto de un número.  
  
```  
' Returns 50.3.  
Dim MyNumber1 As Double = Math.Abs(50.3)  
' Returns 50.3.  
Dim MyNumber2 As Double = Math.Abs(-50.3)  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Atan%2A> de la clase <xref:System.Math> para calcular el valor de pi.  
  
```  
Public Function GetPi() As Double  
    ' Calculate the value of pi.  
    Return 4.0 * Math.Atan(1.0)  
End Function  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Cos%2A> de la clase <xref:System.Math> para devolver el coseno de un ángulo.  
  
```  
Public Function Sec(ByVal angle As Double) As Double  
    ' Calculate the secant of angle, in radians.  
    Return 1.0 / Math.Cos(angle)  
End Function  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Exp%2A> de la clase <xref:System.Math> para devolver e elevado a una potencia.  
  
```  
Public Function Sinh(ByVal angle As Double) As Double  
    ' Calculate hyperbolic sine of an angle, in radians.  
    Return (Math.Exp(angle) - Math.Exp(-angle)) / 2.0  
End Function  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Log%2A> de la clase <xref:System.Math> para devolver el logaritmo natural de un número.  
  
```  
Public Function Asinh(ByVal value As Double) As Double  
    ' Calculate inverse hyperbolic sine, in radians.  
    Return Math.Log(value + Math.Sqrt(value * value + 1.0))  
End Function  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Round%2A> de la clase <xref:System.Math> para redondear un número al entero más próximo.  
  
```  
' Returns 3.  
Dim MyVar2 As Double = Math.Round(2.8)  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Sign%2A> de la clase <xref:System.Math> para determinar el signo de un número.  
  
```  
' Returns 1.  
Dim MySign1 As Integer = Math.Sign(12)  
' Returns -1.  
Dim MySign2 As Integer = Math.Sign(-2.4)  
' Returns 0.  
Dim MySign3 As Integer = Math.Sign(0)  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Sin%2A> de la clase <xref:System.Math> para devolver el seno de un ángulo.  
  
```  
Public Function Csc(ByVal angle As Double) As Double  
    ' Calculate cosecant of an angle, in radians.  
    Return 1.0 / Math.Sin(angle)  
End Function  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Sqrt%2A> de la clase <xref:System.Math> para calcular la raíz cuadrada de un número.  
  
```  
' Returns 2.  
Dim MySqr1 As Double = Math.Sqrt(4)  
' Returns 4.79583152331272.  
Dim MySqr2 As Double = Math.Sqrt(23)  
' Returns 0.  
Dim MySqr3 As Double = Math.Sqrt(0)  
' Returns NaN (not a number).  
Dim MySqr4 As Double = Math.Sqrt(-4)  
```  
  
## Ejemplo  
 En este ejemplo se utiliza el método <xref:System.Math.Tan%2A> de la clase <xref:System.Math> para devolver la tangente de un ángulo.  
  
```  
Public Function Ctan(ByVal angle As Double) As Double  
    ' Calculate cotangent of an angle, in radians.  
    Return 1.0 / Math.Tan(angle)  
End Function  
```  
  
## Requisitos  
 **Clase:** <xref:System.Math>  
  
 **Espacio de nombres:** <xref:System>  
  
 **Ensamblado:** mscorlib \(en mscorlib.dll\)  
  
## Vea también  
 <xref:Microsoft.VisualBasic.VBMath.Rnd%2A>   
 <xref:Microsoft.VisualBasic.VBMath.Randomize%2A>   
 <xref:System.Double.NaN>   
 [Funciones matemáticas derivadas](../../../visual-basic/language-reference/keywords/derived-math-functions.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)