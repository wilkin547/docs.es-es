---
title: Procedimiento para ejecutar un flujo de trabajo
description: En este artículo se muestra cómo crear un host de flujo de trabajo y ejecutar el flujo de trabajo definido en un artículo anterior en esta Windows Workflow Foundation serie de tutoriales.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 7f76ed5ad1a76a155489339a9febf12eefd64ae8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279992"
---
# <a name="how-to-run-a-workflow"></a>Procedimiento para ejecutar un flujo de trabajo

Este tema es una continuación del tutorial introductorio de Windows Workflow Foundation y explica cómo crear un host de flujo de trabajo y ejecutar el flujo de trabajo definido en el tema [How to: Create a Workflow](how-to-create-a-workflow.md) anterior.

> [!NOTE]
> Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, primero debe finalizar [How to: Create an Activity](how-to-create-an-activity.md) y [How to: Create a Workflow](how-to-create-a-workflow.md).

> [!NOTE]
> Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
### <a name="to-create-the-workflow-host-project"></a>Para crear el proyecto de host de flujo de trabajo  
  
1. Abra la solución del tema anterior [Cómo: crear una actividad](how-to-create-an-activity.md) mediante Visual Studio 2012.  
  
2. Haga clic con el botón secundario en la solución **WF45GettingStartedTutorial** en el **Explorador de soluciones** y seleccione **Agregar**, **Nuevo proyecto**.  
  
    > [!TIP]
    > Si no está visible la ventana **Explorador de soluciones**, seleccione **Explorador de soluciones** en el menú **Ver**.

3. En el nodo **Instalado** , seleccione **Visual C#**, **Flujo de trabajo** (o **Visual Basic**, **Flujo de trabajo**).

    > [!NOTE]
    > En función del lenguaje de programación configurado como lenguaje principal en Visual Studio, es posible que el nodo **Visual C#** o **Visual Basic** se encuentre debajo del nodo **Otros lenguajes** del nodo **Instalados**.

     Asegúrese de que **.NET Framework 4.5** está seleccionado en la lista desplegable de versiones de .NET Framework. Seleccione **Aplicación de consola de flujos de trabajo** en la lista **Flujo de trabajo** . Escriba `NumberGuessWorkflowHost` en el cuadro **Nombre** y haga clic en **Aceptar**. Así se crea una aplicación de flujo de trabajo de inicio con soporte básico de hospedaje de flujo de trabajo. Este código de hospedaje básico se modifica y se usa para ejecutar la aplicación de flujo de trabajo.

4. Haga clic con el botón secundario en el proyecto **NumberGuessWorkflowHost** recién agregado en el **Explorador de soluciones** y seleccione **Agregar referencia**. Seleccione **Solución** en la lista **Agregar referencia** , marque la casilla junto **NumberGuessWorkflowActivities** y, a continuación, haga clic en **Aceptar**.

5. Haga clic con el botón secundario en **Workflow1.xaml** en el **Explorador de soluciones** y elija **Eliminar**. Haga clic en **ACEPTAR** para continuar.

### <a name="to-modify-the-workflow-hosting-code"></a>Para modificar el código de hospedaje de flujo de trabajo

