---
title: Uso de la actividad InvokePowerShell
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3ef8b539e490911e5454fe87db483508cc8a5d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-invokepowershell-activity"></a><span data-ttu-id="df20c-102">Uso de la actividad InvokePowerShell</span><span class="sxs-lookup"><span data-stu-id="df20c-102">Using the InvokePowerShell Activity</span></span>
<span data-ttu-id="df20c-103">En el ejemplo InvokePowerShell se muestra cómo invocar comandos de Windows PowerShell mediante la actividad `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-103">The InvokePowerShell sample demonstrates how to invoke Windows PowerShell commands using the `InvokePowerShell` activity.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="df20c-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="df20c-104">Demonstrates</span></span>  
  
-   <span data-ttu-id="df20c-105">Innovación simple de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df20c-105">Simple innovation of Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="df20c-106">Recuperar valores de la canalización de salida de Windows PowerShell y almacenarlos en variables de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="df20c-106">Retrieve values from the Windows PowerShell output pipeline and store them in workflow variables.</span></span>  
  
-   <span data-ttu-id="df20c-107">Pasar datos a Windows PowerShell como canalización de entrada para un comando en ejecución.</span><span class="sxs-lookup"><span data-stu-id="df20c-107">Pass data into windows PowerShell as input pipeline for an executing command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="df20c-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="df20c-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="df20c-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="df20c-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="df20c-110">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df20c-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="df20c-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="df20c-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a><span data-ttu-id="df20c-112">Explicación</span><span class="sxs-lookup"><span data-stu-id="df20c-112">Discussion</span></span>  
 <span data-ttu-id="df20c-113">Este ejemplo contiene estos tres proyectos.</span><span class="sxs-lookup"><span data-stu-id="df20c-113">This sample contains the following three projects.</span></span>  
  
|<span data-ttu-id="df20c-114">Nombre del proyecto</span><span class="sxs-lookup"><span data-stu-id="df20c-114">Project Name</span></span>|<span data-ttu-id="df20c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="df20c-115">Description</span></span>|<span data-ttu-id="df20c-116">Archivos principales</span><span class="sxs-lookup"><span data-stu-id="df20c-116">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="df20c-117">CodedClient</span><span class="sxs-lookup"><span data-stu-id="df20c-117">CodedClient</span></span>|<span data-ttu-id="df20c-118">Una aplicación cliente de ejemplo que utiliza la actividad de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df20c-118">A sample client application that uses the PowerShell activity.</span></span>|<span data-ttu-id="df20c-119">-   **Program.cs**: crea mediante programación un flujo de trabajo basado en la secuencia que llama a la actividad InvokePowerShell.</span><span class="sxs-lookup"><span data-stu-id="df20c-119">-   **Program.cs**: Programmatically creates a sequence-based workflow that calls the InvokePowerShell activity.</span></span>|  
|<span data-ttu-id="df20c-120">DesignerClient</span><span class="sxs-lookup"><span data-stu-id="df20c-120">DesignerClient</span></span>|<span data-ttu-id="df20c-121">Un conjunto de actividades personalizadas que contiene la actividad personalizada `InvokePowerShell` y otras actividades personalizadas y un flujo de trabajo que los utiliza.</span><span class="sxs-lookup"><span data-stu-id="df20c-121">A set of custom activities that contain the `InvokePowerShell` custom activity and other miscellaneous custom activities, and a workflow that uses them.</span></span>|<ul><li><span data-ttu-id="df20c-122">Actividades:</span><span class="sxs-lookup"><span data-stu-id="df20c-122">Activities:</span></span><br /><br /> <ul><li><span data-ttu-id="df20c-123">**PrintCollection.cs**: una actividad de aplicación auxiliar que imprime todos los elementos de una colección en la consola.</span><span class="sxs-lookup"><span data-stu-id="df20c-123">**PrintCollection.cs**: A helper activity that prints all the items in a collection to the console.</span></span></li><li><span data-ttu-id="df20c-124">**ReadLine.cs**: una actividad de aplicación auxiliar para leer la entrada desde la consola.</span><span class="sxs-lookup"><span data-stu-id="df20c-124">**ReadLine.cs**: A helper activity for reading input from the console.</span></span></li></ul></li><li><span data-ttu-id="df20c-125">Sistema de archivos:</span><span class="sxs-lookup"><span data-stu-id="df20c-125">File System:</span></span><br /><br /> <ul><li><span data-ttu-id="df20c-126">**Copy.XAML**: una actividad que copia un archivo.</span><span class="sxs-lookup"><span data-stu-id="df20c-126">**Copy.xaml**: An activity that copies a file.</span></span></li><li><span data-ttu-id="df20c-127">**CreateFile.xaml**: una actividad que crea un archivo.</span><span class="sxs-lookup"><span data-stu-id="df20c-127">**CreateFile.xaml**: An activity that creates a file.</span></span></li><li><span data-ttu-id="df20c-128">**DeleteFile.xaml**: una actividad que elimina un archivo.</span><span class="sxs-lookup"><span data-stu-id="df20c-128">**DeleteFile.xaml**: An activity that deletes a file.</span></span></li><li><span data-ttu-id="df20c-129">**MakeDir.xaml**: una actividad que crea un directorio.</span><span class="sxs-lookup"><span data-stu-id="df20c-129">**MakeDir.xaml**: An activity that creates a directory.</span></span></li><li><span data-ttu-id="df20c-130">**Move.XAML**: una actividad que mueve un archivo.</span><span class="sxs-lookup"><span data-stu-id="df20c-130">**Move.xaml**: An activity that moves a file.</span></span></li><li><span data-ttu-id="df20c-131">**ReadFile.xaml**: una actividad que lee un archivo y devuelve su contenido.</span><span class="sxs-lookup"><span data-stu-id="df20c-131">**ReadFile.xaml**: An activity that reads a file and returns its contents.</span></span></li><li><span data-ttu-id="df20c-132">**TestPath.xaml**: una actividad que comprueba la existencia de una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="df20c-132">**TestPath.xaml**: An activity that tests for the existence of a path.</span></span></li></ul></li><li><span data-ttu-id="df20c-133">Proceso:</span><span class="sxs-lookup"><span data-stu-id="df20c-133">Process:</span></span><br /><br /> <ul><li><span data-ttu-id="df20c-134">**GetProcess.xaml**: una actividad que obtiene una lista de procesos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="df20c-134">**GetProcess.xaml**: An activity that gets a list of running processes.</span></span></li><li><span data-ttu-id="df20c-135">**StopProcess.xaml**: una actividad que detiene un proceso concreto.</span><span class="sxs-lookup"><span data-stu-id="df20c-135">**StopProcess.xaml**: An activity that stops a specific process.</span></span></li></ul></li><li><span data-ttu-id="df20c-136">**Program.cs**: llama el flujo de trabajo Sequence1.</span><span class="sxs-lookup"><span data-stu-id="df20c-136">**Program.cs**: Calls the Sequence1 workflow.</span></span></li><li><span data-ttu-id="df20c-137">**Sequence1.XAML**: un flujo de trabajo basado en secuencia.</span><span class="sxs-lookup"><span data-stu-id="df20c-137">**Sequence1.xaml**: A sequence-based workflow.</span></span></li></ul>|  
|<span data-ttu-id="df20c-138">PowerShell</span><span class="sxs-lookup"><span data-stu-id="df20c-138">PowerShell</span></span>|<span data-ttu-id="df20c-139">La actividad `InvokePowerShell` y sus diseñadores asociados.</span><span class="sxs-lookup"><span data-stu-id="df20c-139">The `InvokePowerShell` activity and its associated designers.</span></span>|<span data-ttu-id="df20c-140">Archivos de actividad</span><span class="sxs-lookup"><span data-stu-id="df20c-140">Activity Files</span></span><br /><br /> <span data-ttu-id="df20c-141">-   **ExecutePowerShell.cs**: la lógica de ejecución principal de la actividad.</span><span class="sxs-lookup"><span data-stu-id="df20c-141">-   **ExecutePowerShell.cs**: The main execution logic of the activity.</span></span><br /><span data-ttu-id="df20c-142">-   **InvokePowerShell.cs**: el contenedor alrededor de la lógica de ejecución principal, que contiene una versión genérica (valor devuelto) y una versión no genérica (valor no devuelto).</span><span class="sxs-lookup"><span data-stu-id="df20c-142">-   **InvokePowerShell.cs**: The wrapper around the main execution logic, which contains a generic (return value) version and a non-generic (non-return value) version.</span></span> <span data-ttu-id="df20c-143">Esta es la interfaz pública de la actividad.</span><span class="sxs-lookup"><span data-stu-id="df20c-143">This is the public interface for the activity.</span></span><br /><span data-ttu-id="df20c-144">-   **NoPersistZone.cs**: esta actividad evita que las actividades secundarias se conserven.</span><span class="sxs-lookup"><span data-stu-id="df20c-144">-   **NoPersistZone.cs**: This activity prevents any child activities from persisting.</span></span> <span data-ttu-id="df20c-145">Esta clase se utiliza dentro de la implementación de la actividad `InvokePowerShell` para evitar que la actividad se conserve en la mitad de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="df20c-145">This class is used within the `InvokePowerShell` activity implementation to prevent the activity from being persisted mid-execution.</span></span><br /><br /> <span data-ttu-id="df20c-146">Archivos de diseñador:</span><span class="sxs-lookup"><span data-stu-id="df20c-146">Designer files:</span></span><br /><br /> <span data-ttu-id="df20c-147">1.  **ArgumentDictionaryEditor.cs**: un diálogo de Windows que permite al usuario modificar los argumentos de la `InvokePowerShell` actividad.</span><span class="sxs-lookup"><span data-stu-id="df20c-147">1.  **ArgumentDictionaryEditor.cs**: A Windows dialog that allows the user to edit the arguments of the `InvokePowerShell` activity.</span></span><br /><span data-ttu-id="df20c-148">2.  **GenericInvokePowerShellDesigner.xaml** y **GenericInvokePowerShellDesigner.xaml.cs**: define el aspecto de la interfaz genérica `InvokePowerShell` actividad en [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df20c-148">2.  **GenericInvokePowerShellDesigner.xaml** and **GenericInvokePowerShellDesigner.xaml.cs**: Defines the appearance of the generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span><br /><span data-ttu-id="df20c-149">3.  **InvokePowerShellDesigner.xaml** y **InvokePowerShellDesigner.cs**: define el aspecto de la interfaz no genérica `InvokePowerShell` actividad en [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df20c-149">3.  **InvokePowerShellDesigner.xaml** and **InvokePowerShellDesigner.cs**: Defines the appearance of the non-generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>|  
  
 <span data-ttu-id="df20c-150">Primero se describen los proyectos de cliente, porque es más fácil entender la funcionalidad interna de la actividad de PowerShell una vez comprendido su uso.</span><span class="sxs-lookup"><span data-stu-id="df20c-150">The client projects are discussed first, as it is easier to understand the internal functionality of the PowerShell activity once its use is understood.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="df20c-151">Utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="df20c-151">Using This Sample</span></span>  
 <span data-ttu-id="df20c-152">En las siguientes secciones se describe cómo utilizar los tres proyectos del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="df20c-152">The following sections describe how to use the three projects in the sample.</span></span>  
  
### <a name="using-the-coded-client-project"></a><span data-ttu-id="df20c-153">Utilizar el proyecto de cliente codificado</span><span class="sxs-lookup"><span data-stu-id="df20c-153">Using the Coded Client Project</span></span>  
 <span data-ttu-id="df20c-154">El cliente del ejemplo crea mediante programación una actividad de secuencia, que contiene ejemplos de varios métodos diferentes de utilizar la actividad `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-154">The sample client programmatically creates a sequence activity, which contains examples of several different methods of using the `InvokePowerShell` activity.</span></span> <span data-ttu-id="df20c-155">La primera invocación inicia el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="df20c-155">The first invocation launches Notepad.</span></span>  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 <span data-ttu-id="df20c-156">La segunda invocación obtiene una lista de los procesos que se están ejecutando en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="df20c-156">The second invocation gets a list of the processes running on the local machine.</span></span>  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 <span data-ttu-id="df20c-157">`Output` es la variable utilizada para almacenar el resultado del comando.</span><span class="sxs-lookup"><span data-stu-id="df20c-157">`Output` is the variable used to store the output of the command.</span></span>  
  
 <span data-ttu-id="df20c-158">La llamada siguiente muestra cómo ejecutar un paso de procesamiento posterior en cada salida individual de la invocación de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df20c-158">The next call demonstrates how to run a post-processing step on each individual output of the PowerShell invocation.</span></span> <span data-ttu-id="df20c-159">`InitializationAction` se establece en la función que genera una representación de cadena de cada proceso.</span><span class="sxs-lookup"><span data-stu-id="df20c-159">`InitializationAction` is set to the function that outputs a string representation for each process.</span></span> <span data-ttu-id="df20c-160">La colección de estas cadenas se devuelve en la variable `Output` por la actividad `InvokePowerShell<string>`.</span><span class="sxs-lookup"><span data-stu-id="df20c-160">The collection of these strings is returned in the `Output` variable by the `InvokePowerShell<string>` activity.</span></span>  
  
 <span data-ttu-id="df20c-161">Las llamadas `InvokePowerShell` subsiguientes muestran el paso de datos a la actividad y la obtención de resultados y errores.</span><span class="sxs-lookup"><span data-stu-id="df20c-161">The succeeding `InvokePowerShell` calls demonstrate passing data into the activity and getting outputs and errors out.</span></span>  
  
