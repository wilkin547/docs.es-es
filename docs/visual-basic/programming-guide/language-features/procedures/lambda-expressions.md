---
title: Expresiones lambda (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e50593e76afecfe8807c3cb5bac479245d2feaef
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="lambda-expressions-visual-basic"></a>Lambda (expresiones) (Visual Basic)
Un *expresión lambda* es una función o subrutina sin nombre que se puede utilizar donde haya un delegado válido. Las expresiones lambda pueden ser funciones o subrutinas y pueden ser una línea o varias líneas. Puede pasar valores del ámbito actual a una expresión lambda.  
  
> [!NOTE]
>  El `RemoveHandler` instrucción es una excepción. No se puede pasar una expresión lambda para el parámetro de delegado de `RemoveHandler`.  
  
 Crear expresiones lambda con la `Function` o `Sub` (palabra clave), como crear una subrutina o función estándar. Sin embargo, las expresiones lambda se incluyen en una instrucción.  
  
 El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor. El ejemplo muestra la sintaxis de expresiones lambda de línea y de varias líneas para una función.  
  
 [!code-vb[VbVbalrLambdas&#14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 El ejemplo siguiente es una expresión lambda que escribe un valor en la consola. El ejemplo muestra la sintaxis de expresiones lambda de línea y de varias líneas para una subrutina.  
  
 [!code-vb[VbVbalrLambdas&#15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Observe que, en los ejemplos anteriores, las expresiones lambda se asignan a un nombre de variable. Cada vez que se hace referencia a la variable, se invoca la expresión lambda. También puede declarar e invocar una expresión lambda al mismo tiempo, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrLambdas&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Una expresión lambda se puede devolver como el valor de una llamada de función (como se muestra en el ejemplo de la [contexto](#context) más adelante en este tema), o se pasa como un argumento a un parámetro que toma un tipo de delegado, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrLambdas Nº&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar al de una subrutina o función estándar. Las diferencias son:  
  
-   Una expresión lambda no tiene un nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.  
  
-   No utilizan las funciones lambda de línea un `As` cláusula para designar el tipo de valor devuelto. En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de la expresión lambda. Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
-   En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante el uso de un `As` cláusula, u omita el `As` cláusula para que se deduce el tipo de valor devuelto. Cuando el `As` se omite la cláusula de una función lambda de varias líneas, se deduce el tipo de valor devuelto es el tipo dominante de todas las `Return` las instrucciones de la función lambda de varias líneas. El *tipo dominante* es un tipo único que todos los demás tipos se pueden ampliar. Si no se puede determinar este tipo único, el tipo dominante es el único tipo que todos los demás tipos de la matriz se pueden restringir. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. En este caso, si `Option Strict` se establece en `On`, se produce un error del compilador.  
  
     Por ejemplo, si las expresiones proporcionado a la `Return` instrucción contienen valores de tipo `Integer`, `Long`, y `Double`, la matriz resultante es de tipo `Double`. Ambos `Integer` y `Long` se amplían a `Double` y sólo `Double`. Por lo tanto, `Double` es el tipo dominante. Para obtener más información, consulte [conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   El cuerpo de una función de la línea debe ser una expresión que devuelve un valor, no una instrucción. No hay ningún `Return` instrucción para las funciones de la línea. El valor devuelto por la función de la línea es el valor de la expresión en el cuerpo de la función.  
  
-   El cuerpo de una subrutina de línea debe ser una instrucción de línea.  
  
-   Línea funciones y subrutinas no incluyen un `End Function` o `End Sub` instrucción.  
  
-   Puede especificar el tipo de datos de un parámetro de expresión lambda utilizando la `As` puede deducirse (palabra clave) o el tipo de datos del parámetro. Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.  
  
-   `Optional`y `Paramarray` no se permiten parámetros.  
  
-   No se permiten parámetros genéricos.  
  
## <a name="async-lambdas"></a>Lambdas asincrónicas  
 Puede crear fácilmente expresiones lambda e instrucciones que incorporen el procesamiento asincrónico mediante la [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [operador Await](../../../../visual-basic/language-reference/operators/await-operator.md) palabras clave. Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 Puede agregar el mismo controlador de eventos mediante una lambda asincrónica en un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 Para obtener más información acerca de cómo crear y usar métodos asincrónicos, vea [la programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
##  <a name="context"></a>Contexto  
 Una expresión lambda comparte su contexto con el ámbito dentro del cual se define. Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor. Esto incluye el acceso a las variables miembro, funciones y subrutinas, `Me`, parámetros y variables locales del ámbito contenedor.  
  
 Acceso a las variables locales y parámetros en el ámbito contenedor se puede extender más allá de la duración de ese ámbito. Como un delegado que hace referencia a una expresión lambda no está disponible para la colección de elementos no utilizados, se conserva el acceso a las variables del entorno original. En el ejemplo siguiente, la variable `target` local `makeTheGame`, el método en el que la expresión lambda `playTheGame` está definido. Tenga en cuenta que la expresión lambda devuelta, asignada a `takeAGuess` en `Main`, todavía tiene acceso a la variable local `target`.  
  
 [!code-vb[VbVbalrLambdas&#12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 En el ejemplo siguiente se muestra la amplia gama de derechos de acceso de la expresión lambda anidada. Cuando se ejecuta la expresión lambda devuelta desde `Main` como `aDel`, tiene acceso a estos elementos:  
  
-   Un campo de la clase en la que se define:`aField`  
  
-   Una propiedad de la clase en la que se define:`aProp`  
  
-   Un parámetro de método `functionWithNestedLambda`, en el que se define:`level1`  
  
-   Una variable local de `functionWithNestedLambda`:`localVar`  
  
-   Un parámetro de la expresión lambda en el que está anidado:`level2`  
  
 [!code-vb[VbVbalrLambdas&#9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a>Convertir a un tipo de delegado  
 Una expresión lambda se puede convertir implícitamente a un tipo de delegado compatible. Para obtener información acerca de los requisitos generales de compatibilidad, vea [la conversión de delegado no estricta](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Func(Of Integer, Boolean)` o una firma de delegado correspondiente.  
  
 [!code-vb[VbVbalrLambdas Nº&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 En el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Sub(Of Double, String, Double)` o una firma de delegado correspondiente.  
  
 [!code-vb[23 de VbVbalrLambdas #](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 Al asignar las expresiones lambda a delegados o pasar como argumentos a los procedimientos, puede especificar los nombres de parámetro pero omite los tipos de datos, permitir que los tipos se toma del delegado.  
  
## <a name="examples"></a>Ejemplos  
  
-   En el ejemplo siguiente se define una expresión lambda que devuelve `True` si el argumento que acepta valores NULL tiene un valor asignado, y `False` si su valor es `Nothing`.  
  
     [!code-vb[VbVbalrLambdas Nº&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   En el ejemplo siguiente se define una expresión lambda que devuelve el índice del último elemento de una matriz.  
  
     [!code-vb[VbVbalrLambdas&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Tipos de valor que aceptan valores null](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Cómo: pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Cómo: crear una expresión Lambda](./how-to-create-a-lambda-expression.md)   
 [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)

