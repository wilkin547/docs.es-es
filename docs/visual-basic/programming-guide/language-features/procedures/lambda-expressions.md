---
title: Expresiones lambda
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: 1827eb5630ed217527de25fc9d9c2bb8994b9aff
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249674"
---
# <a name="lambda-expressions-visual-basic"></a>Lambda (expresiones) (Visual Basic)

Una *expresión lambda* es una función o subrutina sin un nombre que se puede usar siempre que un delegado sea válido. Las expresiones Lambda pueden ser funciones o subrutinas y pueden ser de una sola línea o de varias líneas. Puede pasar valores del ámbito actual a una expresión lambda.

> [!NOTE]
> La `RemoveHandler` instrucción es una excepción. No se puede pasar una expresión `RemoveHandler`lambda para el parámetro de delegado de .

Las expresiones lambda `Function` se `Sub` crean mediante la palabra clave or, del igual que se crea una función o subrutina estándar. Sin embargo, las expresiones lambda se incluyen en una instrucción.

El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor. En el ejemplo se muestra la sintaxis de expresión lambda de una línea y de varias líneas para una función.

[!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]

El ejemplo siguiente es una expresión lambda que escribe un valor en la consola. En el ejemplo se muestra la sintaxis de expresión lambda de una línea y de varias líneas para una subrutina.

[!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]

Observe que en los ejemplos anteriores las expresiones lambda se asignan a un nombre de variable. Siempre que haga referencia a la variable, se invoca la expresión lambda. También puede declarar e invocar una expresión lambda al mismo tiempo, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]

