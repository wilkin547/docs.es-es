---
title: Funciones matemáticas derivadas (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operations, derived math functions
- cosecant function
- arcsecant function
- arccotangent function
- functions [Visual Basic], derived math functions
- inverse functions
- math functions, derived
- derived math functions
- cotangent function
- angles
- secant function
- trigonometric functions
- logarithms
- arccosecant function
- hyperbolic functions
- arcsine function
- degrees
- arccosine function
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
ms.openlocfilehash: 0d0606c52d1d50fcc2fd8eea3ad2851c95b18a69
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836589"
---
# <a name="derived-math-functions-visual-basic"></a>Funciones matemáticas derivadas (Visual Basic)
La siguiente tabla muestra las funciones matemáticas no intrínsecos que se pueden derivar de las funciones matemáticas intrínsecas de los <xref:System.Math?displayProperty=nameWithType> objeto. Puede tener acceso a las funciones matemáticas intrínsecas agregando `Imports System.Math` al archivo o proyecto.  
  
|Función|Equivalentes derivadas|  
|--------------|-------------------------|  
|Secant (Sec(x))|1 / Cos(x)|  
|Cosecante (Csc(x))|1 / Sin(x)|  
|Cotangente (Ctan(x))|1 / tan (x)|  
|Seno inverso (Asin(x))|ATAN (x / Sqrt (-x * x + 1))|  
|Coseno inverso (Acos(x))|ATAN (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)|  
|Secante inversa (Asec(x))|2 * Atan(1) – Atan(Sign(x) / Sqrt (x \* x – 1))|  
|Cosecante inversa (Acsc(x))|ATAN(Sign(x) / Sqrt (x * x – 1))|  
|Cotangente inversa (Acot(x))|2 * Atan(1) - Atan(x)|  
|Seno hiperbólico (Sinh(x))|(Exp(x) – Exp(-x)) / 2|  
|Coseno hiperbólico (Cosh(x))|(EXP (x) + Exp(-x)) / 2|  
|Tangente hiperbólica (TANH|(Exp(x) – Exp(-x)) / (Exp(x) + Exp(-x))|  
|Secante hiperbólica (Sech(x))|2 / (Exp(x) + Exp(-x))|  
|Cosecante hiperbólica (Csch(x))|2 / (Exp(x) – Exp(-x))|  
|Cotangente hiperbólica (Coth(x))|(Exp(x) + Exp(-x)) / (Exp(x) – Exp(-x))|  
|Seno hiperbólico inverso (Asinh(x))|Log(x + Sqrt(x * x + 1))|  
|Coseno hiperbólico inverso (Acosh(x))|Log(x + Sqrt(x * x – 1))|  
|Tangente hiperbólica inversa (Atanh(x))|Log((1 + x) / (1 – x)) / 2|  
|Secante hiperbólica inversa (AsecH(x))|Registro ((Sqrt (-x * x + 1) + 1) / x)|  
|Cosecante hiperbólica inversa (Acsch(x))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|Cotangente hiperbólica inversa (Acoth(x))|Log((x + 1) / (x – 1)) / 2|  
  
## <a name="see-also"></a>Vea también

- [Funciones matemáticas](../../../visual-basic/language-reference/functions/math-functions.md)
