---
title: Procedimiento para crear un flujo de trabajo de diagrama de flujo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: 0faf4d77b1ea2881ba8e029d544f2e42cf552349
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989687"
---
# <a name="how-to-create-a-flowchart-workflow"></a>Procedimiento para crear un flujo de trabajo de diagrama de flujo
Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas. En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas, como la actividad <xref:System.Activities.Statements.Flowchart>, y las actividades personalizadas del [anterior cómo: Cree una actividad](how-to-create-an-activity.md) tema. El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
> Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, primero debe completar [cómo: Cree una](how-to-create-an-activity.md)de actividad.  
  
> [!NOTE]
> Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Para crear el flujo de trabajo  
  
1. Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.  
  
2. En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**. Seleccione **actividad** en la lista **flujo de trabajo** .  
  
3. Escriba `FlowchartNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.  
  
4. Arrastre una actividad de **Diagrama de flujo** desde la sección **Diagrama** de flujo del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Para crear las variables y argumentos de flujo de trabajo  
  
1. Haga doble clic en **FlowchartNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.  
  
2. Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .  
  
3. Haga clic en **crear argumento**.  
  
4. Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.  
  
5. Haga clic en **crear argumento**.  
  
6. Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento `MaxNumber` recién agregado, seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.  
  
7. Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **argumentos** .  
  
8. Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .  
  
9. Haga clic en **crear variable**.  
  
    > [!TIP]
    > Si no se muestra ningún cuadro **crear variable** , haga clic en la actividad <xref:System.Activities.Statements.Flowchart> en la superficie del diseñador de flujo de trabajo para seleccionarla.  
  
10. Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.  
  
11. Haga clic en **crear variable**.  
  
12. Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.  
  
13. Haga clic en **variables** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **variables** .  
  
### <a name="to-add-the-workflow-activities"></a>Para agregar actividades de flujo de trabajo  
  
1. Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y mantenga el mouse sobre el nodo **iniciar** , que se encuentra en la parte superior del diagrama de flujo. Cuando la actividad de **asignación** está sobre el nodo de **Inicio** , aparecen tres triángulos alrededor del nodo de **Inicio** . Coloque la actividad **assign** en el triángulo que está justo debajo del nodo de **Inicio** . Se vincularán los dos elementos juntos y se designará la actividad **assign** como la primera actividad del diagrama de flujo.  
  
    > [!NOTE]
    > Las actividades también se pueden indicar como actividad de inicio en el flujo de trabajo si se vinculan manualmente al nodo de inicio. Para ello, mantenga el mouse sobre el nodo de **Inicio** , haga clic en uno de los rectángulos que aparecen cuando el mouse está sobre el nodo de **Inicio** y arrastre la línea de conexión hacia abajo hasta la actividad deseada y colóquela en uno de los rectángulos que aparecen. También puede designar una actividad como la actividad de inicio; para ello, haga clic con el botón secundario en ella y elija **establecer como nodo de inicio**.  
  
2. Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba C# una expresión** o **Escriba una expresión de VB** .  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > Si no se muestra la ventana **cuadro de herramientas** , seleccione **cuadro de herramientas** en el menú **Ver** .  
  
3. Arrastre una actividad **prompt** de la **sección NumberGuessWorkflowActivities** del cuadro de **herramientas**, colóquela debajo de la actividad **assign** del paso anterior y conecte la actividad **prompt** a la actividad **assign** . Hay tres maneras de conectar las dos actividades. La primera manera es conectarlas a medida que se coloca la actividad **prompt** en el flujo de trabajo. Cuando arrastre la actividad **prompt** al flujo de trabajo, mantenga el mouse sobre la actividad **assign** y colóquela en uno de los cuatro triángulos que aparecen cuando la actividad **prompt** está sobre la actividad **assign** . La segunda manera es colocar la actividad **prompt** en el flujo de trabajo en la ubicación deseada. A continuación, mantenga el mouse sobre la actividad **assign** y arrastre uno de los rectángulos que aparece hacia abajo hasta la actividad **prompt** . Arrastre el mouse para que la línea de conexión de la actividad **assign** se conecte a uno de los rectángulos de la actividad **prompt** y, a continuación, suelte el botón del mouse. La tercera manera es muy similar a la primera, salvo que en lugar de arrastrar la actividad **prompt** desde el cuadro de **herramientas**, se arrastra desde su ubicación en la superficie de diseño de flujo de trabajo, se mantiene el mouse sobre la actividad **assign** y se coloca en uno de los triángulos que aparece.  
  
4. En la **ventana Propiedades** de la actividad **Prompt** , escriba `"EnterGuess"` incluidas las comillas en el cuadro de valor de la propiedad **BookmarkName** . Escriba `Guess` en el cuadro de valor de la propiedad **resultado** y escriba la siguiente expresión en el cuadro de la propiedad **texto** .  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .  
  
5. Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y conéctela con uno de los métodos descritos en el paso anterior para que esté debajo de la actividad **prompt** .  
  
6. Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba C# una expresión** o **Escriba una expresión de VB** .  
  
7. Arrastre un **FlowDecision** desde la sección **Diagrama de flujo** del cuadro de **herramientas** y conéctelo debajo de la actividad **assign** . En la **ventana Propiedades**, escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. Arrastre otra actividad **FlowDecision** desde el **cuadro de herramientas** y colóquela debajo de la primera. Conecte las dos actividades arrastrando desde el rectángulo con la etiqueta **false** en la actividad **FlowDecision** superior hasta el rectángulo situado en la parte superior de la segunda actividad **FlowDecision** .  
  
    > [!TIP]
    > Si no ve las etiquetas **true** y **false** en el **FlowDecision**, mantenga el mouse sobre el **FlowDecision**.  
  
9. Haga clic en la segunda actividad **FlowDecision** para seleccionarla. En la **ventana Propiedades**, escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .  
  
    ```text
    Guess < Target
    ```  
  
10. Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que estén en paralelo debajo de las dos actividades **FlowDecision** . Conecte la acción **true** de la actividad **FlowDecision** inferior a la actividad **WriteLine** situada más a la izquierda y la acción **false** a la actividad **WriteLine** situada más a la derecha.  
  
11. Haga clic en la actividad **WriteLine** situada más a la izquierda para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** en la **ventana Propiedades**.  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. Conecte el **WriteLine** en el lado izquierdo de la actividad **prompt** que está por encima de él.  
  
13. Haga clic en la actividad **WriteLine** situada más a la derecha para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** en la **ventana Propiedades**.  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. Conecte la actividad **WriteLine** al lado derecho de la actividad **prompt** que está sobre ella.  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Diagrama que muestra un diagrama de flujo de Windows Workflow Foundation completado.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a>Para compilar el flujo de trabajo  
  
1. Presione Ctrl+MAYÚS+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md). Si ya ha completado el [cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md) paso con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de diagrama de flujo de este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programación de Windows Workflow Foundation](programming.md)
- [Diseño de flujos de trabajo](designing-workflows.md)
- [Tutorial de introducción](getting-started-tutorial.md)
- [Cómo: Crear una actividad](how-to-create-an-activity.md)
- [Cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md)
