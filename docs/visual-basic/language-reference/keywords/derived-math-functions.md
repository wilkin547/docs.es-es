---
title: "Funciones matem&#225;ticas derivadas (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ángulos"
  - "arccosecant (función)"
  - "arco coseno (función)"
  - "arccotangent (función)"
  - "arco secante (función)"
  - "arco seno (función)"
  - "operaciones aritméticas, funciones matemáticas derivadas"
  - "cosecant (función)"
  - "cotangente (función)"
  - "grados"
  - "funciones matemáticas derivadas"
  - "funciones [Visual Basic], funciones matemáticas derivadas"
  - "funciones hiperbólicas"
  - "funciones inversas"
  - "logaritmos"
  - "funciones matemáticas, derivadas"
  - "secant (función)"
  - "funciones trigonométricas"
ms.assetid: 63e449d8-9444-44fb-8db1-6d9cf346e2aa
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Funciones matem&#225;ticas derivadas (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En la tabla siguiente se muestran las funciones matemáticas no intrínsecas que pueden derivarse de las funciones matemáticas intrínsecas del objeto <xref:System.Math?displayProperty=fullName>.  Para tener acceso a las funciones matemáticas intrínsecas, agregue `Imports System.Math` a su archivo o proyecto.  
  
|Función|Funciones derivadas equivalentes|  
|-------------|--------------------------------------|  
|Secante \(Sec\(x\)\)|1 \/ Cos\(x\)|  
|Cosecante \(Csc\(x\)\)|1 \/ Sin\(x\)|  
|Cotangente \(Ctan\(x\)\)|1 \/ Tan\(x\)|  
|Seno inverso \(Asin\(x\)\)|Atan\(x \/ Sqrt\(\-x \* x \+ 1\)\)|  
|Coseno inverso \(Acos\(x\)\)|Atan\(\-x \/ Sqrt\(\-x \* x \+ 1\)\) \+ 2 \* Atan\(1\)|  
|Secante inversa \(Asec\(x\)\)|2 \* Atan\(1\) – Atan\(Sign\(x\) \/ Sqrt\(x \* x – 1\)\)|  
|Cosecante inversa \(Acsc\(x\)\)|Atan\(Sign\(x\) \/ Sqrt\(x \* x – 1\)\)|  
|Cotangente inversa \(Acot\(x\)\)|2 \* Atan\(1\) \- Atan\(x\)|  
|Seno hiperbólico \(Sinh\(x\)\)|\(Exp\(x\) – Exp\(\-x\)\) \/ 2|  
|Coseno hiperbólico \(Cosh\(x\)\)|\(Exp\(x\) \+ Exp\(\-x\)\) \/ 2|  
|Tangente hiperbólica \(Tanh\(x\)\)|\(Exp\(x\) – Exp\(\-x\)\) \/ \(Exp\(x\) \+ Exp\(\-x\)\)|  
|Secante hiperbólica \(Sech\(x\)\)|2 \/ \(Exp\(x\) \+ Exp\(\-x\)\)|  
|Cosecante hiperbólica \(Csch\(x\)\)|2 \/ \(Exp\(x\) – Exp\(\-x\)\)|  
|Cotangente hiperbólica \(Coth\(x\)\)|\(Exp\(x\) \+ Exp\(\-x\)\) \/ \(Exp\(x\) – Exp\(\-x\)\)|  
|Seno hiperbólico inverso \(Asinh\(x\)\)|Log\(x \+ Sqrt\(x \* x \+ 1\)\)|  
|Coseno hiperbólico inverso \(Acosh\(x\)\)|Log\(x \+ Sqrt\(x \* x – 1\)\)|  
|Tangente hiperbólica inversa \(Atanh\(x\)\)|Log\(\(1 \+ x\) \/ \(1 – x\)\) \/ 2|  
|Secante hiperbólica inversa \(AsecH\(x\)\)|Log\(\(Sqrt\(\-x \* x \+ 1\) \+ 1\) \/ x\)|  
|Cosecante hiperbólica inversa \(Acsch\(x\)\)|Log\(\(Sign\(x\) \* Sqrt\(x \* x \+ 1\) \+ 1\) \/ x\)|  
|Cotangente hiperbólica inversa \(Acoth\(x\)\)|Log\(\(x \+ 1\) \/ \(x – 1\)\) \/ 2|  
  
## Vea también  
 [Funciones matemáticas](../../../visual-basic/language-reference/functions/math-functions.md)