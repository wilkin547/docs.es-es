---
title: "Depuración de árboles de expresión en Visual Studio (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0cf40b38ca9a6f743aca2894506e1d0ea80c9d57
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="ceecc-102">Depuración de árboles de expresión en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="ceecc-102">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="ceecc-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ceecc-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="ceecc-104">Para obtener una introducción rápida de la estructura de árbol de expresión, puede usar la propiedad `DebugView`, que solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="ceecc-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which is available only in debug mode.</span></span> <span data-ttu-id="ceecc-105">Para más información sobre la depuración, vea [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) (Depuración en Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="ceecc-105">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).</span></span>  
  
 <span data-ttu-id="ceecc-106">Para representar mejor el contenido de árboles de expresión, la propiedad `DebugView` usa los visualizadores de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ceecc-106">To better represent the content of expression trees, the `DebugView` property uses Visual Studio visualizers.</span></span> <span data-ttu-id="ceecc-107">Para obtener más información, vea [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados).</span><span class="sxs-lookup"><span data-stu-id="ceecc-107">For more information, see [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data).</span></span>  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="ceecc-108">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-108">To open a visualizer for an expression tree</span></span>  
  
1.  <span data-ttu-id="ceecc-109">Haga clic en el icono de lupa que aparece junto a la propiedad `DebugView` de un árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="ceecc-109">Click the magnifying glass icon that appears next to the `DebugView` property of an expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="ceecc-110">Se mostrará una lista de visualizadores.</span><span class="sxs-lookup"><span data-stu-id="ceecc-110">A list of visualizers is displayed.</span></span>  
  
2.  <span data-ttu-id="ceecc-111">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="ceecc-111">Click the visualizer you want to use.</span></span>  
  
 <span data-ttu-id="ceecc-112">Cada tipo de expresión se muestra en el visualizador como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ceecc-112">Each expression type is displayed in the visualizer as described in the following sections.</span></span>  
  
## <a name="parameterexpressions"></a><span data-ttu-id="ceecc-113">ParameterExpressions</span><span class="sxs-lookup"><span data-stu-id="ceecc-113">ParameterExpressions</span></span>  
 <span data-ttu-id="ceecc-114">Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.</span><span class="sxs-lookup"><span data-stu-id="ceecc-114"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>  
  
 <span data-ttu-id="ceecc-115">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="ceecc-115">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ceecc-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ceecc-116">Examples</span></span>  
  
|<span data-ttu-id="ceecc-117">Expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-117">Expression</span></span>|<span data-ttu-id="ceecc-118">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ceecc-118">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");`|`$num`|  
|`ParameterExpression numParam =  Expression.Parameter(typeof(int));`|`$var1`|  
  
## <a name="constantexpressions"></a><span data-ttu-id="ceecc-119">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="ceecc-119">ConstantExpressions</span></span>  
 <span data-ttu-id="ceecc-120">Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="ceecc-120">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>  
  
 <span data-ttu-id="ceecc-121">Para los tipos numéricos que tienen sufijos estándar como literales de C#, el sufijo se agrega al valor.</span><span class="sxs-lookup"><span data-stu-id="ceecc-121">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="ceecc-122">En la tabla siguiente se muestran los sufijos asociados a varios tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="ceecc-122">The following table shows the suffixes associated with various numeric types.</span></span>  
  
|<span data-ttu-id="ceecc-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="ceecc-123">Type</span></span>|<span data-ttu-id="ceecc-124">Sufijo</span><span class="sxs-lookup"><span data-stu-id="ceecc-124">Suffix</span></span>|  
|----------|------------|  
|<xref:System.UInt32>|<span data-ttu-id="ceecc-125">U</span><span class="sxs-lookup"><span data-stu-id="ceecc-125">U</span></span>|  
|<xref:System.Int64>|<span data-ttu-id="ceecc-126">L</span><span class="sxs-lookup"><span data-stu-id="ceecc-126">L</span></span>|  
|<xref:System.UInt64>|<span data-ttu-id="ceecc-127">UL</span><span class="sxs-lookup"><span data-stu-id="ceecc-127">UL</span></span>|  
|<xref:System.Double>|<span data-ttu-id="ceecc-128">D</span><span class="sxs-lookup"><span data-stu-id="ceecc-128">D</span></span>|  
|<xref:System.Single>|<span data-ttu-id="ceecc-129">F</span><span class="sxs-lookup"><span data-stu-id="ceecc-129">F</span></span>|  
|<xref:System.Decimal>|<span data-ttu-id="ceecc-130">M</span><span class="sxs-lookup"><span data-stu-id="ceecc-130">M</span></span>|  
  
### <a name="examples"></a><span data-ttu-id="ceecc-131">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ceecc-131">Examples</span></span>  
  
