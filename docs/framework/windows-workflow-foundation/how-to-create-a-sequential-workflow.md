---
title: "Crear un flujo de trabajo secuencial | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Crear un flujo de trabajo secuencial
Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.En este tema se trata la creación de un flujo de trabajo que usa tanto las actividades integradas \(como, por ejemplo, la actividad <xref:System.Activities.Statements.Sequence>\) como las actividades personalizadas del tema [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) anterior.El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
>  Cada uno de los temas del tutorial de introducción depende de los temas anteriores.Para completar este tema, primero debe finalizar [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md).  
  
> [!NOTE]
>  Para descargar una versión completa del tutorial, vea [Windows Workflow Foundation \(WF45\): tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### Para crear el flujo de trabajo  
  
1.  Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **Nuevo elemento**.  
  
2.  En el nodo **Instalado**, **Elementos comunes**, seleccione **Flujo de trabajo**.Seleccione **Actividad** en la lista **Flujo de trabajo**.  
  
3.  Escriba `SequentialNumberGuessWorkflow` en el cuadro **Nombre** y haga clic en **Agregar**.  
  
4.  Arrastre una actividad **Sequence** desde la sección **Flujo de control** del **Cuadro de herramientas** y colóquela sobre la etiqueta **Coloque la actividad aquí** en la superficie de diseño de flujo de trabajo.  
  
### Para crear las variables y argumentos de flujo de trabajo  
  
1.  Haga doble clic en **SequentialNumberGuessWorkflow** en el **Explorador de soluciones** para que el flujo de trabajo se muestre en el diseñador, si aún no aparece.  
  
2.  Haga clic en **Argumentos** en la parte inferior izquierda del diseñador de flujo de trabajo para mostrar el panel **Argumentos**.  
  
3.  Haga clic en **Crear argumento**.  
  
4.  Escriba `MaxNumber` en el cuadro **Nombre**, seleccione **En** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.  
  
5.  Haga clic en **Crear argumento**.  
  
6.  Escriba `Turns` en el cuadro **Nombre** que se encuentra debajo del argumento `MaxNumber` recién agregado, seleccione **Salida** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione ENTRAR.  
  
7.  Haga clic en el botón **Argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Argumentos**.  
  
8.  Haga clic en **Variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **Variables**.  
  
9. Haga clic en **Crear variable**.  
  
    > [!TIP]
    >  Si no se muestra ningún cuadro **Crear variable**, haga clic en la actividad **Sequence** en la superficie del diseñador de flujo de trabajo para seleccionarla.  
  
10. Escriba `Guess` en el cuadro **Nombre**, seleccione **Int32** en la lista desplegable **Tipo de variable** y presione ENTRAR para guardar la variable.  
  
11. Haga clic en **Crear variable**.  
  
12. Escriba `Target` en el cuadro **Nombre**, seleccione **Int32** en la lista desplegable **Tipo de variable** y presione ENTRAR para guardar la variable.  
  
13. Haga clic en **Variables** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Variables**.  
  
### Para agregar actividades de flujo de trabajo  
  
1.  Arrastre una actividad **Assign** de la sección **Primitivas** del **cuadro de herramientas** y colóquela en la actividad **Sequence**.Escriba `Target` en el cuadro **Para** y la siguiente expresión en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB**.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Si la ventana **Cuadro de herramientas** no se muestra, seleccione **Cuadro de herramientas** en el menú **Ver**.  
  
2.  Arrastre una actividad **DoWhile** desde la sección **Flujo de control** del **Cuadro de herramientas** y colóquela en el flujo de trabajo para que esté debajo de la actividad **Assign**.  
  
3.  Escriba la siguiente expresión en el cuadro del valor de propiedad **Condición** de la actividad **DoWhile**.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     Una actividad <xref:System.Activities.Statements.DoWhile> ejecuta sus actividades secundarias y después evalúa su <xref:System.Activities.Statements.DoWhile.Condition%2A>.Si <xref:System.Activities.Statements.DoWhile.Condition%2A> se evalúa como `True`, las actividades de <xref:System.Activities.Statements.DoWhile> se ejecutan de nuevo.En este ejemplo, se evalúa el intento del usuario y <xref:System.Activities.Statements.DoWhile> continúa hasta que se acierta el número.  
  
4.  Arrastre una actividad **Prompt** de la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **DoWhile** del paso anterior.  
  
5.  En la **Ventana Propiedades**, escriba `"EnterGuess"`, incluidas las comillas, en el cuadro de valor de propiedad **BookmarkName** para la actividad **Prompt**.Escriba `Guess` en el cuadro de valor de propiedad **Resultado** y escriba la siguiente expresión en el cuadro de propiedad **Texto**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  Si no se muestra la **Ventana Propiedades**, seleccione **Ventana Propiedades** en el menú **Ver**.  
  
6.  Arrastre una actividad **Assign** de la sección **Primitivas** del **cuadro de herramientas** y colóquela en la actividad **DoWhile** de manera que siga a la actividad **Prompt**.  
  
    > [!NOTE]
    >  Al colocar la actividad **Assign**, observe cómo el diseñador de flujo de trabajo agrega automáticamente una actividad **Sequence** para contener la actividad **Prompt** y la actividad **Assign** recién agregada.  
  
7.  Escriba `Turns` en el cuadro **Para** y `Turns + 1` en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB**.  
  
8.  Arrastre una actividad **If** de la sección **Flujo de control** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga a la actividad **Assign** recién agregada.  
  
9. Escriba la siguiente expresión en el cuadro del valor de propiedad **Condición** de la actividad **If**.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. Arrastre otra actividad **If** de la sección **Flujo de control** del **Cuadro de herramientas** y colóquela en la sección **Then** de la primera actividad **If**.  
  
11. Escriba la siguiente expresión en el cuadro del valor de propiedad **Condición** de la actividad **If** recién agregada.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
12. Arrastre dos actividades **WriteLine** de la sección **Primitivas** del **Cuadro de herramientas** y colóquelas de modo que una esté en la sección **Then** de la actividad recién agregada **If** y otra esté en la sección **Else**.  
  
13. Haga clic en la actividad **WriteLine** en la sección **Then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de propiedad **Text**.  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. Haga clic en la actividad **WriteLine** en la sección **Else** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de propiedad **Text**.  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Flujo de trabajo secuencial completado](../../../docs/framework/windows-workflow-foundation//media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### Para compilar el flujo de trabajo  
  
1.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).Si ya ha completado el paso [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo secuencial de este paso, vaya a la sección [Para compilar y ejecutar la aplicación](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).  
  
## Vea también  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Programación de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [Diseñar flujos de trabajo](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)