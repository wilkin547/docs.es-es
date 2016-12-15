---
title: "La expresi&#243;n es un valor y, por lo tanto, no puede ser destino de una asignaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30068"
  - "vbc30068"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30068"
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La expresi&#243;n es un valor y, por lo tanto, no puede ser destino de una asignaci&#243;n
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una instrucción intenta asignar un valor a una expresión.  Sólo puede asignar un valor a una variable de lectura, una propiedad o un elemento de matriz en tiempo de ejecución.  El ejemplo siguiente muestra cómo puede aparecer este error.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Se pueden aplicar ejemplos similares a propiedades y elementos de matriz.  
  
 **Acceso indirecto.** El acceso indirecto mediante un tipo de valor también puede generar este error.  Considere el ejemplo de código siguiente que intenta establecer el valor de <xref:System.Drawing.Point> obteniendo acceso a él indirectamente a través de <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 La última instrucción del ejemplo anterior provoca un error, ya que sólo crea una asignación temporal para la estructura <xref:System.Drawing.Point> devuelta por la propiedad <xref:System.Windows.Forms.Control.Location%2A>.  Una estructura es un tipo de valor y la estructura temporal no se conserva después de la ejecución de la instrucción.  El problema se resuelve declarando y utilizando una variable para <xref:System.Windows.Forms.Control.Location%2A>, que crea una asignación más permanente para la estructura <xref:System.Drawing.Point>.  El ejemplo siguiente muestra un código que puede reemplazar a la última instrucción del ejemplo anterior.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Identificador de error:** BC30068  
  
### Para corregir este error  
  
-   Si la instrucción asigna un valor a una expresión, reemplace la expresión por una variable de escritura única, una propiedad o un elemento de matriz.  
  
-   Si la instrucción obtiene acceso indirecto a través de un tipo de valor \(normalmente una estructura\), cree una variable para contener el tipo de valor.  
  
-   Asigne la estructura adecuada \(u otro tipo de valor\) a la variable.  
  
-   Utilice la variable para tener acceso a la propiedad y asignarle un valor.  
  
## Vea también  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Procedimientos de solución de problemas](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)