|<span data-ttu-id="ceecc-132">Expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-132">Expression</span></span>|<span data-ttu-id="ceecc-133">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ceecc-133">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`int num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="ceecc-134">10</span><span class="sxs-lookup"><span data-stu-id="ceecc-134">10</span></span>|  
|`double num = 10; ConstantExpression expr = Expression.Constant(num);`|<span data-ttu-id="ceecc-135">10D</span><span class="sxs-lookup"><span data-stu-id="ceecc-135">10D</span></span>|  
  
## <a name="blockexpression"></a><span data-ttu-id="ceecc-136">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="ceecc-136">BlockExpression</span></span>  
 <span data-ttu-id="ceecc-137">Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra en la propiedad `DebugInfo` entre corchetes angulares (\< y >).</span><span class="sxs-lookup"><span data-stu-id="ceecc-137">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed in the `DebugInfo` property in angle brackets (\< and >).</span></span> <span data-ttu-id="ceecc-138">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="ceecc-138">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ceecc-139">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ceecc-139">Examples</span></span>  
  
|<span data-ttu-id="ceecc-140">Expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-140">Expression</span></span>|<span data-ttu-id="ceecc-141">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ceecc-141">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`BlockExpression block = Expression.Block(Expression.Constant("test"));`|`.Block() {`<br /><br /> `"test"`<br /><br /> `}`|  
|`BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));`|`.Block<System.Object>() {`<br /><br /> `"test"`<br /><br /> `}`|  
  
## <a name="lambdaexpression"></a><span data-ttu-id="ceecc-142">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="ceecc-142">LambdaExpression</span></span>  
 <span data-ttu-id="ceecc-143">Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="ceecc-143"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>  
  
 <span data-ttu-id="ceecc-144">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="ceecc-144">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ceecc-145">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ceecc-145">Examples</span></span>  
  
|<span data-ttu-id="ceecc-146">Expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-146">Expression</span></span>|<span data-ttu-id="ceecc-147">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ceecc-147">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));`|`.Lambda #Lambda1<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
|`LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);`|`.Lambda SampleLambda<System.Func'1[System.Int32]>() {`<br /><br /> `1`<br /><br /> `}`|  
  
## <a name="labelexpression"></a><span data-ttu-id="ceecc-148">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="ceecc-148">LabelExpression</span></span>  
 <span data-ttu-id="ceecc-149">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="ceecc-149">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>  
  
 <span data-ttu-id="ceecc-150">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ceecc-150">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="ceecc-151">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="ceecc-151">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>  
  
 <span data-ttu-id="ceecc-152">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="ceecc-152">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ceecc-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ceecc-153">Examples</span></span>  
  
|<span data-ttu-id="ceecc-154">Expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-154">Expression</span></span>|<span data-ttu-id="ceecc-155">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ceecc-155">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`LabelTarget target = Expression.Label(typeof(int), "SampleLabel"); BlockExpression block = Expression.Block( Expression.Goto(target, Expression.Constant(0)), Expression.Label(target, Expression.Constant(-1)));`|`.Block() {`<br /><br /> `.Goto SampleLabel { 0 };`<br /><br /> `.Label`<br /><br /> `-1`<br /><br /> `.LabelTarget SampleLabel:`<br /><br /> `}`|  
|`LabelTarget target = Expression.Label(); BlockExpression block = Expression.Block( Expression.Goto(target5), Expression.Label(target5));`|`.Block() {`<br /><br /> `.Goto #Label1 { };`<br /><br /> `.Label`<br /><br /> `.LabelTarget #Label1:`<br /><br /> `}`|  
  
## <a name="checked-operators"></a><span data-ttu-id="ceecc-156">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="ceecc-156">Checked Operators</span></span>  
 <span data-ttu-id="ceecc-157">Los operadores activados se muestran con el símbolo "#" delante del operador.</span><span class="sxs-lookup"><span data-stu-id="ceecc-157">Checked operators are displayed with the "#" symbol in front of the operator.</span></span> <span data-ttu-id="ceecc-158">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="ceecc-158">For example, the checked addition operator is displayed as `#+`.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ceecc-159">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ceecc-159">Examples</span></span>  
  
|<span data-ttu-id="ceecc-160">Expresión</span><span class="sxs-lookup"><span data-stu-id="ceecc-160">Expression</span></span>|<span data-ttu-id="ceecc-161">Propiedad `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ceecc-161">`DebugView` property</span></span>|  
|----------------|--------------------------|  
|`Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));`|`1 #+ 2`|  
|`Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));`|`#(System.Int32)10D`|  
  
## <a name="see-also"></a><span data-ttu-id="ceecc-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="ceecc-162">See Also</span></span>  
 <span data-ttu-id="ceecc-163">[Árboles de expresión (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="ceecc-163">[Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) </span></span>  
 <span data-ttu-id="ceecc-164">[Depurar en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="ceecc-164">[Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
 <span data-ttu-id="ceecc-165">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="ceecc-165">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>

