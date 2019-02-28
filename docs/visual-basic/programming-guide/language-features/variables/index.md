---
title: Variables en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
  - 'variables [Visual Basic]'
  - 'values [Visual Basic], storing'
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
---
# <a name="variables-in-visual-basic"></a>Variables en Visual Basic
A menudo tendrá que almacenar valores al realizar cálculos con Visual Basic. Por ejemplo, tal vez le interese calcular varios valores, compararlos y realizar diversas operaciones con ellos, según el resultado de la comparación. Para poder compararlos, debe conservar los valores.  
  
## <a name="usage"></a>Uso  
 Visual Basic, al igual que la mayoría de los lenguajes de programación, usa variables para almacenar los valores. Las *variables* tienen un nombre (la palabra que se usa para hacer referencia al valor contenido por la variable). Las variables también tienen un tipo de datos (que determina el tipo de datos que puede almacenar la variable). Las variables pueden representar una matriz si tienen que almacenar un conjunto indexado de elementos de datos estrechamente relacionados.  
  
 La inferencia de tipo de variable local permite declarar variables sin especificar explícitamente un tipo de datos. En su lugar, el compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización. Para obtener más información, vea [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) (Inferencia de tipo de variable local) y [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) (Instrucción Option Infer).  
  
## <a name="assigning-values"></a>Asignar valores  
 Para realizar cálculos y asignar el resultado a una variable debe usar instrucciones de asignación, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
>  El signo igual (`=`) de este ejemplo es un operador de asignación, no un operador de igualdad. El valor se asigna a la variable `applesSold`.  
  
 Para obtener más información, vea [Cómo: Movimiento de datos dentro y fuera de una Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## <a name="variables-and-properties"></a>Variables y propiedades  
 Al igual que una variable, una *propiedad* representa un valor al que se puede tener acceso, pero es más compleja que una variable. Una propiedad usa bloques de código que controlan cómo establecer y recuperar su valor. Para obtener más información, vea [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md) (Diferencias entre propiedades y variables en Visual Basic).  
  
## <a name="see-also"></a>Vea también
- [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Solución de problemas de variables](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
- [Cómo: Movimiento de datos dentro y fuera de una Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [Diferencias entre propiedades y Variables en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)
- [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
