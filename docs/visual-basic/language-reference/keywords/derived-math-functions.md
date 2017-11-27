---
title: "Funciones matemáticas derivadas (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5816fa4c8c384eca116fa1512950a3588c6e3392
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="derived-math-functions-visual-basic"></a>Funciones matemáticas derivadas (Visual Basic)
La tabla siguiente muestran funciones matemáticas no intrínsecas que se pueden derivar de las funciones matemáticas intrínsecas de la <xref:System.Math?displayProperty=nameWithType> objeto. Puede tener acceso a las funciones matemáticas intrínsecas agregando `Imports System.Math` en el archivo o proyecto.  
  
|Función|Equivalentes derivadas|  
|--------------|-------------------------|  
|Secante (Sec(x))|1 / cos (x)|  
|Cosecante (Csc(x))|1 / seno (x)|  
|Cotangente (Ctan(x))|1 / tan (x)|  
|Seno inverso (Asin(x))|ATAN (x / Sqrt (-x * x + 1))|  
|Coseno inverso (Acos(x))|ATAN (-x / Sqrt (-x * x + 1)) + 2 \* Atan(1)|  
|Secante inversa (Asec(x))|2 * Atan(1): Atan(Sign(x) / Sqrt (x \* x – 1))|  
|Cosecante inversa (Acsc(x))|ATAN(Sign(x) / Sqrt (x * x – 1))|  
|Cotangente inversa (Acot(x))|2 * Atan(1) - ATAN (x)|  
|Seno hiperbólico (Sinh(x))|(EXP (x) – Exp(-x)) / 2|  
|Coseno hiperbólico (Cosh(x))|(EXP (x) + Exp(-x)) / 2|  
|Tangente hiperbólica (Tanh(x))|(EXP (x) – Exp(-x)) / (EXP (x) + Exp(-x))|  
|Secante hiperbólica (Sech(x))|2 / (EXP (x) + Exp(-x))|  
|Cosecante hiperbólica (Csch(x))|2 / (EXP (x) – Exp(-x))|  
|Cotangente hiperbólica (Coth(x))|(EXP (x) + Exp(-x)) / (EXP (x) – Exp(-x))|  
|Seno hiperbólico inverso (Asinh(x))|Registro (x + Sqrt (x * x + 1))|  
|Coseno hiperbólico inverso (Acosh(x))|Registro (x + Sqrt (x * x – 1))|  
|Tangente hiperbólica inversa (Atanh(x))|Registro ((1 + x) / (1 – x)) / 2|  
|Secante hiperbólica inversa (AsecH(x))|Registro ((Sqrt (-x * x + 1) + 1) / x)|  
|Cosecante hiperbólica inversa (Acsch(x))|Log((Sign(x) * Sqrt (x \* x + 1) + 1) / x)|  
|Cotangente hiperbólica inversa (Acoth(x))|Registro ((x + 1) / (x – 1)) / 2|  
  
## <a name="see-also"></a>Vea también  
 [Funciones matemáticas](../../../visual-basic/language-reference/functions/math-functions.md)
