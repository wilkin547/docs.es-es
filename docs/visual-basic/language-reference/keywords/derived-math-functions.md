---
description: 'Más información sobre: funciones matemáticas derivadas (Visual Basic)'
title: Funciones matemáticas derivadas
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
ms.openlocfilehash: daaed1312f08cecc0c68af0e36d574424fc526a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730777"
---
# <a name="derived-math-functions-visual-basic"></a>Funciones matemáticas derivadas (Visual Basic)

En la tabla siguiente se muestran las funciones matemáticas no intrínsecas que se pueden derivar de las funciones matemáticas intrínsecas del <xref:System.Math?displayProperty=nameWithType> objeto. Puede tener acceso a las funciones matemáticas intrínsecas agregando `Imports System.Math` al archivo o proyecto.  
  
|Función|Equivalentes derivados|  
|--------------|-------------------------|  
|Secante (s (x))|1/cos (x)|  
|Cosecante (CSC (x))|1/sin (x)|  
|Cotangente (CTAN (x))|1/tan (x)|  
|Seno inverso (ASIN (x))|Atan (x/sqrt (-x * x + 1))|  
|Coseno inverso (ACOS (x))|Atan (-x/sqrt (-x * x + 1)) + 2 \* atan (1)|  
|Secante inversa (ASEC (x))|2 * atan (1) – atan (signo (x)/raiz (x \* x – 1))|  
|Cosecación inversa (ACSC (x))|Atan (signo (x)/raiz (x * x – 1))|  
|Cotangente inversa (ACOT (x))|2 * atan (1)-atan (x)|  
|Seno hiperbólico (SENOH (x))|(Exp (x) – exp (-x))/2|  
|Coseno hiperbólico (cosh (x))|(Exp (x) + exp (-x))/2|  
|Tangente hiperbólica (tanh (x))|(Exp (x) – exp (-x))/(exp (x) + exp (-x))|  
|Secante hiperbólica (SECH (x))|2/(exp (x) + exp (-x))|  
|Cosecante hiperbólica (Csch (x))|2/(exp (x) – exp (-x))|  
|Cotangente hiperbólica (coth (x))|(Exp (x) + exp (-x))/(exp (x) – exp (-x))|  
|Seno hiperbólico inverso (Asinh (x))|Log (x + sqrt (x * x + 1))|  
|Coseno hiperbólico inverso (Acosh (x))|Log (x + sqrt (x * x – 1))|  
|Tangente hiperbólica inversa (Atanh (x))|Log ((1 + x)/(1 – x))/2|  
|Secante hiperbólica inversa (AsecH (x))|Log ((sqrt (-x * x + 1) + 1)/x)|  
|Cosecante hiperbólica inversa (Acsch (x))|Log ((signo (x) * sqrt (x \* x + 1) + 1)/x)|  
|Cotangente hiperbólica inversa (Acoth (x))|Log ((x + 1)/(x – 1))/2|  
  
## <a name="see-also"></a>Vea también

- [Funciones matemáticas](../functions/math-functions.md)
