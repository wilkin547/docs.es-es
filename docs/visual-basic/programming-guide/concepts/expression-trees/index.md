---
title: Árboles de expresión
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: 29f2545a3bc1d53e8ab28478f63ef7b0dfe7a15e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075413"
---
# <a name="expression-trees-visual-basic"></a>Árboles de expresión (Visual Basic)

Los árboles de expresión representan el código en una estructura de datos en forma de árbol donde cada nodo es una expresión, por ejemplo, una llamada a método o una operación binaria como `x < y`.  
  
 El código representado en árboles de expresión se puede compilar y ejecutar. Esto permite realizar cambios dinámicos en el código ejecutable, ejecutar consultas LINQ en varias bases de datos y crear consultas dinámicas. Para obtener más información sobre los árboles de expresión en LINQ, consulte [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](how-to-use-expression-trees-to-build-dynamic-queries.md) (Usar árboles de expresión para generar consultas dinámicas en Visual Basic).  
  
 Los árboles de expresión también se usan en Dynamic Language Runtime (DLR) para proporcionar interoperabilidad entre los lenguajes dinámicos y .NET Framework y, asimismo, para permitir que los programadores de compiladores emitan árboles de expresión en lugar de Lenguaje intermedio de Microsoft (MSIL). Para obtener más información sobre el entorno DLR, vea [Información general acerca de Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).  
  
 Puede hacer que el compilador de Visual Basic o de C# cree un árbol de expresión en función de una expresión lambda anónima, o bien puede crear árboles de expresión manualmente usando el espacio de nombres <xref:System.Linq.Expressions>.  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a>Crear árboles de expresión a partir de expresiones lambda  

 Cuando una expresión lambda se asigna a una variable de tipo <xref:System.Linq.Expressions.Expression%601>, el compilador emite código para crear un árbol de expresión que represente la expresión lambda.  
  
 El compilador de Visual Basic puede generar árboles de expresión solo a partir de lambdas de expresión (o de lambdas de una sola línea). No pueden analizar lambdas de instrucción (o lambdas de varias líneas). Para obtener más información sobre las expresiones lambda en Visual Basic, consulte [Expresiones lambda](../../language-features/procedures/lambda-expressions.md).  
  
 Los siguientes ejemplos de código muestran cómo crear un árbol de expresión que represente la expresión lambda `Function(num) num < 5` con el compilador de Visual Basic.  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a>Crear árboles de expresión mediante la API  

 Para crear árboles de expresión mediante la API, use la clase <xref:System.Linq.Expressions.Expression>. Esta clase contiene métodos de fábrica estáticos que crean nodos de árbol de expresión de tipos específicos, como, por ejemplo, <xref:System.Linq.Expressions.ParameterExpression>, que representa una variable o un parámetro, o <xref:System.Linq.Expressions.MethodCallExpression>, que representa una llamada a método. <xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> y los demás tipos específicos de expresión también se definen en el espacio de nombres <xref:System.Linq.Expressions>. Estos tipos se derivan del tipo abstracto <xref:System.Linq.Expressions.Expression>.  
  
 En el siguiente ejemplo de código se muestra cómo crear un árbol de expresión que represente la expresión lambda `Function(num) num < 5` mediante la API.  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Manually build the expression tree for the lambda expression num => num < 5.  
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")  
Dim five As ConstantExpression = Expression.Constant(5, GetType(Integer))  
Dim numLessThanFive As BinaryExpression = Expression.LessThan(numParam, five)  
Dim lambda1 As Expression(Of Func(Of Integer, Boolean)) =  
  Expression.Lambda(Of Func(Of Integer, Boolean))(  
        numLessThanFive,  
        New ParameterExpression() {numParam})  
