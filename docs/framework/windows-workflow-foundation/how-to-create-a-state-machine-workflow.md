---
title: Crear un flujo de trabajo de máquina de estados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8098ab4b056ad6375c248e803134c35d67e3f27b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519826"
---
# <a name="how-to-create-a-state-machine-workflow"></a>Crear un flujo de trabajo de máquina de estados
Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas. En este tema le ayudará a crear un flujo de trabajo que usa tanto las actividades integradas, como el <xref:System.Activities.Statements.StateMachine> actividad y las actividades personalizadas del anterior [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) tema. El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
>  Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, primero debe completar [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).  
  
> [!NOTE]
>  Para descargar una versión completada del tutorial, consulte [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow"></a>Para crear el flujo de trabajo  
  
1.  Haga clic en **NumberGuessWorkflowActivities** en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento**.  
  
2.  En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**. Seleccione **actividad** desde el **flujo de trabajo** lista.  
  
3.  Tipo `StateMachineNumberGuessWorkflow` en el **nombre** y haga clic en **agregar**.  
  
4.  Arrastre un **StateMachine** actividad desde la **máquina de estados** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiquetar en la superficie de diseño de flujo de trabajo.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Para crear las variables y argumentos de flujo de trabajo  
  
1.  Haga doble clic en **StateMachineNumberGuessWorkflow.xaml** en **el Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.  
  
2.  Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de flujo de trabajo para mostrar el **argumentos** panel.  
  
3.  Haga clic en **crear argumento**.  
  
4.  Tipo `MaxNumber` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **Int32** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.  
  
5.  Haga clic en **crear argumento**.  
  
6.  Tipo `Turns` en el **nombre** cuadro que se encuentra debajo de la recién agregada `MaxNumber` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione  **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR.  
  
7.  Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **argumentos** panel.  
  
8.  Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de flujo de trabajo para mostrar el **Variables** panel.  
  
9. Haga clic en **crear Variable**.  
  
    > [!TIP]
    >  Si no hay ningún **crear Variable** se muestra el cuadro, haga clic en el <xref:System.Activities.Statements.StateMachine> actividad en la superficie del Diseñador de flujo de trabajo para seleccionarla.  
  
10. Tipo `Guess` en el **nombre** cuadro, seleccione **Int32** desde el **tipo de Variable** lista desplegable y, a continuación, presione ENTRAR para guardar la variable.  
  
11. Haga clic en **crear Variable**.  
  
12. Tipo `Target` en el **nombre** cuadro, seleccione **Int32** desde el **tipo de Variable** lista desplegable y, a continuación, presione ENTRAR para guardar la variable.  
  
13. Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **Variables** panel.  
  
### <a name="to-add-the-workflow-activities"></a>Para agregar actividades de flujo de trabajo  
  
1.  Haga clic en **State1** para seleccionarlo. En el **ventana propiedades**, cambie el **DisplayName** a `Initialize Target`.  
  
    > [!TIP]
    >  Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.  
  
2.  Haga doble clic en el nombre cambiado recientemente **inicializar destino** estado en el Diseñador de flujo de trabajo para expandirlo.  
  
3.  Arrastre un **asignar** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **entrada** sección del estado. Tipo `Target` en el **a** cuadro y la siguiente expresión en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.  
  
4.  Volver a general el estado de vista de la máquina en el Diseñador de flujo de trabajo haciendo clic en **StateMachine** en la ruta de navegación que se muestran en la parte superior del Diseñador de flujo de trabajo.  
  
5.  Arrastre un **estado** actividad desde la **máquina de estados** sección de la **cuadro de herramientas** hasta el Diseñador de flujo de trabajo y mantenga el mouse sobre el **inicializar destino** estado. Tenga en cuenta que aparecerán cuatro triángulos alrededor del **inicializar destino** estado cuando el estado nueva está sobre él. Coloque el nuevo estado en el triángulo que está justo debajo del **inicializar destino** estado. Esto coloca el nuevo estado en el flujo de trabajo y crea una transición desde el **inicializar destino** estado para el estado nueva.  
  
6.  Haga clic en **State1** para seleccionarlo, cambie el **DisplayName** a `Enter Guess`y, a continuación, haga doble clic en el estado en el Diseñador de flujo de trabajo para expandirlo.  
  
7.  Arrastre un **WriteLine** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **entrada** sección del estado.  
  
8.  Escriba la siguiente expresión en el **texto** cuadro de la propiedad de la **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Arrastre un **asignar** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **Exit** sección del estado.  
  
10. Tipo `Turns` en el **a** cuadro y `Turns + 1` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro.  
  
11. Volver a general el estado de vista de la máquina en el Diseñador de flujo de trabajo haciendo clic en **StateMachine** en la ruta de navegación que se muestran en la parte superior del Diseñador de flujo de trabajo.  
  
12. Arrastre un **FinalState** actividad desde la **máquina de estados** sección de la **cuadro de herramientas**, mantenga el mouse sobre el **Enter Guess** de estado y colóquelo en el triángulo que aparece a la derecha de la **Enter Guess** de estado para que se crea una transición entre **Enter Guess** y **FinalState**.  
  
13. El nombre predeterminado de la transición es **T2**. Haga clic en la transición en el Diseñador de flujo de trabajo para seleccionarla y establezca su **DisplayName** a **Guess Correct**. A continuación, haga clic en y seleccione el **FinalState**y arrástrelo a la derecha para que haya espacio para el nombre de la transición completa que se mostrará sin superposición en cualquiera de los dos Estados. Así resultará más fácil completar los pasos restantes del tutorial.  
  
14. Haga doble clic en el nombre cambiado recientemente **Guess Correct** transición en el Diseñador de flujo de trabajo para expandirlo.  
  
15. Arrastre un **ReadInt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas** y colóquelo el **desencadenador** sección de la transición.  
  
16. En el **ventana propiedades** para el **ReadInt** actividad, tipo `"EnterGuess"` , incluidas las comillas en el **BookmarkName** cuadro del valor de propiedad y tipo `Guess`en el **resultado** cuadro del valor de propiedad  
  
17. Escriba la siguiente expresión en el **Guess Correct** la transición **condición** cuadro del valor de propiedad.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Volver a general el estado de vista de la máquina en el Diseñador de flujo de trabajo haciendo clic en **StateMachine** en la ruta de navegación que se muestran en la parte superior del Diseñador de flujo de trabajo.  
  
    > [!NOTE]
    >  Una transición se produce cuando se recibe el evento desencadenador y <xref:System.Activities.Statements.Transition.Condition%2A>, si está presente, se evalúa como `True`. Para esta transición, si el usuario `Guess` coincide con generado aleatoriamente `Target`, control pasa a la **FinalState** y se completa el flujo de trabajo.  
  
19. Dependiendo de si el intento es correcto, el flujo de trabajo debe realizar la transición a la **FinalState** o volver a la **Enter Guess** estado inténtelo de nuevo. Ambas transiciones comparten el mismo desencadenador de esperar el intento del usuario poder recibir a través de la **ReadInt** actividad. Esto se denomina una transición compartida. Para crear una transición compartida, haga clic en el círculo que indica el inicio de la **Guess Correct** transición y arrástrelo hasta el estado deseado. En este caso, la transición es una transición a sí misma, arrastre hasta el punto inicial de la **Guess Correct** transición y colóquela atrás en la parte inferior de la **Enter Guess** estado. Después de crear la transición, selecciónela en el Diseñador de flujo de trabajo y establezca su **DisplayName** propiedad **Guess Incorrect**.  
  
    > [!NOTE]
    >  Las transiciones compartidas también pueden crearse desde dentro del Diseñador de transición haciendo **Agregar transición de desencadenador compartida** en la parte inferior del diseñador transición y, a continuación, seleccione el estado de destino deseado el  **Estados disponibles para conectar** lista desplegable.  
  
    > [!NOTE]
    >  Tenga en cuenta que si la condición <xref:System.Activities.Statements.Transition.Condition%2A> de una transición se evalúa en `false` (o todas las condiciones de una transición de desencadenador compartido se evalúan en `false`), la transición no se producirá y se reprogramarán todos los desencadenadores para todas las transiciones desde el estado. En este tutorial, no puede suceder esta situación debido a la forma en que están configuradas las condiciones (tenemos acciones específicas para determinar si el supuesto es correcto o incorrecto).  
  
20. Haga doble clic en el **Guess Incorrect** transición en el Diseñador de flujo de trabajo para expandirlo. Tenga en cuenta que el **desencadenador** ya está establecido en el mismo **ReadInt** actividad que ha usado el **Guess Correct** transición.  
  
21. Escriba la siguiente expresión en el **condición** cuadro del valor de propiedad.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Arrastre un **si** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquelo el **acción** sección de la transición.  
  
23. Escriba la siguiente expresión en el **si** la actividad **condición** cuadro del valor de propiedad.  
  
    ```
    Guess < Target  
    ```  
  
24. Arrastre dos **WriteLine** las actividades desde el **primitivas** sección de la **cuadro de herramientas** y colóquelas de modo que una esté en el **, a continuación,** sección de el **si** actividad y otra esté en el **Else** sección.  
  
25. Haga clic en el **WriteLine** actividad en el **, a continuación,** sección para seleccionarla y escriba la siguiente expresión en el **texto** cuadro del valor de propiedad.  
  
    ```
    "Your guess is too low."  
    ```  
  
26. Haga clic en el **WriteLine** actividad en el **Else** sección para seleccionarla y escriba la siguiente expresión en el **texto** cuadro del valor de propiedad.  
  
    ```
    "Your guess is too high."  
    ```  
  
27. Volver a general el estado de vista de la máquina en el Diseñador de flujo de trabajo haciendo clic en **StateMachine** en la ruta de navegación que se muestran en la parte superior del Diseñador de flujo de trabajo.  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Flujo de trabajo de máquina de Estados completado](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### <a name="to-build-the-workflow"></a>Para compilar el flujo de trabajo  
  
1.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md). Si ya ha completado la [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) paso con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de máquina de estado de este paso, puede ir directamente a la [para compilar y ejecutar la aplicación](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sección de [Cómo: ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Programación de Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [Diseño de flujos de trabajo](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [Cómo crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [Cómo ejecutar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