### <a name="using-the-designer-client-project"></a><span data-ttu-id="df20c-162">Utilizar el proyecto de cliente de diseñador</span><span class="sxs-lookup"><span data-stu-id="df20c-162">Using the Designer Client Project</span></span>  
 <span data-ttu-id="df20c-163">El proyecto DesignerClient consta de un conjunto de actividades personalizadas, casi todas compiladas incluyendo la actividad `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-163">The DesignerClient project consists of a set of custom activities, almost all of which are built containing the `InvokePowerShell` activity.</span></span> <span data-ttu-id="df20c-164">La mayoría de las actividades llaman a la versión no genérica de la actividad `InvokePowerShell` y no esperan un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="df20c-164">Most of the activities call the non-generic version of the `InvokePowerShell` activity, and do not expect a return value.</span></span> <span data-ttu-id="df20c-165">Otras actividades utilizan la versión genérica de la actividad `InvokePowerShell` y utilizan el argumento `InitializationAction` para post-procesar los resultados.</span><span class="sxs-lookup"><span data-stu-id="df20c-165">Other activities use the generic version of the `InvokePowerShell` activity, and use the `InitializationAction` argument to post-process the results.</span></span>  
  
## <a name="using-the-powershell-project"></a><span data-ttu-id="df20c-166">Utilizar el proyecto PowerShell</span><span class="sxs-lookup"><span data-stu-id="df20c-166">Using the PowerShell Project</span></span>  
 <span data-ttu-id="df20c-167">La acción principal de la actividad tiene lugar en la clase `ExecutePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-167">The main action of the activity takes place in the `ExecutePowerShell` class.</span></span> <span data-ttu-id="df20c-168">Dado que la ejecución de los comandos de PowerShell no debe bloquear el subproceso del flujo de trabajo principal, la actividad se crea como actividad asincrónica que hereda de la clase <xref:System.Activities.AsyncCodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="df20c-168">Because the execution of PowerShell commands should not block the main workflow thread, the activity is created to be an asynchronous activity by inheriting from the <xref:System.Activities.AsyncCodeActivity> class.</span></span>  
  
 <span data-ttu-id="df20c-169">El tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> para empezar a ejecutar la actividad.</span><span class="sxs-lookup"><span data-stu-id="df20c-169">The <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> method is called by the workflow runtime to begin running the activity.</span></span> <span data-ttu-id="df20c-170">Se inicia llamando a PowerShell API para crear una canalización de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df20c-170">It starts by calling PowerShell APIs to create a PowerShell pipeline.</span></span>  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 <span data-ttu-id="df20c-171">A continuación, crea un comando de PowerShell y lo rellena con parámetros y variables.</span><span class="sxs-lookup"><span data-stu-id="df20c-171">It then creates a PowerShell command and populates it with parameters and variables.</span></span>  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 <span data-ttu-id="df20c-172">Las entradas canalizadas también se envían en este momento a la canalización.</span><span class="sxs-lookup"><span data-stu-id="df20c-172">The inputs piped in are also sent to the pipeline at this point.</span></span> <span data-ttu-id="df20c-173">Por último, la canalización se ajusta en un objeto `PipelineInvokerAsyncResult` y se devuelve.</span><span class="sxs-lookup"><span data-stu-id="df20c-173">Finally, the pipeline is wrapped in a `PipelineInvokerAsyncResult` object and returned.</span></span> <span data-ttu-id="df20c-174">El objeto `PipelineInvokerAsyncResult` registra un agente de escucha e invoca la canalización.</span><span class="sxs-lookup"><span data-stu-id="df20c-174">The `PipelineInvokerAsyncResult` object registers a listener and invokes the pipeline.</span></span>  
  
