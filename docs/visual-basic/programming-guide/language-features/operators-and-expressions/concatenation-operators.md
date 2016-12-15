---
title: "Operadores de concatenaci&#243;n en Visual Basic | Microsoft Docs"
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
  - "& (operador) [Visual Basic], concatenación"
  - "+ (operador) [Visual Basic], concatenación"
  - "operadores de concatenación"
  - "operadores de concatenación, cadenas en Visual Basic"
  - "operadores [Visual Basic], concatenación"
  - "código de Visual Basic, operadores"
ms.assetid: e59908c3-89e0-41ae-933d-3e8826c16a04
caps.latest.revision: 18
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operadores de concatenaci&#243;n en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los operadores de concatenación unen varias cadenas en una sola.  Existen dos operadores de concatenación: `+` y `&`.  Ambos efectúan la operación de concatenación básica, como se aprecia en el siguiente ejemplo.  
  
 [!CODE [Dim x As String = "Mic" & "ro" & "soft" Dim y As String = "Mic" + "ro" + "soft" ' The preceding statements set both x and y to "Microsoft".](Dim x As String = "Mic" & "ro" & "soft" Dim y As String = "Mic" + "ro" + "soft" ' The preceding statements set both x and y to "Microsoft".)]  
  
 Estos operadores también concatenan variables de `String`, como indica el siguiente ejemplo.  
  
 [!code-vb[VbVbalrOperators#76](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operators_1.vb)]  
  
## Diferencias entre los dos operadores de concatenación  
 El propósito principal del [\+ \(Operador\)](../../../../visual-basic/language-reference/operators/addition-operator.md) es sumar dos números,  aunque también puede concatenar operandos numéricos con operandos de cadena.  El operador `+` posee un conjunto de reglas complejo que establecen si hay que sumar, concatenar, señalar un error de compilador o generar una excepción <xref:System.InvalidCastException> en tiempo de ejecución.  
  
 El [& \(Operador\)](../../../../visual-basic/language-reference/operators/concatenation-operator.md) se define únicamente para operandos de `String` y siempre amplía sus operandos a `String`, independientemente de la configuración de `Option Strict`.  El uso del operador `&` es recomendable para concatenar cadenas, ya que se está expresamente definido para cadenas y reduce las probabilidades de generar una conversión inintencionada.  
  
## Rendimiento: String y StringBuilder  
 Si realiza una cantidad considerable de manipulaciones en una cadena \(como concatenaciones, eliminaciones y reemplazos\), el rendimiento puede verse beneficiado si usa la clase <xref:System.Text.StringBuilder> del espacio de nombres <xref:System.Text>.  Esta clase toma una instrucción extra para crear e inicializar un objeto <xref:System.Text.StringBuilder>, así como otra instrucción para convertir su valor final a una `String`, pero este tiempo se puede recuperar, ya que el rendimiento de <xref:System.Text.StringBuilder> es más rápido.  
  
## Vea también  
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Tipos de métodos de manipulación de cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/types-of-string-manipulation-methods.md)   
 [Operadores aritméticos en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)