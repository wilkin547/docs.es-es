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
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="25056-102">Depuración de árboles de expresión en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25056-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="25056-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="25056-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="25056-104">Para obtener una descripción general de la estructura de árbol de expresión, puede usar el `DebugView` propiedad, que se representa mediante una sintaxis especial que se describen los árboles de expresión [debajo](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="25056-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="25056-105">(Tenga en cuenta que `DebugView` solo está disponible en modo de depuración.)</span><span class="sxs-lookup"><span data-stu-id="25056-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView de árbol de expresión en el depurador de Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="25056-107">Puesto que `DebugView` es una cadena, puede usar el [integrados visualizador de texto](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verlo en varias líneas, seleccionando **visualizador de texto** desde el icono de lupa junto a la `DebugView` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="25056-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizador de texto que se aplica a los resultados de 'DebugView'](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="25056-109">Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) árboles de expresiones:</span><span class="sxs-lookup"><span data-stu-id="25056-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="25056-110">[Expresiones legibles](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en el [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como C# código:</span><span class="sxs-lookup"><span data-stu-id="25056-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizador de expresiones legible](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="25056-112">[Visualizador de árboles de expresión](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licencia MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), proporciona una vista gráfica del árbol de expresión, sus propiedades y objetos relacionados; y puede representar el árbol de expresión mediante código de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="25056-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Visualizador de ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="25056-114">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="25056-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="25056-115">Haga clic en el icono de lupa que aparece junto a en el árbol de expresión **DataTips**, un **inspección** ventana, el **automático** ventana, o el **devariableslocales** ventana.</span><span class="sxs-lookup"><span data-stu-id="25056-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="25056-116">Se muestra una lista de visualizadores disponibles.:</span><span class="sxs-lookup"><span data-stu-id="25056-116">A list of available visualizers is displayed.:</span></span> 

      ![Visualizadores de apertura de Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="25056-118">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="25056-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="25056-119">`DebugView` Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25056-119">`DebugView` syntax</span></span> 

<span data-ttu-id="25056-120">Cada tipo de expresión se muestra en el visualizador como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="25056-120">Each expression type is displayed in the visualizer as described in the following sections.</span></span>

## <a name="parameterexpressions"></a><span data-ttu-id="25056-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="25056-121">ParameterExpressions</span></span>

<span data-ttu-id="25056-122">Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.</span><span class="sxs-lookup"><span data-stu-id="25056-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="25056-123">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="25056-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="25056-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25056-124">Examples</span></span>

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    <span data-ttu-id="25056-125">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-125">`DebugView` property</span></span>

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    <span data-ttu-id="25056-126">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-126">`DebugView` property</span></span>

    `$var1`

## <a name="constantexpressions"></a><span data-ttu-id="25056-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="25056-127">ConstantExpressions</span></span>
 <span data-ttu-id="25056-128">Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="25056-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="25056-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25056-129">Examples</span></span>

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="25056-130">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-130">`DebugView` property</span></span>

    <span data-ttu-id="25056-131">10</span><span class="sxs-lookup"><span data-stu-id="25056-131">10</span></span>

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    <span data-ttu-id="25056-132">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-132">`DebugView` property</span></span>

    <span data-ttu-id="25056-133">10D</span><span class="sxs-lookup"><span data-stu-id="25056-133">10D</span></span>

## <a name="blockexpression"></a><span data-ttu-id="25056-134">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="25056-134">BlockExpression</span></span>

<span data-ttu-id="25056-135">Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra en la propiedad `DebugInfo` entre corchetes angulares (\< y >).</span><span class="sxs-lookup"><span data-stu-id="25056-135">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="25056-136">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="25056-136">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="25056-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25056-137">Examples</span></span>

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    <span data-ttu-id="25056-138">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-138">`DebugView` property</span></span>

    `.Block() {`

    `"test"`

    `}`

- `Expression`

    ```vb
    Dim block As BlockExpression =
    Expression.Block(GetType(Object), Expression.Constant("test"))
    ```

    <span data-ttu-id="25056-139">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-139">`DebugView` property</span></span>

    `.Block<System.Object>() {`

    `"test"`

    `}`

## <a name="lambdaexpression"></a><span data-ttu-id="25056-140">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="25056-140">LambdaExpression</span></span>

<span data-ttu-id="25056-141">Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="25056-141"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="25056-142">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="25056-142">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="25056-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25056-143">Examples</span></span>

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    <span data-ttu-id="25056-144">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-144">`DebugView` property</span></span>

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
    ```

    <span data-ttu-id="25056-145">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-145">`DebugView` property</span></span>

    `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`

    `1`

    `}`

## <a name="labelexpression"></a><span data-ttu-id="25056-146">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="25056-146">LabelExpression</span></span>

<span data-ttu-id="25056-147">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="25056-147">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="25056-148">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="25056-148">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="25056-149">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="25056-149">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="25056-150">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="25056-150">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="25056-151">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25056-151">Examples</span></span>

- `Expression`

    ```vb
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
    Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1)))
    ```

    <span data-ttu-id="25056-152">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-152">`DebugView` property</span></span>

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

    <span data-ttu-id="25056-153">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-153">`DebugView` property</span></span>

    `.Block() {`

    `.Goto #Label1 { };`

    `.Label`

    `.LabelTarget #Label1:`

    `}`

## <a name="checked-operators"></a><span data-ttu-id="25056-154">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="25056-154">Checked Operators</span></span>

<span data-ttu-id="25056-155">Los operadores activados se muestran con el símbolo "#" delante del operador.</span><span class="sxs-lookup"><span data-stu-id="25056-155">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="25056-156">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="25056-156">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="25056-157">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="25056-157">Examples</span></span>

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    <span data-ttu-id="25056-158">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-158">`DebugView` property</span></span>

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    <span data-ttu-id="25056-159">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="25056-159">`DebugView` property</span></span>

    `#(System.Int32)10D`

## <a name="see-also"></a><span data-ttu-id="25056-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="25056-160">See also</span></span>

- [<span data-ttu-id="25056-161">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25056-161">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="25056-162">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="25056-162">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- <span data-ttu-id="25056-163">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="25056-163">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
