---
title: Depuración de árboles de expresión en Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 3811958353d1d55ce74da41c6a45dbe730cc9790
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375440"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="af3de-102">Depurar árboles de expresión en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af3de-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="af3de-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="af3de-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="af3de-104">Para obtener una introducción rápida a la estructura del árbol de expresión, puede usar la propiedad `DebugView`, que representa los árboles de expresión [con una sintaxis especial](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="af3de-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="af3de-105">Observe que `DebugView` solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="af3de-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Captura de pantalla del DebugView del árbol de expresión.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

<span data-ttu-id="af3de-107">Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="af3de-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Captura de pantalla del visualizador de texto que se aplica a los resultados de DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

<span data-ttu-id="af3de-109">Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) para árboles de expresión, como:</span><span class="sxs-lookup"><span data-stu-id="af3de-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="af3de-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C# con temas, con varias opciones de representación:</span><span class="sxs-lookup"><span data-stu-id="af3de-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as themeable C# code, with various rendering options:</span></span>

  ![Captura de pantalla del visualizador Readable Expressions.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="af3de-112">El [visualizador de árbol de expresión](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licencia MIT](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) proporciona una vista de árbol del árbol de expresión y sus nodos individuales. y pueden representar el árbol de expresión utilizando Visual Basic sintaxis:</span><span class="sxs-lookup"><span data-stu-id="af3de-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([MIT license](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) provides a tree view of the expression tree and its individual nodes; and can render the expression tree using Visual Basic syntax:</span></span>

  ![Captura de pantalla de Expression Tree Visualizer.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="af3de-114">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="af3de-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="af3de-115">Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="af3de-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
    <span data-ttu-id="af3de-116">Se muestra una lista de los visualizadores disponibles:</span><span class="sxs-lookup"><span data-stu-id="af3de-116">A list of available visualizers is displayed.:</span></span>

    ![Captura de pantalla del usuario que abre visualizadores desde Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. <span data-ttu-id="af3de-118">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="af3de-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="af3de-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="af3de-119">See also</span></span>

- [<span data-ttu-id="af3de-120">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af3de-120">Expression Trees (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="af3de-121">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="af3de-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- <span data-ttu-id="af3de-122">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="af3de-122">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
- [<span data-ttu-id="af3de-123">Sintaxis `DebugView`</span><span class="sxs-lookup"><span data-stu-id="af3de-123">`DebugView` syntax</span></span>](debugview-syntax.md)
