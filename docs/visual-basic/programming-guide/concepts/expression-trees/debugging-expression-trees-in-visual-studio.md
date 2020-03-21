---
title: Depuración de árboles de expresión en Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: c6c44d079ab0854b2325b82d3569280752da32fb
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266838"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="65442-102">Depuración de árboles de expresión en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65442-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="65442-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="65442-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="65442-104">Para obtener una introducción rápida a la estructura del árbol de expresión, puede usar la propiedad `DebugView`, que representa los árboles de expresión [con una sintaxis especial](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="65442-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="65442-105">Observe que `DebugView` solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="65442-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![Captura de pantalla de la DebugView del árbol de expresiones.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

<span data-ttu-id="65442-107">Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="65442-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Captura de pantalla del visualizador de texto aplicado a los resultados de DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

<span data-ttu-id="65442-109">Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) para árboles de expresión, como:</span><span class="sxs-lookup"><span data-stu-id="65442-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

- <span data-ttu-id="65442-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C#:</span><span class="sxs-lookup"><span data-stu-id="65442-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Captura de pantalla del visualizador Readable Expressions.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- <span data-ttu-id="65442-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) [(licencia MIT),](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)proporciona una vista gráfica del árbol de expresiones, sus propiedades y objetos relacionados; y puede representar el árbol de expresiones mediante código de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="65442-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Captura de pantalla del visualizador ExpressionToString.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="65442-114">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="65442-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="65442-115">Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="65442-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
    <span data-ttu-id="65442-116">Se muestra una lista de los visualizadores disponibles:</span><span class="sxs-lookup"><span data-stu-id="65442-116">A list of available visualizers is displayed.:</span></span>

    ![Captura de pantalla de los visualizadores de apertura de usuario de Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. <span data-ttu-id="65442-118">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="65442-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="65442-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="65442-119">See also</span></span>

- [<span data-ttu-id="65442-120">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65442-120">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="65442-121">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="65442-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- <span data-ttu-id="65442-122">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="65442-122">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
- [<span data-ttu-id="65442-123">Sintaxis `DebugView`</span><span class="sxs-lookup"><span data-stu-id="65442-123">`DebugView` syntax</span></span>](debugview-syntax.md)
