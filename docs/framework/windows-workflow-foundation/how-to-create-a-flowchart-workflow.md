---
title: Crear un flujo de trabajo de diagrama de flujo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 570e51c3b9c8ee227a9c5688fc7caa1b4a0d9c6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-flowchart-workflow"></a>Crear un flujo de trabajo de diagrama de flujo
Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas. Este tema ayudará a crear un flujo de trabajo que utiliza las actividades integradas, como el <xref:System.Activities.Statements.Flowchart> actividad y las actividades personalizadas desde el anterior [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) tema. El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
>  Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, debe completar primero [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Para crear el flujo de trabajo  
  
1.  Haga clic en **NumberGuessWorkflowActivities** en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento**.  
  
2.  En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**. Seleccione **actividad** desde el **flujo de trabajo** lista.  
  
3.  Tipo de `FlowchartNumberGuessWorkflow` en el **nombre** y haga clic en **agregar**.  
  
4.  Arrastre un **diagrama de flujo** actividad desde la **diagrama de flujo** sección de la **cuadro de herramientas** y colóquela en la **coloque la actividad aquí** etiquetar en el superficie de diseño de flujo de trabajo.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Para crear las variables y argumentos de flujo de trabajo  
  
1.  Haga doble clic en **FlowchartNumberGuessWorkflow.xaml** en **el Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.  
  
2.  Haga clic en **argumentos** en la parte inferior izquierda del Diseñador de flujo de trabajo para mostrar la **argumentos** panel.  
  
3.  Haga clic en **crear argumento**.  
  
4.  Tipo de `MaxNumber` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **Int32** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
5.  Haga clic en **crear argumento**.  
  
6.  Tipo de `Turns` en el **nombre** cuadro que se encuentra debajo de la recién agregado `MaxNumber` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione  **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR.  
  
7.  Haga clic en **argumentos** en la parte inferior izquierda del Diseñador de actividad para cerrar la **argumentos** panel.  
  
8.  Haga clic en **Variables** en la parte inferior izquierda del Diseñador de flujo de trabajo para mostrar la **Variables** panel.  
  
9. Haga clic en **crear Variable**.  
  
    > [!TIP]
    >  Si no hay ningún **crear Variable** aparece el cuadro, haga clic en la <xref:System.Activities.Statements.Flowchart> actividad en la superficie del Diseñador de flujo de trabajo para seleccionarla.  
  
10. Tipo de `Guess` en el **nombre** cuadro, seleccione **Int32** desde el **tipo de Variable** lista desplegable y, a continuación, presione ENTRAR para guardar la variable.  
  
11. Haga clic en **crear Variable**.  
  
12. Tipo de `Target` en el **nombre** cuadro, seleccione **Int32** desde el **tipo de Variable** lista desplegable y, a continuación, presione ENTRAR para guardar la variable.  
  
13. Haga clic en **Variables** en la parte inferior izquierda del Diseñador de actividad para cerrar la **Variables** panel.  
  
### <a name="to-add-the-workflow-activities"></a>Para agregar actividades de flujo de trabajo  
  
1.  Arrastre un **asignar** actividad desde la **primitivas** sección de la **cuadro de herramientas** y mantenga el mouse sobre la **iniciar** nodo, que es la parte superior de la diagrama de flujo. Cuando el **asignar** actividad está por encima del **iniciar** nodo, aparecerán tres triángulos alrededor de la **iniciar** nodo. Quitar el **asignar** actividad en el triángulo que está justo debajo del **iniciar** nodo. Esto vinculará los dos elementos juntos y designa el **asignar** actividad como la primera actividad en el diagrama de flujo.  
  
    > [!NOTE]
    >  Las actividades también se pueden indicar como actividad de inicio en el flujo de trabajo si se vinculan manualmente al nodo de inicio. Para ello, mantenga el mouse sobre la **iniciar** nodo, haga clic en uno de los rectángulos que aparecen cuando el mouse está sobre la **iniciar** nodo y arrastre la conexión de línea hacia abajo hasta la actividad deseada y colóquela en uno de los rectángulos que aparecen. También puede designar y la actividad como la actividad de inicio haciendo clic en la TI y elegir **establecer como nodo inicial**.  
  
2.  Tipo de `Target` en el **a** cuadro y la siguiente expresión en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.  
  
3.  Arrastre un **Prompt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas**, colóquela debajo la **asignar** actividad desde el anterior paso a paso y conecte el **Prompt** actividad para la **asignar** actividad. Hay tres maneras de conectar las dos actividades. La primera manera consiste en conectarlas cuando se coloca el **Prompt** actividad en el flujo de trabajo. Medida que arrastra la **Prompt** actividad al flujo de trabajo, mantenga el mouse sobre la **asignar** actividad y colóquela en uno de los cuatro triángulos que aparecen cuando el **Prompt** actividad está por encima del **asignar** actividad. La segunda manera es colocar el **Prompt** actividad en el flujo de trabajo en la ubicación deseada. A continuación, mantenga el mouse sobre la **asignar** actividad y arrastre uno de los rectángulos que aparece hacia abajo hasta la **Prompt** actividad. Arrastre el mouse para que la línea de conexión desde el **asignar** actividad se conecta a uno de los rectángulos de la **Prompt** actividad y, a continuación, suelte el botón del mouse. La tercera es muy similar a la primera, salvo que en lugar de arrastrar la **Prompt** actividad desde la **cuadro de herramientas**, arrástrelo desde su ubicación en la superficie de diseño de flujo de trabajo, mantenga el mouse sobre el  **Asignar** actividad y colóquela en uno de los triángulos que aparece.  
  
4.  En el **ventana propiedades** para el **Prompt** actividad, tipo `"EnterGuess"` incluidas las comillas en el **BookmarkName** cuadro de valor de propiedad. Tipo de `Guess` en el **resultado** propiedad cuadro de valor y escriba la siguiente expresión en el **texto** cuadro de la propiedad.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.  
  
5.  Arrastre un **asignar** actividad desde la **primitivas** sección de la **cuadro de herramientas** y conéctela mediante uno de los métodos descritos en el paso anterior para que quede por debajo de la  **Símbolo del sistema** actividad.  
  
6.  Tipo de `Turns` en el **a** cuadro y `Turns + 1` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro.  
  
7.  Arrastre un **FlowDecision** desde el **diagrama de flujo de** sección de la **cuadro de herramientas** y conéctela debajo la **asignar** actividad. En el **ventana propiedades**, escriba la siguiente expresión en el **condición** cuadro de valor de propiedad.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  Arrastre otra **FlowDecision** actividad desde la **cuadro de herramientas** y colóquela debajo de la primera de ellas. Conecte las dos actividades arrastrando desde el rectángulo que tiene la etiqueta **False** en la parte superior **FlowDecision** actividad en el rectángulo en la parte superior de la segunda **FlowDecision**actividad.  
  
    > [!TIP]
    >  Si no ve el **True** y **False** las etiquetas en el **FlowDecision**, mantenga el mouse sobre la **FlowDecision**.  
  
9. Haga clic en el segundo **FlowDecision** actividad para seleccionarlo. En el **ventana propiedades**, escriba la siguiente expresión en el **condición** cuadro de valor de propiedad.  
  
    ```
    Guess < Target  
    ```  
  
10. Arrastre dos **WriteLine** actividades desde el **primitivas** sección de la **cuadro de herramientas** y colóquelas para que estén en paralelo por debajo de los dos **FlowDecision**  actividades. Conectar el **True** acción de la parte inferior **FlowDecision** actividad a la izquierda **WriteLine** actividad y el **False** acción a la derecha **WriteLine** actividad.  
  
11. Haga clic en el extremo izquierdo **WriteLine** actividad para seleccionarla y escriba la siguiente expresión en el **texto** cuadro de valor de propiedad el **ventana propiedades**.  
  
    ```
    "Your guess is too low."  
    ```  
  
12. Conectar el **WriteLine** a la izquierda de la **Prompt** actividad que está por encima de él.  
  
13. Haga clic en el extremo derecho **WriteLine** actividad para seleccionarla y escriba la siguiente expresión en el **texto** cuadro de valor de propiedad el **ventana propiedades**.  
  
    ```
    "Your guess is too high."  
    ```  
  
14. Conectar el **WriteLine** actividad en el lado derecho de la **Prompt** actividad por encima de él.  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Completado de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### <a name="to-build-the-workflow"></a>Para compilar el flujo de trabajo  
  
1.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, consulte el tema siguiente, [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Si ya ha completado la [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) paso a paso con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de este paso, ir directamente a la [para compilar y ejecutar la aplicación](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)sección de [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Programación de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Diseño de flujos de trabajo](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Cómo crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Cómo ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
