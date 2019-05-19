---
title: Depuración de árboles de expresión en Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879831"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Depuración de árboles de expresión en Visual Studio (Visual Basic)
Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones. Para obtener una descripción general de la estructura de árbol de expresión, puede usar el `DebugView` propiedad, que se representa mediante una sintaxis especial que se describen los árboles de expresión [debajo](#debugview-syntax). (Tenga en cuenta que `DebugView` solo está disponible en modo de depuración.)  

![DebugView de árbol de expresión en el depurador de Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

Puesto que `DebugView` es una cadena, puede usar el [integrados visualizador de texto](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verlo en varias líneas, seleccionando **visualizador de texto** desde el icono de lupa junto a la `DebugView` etiqueta.

 ![Visualizador de texto que se aplica a los resultados de 'DebugView'](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) árboles de expresiones:

* [Expresiones legibles](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en el [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como C# código:

  ![Visualizador de expresiones legible](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [Visualizador de árboles de expresión](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licencia MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), proporciona una vista gráfica del árbol de expresión, sus propiedades y objetos relacionados; y puede representar el árbol de expresión mediante código de Visual Basic:

  ![Visualizador de ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Para abrir un visualizador para un árbol de expresión  
  
1. Haga clic en el icono de lupa que aparece junto a en el árbol de expresión **DataTips**, un **inspección** ventana, el **automático** ventana, o el **devariableslocales** ventana.  
  
     Se muestra una lista de visualizadores disponibles.: 

      ![Visualizadores de apertura de Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. Haga clic en el visualizador que desee usar.  

## <a name="debugview-syntax"></a>`DebugView` Sintaxis 

Cada tipo de expresión se muestra en el visualizador como se describe en las secciones siguientes.

## <a name="parameterexpressions"></a>ParameterExpressions

Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.

Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.

### <a name="examples"></a>Ejemplos

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    Propiedad `DebugView`

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    Propiedad `DebugView`

    `$var1`

## <a name="constantexpressions"></a>ConstantExpressions
 Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.

### <a name="examples"></a>Ejemplos

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    Propiedad `DebugView`

    10

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    Propiedad `DebugView`

    10D

## <a name="blockexpression"></a>BlockExpression

Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra en la propiedad `DebugInfo` entre corchetes angulares (\< y >). De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.

### <a name="examples"></a>Ejemplos

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    Propiedad `DebugView`

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    Propiedad `DebugView`

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a>LambdaExpression

Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.

Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.

### <a name="examples"></a>Ejemplos

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    Propiedad `DebugView`

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    Propiedad `DebugView`

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a>LabelExpression

Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.

El token `.Label` indica el inicio de la etiqueta. El token `.LabelTarget` indica el destino al que se va a saltar.

Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.

### <a name="examples"></a>Ejemplos

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    Propiedad `DebugView`

    `.Block() {`

    `.Goto SampleLabel { 0 };`

    `.Label`

    `-1`

    `.LabelTarget SampleLabel:`

    `}`

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label()
    Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target), Expression.Label(target))
    ```

    Propiedad `DebugView`

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a>Operadores activados

Los operadores activados se muestran con el símbolo "#" delante del operador. Por ejemplo, el operador de adición activado se muestra como `#+`.

### <a name="examples"></a>Ejemplos

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    Propiedad `DebugView`

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    Propiedad `DebugView`

    `#(System.Int32)10D`

## <a name="see-also"></a>Vea también

- [Árboles de expresión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Depurar en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)