```  
  
 En .NET Framework 4 y versiones posteriores, la API de árboles de expresión admite también asignaciones y expresiones de flujo de control como bucles, bloques condicionales y bloques `try-catch`. Con la API, se pueden crear árboles de expresión más complejos que los que pueden crear el compilador de Visual Basic a partir de expresiones lambda. En el siguiente ejemplo se indica cómo crear un árbol de expresión que calcula el factorial de un número.  
  
```vb  
' Creating a parameter expression.  
Dim value As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "value")  
  
' Creating an expression to hold a local variable.
Dim result As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "result")  
  
' Creating a label to jump to from a loop.  
Dim label As LabelTarget = Expression.Label(GetType(Integer))  
  
' Creating a method body.  
Dim block As BlockExpression = Expression.Block(  
    New ParameterExpression() {result},  
    Expression.Assign(result, Expression.Constant(1)),  
    Expression.Loop(  
        Expression.IfThenElse(  
            Expression.GreaterThan(value, Expression.Constant(1)),  
            Expression.MultiplyAssign(result,  
                Expression.PostDecrementAssign(value)),  
            Expression.Break(label, result)  
        ),  
        label  
    )  
)  
  
' Compile an expression tree and return a delegate.  
Dim factorial As Integer =  
    Expression.Lambda(Of Func(Of Integer, Integer))(block, value).Compile()(5)  
  
Console.WriteLine(factorial)  
' Prints 120.  
```

Para obtener más información, consulte [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/) (Generar métodos dinámicos con árboles de expresión en Visual Studio 2010), que también se aplica a las últimas versiones de Visual Studio.
  
## <a name="parsing-expression-trees"></a>Analizar árboles de expresión  

 En el siguiente ejemplo de código se muestra cómo la expresión del árbol que representa la expresión lambda `Function(num) num < 5` se puede descomponer en partes.  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Create an expression tree.  
Dim exprTree As Expression(Of Func(Of Integer, Boolean)) = Function(num) num < 5  
  
' Decompose the expression tree.  
Dim param As ParameterExpression = exprTree.Parameters(0)  
Dim operation As BinaryExpression = exprTree.Body  
Dim left As ParameterExpression = operation.Left  
Dim right As ConstantExpression = operation.Right  
  
Console.WriteLine(String.Format("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value))  
  
' This code produces the following output:  
'  
' Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a>Inmutabilidad de los árboles de expresión  

 Los árboles de expresión deben ser inmutables. Esto significa que, si desea modificar un árbol de expresión, deberá construir un nuevo árbol de expresión copiando el ya existente y reemplazando los nodos que hay en él. Puede usar un visitante de árbol de expresión para recorrer el árbol de expresión existente. Para obtener más información, consulte [How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md) (Cómo modificar árboles de expresión en Visual Basic).  
  
## <a name="compiling-expression-trees"></a>Compilar árboles de expresión  

 El tipo <xref:System.Linq.Expressions.Expression%601> proporciona el método <xref:System.Linq.Expressions.Expression%601.Compile%2A> que compila el código representado por un árbol de expresión en un delegado ejecutable.  
  
 En el siguiente ejemplo de código se indica cómo compilar un árbol de expresión y ejecutar el código resultante.  
  
```vb  
' Creating an expression tree.  
Dim expr As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
  
' Compiling the expression tree into a delegate.  
Dim result As Func(Of Integer, Boolean) = expr.Compile()  
  
' Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4))  
  
' Prints True.  
  
' You can also use simplified syntax  
' to compile and run an expression tree.  
' The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4))  
  
' Also prints True.  
```  
  
 Para obtener más información, consulte [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq.Expressions>
- [How to: Execute Expression Trees (Visual Basic)](how-to-execute-expression-trees.md) (Cómo ejecutar árboles de expresión en Visual Basic)
- [How to: Modify Expression Trees (Visual Basic)](how-to-modify-expression-trees.md) (Cómo modificar árboles de expresión en Visual Basic)
- [Expresiones lambda](../../language-features/procedures/lambda-expressions.md)
- [Información general sobre Dynamic Language Runtime](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [Conceptos de programación (Visual Basic)](../index.md)
