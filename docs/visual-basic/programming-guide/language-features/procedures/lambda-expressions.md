---
title: "Lambda (expresiones) (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.LambdaFunction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "expresiones [Visual Basic], lambda"
  - "funciones [Visual Basic], expresiones lambda"
  - "inline (funciones) [Visual Basic]"
  - "lambda (expresiones) [Visual Basic]"
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 52
---
# Lambda (expresiones) (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una *expresión lambda* es una función o una subrutina sin nombre que se puede utilizar donde haya un delegado válido.  Las expresiones lambda pueden ser funciones o subrutinas y tener una sola línea o varias líneas.  Puede pasar valores del ámbito actual a una expresión lambda.  
  
> [!NOTE]
>  La instrucción `RemoveHandler` es una excepción.  No puede pasar ninguna expresión lambda para el parámetro de delegado de `RemoveHandler`.  
  
 Las expresiones lambda se crean utilizando la palabra clave `Function` o `Sub`, del mismo modo que se crea una subrutina o función estándar.  Sin embargo, las expresiones lambda van incluidas en una instrucción.  
  
 El ejemplo siguiente es una expresión lambda que incrementa su argumento y devuelve el valor.  En el ejemplo se muestra la sintaxis de expresiones lambda de una sola línea y de varias líneas para una función.  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 El ejemplo siguiente es una expresión lambda que escribe un valor en la consola.  En el ejemplo se muestra la sintaxis de expresiones lambda de una sola línea y de varias líneas para una subrutina.  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 Observe que en los ejemplos anteriores las expresiones lambda se asignan a un nombre de variable.  Cada vez que se hace referencia a la variable, se invoca la expresión lambda.  También se puede declarar e invocar una expresión lambda al mismo tiempo, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 Una expresión lambda se puede devolver como el valor de una llamada de función \(como se muestra en el ejemplo de la sección [Contexto](#context) más adelante en este tema\) o se puede pasar como argumento a un parámetro que toma un tipo delegado, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## Sintaxis de la expresión lambda  
 La sintaxis de una expresión lambda se parece a la de una subrutina o función estándar.  Las diferencias son las siguientes:  
  
-   Una expresión lambda no tiene nombre.  
  
-   Las expresiones lambda no pueden tener modificadores, como `Overloads` u `Overrides`.  
  
-   Las funciones lambda de una sola línea no utilizan una cláusula `As` para designar el tipo de valor devuelto.  En su lugar, el tipo se deduce del valor en el que se evalúa el cuerpo de la expresión lambda.  Por ejemplo, si el cuerpo de la expresión lambda es `cust.City = "London"`, su tipo de valor devuelto es `Boolean`.  
  
-   En funciones de varias líneas, se puede especificar un tipo de valor devuelto utilizando una cláusula `As` u omitir la cláusula `As` para que se deduzca el tipo de valor devuelto.  Cuando la cláusula `As` se omite para una función lambda de varias líneas, el tipo de valor devuelto se deduce para que sea el tipo dominante de todas las instrucciones `Return` en la función lambda de varias líneas.  El  *tipo dominante* es un tipo único que pueden ampliar todos los demás tipos.  Si no se puede determinar este tipo único, el tipo dominante es el tipo único al que todos los demás tipos de la matriz se pueden restringir.  Si no se puede determinar ninguno de estos tipos únicos, el tipo dominante es `Object`.  En este caso, si `Option Strict` está establecido en `On`, se produce un error del compilador.  
  
     Por ejemplo, si las expresiones suministrado a la `Return` instrucción contienen valores de tipo `Integer`, `Long`, y `Double`, la matriz resultante es de tipo `Double`.  Tanto `Integer` como `Long` se amplían a `Double` y sólo `Double`.  Por consiguiente, `Double` es el tipo dominante.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
-   El cuerpo de una función de una sola línea debe ser una expresión que devuelva un valor, no una instrucción.  No hay ninguna instrucción `Return` para las funciones de una sola línea.  El valor devuelto por la función de una sola línea es el valor de la expresión del cuerpo de la función.  
  
-   El cuerpo de una subrutina de una sola línea debe ser una instrucción de una sola línea.  
  
-   Las subrutinas y funciones de una sola línea no incluyen una instrucción `End Sub` o `End Function`.  
  
-   Puede especificar el tipo de datos de un parámetro de expresión lambda utilizando la palabra clave `As`, o se puede deducir el tipo de datos del parámetro.  Todos los parámetros deben de tener tipos de datos especificados o se deben deducir.  
  
-   No se permiten los parámetros `Optional` y `Paramarray`.  
  
-   No se permiten los parámetros Generic.  
  
## Lambdas de Async  
 Puede crear fácilmente las expresiones lambda y las instrucciones que incorporan el procesamiento asincrónico mediante el uso de la [Async](../../../../visual-basic/language-reference/modifiers/async.md) y [Await \(Operador\)](../../../../visual-basic/language-reference/operators/await-operator.md) palabras clave.  Por ejemplo, el siguiente ejemplo de formularios Windows Forms contiene un controlador de eventos que llama y espera a que un método asincrónico, `ExampleMethodAsync`.  
  
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
  
 Puede agregar el mismo controlador de eventos mediante una lambda asincrónica en un [AddHandler \(Instrucción\)](../../../../visual-basic/language-reference/statements/addhandler-statement.md).  Para agregar este controlador, agregue un `Async` modificador antes de la lista de parámetros de la lambda, como se muestra en el ejemplo siguiente.  
  
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
  
 Para obtener más información acerca de cómo crear y utilizar los métodos de async, consulte [Programación asincrónica con Async y Await](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md).  
  
##  <a name="context"></a> Contexto  
 Una expresión lambda comparte su contexto con el ámbito en el que se define.  Tiene los mismos derechos de acceso que cualquier código escrito en el ámbito contenedor.  Esto incluye el acceso a las variables miembro, funciones y subrutinas, `Me`, así como a los parámetros y las variables locales del ámbito contenedor.  
  
 El acceso a las variables locales y a los parámetros del ámbito contenedor se puede ampliar una vez transcurrida la duración de dicho ámbito.  En tanto que un delegado que hace referencia a una expresión lambda no esté disponible para la recolección de elementos no utilizados, se conserva el acceso a las variables del entorno original.  En el ejemplo siguiente, la variable `target` es local respecto a `makeTheGame`, el método en el que se define la expresión lambda `playTheGame`.  Observe que la expresión lambda devuelta, asignada a `takeAGuess` en `Main`, todavía tiene acceso a la variable local `target`.  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 El ejemplo siguiente muestra la amplia gama de derechos de acceso de la expresión lambda anidada.  Cuando la expresión lambda devuelta se ejecuta desde `Main` como `aDel`, tiene acceso a estos elementos:  
  
-   Un campo de la clase en la que se define: `aField`  
  
-   Una propiedad de la clase en la que se define: `aProp`  
  
-   Un parámetro de método `functionWithNestedLambda` en el que se define: `level1`  
  
-   Una variable local de `functionWithNestedLambda`: `localVar`  
  
-   Un parámetro de la expresión lambda en la que está anidada: `level2`  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## Convertir en un tipo de delegado  
 Una expresión lambda se puede convertir implícitamente en un tipo de delegado compatible.  Para obtener información sobre los requisitos generales de compatibilidad, vea [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  Por ejemplo, en el ejemplo de código siguiente se muestra una expresión lambda que se convierte implícitamente a `Func(Of Integer, Boolean)` o una firma de delegado correspondiente.  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 En el ejemplo de código siguiente, se muestra una expresión lambda que se convierte implícitamente a `Sub(Of Double, String, Double)` o una firma de delegado correspondiente.  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 Cuando se asignan expresiones lambda a delegados o se pasan como argumentos a procedimientos, se pueden especificar los nombres de parámetro pero omitir sus tipos de datos, permitiendo que los tipos se tomen del delegado.  
  
## Ejemplos  
  
-   El ejemplo siguiente define una expresión lambda que devuelve `True` si el argumento que acepta valores NULL tiene un valor asignado y `False` si su valor es `Nothing`.  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   El ejemplo siguiente define una expresión lambda que devuelve el índice del último elemento de una matriz.  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Function \(Instrucción\)](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Tipos de valor que aceptan valores NULL](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Cómo: Pasar procedimientos a otro procedimiento en Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Cómo: Crear una expresión lambda](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-lambda-expression.md)   
 [Conversión de delegado flexible](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)