Una expresión lambda se puede devolver como el valor de una llamada de función (como se muestra en el ejemplo de la sección [Contexto](#context) más adelante en este tema) o pasarse como argumento a un parámetro que toma un tipo de delegado, como se muestra en el ejemplo siguiente.

[!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]

## <a name="lambda-expression-syntax"></a>Sintaxis de la expresión lambda

La sintaxis de una expresión lambda es similar a la de una función o subrutina estándar. Las diferencias son las siguientes:

- Una expresión lambda no tiene un nombre.

- Las expresiones Lambda no `Overloads` pueden `Overrides`tener modificadores, como o .

- Las funciones lambda de `As` una sola línea no utilizan una cláusula para designar el tipo de valor devuelto. En su lugar, el tipo se deduce del valor que evalúa el cuerpo de la expresión lambda. Por ejemplo, si el cuerpo `cust.City = "London"`de la expresión `Boolean`lambda es , su tipo de valor devuelto es .

- En las funciones lambda de varias líneas, puede `As` especificar un `As` tipo de valor devuelto mediante una cláusula u omitir la cláusula para que se deduzcan el tipo de valor devuelto. Cuando `As` se omite la cláusula para una función lambda de varias líneas, se `Return` deduce que el tipo de valor devuelto es el tipo dominante de todas las instrucciones de la función lambda de varias líneas. El *tipo dominante* es un tipo único al que todos los demás tipos pueden ampliarse. Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que pueden restringirse todos los demás tipos de la matriz. Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`. En este caso, `Option Strict` si `On`se establece en , se produce un error del compilador.

     Por ejemplo, si las `Return` expresiones proporcionadas `Integer` `Long`a `Double`la instrucción contienen `Double`valores de tipo , , y , la matriz resultante es de tipo . Tanto `Integer` `Long` y ampliar `Double` a `Double`y sólo . Por lo tanto, `Double` es el tipo dominante. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

- El cuerpo de una función de una sola línea debe ser una expresión que devuelve un valor, no una instrucción. No hay `Return` ninguna instrucción para funciones de una sola línea. El valor devuelto por la función de una sola línea es el valor de la expresión en el cuerpo de la función.

- El cuerpo de una subrutina de una sola línea debe ser una instrucción de una sola línea.

- Las funciones y subrutinas de `End Function` `End Sub` una sola línea no incluyen una instrucción o.

- Puede especificar el tipo de datos de `As` un parámetro de expresión lambda mediante la palabra clave o se puede deducir el tipo de datos del parámetro. Todos los parámetros deben tener tipos de datos especificados o todos deben deducirse.

- `Optional`y `Paramarray` no se permiten parámetros.

- No se permiten parámetros genéricos.

## <a name="async-lambdas"></a>Lambdas asincrónicas

Puede crear fácilmente expresiones lambda e instrucciones que incorporen el procesamiento asincrónico mediante las palabras clave [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [Await Operator.](../../../../visual-basic/language-reference/operators/await-operator.md) Por ejemplo, en el siguiente ejemplo de formularios Windows Forms se incluye un controlador de eventos que llama y espera un método asincrónico, `ExampleMethodAsync`.

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

Puede agregar el mismo controlador de eventos mediante una expresión lambda asincrónica en una [instrucción AddHandler](../../../../visual-basic/language-reference/statements/addhandler-statement.md). Para agregar este controlador, agregue un modificador `Async` antes de la lista de parámetros lambda, como se muestra en el ejemplo siguiente.

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

Para obtener más información acerca de cómo crear y usar métodos asincrónicos, vea [Programación asincrónica con Async y Await](../../../../visual-basic/programming-guide/concepts/async/index.md).

## <a name="context"></a>Context

Una expresión lambda comparte su contexto con el ámbito en el que se define. Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor. Esto incluye el acceso a variables `Me`miembro, funciones y subs, y parámetros y variables locales en el ámbito contenedor.

El acceso a variables y parámetros locales en el ámbito contenedor puede extenderse más allá de la duración de ese ámbito. Siempre que un delegado que hace referencia a una expresión lambda no está disponible para la recolección de elementos no utilizados, se conserva el acceso a las variables en el entorno original. En el ejemplo `target` siguiente, `makeTheGame`variable es local to `playTheGame` , el método en el que se define la expresión lambda. Tenga en cuenta que la `takeAGuess` `Main`expresión lambda devuelta, `target`asignada a , todavía tiene acceso a la variable local .

[!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]

En el ejemplo siguiente se muestra la amplia gama de derechos de acceso de la expresión lambda anidada. Cuando la expresión lambda `Main` devuelta se ejecuta desde as `aDel`, tiene acceso a estos elementos:

- Un campo de la clase en la que se define:`aField`

- Propiedad de la clase en la que se define:`aProp`

- Un parámetro `functionWithNestedLambda`de método, en el que se define:`level1`

- Una variable `functionWithNestedLambda`local de:`localVar`

- Parámetro de la expresión lambda en la que está anidada:`level2`

 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]

## <a name="converting-to-a-delegate-type"></a>Convertir a un tipo de delegado

Una expresión lambda se puede convertir implícitamente en un tipo de delegado compatible. Para obtener información sobre los requisitos generales de compatibilidad, vea [Conversión de delegados relajadas](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md). Por ejemplo, en el ejemplo de código siguiente `Func(Of Integer, Boolean)` se muestra una expresión lambda que se convierte implícitamente en o una firma de delegado coincidente.

[!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]

En el ejemplo de código siguiente se `Sub(Of Double, String, Double)` muestra una expresión lambda que se convierte implícitamente en o una firma de delegado coincidente.

[!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]

Al asignar expresiones lambda a delegados o pasarlas como argumentos a procedimientos, puede especificar los nombres de parámetro pero omitir sus tipos de datos, lo que permite que los tipos se tomen del delegado.

## <a name="examples"></a>Ejemplos

- En el ejemplo siguiente se `True` define una expresión lambda que devuelve `False` si el `Nothing`argumento de tipo de valor que acepta valores NULL tiene un valor asignado y si su valor es .

     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]

- En el ejemplo siguiente se define una expresión lambda que devuelve el índice del último elemento de una matriz.

     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]

## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Instrucción Function](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Instrucción Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Tipos de valores que aceptan valores NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Procedimiento para crear una expresión lambda](./how-to-create-a-lambda-expression.md)
- [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
