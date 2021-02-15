---
description: 'Más información acerca de: conversión de delegado relajado (Visual Basic)'
title: Conversión de delegado flexible
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: 36917017cd29d2c71f0c04ca9545b7d4e90c644e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428498"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a>Conversión de delegado no estricta (Visual Basic)

La conversión de delegado relajado le permite asignar las funciones Subs y a los delegados o controladores incluso cuando sus firmas no son idénticas. Por consiguiente, el enlace a los delegados es coherente con el enlace ya permitido para las invocaciones de método.  
  
## <a name="parameters-and-return-type"></a>Parámetros y tipo de valor devuelto  

 En lugar de la coincidencia exacta de la firma, la conversión relajada requiere que se cumplan las siguientes condiciones cuando `Option Strict` se establece en `On` :  
  
- Debe existir una conversión de ampliación desde el tipo de datos de cada parámetro de delegado al tipo de datos del parámetro correspondiente de la función asignada o `Sub` . En el ejemplo siguiente, el delegado `Del1` tiene un parámetro, `Integer` . `m`Los parámetros de las expresiones lambda asignadas deben tener un tipo de datos para el que haya una conversión de ampliación `Integer` , como `Long` o `Double` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     Solo se permiten las conversiones de restricción cuando `Option Strict` se establece en `Off` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- Debe existir una conversión de ampliación en la dirección opuesta a la del tipo de valor devuelto de la función asignada o `Sub` al tipo de valor devuelto del delegado. En los ejemplos siguientes, el cuerpo de cada expresión lambda asignada se debe evaluar como un tipo de datos que `Integer` se amplía a porque el tipo de valor devuelto de `del1` es `Integer` .  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 Si `Option Strict` se establece en `Off` , se quita la restricción de ampliación en ambas direcciones.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a>Omitir especificaciones de parámetros  

 Los delegados relajados también permiten omitir completamente las especificaciones de los parámetros en el método asignado:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 Tenga en cuenta que no puede especificar algunos parámetros y omitir otros.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 La capacidad de omitir parámetros resulta útil en una situación como la definición de un controlador de eventos, donde se implican varios parámetros complejos. No se usan los argumentos para algunos controladores de eventos. En su lugar, el controlador accede directamente al estado del control en el que se registra el evento y omite los argumentos. Los delegados relajados permiten omitir los argumentos en estas declaraciones cuando no se produce ninguna ambigüedad. En el ejemplo siguiente, el método completamente especificado `OnClick` se puede volver a escribir como `RelaxedOnClick` .  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a>Ejemplos de AddressOf  

 Las expresiones lambda se usan en los ejemplos anteriores para que las relaciones de tipos resulten fáciles de ver. Sin embargo, se permiten las mismas relajaciones para las asignaciones de delegado que usan `AddressOf` , `Handles` o `AddHandler` .  
  
 En el ejemplo siguiente, las funciones `f1` , `f2` , `f3` y `f4` se pueden asignar a `Del1` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 El ejemplo siguiente solo es válido cuando `Option Strict` se establece en `Off` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a>Quitar la función devuelve  

 La conversión de delegado relajado le permite asignar una función a un `Sub` delegado, omitiendo de forma eficaz el valor devuelto de la función. Sin embargo, no se puede asignar `Sub` a un delegado de función. En el ejemplo siguiente, la dirección de la función `doubler` se asigna al `Sub` delegado `Del3` .  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a>Consulte también

- [Expresiones lambda](../procedures/lambda-expressions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
- [Delegados](index.md)
- [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](how-to-pass-procedures-to-another-procedure.md)
- [Inferencia de tipo de variable local](../variables/local-type-inference.md)
- [Option Strict (instrucción)](../../../language-reference/statements/option-strict-statement.md)
