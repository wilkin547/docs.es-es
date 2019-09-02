---
title: Depuración de árboles de expresión en Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 43091d11dfc1fae3e6f047f35b61e992c5aaf50b
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70104906"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Depuración de árboles de expresión en Visual Studio (C#)
Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones. Para obtener una introducción rápida a la estructura del árbol de expresión, puede usar la propiedad `DebugView`, que representa los árboles de expresión [con una sintaxis especial](debugview-syntax.md). Observe que `DebugView` solo está disponible en modo de depuración.  

![DebugView de árbol de expresión en el depurador de Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview.png)

Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.

 ![Visualizador de texto aplicado a los resultados de "DebugView"](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

Como alternativa, puede instalar y usar [un visualizador personalizado](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) para árboles de expresión, como:

- [Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C#:

  ![Visualizador Readable Expressions](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

- [Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([licencia MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), proporciona una vista gráfica del árbol de expresión, sus propiedades y los objetos relacionados:

  ![Visualizador ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Para abrir un visualizador para un árbol de expresión  
  
1. Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.  
  
     Se muestra una lista de los visualizadores disponibles: 

      ![Apertura de visualizadores desde Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. Haga clic en el visualizador que desee usar.  
  
## <a name="see-also"></a>Vea también

- [Árboles de expresión (C#)](./index.md)
- [Depurar en Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)
- [Sintaxis `DebugView`](debugview-syntax.md)
