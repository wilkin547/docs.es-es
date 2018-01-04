---
title: Actividad NoPersistScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc651403988fa7558f79a4c99e42fb776efec4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="nopersistscope-activity"></a><span data-ttu-id="56c7f-102">Actividad NoPersistScope</span><span class="sxs-lookup"><span data-stu-id="56c7f-102">NoPersistScope Activity</span></span>
<span data-ttu-id="56c7f-103">En este ejemplo se muestra cómo manipular un estado no serializable y descartable dentro de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56c7f-103">This sample shows how to manipulate a non-serializable and disposable state within a workflow.</span></span> <span data-ttu-id="56c7f-104">Es importante que los flujos de trabajo no intenten conservar el estado no serializable y también que los objetos descartables se limpien después de utilizarse en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56c7f-104">It is important that workflows do not attempt to persist non-serializable state and it is also important for disposable objects to be cleaned up after they are used in workflow.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="56c7f-105">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="56c7f-105">Demonstrates</span></span>  
 <span data-ttu-id="56c7f-106">Actividad `NoPersistScope` personalizada y diseñador.</span><span class="sxs-lookup"><span data-stu-id="56c7f-106">`NoPersistScope` custom activity and designer.</span></span>  
  
## <a name="using-the-nopersistzone-activity"></a><span data-ttu-id="56c7f-107">Usar la actividad NoPersistZone</span><span class="sxs-lookup"><span data-stu-id="56c7f-107">Using the NoPersistZone activity</span></span>  
 <span data-ttu-id="56c7f-108">Cuando el flujo de trabajo del ejemplo se ejecuta, una actividad personalizada denominada `CreateTextWriter` crea un objeto de tipo <xref:System.IO.TextWriter> y lo guarda en una variable de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56c7f-108">When the sample workflow runs, a custom activity called `CreateTextWriter` creates an object of type <xref:System.IO.TextWriter> and saves it into a workflow variable.</span></span> <span data-ttu-id="56c7f-109"><xref:System.IO.TextWriter> es un objeto <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="56c7f-109"><xref:System.IO.TextWriter> is an <xref:System.IDisposable> object.</span></span> <span data-ttu-id="56c7f-110">Este <xref:System.IO.TextWriter>, que se configura para escribir en un archivo denominado 'out.txt' en el directorio en el que se ejecuta el ejemplo, es utilizado por una actividad <xref:System.Activities.Statements.WriteLine> porque devuelve cualquier texto que se escriba en la consola.</span><span class="sxs-lookup"><span data-stu-id="56c7f-110">This <xref:System.IO.TextWriter>, which is configured to write to a file named ‘out.txt’ in the directory in which the sample runs, is used by a <xref:System.Activities.Statements.WriteLine> activity as it echoes any text you type in at the console.</span></span>  
  
 <span data-ttu-id="56c7f-111">La lógica de devolución se ejecuta dentro de una actividad `NoPersistScope` (cuyo código forma también parte de este ejemplo), que evita que se conserve el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="56c7f-111">The echo logic runs within a `NoPersistScope` activity (the code for which is also part of this sample), which prevents the workflow from being persisted.</span></span> <span data-ttu-id="56c7f-112">Si escribe en `unload` en la consola, el host intenta conservar la instancia de flujo de trabajo pero caduca esta operación porque el flujo de trabajo permanece dentro de un `NoPersistScope`.</span><span class="sxs-lookup"><span data-stu-id="56c7f-112">If you type in `unload` at the console, the host attempts to persist the workflow instance but this operation times out because the workflow remains within a `NoPersistScope`.</span></span> <span data-ttu-id="56c7f-113">El flujo de trabajo también utiliza una actividad personalizada denominada `Dispose` para eliminar el objeto <xref:System.IO.TextWriter> cuando el flujo de trabajo ha terminado de utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="56c7f-113">The workflow also utilizes a custom activity called `Dispose` to dispose the <xref:System.IO.TextWriter> object when the workflow is finished using it.</span></span> <span data-ttu-id="56c7f-114">La actividad `Dispose` se coloca dentro del bloque <xref:System.Activities.Statements.TryCatch.Finally%2A> de la actividad <xref:System.Activities.Statements.TryCatch> en la que se declara la variable <xref:System.IO.TextWriter>, para asegurarse de que ejecuta aunque se produzca una excepción durante la ejecución del bloque Try.</span><span class="sxs-lookup"><span data-stu-id="56c7f-114">The `Dispose` activity is placed within the <xref:System.Activities.Statements.TryCatch.Finally%2A> block of the <xref:System.Activities.Statements.TryCatch> activity in which the <xref:System.IO.TextWriter> variable is declared, to ensure that it runs even if an exception should occur during execution of the Try block.</span></span>  
  
 <span data-ttu-id="56c7f-115">Puede escribir en `exit` para completar la instancia de flujo de trabajo y salir del programa.</span><span class="sxs-lookup"><span data-stu-id="56c7f-115">You can type in `exit` to complete the workflow instance and exit the program.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="56c7f-116">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="56c7f-116">To run the sample</span></span>  
  
1.  <span data-ttu-id="56c7f-117">Abra la solución NoPersistZone.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56c7f-117">Open the NoPersistZone.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="56c7f-118">Para compilar la solución, presione CTRL + MAYÚS + B o seleccione **generar solución** desde el **generar** menú.</span><span class="sxs-lookup"><span data-stu-id="56c7f-118">To build the solution, press CTRL+SHIFT+B or select **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="56c7f-119">Cuando la compilación finalice correctamente, presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú como alternativa, puede presionar CTRL + F5 o seleccione **iniciar sin depurar** desde el **Depurar** menú para ejecutarlo sin depuración.</span><span class="sxs-lookup"><span data-stu-id="56c7f-119">Once the build has succeeded, press F5 or select **Start Debugging** from the **Debug** menu alternatively, you can press CTRL+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="56c7f-120">Para realizar la limpieza (opcional)</span><span class="sxs-lookup"><span data-stu-id="56c7f-120">To cleanup (optional)</span></span>  
  
1.  <span data-ttu-id="56c7f-121">Para quitar el almacén de instancias de SQL, ejecute Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="56c7f-121">To remove the SQL Instance Store, run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56c7f-122">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="56c7f-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="56c7f-123">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="56c7f-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="56c7f-124">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="56c7f-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="56c7f-125">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="56c7f-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`