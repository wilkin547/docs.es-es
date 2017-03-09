---
title: "Conversi&#243;n de delegado no estricta (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversiones, delegados flexibles"
  - "delegados [Visual Basic], conversión no estricta"
  - "conversión de delegado no estricta [Visual Basic]"
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Conversi&#243;n de delegado no estricta (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La conversión de delegado flexible permite asignar funciones y subrutinas a delegados o controladores incluso cuando sus firmas no son idénticas. Por tanto, el enlace a los delegados se vuelve coherente con el enlace ya permitido en las llamadas a métodos.  
  
## Parámetros y tipo de valor devuelto  
 En lugar de la coincidencia exacta de firmas, la conversión flexible requiere que se cumplan las condiciones siguientes cuando `Option Strict` está establecido en `On`:  
  
-   Debe existir una conversión de ampliación desde el tipo de datos de cada parámetro delegado al tipo de datos del parámetro correspondiente de la función asignada o `Sub`.  En el ejemplo siguiente, el delegado `Del1` tiene un parámetro, `Integer`.  El parámetro `m` en las expresiones lambda asignadas debe tener un tipo de datos para el que haya una conversión de ampliación desde `Integer`, como `Long` o `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#2)]  
  
     Sólo se permiten las conversiones de restricción cuando `Option Strict` está establecido en `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module2.vb#8)]  
  
-   Debe existir una conversión de ampliación en la dirección contraria desde el tipo de valor devuelto de la función o `Sub` asignada al tipo de valor devuelto del delegado.  En los ejemplos siguientes, el cuerpo de cada expresión lambda asignada se debe evaluar como un tipo de datos que se amplía a `Integer`, porque el tipo de valor devuelto de `del1` es `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#3)]  
  
 Si `Option Strict` está establecido en `Off`, se quita la restricción de ampliación en ambas direcciones.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module2.vb#4)]  
  
## Omisión de las especificaciones del parámetro  
 Los delegados flexibles también permiten omitir completamente las especificaciones del parámetro en el método asignado:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#6)]  
  
 Observe que no puede especificar algunos parámetros y omitir otros.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#15)]  
  
 La capacidad de omitir parámetros es útil en una situación en la que se define un controlador de eventos, donde están implicados varios parámetros complejos.  No se usan argumentos en algunos controladores de eventos.  En su lugar, el controlador tiene directamente acceso al estado del control en el que se registra el evento y omite los argumentos.  Los delegados flexibles permiten omitir argumentos en aquellas declaraciones sin ambigüedades.  En el ejemplo siguiente, el método completo `OnClick` se puede volver a escribir como `RelaxedOnClick`.  
  
```vb#  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## Ejemplos de AddressOf  
 Las expresiones lambda se usan en los ejemplos anteriores para que se vean fácilmente las relaciones entre tipos.  Sin embargo, se permite la misma flexibilidad para las asignaciones de delegado que usan `AddressOf`, `Handles` o `AddHandler`.  
  
 En el siguiente ejemplo, las funciones `f1`, `f2`, `f3` y `f4` se pueden asignar a `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#9)]  
  
 El ejemplo siguiente sólo es válido cuando `Option Strict` está establecido en `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module2.vb#14)]  
  
## Colocar valores devueltos de una función  
 La conversión de delegado flexible permite asignar una función a un delegado `Sub`, omitiendo así el valor devuelto de la función.  Sin embargo, no se puede asignar un `Sub` a un delegado de función.  En el ejemplo siguiente, la dirección de función `doubler` se asigna al delegado `Sub``Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/visualbasic/VbVbalrRelaxedDelegates/Module1.vb#11)]  
  
## Vea también  
 [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)