---
description: Más información sobre cómo depurar árboles de expresión en Visual Studio (Visual Basic)
title: Depuración de árboles de expresión en Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 0221533a79dbc76be479380bd9b6e6df4156e288
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100459089"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Depurar árboles de expresión en Visual Studio (Visual Basic)

Se puede analizar la estructura y el contenido de los árboles de expresión cuando se depuran las aplicaciones. Para obtener una introducción rápida a la estructura del árbol de expresión, puede usar la propiedad `DebugView`, que representa los árboles de expresión [con una sintaxis especial](debugview-syntax.md). Observe que `DebugView` solo está disponible en modo de depuración.  

![Captura de pantalla del DebugView del árbol de expresión.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Puesto que `DebugView` es una cadena, puede usar el [visualizador de texto integrado](/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) para verla en varias líneas si selecciona **Visualizador de texto** en el icono de lupa situado junto a la etiqueta `DebugView`.

 ![Captura de pantalla del visualizador de texto que se aplica a los resultados de DebugView.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

Como alternativa, puede instalar y usar [un visualizador personalizado](/visualstudio/debugger/create-custom-visualizers-of-data) para árboles de expresión, como:

- [Readable Expressions](https://github.com/agileobjects/ReadableExpressions) ([licencia MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), disponible en [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), representa el árbol de expresión como código de C# con temas, con varias opciones de representación:

  ![Captura de pantalla del visualizador Readable Expressions.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- El [visualizador de árbol de expresión](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) ([licencia MIT](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) proporciona una vista de árbol del árbol de expresión y sus nodos individuales. y pueden representar el árbol de expresión utilizando Visual Basic sintaxis:

  ![Captura de pantalla de Expression Tree Visualizer.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Para abrir un visualizador para un árbol de expresión  
  
1. Haga clic en el icono de lupa que aparece junto al árbol de expresión en **Información sobre datos**, en una ventana **Inspección** o en las ventanas **Automático** o **Variables locales**.  
  
    Se muestra una lista de los visualizadores disponibles:

    ![Captura de pantalla del usuario que abre visualizadores desde Visual Studio.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Haga clic en el visualizador que desee usar.  

## <a name="see-also"></a>Vea también

- [Árboles de expresión (Visual Basic)](index.md)
- [Depurar en Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Create Custom Visualizers](/visualstudio/debugger/create-custom-visualizers-of-data) (Crear visualizadores personalizados)
- [Sintaxis `DebugView`](debugview-syntax.md)
