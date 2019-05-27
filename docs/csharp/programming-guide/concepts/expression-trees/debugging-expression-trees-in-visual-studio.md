---
title: Depuración de árboles de expresión en Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 4017e2c2592dc1d6067b428fc1d47f37775abf85
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877134"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="6c65b-102">Depuración de árboles de expresión en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="6c65b-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="6c65b-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6c65b-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="6c65b-104">Para obtener una introducción rápida a la estructura del árbol de expresión, puede usar la propiedad `DebugView`, que representa los árboles de expresión con una sintaxis especial que se describe [a continuación](#debugview-syntax).</span><span class="sxs-lookup"><span data-stu-id="6c65b-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees using a special syntax described [below](#debugview-syntax).</span></span> <span data-ttu-id="6c65b-105">Observe que `DebugView` solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="6c65b-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView de árbol de expresión en el depurador de Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

<span data-ttu-id="6c65b-107">Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="6c65b-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizador de texto aplicado a los resultados de "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

<span data-ttu-id="6c65b-109">Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) para árboles de expresión:</span><span class="sxs-lookup"><span data-stu-id="6c65b-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees:</span></span>

* <span data-ttu-id="6c65b-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C#:</span><span class="sxs-lookup"><span data-stu-id="6c65b-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizador Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="6c65b-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licencia MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), proporciona una vista gráfica del árbol de expresión, sus propiedades y los objetos relacionados:</span><span class="sxs-lookup"><span data-stu-id="6c65b-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects:</span></span>

  ![Visualizador ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="6c65b-114">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="6c65b-115">Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="6c65b-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="6c65b-116">Se muestra una lista de los visualizadores disponibles:</span><span class="sxs-lookup"><span data-stu-id="6c65b-116">A list of available visualizers is displayed.:</span></span> 

      ![Apertura de visualizadores desde Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. <span data-ttu-id="6c65b-118">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="6c65b-118">Click the visualizer you want to use.</span></span>  

## <a name="debugview-syntax"></a><span data-ttu-id="6c65b-119">Sintaxis de `DebugView`</span><span class="sxs-lookup"><span data-stu-id="6c65b-119">`DebugView` syntax</span></span> 

<span data-ttu-id="6c65b-120">Cada tipo de expresión se muestra mediante la propiedad `DebugView`, como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6c65b-120">Each expression type is displayed by the `DebugView` property as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="6c65b-121">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="6c65b-121">ParameterExpressions</span></span>  
 <span data-ttu-id="6c65b-122">Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.</span><span class="sxs-lookup"><span data-stu-id="6c65b-122"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="6c65b-123">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="6c65b-123">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6c65b-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6c65b-124">Examples</span></span>  
  
|<span data-ttu-id="6c65b-125">Expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-125">Expression</span></span>|<span data-ttu-id="6c65b-126">Propiedad`DebugView` </span><span class="sxs-lookup"><span data-stu-id="6c65b-126">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="6c65b-127">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="6c65b-127">ConstantExpressions</span></span>  
 <span data-ttu-id="6c65b-128">Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="6c65b-128">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="6c65b-129">Para los tipos numéricos que tienen sufijos estándar como literales de C#, el sufijo se agrega al valor.</span><span class="sxs-lookup"><span data-stu-id="6c65b-129">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="6c65b-130">En la tabla siguiente se muestran los sufijos asociados a varios tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="6c65b-130">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="6c65b-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c65b-131">Type</span></span>|<span data-ttu-id="6c65b-132">Sufijo</span><span class="sxs-lookup"><span data-stu-id="6c65b-132">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="6c65b-133">U</span><span class="sxs-lookup"><span data-stu-id="6c65b-133">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="6c65b-134">L</span><span class="sxs-lookup"><span data-stu-id="6c65b-134">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="6c65b-135">UL</span><span class="sxs-lookup"><span data-stu-id="6c65b-135">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="6c65b-136">D</span><span class="sxs-lookup"><span data-stu-id="6c65b-136">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="6c65b-137">F</span><span class="sxs-lookup"><span data-stu-id="6c65b-137">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="6c65b-138">M</span><span class="sxs-lookup"><span data-stu-id="6c65b-138">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="6c65b-139">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6c65b-139">Examples</span></span>  
  
|<span data-ttu-id="6c65b-140">Expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-140">Expression</span></span>|<span data-ttu-id="6c65b-141">Propiedad`DebugView` </span><span class="sxs-lookup"><span data-stu-id="6c65b-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="6c65b-142">10</span><span class="sxs-lookup"><span data-stu-id="6c65b-142">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="6c65b-143">10D</span><span class="sxs-lookup"><span data-stu-id="6c65b-143">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="6c65b-144">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="6c65b-144">BlockExpression</span></span>  
 <span data-ttu-id="6c65b-145">Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra en la propiedad `DebugInfo` entre corchetes angulares (\< y >).</span><span class="sxs-lookup"><span data-stu-id="6c65b-145">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="6c65b-146">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="6c65b-146">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6c65b-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6c65b-147">Examples</span></span>  
  
|<span data-ttu-id="6c65b-148">Expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-148">Expression</span></span>|<span data-ttu-id="6c65b-149">Propiedad`DebugView` </span><span class="sxs-lookup"><span data-stu-id="6c65b-149">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="6c65b-150">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="6c65b-150">LambdaExpression</span></span>  
 <span data-ttu-id="6c65b-151">Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="6c65b-151"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="6c65b-152">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="6c65b-152">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6c65b-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6c65b-153">Examples</span></span>  
  
|<span data-ttu-id="6c65b-154">Expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-154">Expression</span></span>|<span data-ttu-id="6c65b-155">Propiedad`DebugView` </span><span class="sxs-lookup"><span data-stu-id="6c65b-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="6c65b-156">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="6c65b-156">LabelExpression</span></span>  
 <span data-ttu-id="6c65b-157">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="6c65b-157">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="6c65b-158">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6c65b-158">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="6c65b-159">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="6c65b-159">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="6c65b-160">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="6c65b-160">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6c65b-161">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6c65b-161">Examples</span></span>  
  
|<span data-ttu-id="6c65b-162">Expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-162">Expression</span></span>|<span data-ttu-id="6c65b-163">Propiedad`DebugView` </span><span class="sxs-lookup"><span data-stu-id="6c65b-163">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="6c65b-164">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="6c65b-164">Checked Operators</span></span>  
 <span data-ttu-id="6c65b-165">Los operadores activados se muestran con el símbolo "#" delante del operador.</span><span class="sxs-lookup"><span data-stu-id="6c65b-165">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="6c65b-166">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="6c65b-166">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="6c65b-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6c65b-167">Examples</span></span>  
  
|<span data-ttu-id="6c65b-168">Expresión</span><span class="sxs-lookup"><span data-stu-id="6c65b-168">Expression</span></span>|<span data-ttu-id="6c65b-169">Propiedad`DebugView` </span><span class="sxs-lookup"><span data-stu-id="6c65b-169">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="6c65b-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c65b-170">See also</span></span>

- [<span data-ttu-id="6c65b-171">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="6c65b-171">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="6c65b-172">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6c65b-172">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- <span data-ttu-id="6c65b-173">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="6c65b-173">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
