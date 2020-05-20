---
title: Usar WorkflowInvoker y WorkflowApplication
description: En este artículo se describe el hospedaje de flujos de trabajo mediante WorkflowInvoker y WorkflowApplication en Windows Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: cd0e583c-a3f9-4fa2-b247-c7b3368c48a7
ms.openlocfilehash: 50ad291bc73818092e7a08d489d6860636f9c379
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421324"
---
# <a name="using-workflowinvoker-and-workflowapplication"></a>Usar WorkflowInvoker y WorkflowApplication
Windows Workflow Foundation (WF) proporciona varios métodos para hospedar flujos de trabajo. <xref:System.Activities.WorkflowInvoker> proporciona una manera sencilla de invocar un flujo de trabajo como si fuera una llamada al método y se puede usar solo para los flujos de trabajo que no usan la persistencia. <xref:System.Activities.WorkflowApplication> proporciona un modelo más enriquecido para ejecutar flujos de trabajo que incluye notificación de eventos de ciclo de vida, control de ejecución, reanudación de marcadores y persistencia. <xref:System.ServiceModel.Activities.WorkflowServiceHost> proporciona compatibilidad para las actividades de mensajería y se usa principalmente con servicios de flujo de trabajo. Este tema presenta el hospedaje del flujo de trabajo con <xref:System.Activities.WorkflowInvoker> y <xref:System.Activities.WorkflowApplication>. Para obtener más información sobre el hospedaje de flujos de trabajo con <xref:System.ServiceModel.Activities.WorkflowServiceHost> , vea Introducción a los servicios de [flujo](../wcf/feature-details/workflow-services.md) de trabajo y [host Workflow Services](../wcf/feature-details/hosting-workflow-services-overview.md).  
  
## <a name="using-workflowinvoker"></a>Usar WorkflowInvoker  
 <xref:System.Activities.WorkflowInvoker> proporciona un modelo para ejecutar un flujo de trabajo como si fuera una llamada al método. Para invocar un flujo de trabajo mediante <xref:System.Activities.WorkflowInvoker>, llame al método <xref:System.Activities.WorkflowInvoker.Invoke%2A> y pase la definición del flujo de trabajo que se vaya a invocar. En este ejemplo, se invoca una actividad <xref:System.Activities.Statements.WriteLine> mediante <xref:System.Activities.WorkflowInvoker>.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#1)]  
  
 Cuando se invoca un flujo de trabajo con <xref:System.Activities.WorkflowInvoker>, el flujo de trabajo se ejecuta en el subproceso que realiza la llamada y el método <xref:System.Activities.WorkflowInvoker.Invoke%2A> se bloquea hasta que el flujo de trabajo haya finalizado, incluido el tiempo de inactividad. Para configurar un intervalo de tiempo de espera en el que se debe completar el flujo de trabajo, use una de las sobrecargas <xref:System.Activities.WorkflowInvoker.Invoke%2A> que tome un parámetro <xref:System.TimeSpan>. En este ejemplo, se invoca un flujo de trabajo dos veces con dos intervalos de tiempo de espera diferentes. El primer flujo de trabajo se completa, pero el segundo no.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#50](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#50)]  
  
> [!NOTE]
> La excepción <xref:System.TimeoutException> solo se produce si se agota el tiempo de espera y el flujo de trabajo queda inactivo durante la ejecución. Un flujo de trabajo que tarda en completarse más tiempo que el especificado por el intervalo de tiempo de espera se completa correctamente si el flujo de trabajo no queda inactivo.  
  
 <xref:System.Activities.WorkflowInvoker> también proporciona versiones asincrónicas del método de invocación. Para obtener más información, vea <xref:System.Activities.WorkflowInvoker.InvokeAsync%2A> y <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A>.  
  
