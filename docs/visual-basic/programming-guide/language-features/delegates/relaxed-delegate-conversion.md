---
title: "Suaviza la conversión de delegado (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c0160165d3df9755481b89570b4cd135b3a990a2
ms.lasthandoff: 03/13/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversión de delegado no estricta (Visual Basic)
Conversión de delegado flexible le permite asignar funciones y subrutinas a delegados o controladores incluso cuando sus firmas no son idénticas. Por lo tanto, el enlace a delegados se vuelve coherente con el enlace ya permitido para las invocaciones de método.  
  
## <a name="parameters-and-return-type"></a>Parámetros y tipo de valor devuelto  
 En lugar de la firma con coincidencia exacta, la conversión flexible requiere que se cumplen las condiciones siguientes cuando `Option Strict` está establecido en `On`:  
  
-   Debe existir una conversión de ampliación desde el tipo de datos de cada parámetro de delegado para el tipo de datos del parámetro correspondiente de la función asignada o `Sub`. En el ejemplo siguiente, el delegado `Del1` tiene un parámetro, un `Integer`. Parámetro `m` en la expresión lambda asignada expresiones deben tener un tipo de datos para el que hay una conversión de ampliación de `Integer`, como `Long` o `Double`.  
  
     [!code-vb[1 VbVbalrRelaxedDelegates](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates&#2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Las conversiones de restricción se permiten solo cuando `Option Strict` está establecido en `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates Nº&8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Debe existir una conversión de ampliación en la dirección contraria desde el tipo de valor devuelto de la función asignada o `Sub` para el tipo de valor devuelto del delegado. En los ejemplos siguientes, el cuerpo de cada expresión lambda asignada se debe evaluar como un tipo de datos que se amplíe a `Integer` porque el tipo devuelto de `del1` es `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates&3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Si `Option Strict` se establece en `Off`, se quitan la restricción de ampliación en ambas direcciones.  
  
 [!code-vb[VbVbalrRelaxedDelegates Nº&4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>La omisión de las especificaciones del parámetro  
 Delegados flexibles también permiten omitir completamente las especificaciones de parámetros en el método asignado:  
  
 [!code-vb[VbVbalrRelaxedDelegates&#5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates Nº&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Tenga en cuenta que no puede especificar algunos parámetros y omitir otros.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 La capacidad de omitir parámetros es útil en una situación como la definición de un controlador de eventos, donde están implicados varios parámetros complejos. No se utilizan los argumentos de algunos controladores de eventos. En su lugar, el controlador directamente tiene acceso al estado del control en el que está registrado el evento y omite los argumentos. Delegados flexibles permiten omitir argumentos en aquellas declaraciones sin ambigüedades. En el ejemplo siguiente, el método completo `OnClick` puede reescribirse como `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Ejemplos de AddressOf  
 Las expresiones lambda se usan en los ejemplos anteriores para facilitar las relaciones de tipo ver. Sin embargo, el mismas relajaciones permitidas para las asignaciones de delegado que usan `AddressOf`, `Handles`, o `AddHandler`.  
  
 En el ejemplo siguiente, las funciones `f1`, `f2`, `f3`, y `f4` puede asignarse a `Del1`.  
  
 [!code-vb[1 VbVbalrRelaxedDelegates](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 El ejemplo siguiente es válido solamente cuando `Option Strict` está establecido en `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Quitar la función devuelve  
 Conversión de delegado flexible le permite asignar una función a un `Sub` delegado, omitiendo el valor devuelto de la función de forma eficaz. Sin embargo, no puede asignar un `Sub` a un delegado de función. En el ejemplo siguiente, la dirección de función `doubler` se asigna a `Sub` delegar `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates&#10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates&#11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Conversiones de restricción y ampliación](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Cómo: pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