1. Haga doble clic en **Program.cs** o en **Module1.vb** en el **Explorador de soluciones** para mostrar el código.

    > [!TIP]
    > Si no está visible la ventana **Explorador de soluciones**, seleccione **Explorador de soluciones** en el menú **Ver**.

     Dado que este proyecto se creó con la plantilla **Aplicación de consola de flujos de trabajo** , **Program.cs** o **Module1.vb** , contiene el siguiente código básico de hospedaje de flujo de trabajo.

    ```vb
    ' Create and cache the workflow definition.
    Dim workflow1 As Activity = New Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition.
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     Este código de hospedaje generado usa <xref:System.Activities.WorkflowInvoker>. <xref:System.Activities.WorkflowInvoker> proporciona una manera sencilla de invocar un flujo de trabajo como si fuera una llamada al método y se puede usar solo para los flujos de trabajo que no usan la persistencia. <xref:System.Activities.WorkflowApplication> proporciona un modelo más enriquecido para ejecutar flujos de trabajo que incluye notificación de eventos de ciclo de vida, control de ejecución, reanudación de marcadores y persistencia. Este ejemplo usa marcadores y <xref:System.Activities.WorkflowApplication> se usa para hospedar el flujo de trabajo. Agregue la siguiente instrucción `using` o **Imports** al principio de **Program.cs** o **Module1.vb** debajo de las instrucciones **using** o **Imports** existentes.

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     Reemplace las líneas de código que usan <xref:System.Activities.WorkflowInvoker> por el siguiente código básico de hospedaje <xref:System.Activities.WorkflowApplication> . Este código de hospedaje de ejemplo muestra los pasos básicos para hospedar e invocar un flujo de trabajo, pero no contiene, sin embargo, la funcionalidad necesaria para ejecutar correctamente el flujo de trabajo en este tema. En los pasos que figuran a continuación, el código básico se modifica y se agregan características adicionales hasta completar la aplicación.

    > [!NOTE]
    > Reemplace `Workflow1` en estos ejemplos por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del flujo de trabajo que completara en el paso [How to: Create a Workflow](how-to-create-a-workflow.md) anterior. Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     Este código crea un objeto <xref:System.Activities.WorkflowApplication>, se suscribe a tres eventos de ciclo de vida de flujo de trabajo, inicia el flujo de trabajo con una llamada a <xref:System.Activities.WorkflowApplication.Run%2A>y espera a que el flujo de trabajo se complete. Cuando el flujo de trabajo finaliza, se establece <xref:System.Threading.AutoResetEvent> y se completa la aplicación host.

### <a name="to-set-input-arguments-of-a-workflow"></a>Para definir argumentos de entrada de un flujo de trabajo

1. Agregue la siguiente instrucción al principio de **Program.cs** o **Module1.vb** debajo de las instrucciones `using` o `Imports` existentes.

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. Reemplace la línea de código que crea el nuevo <xref:System.Activities.WorkflowApplication> con el siguiente código que crea y pasa un diccionario de parámetros al flujo de trabajo cuando se crea.

    > [!NOTE]
    > Reemplace `Workflow1` en estos ejemplos por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del flujo de trabajo que completara en el paso [How to: Create a Workflow](how-to-create-a-workflow.md) anterior. Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Este diccionario contiene un elemento con una clave de `MaxNumber`. Las claves del diccionario de entrada corresponden a argumentos de entrada en la actividad raíz del flujo de trabajo. El flujo de trabajo usa`MaxNumber` para determinar el límite superior para el número generado aleatoriamente.

### <a name="to-retrieve-output-arguments-of-a-workflow"></a>Para recuperar parámetros de salida de un flujo de trabajo

1. Modifique el controlador <xref:System.Activities.WorkflowApplication.Completed%2A> para recuperar y mostrar el número de intentos que usó el flujo de trabajo.

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a>Para reanudar un marcador

1. Agregue el siguiente código en la parte superior del método `Main` justo después de la declaración <xref:System.Threading.AutoResetEvent> existente.

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. Agregue el siguiente controlador <xref:System.Activities.WorkflowApplication.Idle%2A> justo después de los tres controladores de ciclo de vida de flujo de trabajo existentes en `Main`.

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     Cada vez que el flujo de trabajo se vuelve inactivo a la espera de la siguiente estimación, se llama a este controlador y `idleAction` <xref:System.Threading.AutoResetEvent> se establece. El código en el siguiente paso usa `idleEvent` y `syncEvent` para determinar si el flujo de trabajo está esperando la siguiente suposición o si se ha completado.

    > [!NOTE]
    > En este ejemplo, la aplicación host usa eventos de restablecimiento automático en los controladores <xref:System.Activities.WorkflowApplication.Completed%2A> y <xref:System.Activities.WorkflowApplication.Idle%2A> para sincronizar la aplicación host con el progreso del flujo de trabajo. No es necesario bloquear y esperar a que el flujo de trabajo se vuelva inactivo para reanudar un marcador, aunque en este ejemplo los eventos de sincronización resultan necesarios para que el host sepa si se ha completado el flujo de trabajo o si está esperando más entradas de usuario mediante <xref:System.Activities.Bookmark>. Para obtener más información, vea [marcadores](bookmarks.md).

3. Quite la llamada a `WaitOne`y reemplácela con código para recopilar la entrada del usuario y reanudar el marcador <xref:System.Activities.Bookmark>.

     Quite la siguiente línea de código.

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     Reemplácela con el siguiente ejemplo.

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="to-build-and-run-the-application"></a><a name="BKMK_ToRunTheApplication"></a> Para compilar y ejecutar la aplicación

1. Haga clic con el botón secundario en **NumberGuessWorkflowHost** en el **Explorador de soluciones** y seleccione **Establecer como proyecto de inicio**.

2. Presione CTRL+F5 para compilar y ejecutar la aplicación. Intente adivinar el número en los menos intentos posibles.

     Para probar la aplicación con uno de los demás estilos de flujo de trabajo, reemplace `Workflow1` en el código que crea <xref:System.Activities.WorkflowApplication> por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del estilo de flujo de trabajo que desee.

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     Para obtener instrucciones sobre cómo agregar la persistencia a una aplicación de flujo de trabajo, consulte el siguiente tema: [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).

## <a name="example"></a>Ejemplo

 En el ejemplo siguiente se muestra la lista de código completa del método `Main` .

> [!NOTE]
> Reemplace `Workflow1` en estos ejemplos por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del flujo de trabajo que completara en el paso [How to: Create a Workflow](how-to-create-a-workflow.md) anterior. Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a>Vea también

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [Programación de Windows Workflow Foundation](programming.md)
- [Tutorial de introducción](getting-started-tutorial.md)
- [Procedimiento para crear un flujo de trabajo](how-to-create-a-workflow.md)
- [Procedimiento para crear y ejecutar un flujo de trabajo de larga duración](how-to-create-and-run-a-long-running-workflow.md)
- [Esperar entrada en un flujo de trabajo](waiting-for-input-in-a-workflow.md)
- [Hospedar flujos de trabajo](hosting-workflows.md)
