---
title: "Crear un flujo de trabajo de m&#225;quina de estados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Crear un flujo de trabajo de m&#225;quina de estados
Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.En este tema se trata la creación de un flujo de trabajo que usa tanto las actividades integradas \(como, por ejemplo, la actividad <xref:System.Activities.Statements.StateMachine>\) como las actividades personalizadas del tema [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) anterior.El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
>  Cada uno de los temas del tutorial de introducción depende de los temas anteriores.Para completar este tema, primero debe finalizar [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md).  
  
> [!NOTE]
>  Para descargar una versión completa del tutorial, vea [Windows Workflow Foundation \(WF45\): tutorial de introducción](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### Para crear el flujo de trabajo  
  
1.  Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **Nuevo elemento**.  
  
2.  En el nodo **Instalado**, **Elementos comunes**, seleccione **Flujo de trabajo**.Seleccione **Actividad** en la lista **Flujo de trabajo**.  
  
3.  Escriba `StateMachineNumberGuessWorkflow` en el cuadro **Nombre** y haga clic en **Agregar**.  
  
4.  Arrastre una actividad **StateMachine** desde la sección **Máquina de estados** del **Cuadro de herramientas** y colóquela sobre la etiqueta **Coloque la actividad aquí** en la superficie de diseño de flujo de trabajo.  
  
### Para crear las variables y argumentos de flujo de trabajo  
  
1.  Haga doble clic en **StateMachineNumberGuessWorkflow.xaml** en el **Explorador de soluciones** para que el flujo de trabajo se muestre en el diseñador, si aún no aparece.  
  
2.  Haga clic en **Argumentos** en la parte inferior izquierda del diseñador de flujo de trabajo para mostrar el panel **Argumentos**.  
  
3.  Haga clic en **Crear argumento**.  
  
4.  Escriba `MaxNumber` en el cuadro **Nombre**, seleccione **En** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.  
  
5.  Haga clic en **Crear argumento**.  
  
6.  Escriba `Turns` en el cuadro **Nombre** que se encuentra debajo del argumento `MaxNumber` recién agregado, seleccione **Salida** en la lista desplegable **Dirección**, seleccione **Int32** en la lista desplegable **Tipo de argumento** y, a continuación, presione ENTRAR.  
  
7.  Haga clic en el botón **Argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Argumentos**.  
  
8.  Haga clic en **Variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **Variables**.  
  
9. Haga clic en **Crear variable**.  
  
    > [!TIP]
    >  Si no se muestra ningún cuadro **Crear variable**, haga clic en la actividad <xref:System.Activities.Statements.StateMachine> en la superficie del diseñador de flujo de trabajo para seleccionarla.  
  
10. Escriba `Guess` en el cuadro **Nombre**, seleccione **Int32** en la lista desplegable **Tipo de variable** y presione ENTRAR para guardar la variable.  
  
11. Haga clic en **Crear variable**.  
  
12. Escriba `Target` en el cuadro **Nombre**, seleccione **Int32** en la lista desplegable **Tipo de variable** y presione ENTRAR para guardar la variable.  
  
13. Haga clic en **Variables** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **Variables**.  
  
### Para agregar actividades de flujo de trabajo  
  
1.  Haga clic en **State1** para seleccionarlo.En la **Ventana Propiedades**, cambie **DisplayName** a `Inicializar destino`.  
  
    > [!TIP]
    >  Si no se muestra la **Ventana Propiedades**, seleccione **Ventana Propiedades** en el menú **Ver**.  
  
2.  Haga doble clic en el estado **Inicializar destino** cuyo nombre se ha cambiado recientemente en el diseñador de flujo de trabajo para expandirlo.  
  
3.  Arrastre una actividad **Assign** de la sección **Primitivas** del **cuadro de herramientas** y colóquela en la sección **Entrada** del estado.Escriba `Target` en el cuadro **Para** y la siguiente expresión en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB**.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Si la ventana **Cuadro de herramientas** no se muestra, seleccione **Cuadro de herramientas** en el menú **Ver**.  
  
4.  Vuelva a la vista global de la máquina de estados en el diseñador de flujo de trabajo; para ello, haga clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
5.  Arrastre una actividad **State** desde la sección **Máquina de estados** del **Cuadro de herramientas** sobre el diseñador de flujo de trabajo y mantenga el mouse sobre el estado **Inicializar destino**.Observe que aparecerán cuatro triángulos alrededor del estado **Inicializar destino** cuando el nuevo estado esté encima de él.Coloque el nuevo estado en el triángulo que está justo debajo del estado **Inicializar destino**.Así se pone el nuevo estado en el flujo de trabajo y se crea una transición desde el estado **Inicializar destino** al nuevo estado.  
  
6.  Haga clic en **State1** para seleccionarlo, cambie **DisplayName** a `Enter Guess` y haga doble clic en el estado en el diseñador de flujo de trabajo para expandirlo.  
  
7.  Arrastre una actividad **WriteLine** de la sección **Primitivas** del **cuadro de herramientas** y colóquela en la sección **Entrada** del estado.  
  
8.  Escriba la siguiente expresión en el cuadro de propiedades **Texto** de **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Arrastre una actividad **Assign** de la sección **Primitivas** del **cuadro de herramientas** y colóquela en la sección **Salida** del estado.  
  
10. Escriba `Turns` en el cuadro **Para** y `Turns + 1` en el cuadro **Escriba una expresión de C\#** o **Escriba una expresión de VB**.  
  
11. Vuelva a la vista global de la máquina de estados en el diseñador de flujo de trabajo; para ello, haga clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
12. Arrastre una actividad **FinalState** desde la sección **Máquina de estados** del **Cuadro de herramientas**, mantenga el mouse sobre el estado **Enter Guess** y colóquela en el triángulo que aparece a la derecha del estado **Enter Guess** para crear una transición entre **Enter Guess** y **FinalState**.  
  
13. El nombre predeterminado de la transición es **T2**.Haga clic en la transición en el diseñador de flujo de trabajo para seleccionarla y establezca su **DisplayName** en **Guess Correct**.A continuación, haga clic y seleccione **FinalState**, y arrástrelo hacia la derecha de modo que haya espacio para mostrar el nombre completo de la transición sin superposición en cualquiera de los dos estados.Así resultará más fácil completar los pasos restantes del tutorial.  
  
14. Haga doble clic en la transición **Guess Correct** cuyo nombre se ha cambiado recientemente en el diseñador de flujo de trabajo para expandirla.  
  
15. Arrastre una actividad **ReadInt** de la sección **NumberGuessWorkflowActivities** del **Cuadro de herramientas** y colóquela en la sección **Desencadenador** de la transición.  
  
16. En la **Ventana Propiedades** para la actividad **ReadInt**, escriba `"EnterGuess"` incluyendo las comillas en el cuadro de valor de propiedad **BookmarkName** y escriba `Guess` en el cuadro de valor de propiedad **Result**  
  
17. Escriba la siguiente expresión en el cuadro de valor de propiedad de **Condición** de la transición **Guess Correct**.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Vuelva a la vista global de la máquina de estados en el diseñador de flujo de trabajo; para ello, haga clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
    > [!NOTE]
    >  Una transición se produce cuando se recibe el evento desencadenador y <xref:System.Activities.Statements.Transition.Condition%2A>, si está presente, se evalúa como `True`.Para esta transición, si el `Guess` del usuario coincide con el `Target`generado aleatoriamente, el control pasa a **FinalState** y el flujo de trabajo se completa.  
  
19. En función de si el intento es correcto o no, el flujo de trabajo debe cambiar a **FinalState** o de nuevo al estado **Enter Guess** para volver a intentarlo.Ambas transiciones comparten el mismo desencadenador de esperar que se reciba el intento del usuario mediante la actividad **ReadInt**.Esto se denomina una transición compartida.Para crear una transición compartida, haga clic en el círculo que indica el inicio de la transición **Guess Correct** y arrástrelo hasta el estado deseado.En este caso la transición es una transición a sí misma, por lo que debe arrastrar el punto inicial de la transición **Guess Correct** y colocarlo de nuevo en la parte inferior del estado **Enter Guess**.Después de crear la transición, selecciónela en el diseñador de flujo de trabajo y establezca su propiedad **DisplayName** en **Guess Incorrect**.  
  
    > [!NOTE]
    >  Las transiciones compartidas también se pueden crear desde el diseñador de transición haciendo clic en **Agregar transición de desencadenador compartida** en la parte inferior del diseñador de transición y mediante la selección del estado de destino deseado en la lista desplegable **Estados disponibles para conectar**.  
  
    > [!NOTE]
    >  Tenga en cuenta que si la condición <xref:System.Activities.Statements.Transition.Condition%2A> de una transición se evalúa en `false` \(o todas las condiciones de una transición de desencadenador compartido se evalúan en `false`\), la transición no se producirá y se reprogramarán todos los desencadenadores para todas las transiciones desde el estado.En este tutorial, no puede suceder esta situación debido a la forma en que están configuradas las condiciones \(tenemos acciones específicas para determinar si el supuesto es correcto o incorrecto\).  
  
20. Haga doble clic en la transición **Guess Incorrect** en el diseñador de flujo de trabajo para expandirla.Observe que **Desencadenador** ya está establecido en la misma actividad **ReadInt** usada por la transición **Guess Correct**.  
  
21. Escriba la siguiente expresión en el cuadro de valor de propiedad **Condición**.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Arrastre una actividad **If** de la sección **Flujo de control** del **Cuadro de herramientas** y colóquela en la sección **Acción** de la transición.  
  
23. Escriba la siguiente expresión en el cuadro del valor de propiedad **Condición** de la actividad **If**.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
24. Arrastre dos actividades **WriteLine** de la sección **Primitivas** del **Cuadro de herramientas** y colóquelas de modo que una esté en la sección **Then** de la actividad **If** y otra esté en la sección **Else**.  
  
25. Haga clic en la actividad **WriteLine** en la sección **Then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de propiedad **Text**.  
  
    ```vb-c#  
    "Your guess is too low."  
    ```  
  
26. Haga clic en la actividad **WriteLine** en la sección **Else** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de propiedad **Text**.  
  
    ```vb-c#  
    "Your guess is too high."  
    ```  
  
27. Vuelva a la vista global de la máquina de estados en el diseñador de flujo de trabajo; para ello, haga clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Flujo de trabajo de máquina de estados completado](../../../docs/framework/windows-workflow-foundation//media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### Para compilar el flujo de trabajo  
  
1.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).Si ya ha completado el paso [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de máquina de estados de este paso, vaya a la sección [Para compilar y ejecutar la aplicación](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md).  
  
## Vea también  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Programación de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [Diseñar flujos de trabajo](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [Cómo: Ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)