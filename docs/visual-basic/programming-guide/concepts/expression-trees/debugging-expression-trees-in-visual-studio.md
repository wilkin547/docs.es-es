---
title: Depuración de árboles de expresión en Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 9aead09e0e9469f13e2d6befbad444d3c7fecabd
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196023"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a><span data-ttu-id="94f7b-102">Depuración de árboles de expresión en Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94f7b-102">Debugging Expression Trees in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="94f7b-103">Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="94f7b-103">You can analyze the structure and content of expression trees when you debug your applications.</span></span> <span data-ttu-id="94f7b-104">Para obtener una descripción general de la estructura de árbol de expresión, puede usar el `DebugView` propiedad, que representa los árboles de expresión [mediante una sintaxis especial](debugview-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="94f7b-104">To get a quick overview of the expression tree structure, you can use the `DebugView` property, which represents expression trees [using a special syntax](debugview-syntax.md).</span></span> <span data-ttu-id="94f7b-105">Observe que `DebugView` solo está disponible en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="94f7b-105">(Note that `DebugView` is available only in debug mode.)</span></span>  

![DebugView de árbol de expresión en el depurador de Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

<span data-ttu-id="94f7b-107">Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="94f7b-107">Since `DebugView` is a string, you can use the [built-in Text Visualizer](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) to view it across multiple lines, by selecting **Text Visualizer** from the magnifying glass icon next to the `DebugView` label.</span></span>

 ![Visualizador de texto aplicado a los resultados de "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

<span data-ttu-id="94f7b-109">Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) árboles de expresiones, como:</span><span class="sxs-lookup"><span data-stu-id="94f7b-109">Alternatively, you can install and use [a custom visualizer](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) for expression trees, such as:</span></span>

* <span data-ttu-id="94f7b-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C#:</span><span class="sxs-lookup"><span data-stu-id="94f7b-110">[Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([MIT license](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), available at the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), renders the expression tree as C# code:</span></span>

  ![Visualizador Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* <span data-ttu-id="94f7b-112">[Visualizador de árboles de expresión](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licencia MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), proporciona una vista gráfica del árbol de expresión, sus propiedades y objetos relacionados; y puede representar el árbol de expresión mediante código de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="94f7b-112">[Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT license](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), provides a graphical view of the expression tree, its properties, and related objects; and can render the expression tree using Visual Basic code:</span></span>

  ![Visualizador ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a><span data-ttu-id="94f7b-114">Para abrir un visualizador para un árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="94f7b-114">To open a visualizer for an expression tree</span></span>  
  
1. <span data-ttu-id="94f7b-115">Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="94f7b-115">Click the magnifying glass icon that appears next to the expression tree in **DataTips**, a **Watch** window, the **Autos** window, or the **Locals** window.</span></span>  
  
     <span data-ttu-id="94f7b-116">Se muestra una lista de los visualizadores disponibles:</span><span class="sxs-lookup"><span data-stu-id="94f7b-116">A list of available visualizers is displayed.:</span></span> 

      ![Apertura de visualizadores desde Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. <span data-ttu-id="94f7b-118">Haga clic en el visualizador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="94f7b-118">Click the visualizer you want to use.</span></span>  

## <a name="see-also"></a><span data-ttu-id="94f7b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="94f7b-119">See also</span></span>

- [<span data-ttu-id="94f7b-120">Árboles de expresión (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94f7b-120">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="94f7b-121">Depurar en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94f7b-121">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugging-in-visual-studio)
- <span data-ttu-id="94f7b-122">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)</span><span class="sxs-lookup"><span data-stu-id="94f7b-122">[Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data)</span></span>
- [<span data-ttu-id="94f7b-123">`DebugView` Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94f7b-123">`DebugView` syntax</span></span>](debugview-syntax.md)