```  
pipeline.InvokeAsync();  
```  
  
 <span data-ttu-id="df20c-175">Cuando finaliza la ejecución, los resultados y los errores se almacenan dentro del mismo objeto `PipelineInvokerAsyncResult` y el control se devuelve al tiempo de ejecución del flujo de trabajo llamando al método de devolución de llamada pasado originalmente a <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="df20c-175">When execution finishes, output and errors are stored within the same `PipelineInvokerAsyncResult` object, and control is handed back to the workflow runtime by calling the callback method originally passed to <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span>  
  
 <span data-ttu-id="df20c-176">Al final de la ejecución del método, el tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> de la actividad.</span><span class="sxs-lookup"><span data-stu-id="df20c-176">At the end of the method's execution, the workflow runtime calls the activity’s <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> method.</span></span>  
  
 <span data-ttu-id="df20c-177">La clase `InvokePowerShell` ajusta la clase `ExecutePowerShellCommand` y crea dos versiones de la actividad; una versión genérica y otra no genérica.</span><span class="sxs-lookup"><span data-stu-id="df20c-177">The `InvokePowerShell` class wraps the `ExecutePowerShellCommand` class and creates two versions of the activity; a generic version and a non-generic version.</span></span> <span data-ttu-id="df20c-178">La versión no genérica devuelve el resultado de la ejecución de PowerShell directamente, mientras que la versión genérica transforma los resultados individuales al tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="df20c-178">The non-generic version returns the output of the PowerShell execution directly, whereas the generic version transforms the individual results to the generic type.</span></span>  
  
 <span data-ttu-id="df20c-179">La versión genérica de la actividad se implementa como un flujo de trabajo secuencial que llama a `ExecutePowerShellCommand` y post-procesa sus resultados.</span><span class="sxs-lookup"><span data-stu-id="df20c-179">The generic version of the activity is implemented as a sequential workflow that calls `ExecutePowerShellCommand` and post-processes its results.</span></span> <span data-ttu-id="df20c-180">Para cada elemento de la colección de resultados, el paso de procesamiento posterior llama a `InitializationAction` si se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="df20c-180">For each element in the result collection, the post-processing step calls `InitializationAction` if it is set.</span></span> <span data-ttu-id="df20c-181">De lo contrario, realiza una conversión de tipos simple.</span><span class="sxs-lookup"><span data-stu-id="df20c-181">Otherwise, it does a simple cast.</span></span>  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 <span data-ttu-id="df20c-182">Se creó un diseñador para cada una de las dos actividades `InvokePowerShell` (genérica y no genérica).</span><span class="sxs-lookup"><span data-stu-id="df20c-182">For each of the two `InvokePowerShell` activities (generic, and non-generic), a designer was created.</span></span> <span data-ttu-id="df20c-183">InvokePowerShellDesigner.xaml y su archivo .cs asociado definen el aspecto en [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] para la versión no genérica de la actividad `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-183">InvokePowerShellDesigner.xaml and its associated .cs file define the appearance in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] for the non-generic version of the `InvokePowerShell` activity.</span></span> <span data-ttu-id="df20c-184">Dentro de InvokePowerShellDesigner.xaml, <xref:System.Windows.Controls.DockPanel> se utiliza para representar la interfaz gráfica.</span><span class="sxs-lookup"><span data-stu-id="df20c-184">Inside InvokePowerShellDesigner.xaml, a <xref:System.Windows.Controls.DockPanel> is used to represent the graphical interface.</span></span>  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 <span data-ttu-id="df20c-185">Observe que la propiedad `Text` del cuadro de texto es un enlace bidireccional que garantiza que el valor de la propiedad `CommandText` de la actividad es equivalente al valor introducido en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="df20c-185">Note that the `Text` property of the text box is a two-way binding that ensures that the value of the activity’s `CommandText` property is equivalent to the value input into the designer.</span></span>  
  
 <span data-ttu-id="df20c-186">GenericInvokePowerShellDesigner.xaml y su archivo .cs asociado definen la interfaz gráfica de la actividad `InvokePowerShell` genérica.</span><span class="sxs-lookup"><span data-stu-id="df20c-186">GenericInvokePowerShellDesigner.xaml and its associated .cs file define the graphical interface for the generic `InvokePowerShell` activity.</span></span> <span data-ttu-id="df20c-187">El diseñador es ligeramente más complicado, porque permite a los usuarios establecer una acción `InitializationAction`.</span><span class="sxs-lookup"><span data-stu-id="df20c-187">The designer is slightly more complicated because it allows users to set an `InitializationAction`.</span></span> <span data-ttu-id="df20c-188">El elemento clave es el uso de <xref:System.Activities.Presentation.WorkflowItemPresenter> para permitir arrastrar y colocar las actividades secundarias en la superficie del diseñador de `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-188">The key element is the usage of <xref:System.Activities.Presentation.WorkflowItemPresenter> to allow drag and drop of child activities onto the `InvokePowerShell` designer surface.</span></span>  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 <span data-ttu-id="df20c-189">La personalización del diseñador no se detiene con los archivos .xaml que definen el aspecto de la actividad en el lienzo del diseño.</span><span class="sxs-lookup"><span data-stu-id="df20c-189">The designer customization does not stop with the .xaml files that define the appearance of the activity on the design canvas.</span></span> <span data-ttu-id="df20c-190">Los cuadros de diálogo utilizados para mostrar los parámetros de la actividad también se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="df20c-190">The dialog boxes used to display the parameters of the activity can also be customized.</span></span> <span data-ttu-id="df20c-191">Estos parámetros y las variables de PowerShell afectan al comportamiento de los comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df20c-191">These parameters and PowerShell variables affect the behavior of PowerShell commands.</span></span> <span data-ttu-id="df20c-192">La actividad los expone como <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` tipos.</span><span class="sxs-lookup"><span data-stu-id="df20c-192">The activity exposes them as <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` types.</span></span> <span data-ttu-id="df20c-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml y PropertyEditorResources.cs definen el cuadro de diálogo que permite modificar estos tipos.</span><span class="sxs-lookup"><span data-stu-id="df20c-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml and PropertyEditorResources.cs define the dialog box that allows you to edit these types.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="df20c-194">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="df20c-194">To set up, build, and run the sample</span></span>  
 <span data-ttu-id="df20c-195">Debe instalar Windows PowerShell para ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="df20c-195">You must install Windows PowerShell to run this sample.</span></span> <span data-ttu-id="df20c-196">Windows PowerShell se puede instalar desde esta ubicación: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span><span class="sxs-lookup"><span data-stu-id="df20c-196">Windows PowerShell can be installed from this location: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span></span>  
  
