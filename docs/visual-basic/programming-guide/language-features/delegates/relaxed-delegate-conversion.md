---
title: Conversión de delegado no estricta (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 57e863d9781721a997ae49e1a5c9d8f3562a1bd0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842725"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversión de delegado no estricta (Visual Basic)
Conversión de delegado flexible le permite asignar subfunciones y funciones a delegados o controladores incluso cuando sus firmas no son idénticas. Por lo tanto, el enlace a delegados pasa a ser coherente con el enlace permitido ya las invocaciones de método.  
  
## <a name="parameters-and-return-type"></a>Los parámetros y tipo de valor devuelto  
 En lugar de firma con coincidencia exacta, se requiere conversión flexible que se cumplen las condiciones siguientes cuando `Option Strict` está establecido en `On`:  
  
-   Debe existir una conversión de ampliación desde el tipo de datos de cada parámetro de delegado para el tipo de datos del parámetro correspondiente de la función asignada o `Sub`. En el ejemplo siguiente, el delegado `Del1` tiene un parámetro, un `Integer`. Parámetro `m` en la expresión lambda asignada expresiones deben tener un tipo de datos para el que hay una conversión de ampliación desde `Integer`, tales como `Long` o `Double`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Las conversiones de restricción se permiten solo cuando `Option Strict` está establecido en `Off`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
-   Debe existir una conversión de ampliación en la dirección opuesta, el tipo de valor devuelto de la función asignada o `Sub` para el tipo de valor devuelto del delegado. En los ejemplos siguientes, se debe evaluar el cuerpo de cada expresión lambda asignada a un tipo de datos que se amplía a `Integer` porque el tipo de valor devuelto de `del1` es `Integer`.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Si `Option Strict` está establecido en `Off`, la restricción de ampliación se quitan en ambas direcciones.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Si se omite las especificaciones de parámetros  
 Delegados relajados permiten omitir completamente las especificaciones de parámetros en el método asignado:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Tenga en cuenta que no se puede especificar algunos parámetros y omitir otros.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 La capacidad de omitir los parámetros es útil en una situación como la definición de un controlador de eventos, donde están implicados varios parámetros complejos. No se usan los argumentos para algunos controladores de eventos. En su lugar, el controlador accede directamente al estado del control en el que está registrado el evento y pasa por alto los argumentos. Delegados relajados permiten omitir argumentos en estas declaraciones sin ambigüedades. En el ejemplo siguiente, el método completo `OnClick` puede volver a escribirse como `RelaxedOnClick`.  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Ejemplos de AddressOf  
 Las expresiones lambda se usan en los ejemplos anteriores para hacer más fácil ver las relaciones de tipo. Sin embargo, se permiten las relajaciones de la mismas para las asignaciones de delegado que usan `AddressOf`, `Handles`, o `AddHandler`.  
  
 En el ejemplo siguiente, las funciones `f1`, `f2`, `f3`, y `f4` puede asignarse a `Del1`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 El ejemplo siguiente es válido solamente cuando `Option Strict` está establecido en `Off`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Quitar la función devuelve  
 Conversión de delegado flexible le permite asignar una función a un `Sub` delegado, omitiendo el valor devuelto de la función de forma eficaz. Sin embargo, no puede asignar un `Sub` a un delegado de función. En el ejemplo siguiente, la dirección de función `doubler` se asigna a `Sub` delegar `Del3`.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>Vea también

- [Expresiones lambda](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
