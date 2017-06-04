---
title: "Crear un flujo de trabajo de diagrama de flujo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Crear un flujo de trabajo de diagrama de flujo
Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.En este tema se trata la creación de un flujo de trabajo que usa tanto las actividades integradas \(como, por ejemplo, la actividad <xref:System.Activities.Statements.Flowchart>\) como las actividades personalizadas del tema [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) anterior.El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
>  Cada uno de los temas del tutorial de introducción depende de los temas anteriores.Para completar este tema, primero debe finalizar [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md).  
  
> [!NOTE]
>  Para descargar una versión completa del tutorial, vea [Windows Workflow Foundation \(WF45\): tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### Para crear el flujo de trabajo  
  
1.  Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **Nuevo elemento**.  
  
2.  En el nodo **Instalado**, de **Elementos comunes**, seleccione **Flujo de trabajo**.Seleccione **Actividad** en la lista **Flujo de trabajo**.  
  
3.  Escriba `FlowchartNumberGuessWorkflow` en el cuadro **Nombre** y haga clic en **Agregar**.  
  
4.  Arrastre una actividad **Flowchart** desde la sección **Diagrama de flujo** del **Cuadro de herramientas** y colóquela sobre la etiqueta **Coloque la actividad aquí** en la superficie de diseño de flujo de trabajo.  
  
### Para crear las variables y argumentos de flujo de trabajo  
  
1.  Haga doble clic en **FlowchartNumberGuessWorkflow.xaml** en el **Explorador de soluciones** para que el flujo de trabajo se muestre en el diseñador, si aún no ha aparecido.  
  
2.  Haga clic en **Argumentos** en la parte inferior izquierda del diseñador de flujo de trabajo para mostrar el panel **Argumentos**.  
  
3.  Haga clic en **Crear argumento**.  
  
4.  Escriba `MaxNumber` en el cuadro **Nombre**, seleccione **En** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.  
  
5.  Haga clic en **Crear argumento**.  
  
6.  Escriba `Turns` en el cuadro **Nombre** que se encuentra debajo del argumento `MaxNumber` recién agregado, seleccione **Salida** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione ENTRAR.  
  
7.  Haga clic en el botón **Argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Argumentos**.  
  
8.  Haga clic en **Variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **Variables**.  
  
9. Haga clic en **Crear variable**.  
  
    > [!TIP]
    >  Si no se muestra ningún cuadro **Crear variable**, haga clic en la actividad <xref:System.Activities.Statements.Flowchart> en la superficie del diseñador de flujo de trabajo para seleccionarla.  
  
10. Escriba `Guess` en el cuadro **Nombre**, seleccione **Int32** en la lista desplegable **Tipo de variable** y presione ENTRAR para guardar la variable.  
  
11. Haga clic en **Crear variable**.  
  
12. Escriba `Target` en el cuadro **Nombre**, seleccione **Int32** en la lista desplegable **Tipo de variable** y presione ENTRAR para guardar la variable.  
  
13. Haga clic en **Variables** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Variables**.  
  
### Para agregar actividades de flujo de trabajo  
  
1.  Arrastre una actividad **Assign** desde la sección **Primitivas** del **Cuadro de herramientas** y mantenga el mouse sobre el nodo **Iniciar**, que está en la parte superior del diagrama de flujo.Cuando la actividad **Assign** esté sobre el nodo **Iniciar**, aparecerán tres triángulos alrededor del nodo **Iniciar**.Coloque la actividad **Assign** en el triángulo que está justo debajo del nodo **Iniciar**.Esto vinculará los dos elementos y designará la actividad **Assign** como la primera actividad del diagrama de flujo.  
  
    > [!NOTE]
    >  Las actividades también se pueden indicar como actividad de inicio en el flujo de trabajo si se vinculan manualmente al nodo de inicio.Para ello, mantenga el mouse sobre el nodo **Iniciar**, haga clic en uno de los rectángulos que aparecen cuando el mouse está sobre el nodo **Iniciar** y arrastre la línea de conexión hacia abajo hasta la actividad deseada y colóquela en uno de los rectángulos que aparecen.También puede designar una actividad como la actividad inicial si hace clic con el botón secundario en ella y selecciona **Establecer como nodo inicial**.  
  
2.  Escriba `Target` en el cuadro **Para** y la siguiente expresión en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB**.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Si la ventana **Cuadro de herramientas** no se muestra, seleccione **Cuadro de herramientas** en el menú **Ver**.  
  
3.  Arrastre una actividad **Prompt** desde la sección **NumberGuessWorkflowActivities** del **Cuadro de herramientas**, colóquela debajo de la actividad **Assign** del paso anterior y conecte la actividad **Prompt** con la actividad **Assign**.Hay tres maneras de conectar las dos actividades.La primera consiste en conectarlas cuando se coloca la actividad **Prompt** en el flujo de trabajo.A medida que arrastra la actividad **Prompt** al flujo de trabajo, mantenga el mouse sobre la actividad **Assign** y colóquela en uno de los cuatro triángulos que aparecen cuando la actividad **Prompt** está sobre la actividad **Assign**.La segunda manera es colocar la actividad **Prompt** en el flujo de trabajo en la ubicación deseada.A continuación, mantenga el mouse sobre la actividad **Assign** y arrastre uno de los rectángulos que aparece hacia abajo hasta la actividad **Prompt**.Arrastre el mouse para que la línea de conexión de la actividad **Assign** se conecte con uno de los rectángulos de la actividad **Prompt** y, a continuación, suelte el botón del mouse.La tercera es muy similar a la primera, salvo que en lugar de arrastrar la actividad **Prompt** desde el **Cuadro de herramientas**, se arrastra desde su ubicación en la superficie de diseño de flujo de trabajo, se mantiene el mouse sobre la actividad **Assign** y se coloca en uno de los triángulos que aparece.  
  
4.  En la **Ventana Propiedades** de la actividad **Prompt**, escriba `"EnterGuess"`, incluidas las comillas, en el cuadro de valor de propiedad **BookmarkName**.Escriba `Guess` en el cuadro de valor de propiedad **Resultado** y escriba la siguiente expresión en el cuadro de propiedad **Texto**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Si no se muestra la **Ventana Propiedades**, seleccione **Ventana Propiedades** en el menú **Ver**.  
  
5.  Arrastre una actividad **Assign** desde la sección **Primitivas** del **Cuadro de herramientas** y conéctela mediante uno de los métodos descritos en el paso anterior para que esté debajo de la actividad **Prompt**.  
  
6.  Escriba `Turns` en el cuadro **Para** y `Turns + 1` en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB**.  
  
7.  Arrastre **FlowDecision** desde la sección **Diagrama de flujo** del **Cuadro de herramientas** y conéctela debajo de la actividad **Assign**.En la **Ventana Propiedades**, escriba la siguiente expresión en el cuadro del valor de propiedad **Condición**.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  Arrastre otra actividad **FlowDecision** del **cuadro de herramientas** y colóquela debajo de la primera.Conecte las dos actividades al arrastrar desde el rectángulo con la etiqueta **Falso** en la actividad **FlowDecision** superior con rectángulo en la parte superior de la segunda actividad **FlowDecision**.  
  
    > [!TIP]
    >  Si no ve las etiquetas **Verdadero** y **Falso** en **FlowDecision**, mantenga el mouse sobre **FlowDecision**.  
  
9. Haga clic en la segunda actividad **FlowDecision** para seleccionarla.En la **Ventana Propiedades**, escriba la siguiente expresión en el cuadro del valor de la propiedad **Condición**.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
10. Arrastre dos actividades **WriteLine** de la sección **Primitivas** del **cuadro de herramientas** y colóquelas para que estén una junto a otra debajo de las dos actividades **FlowDecision**.Conecte la acción **Verdadero** de la actividad **FlowDecision** inferior a la actividad **WriteLine** situada más a la izquierda y la acción **Falso** a la actividad **WriteLine** situada más a la derecha.  
  
11. Haga clic en la actividad **WriteLine** situada más a la izquierda para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Texto** en la **Ventana Propiedades**.  
  
    ```vb-c#  
    "Your guess is too low."  
    ```  
  
12. Conecte **WriteLine** al lado izquierdo de la actividad **Prompt** que está sobre ella.  
  
13. Haga clic en la actividad **WriteLine** situada más a la derecha para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Texto** en la **Ventana Propiedades**.  
  
    ```vb-c#  
    "Your guess is too high."  
    ```  
  
14. Conecte la actividad **WriteLine** al lado derecho de la actividad **Prompt** que está sobre ella.  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Windows Workflow Foundation &#45; Completo](../../../docs/framework/windows-workflow-foundation//media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### Para compilar el flujo de trabajo  
  
1.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).Si ya ha completado el paso [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de diagrama de flujo de este paso, vaya a la sección [Para compilar y ejecutar la aplicación](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).  
  
## Vea también  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Programación de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [Diseñar flujos de trabajo](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)