#### <a name="to-run-the-coded-client"></a><span data-ttu-id="df20c-197">Para ejecutar el cliente codificado</span><span class="sxs-lookup"><span data-stu-id="df20c-197">To run the coded client</span></span>  
  
1.  <span data-ttu-id="df20c-198">Abra PowerShell.sln mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df20c-198">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="df20c-199">Haga clic con el botón secundario en la solución y compílela.</span><span class="sxs-lookup"><span data-stu-id="df20c-199">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="df20c-200">Haga clic en el **CodedClient** de proyecto y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="df20c-200">Right-click the **CodedClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="df20c-201">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df20c-201">Press CTRL+F5 to run the application.</span></span>  
  
#### <a name="to-run-the-designer-client"></a><span data-ttu-id="df20c-202">Para ejecutar el cliente del diseñador</span><span class="sxs-lookup"><span data-stu-id="df20c-202">To run the designer client</span></span>  
  
1.  <span data-ttu-id="df20c-203">Abra PowerShell.sln mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df20c-203">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="df20c-204">Haga clic con el botón secundario en la solución y compílela.</span><span class="sxs-lookup"><span data-stu-id="df20c-204">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="df20c-205">Haga clic en el **DesignerClient** de proyecto y seleccione **establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="df20c-205">Right-click the **DesignerClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="df20c-206">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df20c-206">Press CTRL+F5 to run the application.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="df20c-207">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="df20c-207">Known Issues</span></span>  
  
