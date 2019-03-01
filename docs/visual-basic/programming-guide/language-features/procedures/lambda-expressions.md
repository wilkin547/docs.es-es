---
title: Lambda (expresiones) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: de09612ee978ee809ee07f0db2e37b14533760da
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974814"
---
# <a name="lambda-expressions-visual-basic"></a>Lambda (expresiones) (Visual Basic)
Un *expresión lambda* es una función o subrutina sin un nombre que puede usarse siempre que un delegado es válido. Las expresiones lambda pueden ser funciones o subrutinas y pueden ser una línea o varias líneas. Puede pasar valores desde el ámbito actual a una expresión lambda.  
  
> [!NOTE]
>  El `RemoveHandler` instrucción es una excepción. No se puede pasar una expresión lambda para el parámetro de delegado de `RemoveHandler`.  
  
 Crear expresiones lambda con la `Function` o `Sub` palabra clave, al igual que crear una subrutina o función estándar. Sin embargo, las expresiones lambda se incluyen en una instrucción.  
  
 El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor. El ejemplo muestra la sintaxis de expresiones lambda de varias líneas y de línea para una función.  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 El ejemplo siguiente es una expresión lambda que escribe un valor en la consola. El ejemplo muestra la sintaxis de expresiones lambda de varias líneas y de línea de una subrutina.  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 Tenga en cuenta que, en los ejemplos anteriores, las expresiones lambda se asignan a un nombre de variable. Cada vez que se hace referencia a la variable, se invoca la expresión lambda. También puede declarar e invocar una expresión lambda al mismo tiempo, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 Una expresión lambda puede devolverse como valor de una llamada de función (como se muestra en el ejemplo de la [contexto](#context) sección más adelante en este tema), o se pasa como argumento a un parámetro que toma un tipo de delegado, como se muestra en la siguiente ejemplo.  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda es similar al de una subrutina o función estándar. Las diferencias son como sigue:  
  
-   Una expresión lambda no tiene un nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` o `Overrides`.  
  
-   No utilizan las funciones lambda de una línea un `As` cláusula para designar el tipo de valor devuelto. En su lugar, el tipo se deduce del valor que se evalúa como el cuerpo de la expresión lambda. Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
-   En las funciones lambda de varias líneas, puede especificar un tipo de valor devuelto mediante el uso de un `As` cláusula, u omita el `As` cláusula para que se deduce el tipo de valor devuelto. Cuando el `As` se omite la cláusula para una función lambda de varias líneas, el tipo de valor devuelto se infiere para ser el tipo dominante de todos los `Return` las instrucciones de la función lambda de varias líneas. El *tipo dominante* es un tipo único que todos los demás tipos se pueden ampliar. Si no se puede determinar este tipo único, el tipo dominante es el único tipo que todos los demás tipos de la matriz se pueden restringir. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. En este caso, si `Option Strict` está establecido en `On`, se produce un error del compilador.  
  
     Por ejemplo, si las expresiones proporcionado a la `Return` instrucción contienen valores de tipo `Integer`, `Long`, y `Double`, la matriz resultante es de tipo `Double`. Ambos `Integer` y `Long` se convierten en `Double` y sólo `Double`. Por lo tanto, `Double` es el tipo dominante. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   El cuerpo de una sola línea de función debe ser una expresión que devuelve un valor, no una instrucción. No hay ningún `Return` instrucción para las funciones de la línea. El valor devuelto por la función de la línea es el valor de la expresión en el cuerpo de la función.  
  
-   El cuerpo de una sola línea de subrutina debe ser una instrucción de línea.  
  
-   Línea funciones y subrutinas no incluyen un `End Function` o `End Sub` instrucción.  
  
-   Puede especificar el tipo de datos de un parámetro de expresión lambda utilizando la `As` puede deducir la palabra clave o el tipo de datos del parámetro. Deben haber especificado todos los parámetros deben deducir los tipos de datos o todos.  
  
-   `Optional` y `Paramarray` no se permiten parámetros.  
  
-   No se permiten parámetros genéricos.  
  
## <a name="async-lambdas"></a>Lambdas asincrónicas  
 Puede crear fácilmente expresiones lambda y las instrucciones que incorporen el procesamiento asincrónico mediante el uso de la [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [operador Await](../../../../visual-basic/language-reference/operators/await-operator.md) palabras clave. Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.  
  
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
  
 Puede agregar el mismo controlador de eventos mediante el uso de una expresión lambda asincrónica en un [AddHandler (instrucción)](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.  
  
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
  
 Para obtener más información acerca de cómo crear y usar métodos asincrónicos, vea [programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
##  <a name="context"></a> Contexto  
 Una expresión lambda comparte su contexto con el ámbito en el que se definió. Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor. Esto incluye el acceso a las variables de miembro, funciones y subrutinas, `Me`, parámetros y variables locales en el ámbito contenedor.  
  
 Acceso a las variables locales y parámetros en el ámbito contenedor puede extender más allá de la duración de ese ámbito. Siempre que un delegado que hace referencia a una expresión lambda no está disponible para la recolección de elementos, se conserva el acceso a las variables del entorno original. En el ejemplo siguiente, la variable `target` es local para `makeTheGame`, el método en el que la expresión lambda `playTheGame` está definido. Tenga en cuenta que la expresión lambda devuelta, asignada a `takeAGuess` en `Main`, todavía tiene acceso a la variable local `target`.  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 El ejemplo siguiente muestra la amplia gama de derechos de acceso de la expresión lambda anidada. Cuando se ejecuta la expresión lambda devuelta desde `Main` como `aDel`, tiene acceso a estos elementos:  
  
-   Un campo de la clase donde se define: `aField`  
  
-   Una propiedad de la clase donde se define: `aProp`  
  
-   Un parámetro de método `functionWithNestedLambda`, en el que se define: `level1`  
  
-   Una variable local de `functionWithNestedLambda`: `localVar`  
  
-   Un parámetro de la expresión lambda en la que está anidado: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a>Convertir a un tipo delegado  
 Una expresión lambda se puede convertir implícitamente a un tipo delegado compatible. Para obtener información acerca de los requisitos generales para la compatibilidad, vea [conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Func(Of Integer, Boolean)` o una firma de delegado correspondiente.  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 En el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Sub(Of Double, String, Double)` o una firma de delegado correspondiente.  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 Al asignar las expresiones lambda a delegados o pasar como argumentos a los procedimientos, puede especificar los nombres de parámetro pero omite los tipos de datos, lo que permite a los tipos se toman de delegado.  
  
## <a name="examples"></a>Ejemplos  
  
-   En el ejemplo siguiente se define una expresión lambda que devuelve `True` si el argumento que acepta valores NULL tiene un valor asignado, y `False` si su valor es `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
-   El ejemplo siguiente define una expresión lambda que devuelve el índice del último elemento de una matriz.  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](./index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Tipos de valor que aceptan valores NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Cómo: Crear una expresión Lambda](./how-to-create-a-lambda-expression.md)
- [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
