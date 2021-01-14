---
title: Procedimiento para crear un flujo de trabajo de máquina de estados
description: En este artículo se crea un flujo de trabajo que utiliza las actividades integradas, como la actividad StateMachine, y las actividades personalizadas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8e977a182d55143f8d877d61a0f0345bbe6bded4
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190473"
---
# <a name="how-to-create-a-state-machine-workflow"></a>Procedimiento para crear un flujo de trabajo de máquina de estados

Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas. En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas, como la <xref:System.Activities.Statements.StateMachine> actividad, y las actividades personalizadas del tema [Cómo: crear una actividad](how-to-create-an-activity.md) anterior. El flujo de trabajo modela un juego de adivinanzas de números.  
  
> [!NOTE]
> Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, primero debe completar [Cómo: crear una actividad](how-to-create-an-activity.md).  
  
### <a name="to-create-the-workflow"></a>Para crear el flujo de trabajo  
  
1. Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.  
  
2. En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**. Seleccione **Actividad** en la lista **Flujo de trabajo**.  
  
3. Escriba `StateMachineNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.  
  
4. Arrastre una actividad **StateMachine** desde la sección **máquina de Estados** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>Para crear las variables y argumentos de flujo de trabajo  
  
1. Haga doble clic en **StateMachineNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.  
  
2. Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .  
  
3. Haga clic en **Crear argumento**.  
  
4. Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.  
  
5. Haga clic en **Crear argumento**.  
  
6. Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `MaxNumber` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.  
  
7. Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.  
  
8. Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .  
  
9. Haga clic en **Crear variable**.  
  
    > [!TIP]
    > Si no se muestra ningún cuadro **crear variable** , haga clic en la <xref:System.Activities.Statements.StateMachine> actividad en la superficie del diseñador de flujo de trabajo para seleccionarla.  
  
10. Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.  
  
11. Haga clic en **Crear variable**.  
  
12. Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.  
  
13. Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Variables**.  
  
### <a name="to-add-the-workflow-activities"></a>Para agregar actividades de flujo de trabajo  
  
1. Haga clic en **State1** para seleccionarlo. En la **ventana Propiedades**, cambie **displayName** a `Initialize Target` .  
  
    > [!TIP]
    > Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .  
  
2. Haga doble clic en el estado de **destino Initialize** recién cambiado en el diseñador de flujo de trabajo para expandirlo.  
  
3. Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la sección **entrada** del estado. Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.  
  
4. Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
5. Arrastre una actividad **State** desde la sección **máquina de Estados** del **cuadro de herramientas** hasta el diseñador de flujo de trabajo y mantenga el mouse sobre el estado de **inicialización de destino** . Tenga en cuenta que se mostrarán cuatro triángulos alrededor del estado de **destino de inicialización** cuando el nuevo estado se sitúa sobre él. Quite el nuevo estado del triángulo que está inmediatamente por debajo del estado de **inicialización de destino** . Esto coloca el nuevo estado en el flujo de trabajo y crea una transición desde el estado de **destino Initialize** al nuevo estado.  
  
6. Haga clic en **State1** para seleccionarlo, cambie **displayName** a y, a continuación, haga `Enter Guess` doble clic en el estado en el diseñador de flujo de trabajo para expandirlo.  
  
7. Arrastre una actividad **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la sección **entrada** del estado.  
  
8. Escriba la siguiente expresión en el cuadro de propiedad **texto** de **WriteLine**.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. Arrastre una actividad **assign** desde la sección **primitivas** del **cuadro de herramientas** y colóquela en la sección de **salida** del estado.  
  
10. Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .  
  
11. Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
12. Arrastre una actividad **FinalState** desde la sección **máquina de Estados** del **cuadro de herramientas**, mantenga el mouse sobre el estado **Enter Guess** y colóquela en el triángulo que aparece a la derecha del estado **Enter Guess** para que se cree una transición entre **Enter Guess** y **FinalState**.  
  
13. El nombre predeterminado de la transición es **T2**. Haga clic en la transición en el diseñador de flujo de trabajo para seleccionarla y establezca su **displayName** en **Guess correct**. Después, haga clic en el **FinalState** y selecciónelo y arrástrelo hacia la derecha para que haya espacio para que se muestre el nombre completo de la transición sin superposición de ninguno de los dos Estados. Así resultará más fácil completar los pasos restantes del tutorial.  
  
14. Haga doble clic en la transición **Guess correct** con el nuevo nombre en el diseñador de flujo de trabajo para expandirla.  
  
15. Arrastre una actividad **ReadInt** desde la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la sección **desencadenador** de la transición.  
  
16. En la **ventana Propiedades** de la actividad **ReadInt** , escriba `"EnterGuess"` entre comillas en el cuadro de valor de la propiedad **BookmarkName** y escriba `Guess` en el cuadro de valor de la propiedad **resultado** .  
  
17. Escriba la siguiente expresión en el cuadro de valor de la propiedad de **condición** **adivinar** la transición correcta.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
    > [!NOTE]
    > Una transición se produce cuando se recibe el evento desencadenador y <xref:System.Activities.Statements.Transition.Condition%2A>, si está presente, se evalúa como `True`. En esta transición, si el usuario `Guess` coincide con el generado aleatoriamente `Target` , el control pasa a **FinalState** y el flujo de trabajo se completa.  
  
19. Dependiendo de si la estimación es correcta, el flujo de trabajo debe realizar la transición a **FinalState** o al estado **Enter Guess** para otro intento. Ambas transiciones comparten el mismo desencadenador de espera para que la estimación del usuario se reciba a través de la actividad **ReadInt** . Esto se denomina una transición compartida. Para crear una transición compartida, haga clic en el círculo que indica el inicio de la transición **Guess correct** y arrástrela hasta el estado deseado. En este caso, la transición es una transición automática, por lo que debe arrastrar el punto inicial de la transición **Guess correct** y colocarla de nuevo en la parte inferior del estado **Enter Guess** . Después de crear la transición, selecciónela en el diseñador de flujo de trabajo y establezca su propiedad **displayName** en **Guess Incorrect**.  
  
    > [!NOTE]
    > Las transiciones compartidas también se pueden crear desde el diseñador de transición haciendo clic en **Agregar transición de desencadenador compartido** en la parte inferior del diseñador de transición y, a continuación, seleccionando el estado de destino deseado en la lista desplegable **Estados disponibles para conectar** .  
    > [!NOTE]
    > Tenga en cuenta que si la condición <xref:System.Activities.Statements.Transition.Condition%2A> de una transición se evalúa en `false` (o todas las condiciones de una transición de desencadenador compartido se evalúan en `false`), la transición no se producirá y se reprogramarán todos los desencadenadores para todas las transiciones desde el estado. En este tutorial, no puede suceder esta situación debido a la forma en que están configuradas las condiciones (tenemos acciones específicas para determinar si el supuesto es correcto o incorrecto).  
  
20. Haga doble clic en la transición **adivinar incorrectamente** en el diseñador de flujo de trabajo para expandirla. Tenga en cuenta que el **desencadenador** ya está establecido en la misma actividad **ReadInt** usada por la transición **Guess correct** .  
  
21. Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. Arrastre una actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la sección **acción** de la transición.  
  
23. Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** .  
  
    ```text
    Guess < Target
    ```  
  
24. Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que una esté en la sección **then** de la actividad **If** y otra esté en la sección **else** .  
  
25. Haga clic en la actividad **WriteLine** en la sección **then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Text** .  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. Haga clic en la actividad **WriteLine** en la sección **otro** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** .  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.  
  
     En el siguiente ejemplo se muestra el flujo de trabajo completado.  
  
     ![Ilustración que muestra el flujo de trabajo de equipo de estado completado.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a>Para compilar el flujo de trabajo  
  
1. Presione CTRL+MAYÚS+B para compilar la solución.  
  
     Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md). Si ya ha completado el paso [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de máquina de Estados desde este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).  
  
## <a name="see-also"></a>Consulta también

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [Programación de Windows Workflow Foundation](programming.md)
- [Diseñar flujos de trabajo](designing-workflows.md)
- [Tutorial de introducción](getting-started-tutorial.md)
- [Procedimiento para crear una actividad](how-to-create-an-activity.md)
- [Procedimiento para ejecutar un flujo de trabajo](how-to-run-a-workflow.md)