1.  <span data-ttu-id="df20c-208">Si se hace referencia al ensamblado de actividad o proyecto `InvokePowerShell` desde otro proyecto, se produce un error de compilación; es posible que necesite agregar manualmente el elemento `<SpecificVersion>True</SpecificVersion>` al archivo .csproj del nuevo proyecto bajo la línea que hace referencia a `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="df20c-208">If referencing the `InvokePowerShell` activity assembly or project from another project results in a build error, you may need to manually add the `<SpecificVersion>True</SpecificVersion>` element to the .csproj file of the new project under the line that references `InvokePowerShell`.</span></span>  
  
2.  <span data-ttu-id="df20c-209">Si no está instalado Windows PowerShell, se muestra el siguiente mensaje de error en Visual Studio en cuanto se agrega un `InvokePowerShell` actividad en un flujo de trabajo:`Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span><span class="sxs-lookup"><span data-stu-id="df20c-209">If Windows PowerShell is not installed, the following error message is displayed in Visual Studio as soon as you add an `InvokePowerShell` activity onto a workflow: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span></span>  
  
3.  <span data-ttu-id="df20c-210">En Windows PowerShell 2.0, al llamar mediante programación a los errores y scripts de `$input.MoveNext()` utilizando `$input.MoveNext()`, se generan errores y resultados imprevistos.</span><span class="sxs-lookup"><span data-stu-id="df20c-210">In Windows PowerShell 2.0, programmatically calling `$input.MoveNext()` fails and scripts using `$input.MoveNext()` produce unintended errors and results.</span></span> <span data-ttu-id="df20c-211">Para evitar este problema, considere la utilización del verbo de PowerShell `foreach` en lugar de llamar a `MoveNext()` al recorrer en iteración una matriz.</span><span class="sxs-lookup"><span data-stu-id="df20c-211">To work around this issue, consider using the PowerShell verb `foreach` instead of calling `MoveNext()` when iterating an array.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="df20c-212">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="df20c-212">The samples may already be installed on your machine.</span></span> <span data-ttu-id="df20c-213">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="df20c-213">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="df20c-214">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="df20c-214">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="df20c-215">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="df20c-215">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`