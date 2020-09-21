---
title: Depuración de árboles de expresión en Visual Studio (C#)
description: Obtenga información sobre la propiedad DebugView en Visual Studio. Vea cómo usar esta propiedad para analizar la estructura y el contenido de los árboles de expresión.
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: fab378149fb14ccf6a66434c933aa24a8c9c6119
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555619"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a><span data-ttu-id="e6be3-104">Depuración de árboles de expresión en Visual Studio (C#)</span><span class="sxs-lookup"><span data-stu-id="e6be3-104">Debugging Expression Trees in Visual Studio (C#)</span></span>
<span data-ttu-id="e6be3-105">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e6be3-105">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="e6be3-106">Para obtener una introducción rápida a la estructura del árbol de expresión, puede usar la propiedad `DebugView`, que representa los árboles de expresión [con una sintaxis especial](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="e6be3-106">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="e6be3-107">Observe que `DebugView` solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="e6be3-107">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Captura de pantalla de DebugView de un árbol de expresión en el depurador de VS.](media/debugging-expression-trees-in-visual-studio/debugview-expression-tree.png)

<span data-ttu-id="e6be3-109">Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="e6be3-109">Since `DebugView` is a string, you can use the [built-in Text Visualizer](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Captura de pantalla del visualizador de texto aplicado a los resultados de DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-debugview.png)

<span data-ttu-id="e6be3-111">Como alternativa, puede instalar y usar [un visualizador personalizado](/visualstudio/debugger/create-custom-visualizers-of-data) para árboles de expresión, como:</span><span class="sxs-lookup"><span data-stu-id="e6be3-111">Alternatively, you can install and use [a custom visualizer](/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="e6be3-112">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C# con temas, con varias opciones de representación:</span><span class="sxs-lookup"><span data-stu-id="e6be3-112">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Captura de pantalla del visualizador Readable Expressions.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="e6be3-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licencia MIT](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)), proporciona una vista de árbol del árbol de expresión y sus nodos individuales:</span><span class="sxs-lookup"><span data-stu-id="e6be3-114">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes:</span></span>

  ![Captura de pantalla de Expression Tree Visualizer.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="e6be3-116">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="e6be3-116">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="e6be3-117">Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="e6be3-117">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  

    <span data-ttu-id="e6be3-118">Se muestra una lista de los visualizadores disponibles:</span><span class="sxs-lookup"><span data-stu-id="e6be3-118">A list of available visualizers is displayed.:</span></span>

    ![Captura de pantalla que muestra la apertura de visualizadores desde Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers.png)

2. <span data-ttu-id="e6be3-120">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="e6be3-120">Click the visualizer you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6be3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6be3-121">See also</span></span>

- [<span data-ttu-id="e6be3-122">Árboles de expresión (C#)</span><span class="sxs-lookup"><span data-stu-id="e6be3-122">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="e6be3-123">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e6be3-123">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- <span data-ttu-id="e6be3-124">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="e6be3-124">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
- [<span data-ttu-id="e6be3-125">Sintaxis `DebugView`</span><span class="sxs-lookup"><span data-stu-id="e6be3-125">`DebugView` syntax</span></span>](debugview-syntax.md)
