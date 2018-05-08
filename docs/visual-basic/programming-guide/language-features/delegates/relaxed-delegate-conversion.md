---
title: Conversión de delegado no estricta (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversión de delegado no estricta (Visual Basic)
Conversión de delegado flexible le permite asignar funciones y subrutinas a delegados o controladores incluso cuando sus firmas no son idénticas. Por lo tanto, el enlace a delegados pasa a ser coherente con el enlace ya permitido para las invocaciones de método.  
  
## <a name="parameters-and-return-type"></a>Parámetros y tipo de valor devuelto  
 En lugar de coincidencia exacta de firmas, la conversión flexible requiere que se cumplen las condiciones siguientes cuando `Option Strict` está establecido en `On`:  
  
-   Debe existir una conversión de ampliación desde el tipo de datos de cada parámetro de delegado para el tipo de datos del parámetro correspondiente de la función asignada o `Sub`. En el ejemplo siguiente, el delegado `Del1` tiene un parámetro, un `Integer`. Parámetro `m` en la expresión lambda asignada expresiones deben tener un tipo de datos para el que hay una conversión de ampliación desde `Integer`, como `Long` o `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     Las conversiones de restricción se permiten solo cuando `Option Strict` está establecido en `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   Debe existir una conversión de ampliación en la dirección opuesta desde el tipo de valor devuelto de la función asignada o `Sub` para el tipo de valor devuelto del delegado. En los ejemplos siguientes, el cuerpo de cada expresión lambda asignada se debe evaluar como un tipo de datos que se amplíe a `Integer` porque el tipo devuelto de `del1` es `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 Si `Option Strict` se establece en `Off`, se quitan la restricción de ampliación en ambas direcciones.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a>Omisión de especificaciones de parámetros  
 Delegados flexibles también permiten omitir completamente las especificaciones del parámetro en el método asignado:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 Tenga en cuenta que no se puede especificar algunos parámetros y omitir otros.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 La capacidad para omitir los parámetros es útil en una situación como definir un controlador de eventos, donde están implicados varios parámetros complejos. No se usan los argumentos a algunos controladores de eventos. En su lugar, el controlador accede directamente el estado del control en el que se ha registrado el evento y pasa por alto los argumentos. Delegados flexibles permiten omitir los argumentos en aquellas declaraciones sin ambigüedades. En el ejemplo siguiente, el método especificado totalmente `OnClick` se puede reescribir como `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Ejemplos de AddressOf  
 Las expresiones lambda se usan en los ejemplos anteriores para que sea fácil ver las relaciones de tipo. Sin embargo, se permiten las relajaciones mismo para las asignaciones de delegado que usen `AddressOf`, `Handles`, o `AddHandler`.  
  
 En el ejemplo siguiente, las funciones de `f1`, `f2`, `f3`, y `f4` puede asignarse a `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 El ejemplo siguiente es válido solamente cuando `Option Strict` está establecido en `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a>Quitar la función devuelve  
 Conversión de delegado flexible le permite asignar una función a un `Sub` delegado, de forma eficaz se omitirá el valor devuelto de la función. Sin embargo, no puede asignar un `Sub` a un delegado de función. En el ejemplo siguiente, la dirección de función `doubler` se asigna a `Sub` delegar `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Paso de procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