### <a name="setting-input-arguments-of-a-workflow"></a>Definir argumentos de entrada de un flujo de trabajo  
 Los datos se pueden pasar a un flujo de trabajo mediante un diccionario de parámetros de entrada, con claves por nombre de argumento, que se asignan a los argumentos de entrada del flujo de trabajo. En este ejemplo, se invoca <xref:System.Activities.Statements.WriteLine> y el valor de su argumento <xref:System.Activities.Statements.WriteLine.Text%2A> se especifica con el diccionario de parámetros de entrada.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#3)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a>Recuperar argumentos de salida de un flujo de trabajo  
 Los parámetros de salida de un flujo de trabajo se pueden obtener usando el diccionario de salidas que se devuelve de la llamada a <xref:System.Activities.WorkflowInvoker.Invoke%2A>. En el siguiente ejemplo se invoca un flujo de trabajo formado por una sola actividad `Divide` que tiene dos argumentos de entrada y dos argumentos de salida. Cuando se invoca el flujo de trabajo, se pasa el diccionario de `arguments` que contiene los valores de cada argumento de entrada, ordenados por nombre de argumento. Cuando la llamada a `Invoke` devuelve resultados, cada uno de los argumentos de salida se devuelve en el diccionario `outputs`, ordenados por nombre de argumento.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#120](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#120)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#20](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#20)]  
  
 Si el flujo de trabajo se deriva de <xref:System.Activities.ActivityWithResult>, como `CodeActivity<TResult>` o `Activity<TResult>`, y hay argumentos de salida, además del argumento de salida <xref:System.Activities.Activity%601.Result%2A> bien determinado, se debe utilizar una sobrecarga no genérica de `Invoke` para recuperar argumentos adicionales. Para ello, la definición de flujo de trabajo pasada a `Invoke` debe ser de tipo <xref:System.Activities.Activity>. En este ejemplo la actividad `Divide` se deriva de `CodeActivity<int>`, pero se declara como <xref:System.Activities.Activity> para utilizar una sobrecarga no genérica de `Invoke` que devuelve un diccionario de argumentos en lugar de un valor único.  
  
 [!code-csharp[CFX_WorkflowInvokerExample#121](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#121)]  
  
 [!code-csharp[CFX_WorkflowInvokerExample#21](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowinvokerexample/cs/program.cs#21)]  
  
## <a name="using-workflowapplication"></a>Usar WorkflowApplication  
 <xref:System.Activities.WorkflowApplication> proporciona un amplio conjunto de características para la administración de instancias de flujo de trabajo. <xref:System.Activities.WorkflowApplication> actúa como un proxy seguro para subprocesos para la <xref:System.Activities.Hosting.WorkflowInstance> real, que encapsula el tiempo de ejecución y proporciona métodos para crear y cargar las instancias de flujo de trabajo, pausar y reanudar, terminar y notificar los eventos de ciclo de vida. Para ejecutar un flujo de trabajo mediante <xref:System.Activities.WorkflowApplication>, cree <xref:System.Activities.WorkflowApplication>, suscríbase a cualquier evento de ciclo de vida que desee, inicie el flujo de trabajo y, a continuación, espere a que termine. En este ejemplo, se crea una definición de flujo de trabajo que consta de una actividad <xref:System.Activities.Statements.WriteLine> y se crea una <xref:System.Activities.WorkflowApplication> usando la definición de flujo de trabajo especificada. Se controla <xref:System.Activities.WorkflowApplication.Completed%2A> de forma que se notifica al host cuando el flujo de trabajo se completa, el flujo de trabajo se inicia con una llamada a <xref:System.Activities.WorkflowApplication.Run%2A> y el host espera a que el flujo de trabajo se complete. Cuando se completa el flujo de trabajo, se establece <xref:System.Threading.AutoResetEvent> y la aplicación host puede reanudar la ejecución, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#31](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#31)]  
  
### <a name="workflowapplication-lifecycle-events"></a>Eventos de ciclo de vida de WorkflowApplication  
 Además de <xref:System.Activities.WorkflowApplication.Completed%2A>, se puede notificar a los autores de hosts cuando se descargue un flujo de trabajo (<xref:System.Activities.WorkflowApplication.Unloaded%2A>), se anule (<xref:System.Activities.WorkflowApplication.Aborted%2A>), se vuelva inactivo (<xref:System.Activities.WorkflowApplication.Idle%2A> y <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>) o se produzca una excepción no controlada (<xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>). Los desarrolladores de aplicaciones de flujo de trabajo pueden administrar estas notificaciones y realizar la acción adecuada, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#32](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#32)]  
  
### <a name="setting-input-arguments-of-a-workflow"></a>Definir argumentos de entrada de un flujo de trabajo  
 Se pueden pasar datos a un flujo de trabajo cuando se inicia gracias a un diccionario de parámetros, al igual que la manera en que los datos se pasan cuando se usa <xref:System.Activities.WorkflowInvoker>. Cada elemento en el diccionario se asigna a un argumento de entrada del flujo de trabajo especificado. En este ejemplo, se invoca un flujo de trabajo que está compuesto de una actividad <xref:System.Activities.Statements.WriteLine> y se especifica su argumento <xref:System.Activities.Statements.WriteLine.Text%2A> mediante el diccionario de parámetros de entrada.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#30](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#30)]  
  
### <a name="retrieving-output-arguments-of-a-workflow"></a>Recuperar argumentos de salida de un flujo de trabajo  
 Cuando un flujo de trabajo se completa, se puede recuperar cualquier parámetro de salida en el controlador <xref:System.Activities.WorkflowApplication.Completed%2A> teniendo acceso al diccionario <xref:System.Activities.WorkflowApplicationCompletedEventArgs.Outputs%2A?displayProperty=nameWithType>. En el siguiente ejemplo, se hospeda un flujo de trabajo utilizando <xref:System.Activities.WorkflowApplication>. Una <xref:System.Activities.WorkflowApplication> instancia de se construye utilizando una definición de flujo de trabajo que consta de una sola `DiceRoll` actividad. La actividad `DiceRoll` tiene dos argumentos de salida que representan los resultados de la operación de tirar los dados. Cuando se completa el flujo de trabajo, las salidas se recuperan en el controlador <xref:System.Activities.WorkflowApplication.Completed%2A>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#130](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#130)]  
  
 [!code-csharp[CFX_WorkflowApplicationExample#21](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#21)]  
  
> [!NOTE]
> <xref:System.Activities.WorkflowApplication> y <xref:System.Activities.WorkflowInvoker> toman un diccionario de argumentos de entrada y devuelven un diccionario de argumentos `out`. Estos parámetros, propiedades y valores devueltos del diccionario son del tipo `IDictionary<string, object>`. La instancia real de la clase de diccionario que se pasa puede ser cualquier clase que implemente `IDictionary<string, object>`. En estos ejemplos, se usa `Dictionary<string, object>`. Para obtener más información acerca de los diccionarios, vea <xref:System.Collections.Generic.IDictionary%602> y <xref:System.Collections.Generic.Dictionary%602> .  
  
### <a name="passing-data-into-a-running-workflow-using-bookmarks"></a>Pasar datos en un flujo de trabajo en ejecución mediante marcadores  
 Los marcadores son el mecanismo por el que una actividad puede esperar de forma pasiva a que se reanude y, además, un mecanismo para pasar los datos a una instancia de flujo de trabajo en ejecución. Si una actividad está esperando los datos, puede crear <xref:System.Activities.Bookmark> y registrar un método de devolución de llamada que se va a llamar cuando se reanude <xref:System.Activities.Bookmark>, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
 Cuando se ejecuta, la actividad `ReadLine` crea un <xref:System.Activities.Bookmark>, registra una devolución de llamada y, a continuación, espera a que se reanude <xref:System.Activities.Bookmark>. Cuando lo haga, la actividad `ReadLine` asigna los datos que se pasaron con <xref:System.Activities.Bookmark> a su argumento <xref:System.Activities.Activity%601.Result%2A>. En este ejemplo, se crea un flujo de trabajo que usa la actividad `ReadLine` para recopilar el nombre del usuario y mostrarlo en la ventana de la consola.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#22](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#22)]  
  
 Cuando se ejecuta la actividad `ReadLine`, crea un <xref:System.Activities.Bookmark> denominado `UserName` y, a continuación, espera a que se reanude el marcador. El host recopila los datos deseados y, a continuación, reanuda <xref:System.Activities.Bookmark>. El flujo de trabajo se reanuda, muestra el nombre y, a continuación, finaliza.  
  
 La aplicación host puede inspeccionar el flujo de trabajo para determinar si hay marcadores activos. Puede hacerlo llamando al método <xref:System.Activities.WorkflowApplication.GetBookmarks%2A> de una instancia <xref:System.Activities.WorkflowApplication> o inspeccionando el objeto <xref:System.Activities.WorkflowApplicationIdleEventArgs> en el controlador <xref:System.Activities.WorkflowApplication.Idle%2A>.  
  
 El siguiente ejemplo de código es similar al ejemplo anterior salvo que los marcadores activos se enumeran antes de que se reanude el marcador. Se inicia el flujo de trabajo, y una vez se ha creado el objeto <xref:System.Activities.Bookmark> y se ha quedado inactivo el flujo de trabajo, se llama al método <xref:System.Activities.WorkflowApplication.GetBookmarks%2A>. Cuando se completa el flujo de trabajo, se muestra la siguiente salida en la consola.  
  
 **¿Cómo se llama?**  
**BookmarkName: username-OwnerDisplayName: readline** 
 **Steve** 
 **Hola, Steve**

[!code-csharp[CFX_WorkflowApplicationExample#14](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#14)]  
  
 El siguiente ejemplo de código inspecciona el objeto <xref:System.Activities.WorkflowApplicationIdleEventArgs> pasado al controlador de la propiedad <xref:System.Activities.WorkflowApplication.Idle%2A> de una instancia de <xref:System.Activities.WorkflowApplication>. En este ejemplo, el flujo de trabajo que va a estar inactivo tiene un objeto <xref:System.Activities.Bookmark> con el nombre `EnterGuess`, que una actividad denominada `ReadInt` posee. Este ejemplo de código se basa en [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md), que forma parte del [tutorial de introducción](getting-started-tutorial.md). Si el controlador de la propiedad <xref:System.Activities.WorkflowApplication.Idle%2A> en ese paso se modifica para contener el código de este ejemplo, se muestra la siguiente salida.  
  
 **BookmarkName: EnterGuess - OwnerDisplayName: ReadInt**

 [!code-csharp[CFX_WorkflowApplicationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#2)]  
  
## <a name="summary"></a>Resumen  
 <xref:System.Activities.WorkflowInvoker> proporciona una manera ligera de invocar los flujos de trabajo y, aunque proporciona los métodos para pasar los datos al principio de un flujo de trabajo y extraer los datos de un flujo de trabajo completado, no se proporciona para escenarios más complejos, que son aquellos en los se puede usar <xref:System.Activities.WorkflowApplication>.
