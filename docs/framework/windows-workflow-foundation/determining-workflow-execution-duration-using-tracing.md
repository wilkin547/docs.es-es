---
title: "Determinar la duración de la ejecución del flujo de trabajo mediante seguimiento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c635dbd551eaba6ce338c38564480d0f5cfae553
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="determining-workflow-execution-duration-using-tracing"></a><span data-ttu-id="893c7-102">Determinar la duración de la ejecución del flujo de trabajo mediante seguimiento</span><span class="sxs-lookup"><span data-stu-id="893c7-102">Determining Workflow Execution Duration Using Tracing</span></span>
<span data-ttu-id="893c7-103">En este tema se muestra cómo determinar el tiempo que emplea en ejecutarse, usando el seguimiento de flujo de trabajo, un flujo de trabajo correctamente completado y autohospedado.</span><span class="sxs-lookup"><span data-stu-id="893c7-103">This topic demonstrates how to determine the time it takes for a successfully completed, self-hosted workflow to execute by using workflow tracing.</span></span>  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a><span data-ttu-id="893c7-104">Determinar la duración de la ejecución de la aplicación de flujo de trabajo utilizando el seguimiento de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="893c7-104">To determine workflow application execution duration by using workflow tracing</span></span>  
  
1.  <span data-ttu-id="893c7-105">Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="893c7-105">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  <span data-ttu-id="893c7-106">Seleccione **archivo**, **nueva**, **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="893c7-106">Select **File**, **New**, **Project**.</span></span>  <span data-ttu-id="893c7-107">En **C#**, seleccione la **flujo de trabajo** nodo.</span><span class="sxs-lookup"><span data-stu-id="893c7-107">Under **C#**, select the **Workflow** node.</span></span>  <span data-ttu-id="893c7-108">Seleccione **aplicación de consola de flujos de trabajo** de la lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="893c7-108">Select **Workflow Console Application** from the list of templates.</span></span>  <span data-ttu-id="893c7-109">Asigne al nuevo proyecto `WorkflowDurationTracing` y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="893c7-109">Name the new project `WorkflowDurationTracing` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="893c7-110">Abra Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="893c7-110">Open Workflow1.xaml.</span></span>  <span data-ttu-id="893c7-111">Arrastre una actividad <xref:System.Activities.Statements.Delay> a la superficie del diseñador.</span><span class="sxs-lookup"><span data-stu-id="893c7-111">Drag a <xref:System.Activities.Statements.Delay> activity onto the designer surface.</span></span> <span data-ttu-id="893c7-112">Asigne el valor 00:00:10 (diez segundos) a la propiedad Duration de la actividad.</span><span class="sxs-lookup"><span data-stu-id="893c7-112">Assign the value 00:00:10 (ten seconds) to the Duration property of the activity.</span></span>  
  
3.  <span data-ttu-id="893c7-113">Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.</span><span class="sxs-lookup"><span data-stu-id="893c7-113">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
4.  <span data-ttu-id="893c7-114">Si no ha habilitado el seguimiento del flujo de trabajo, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="893c7-114">If you haven’t enabled workflow tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="893c7-115">Seleccione **vista**, **mostrar analíticos y de depuración registros**.</span><span class="sxs-lookup"><span data-stu-id="893c7-115">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="893c7-116">Haga clic en **depurar** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="893c7-116">Right-click **Debug** and select **Enable Log**.</span></span> <span data-ttu-id="893c7-117">Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="893c7-117">Leave Event Viewer open so that traces can be viewed after the workflow is run.</span></span>  
  
5.  <span data-ttu-id="893c7-118">Ejecute la aplicación de flujo de trabajo presionando CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="893c7-118">Execute the workflow application by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="893c7-119">En Visor de eventos, busque un evento reciente con el identificador 1009 y un mensaje similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="893c7-119">In Event Viewer, find a recent event with ID 1009 and a message similar to the following.</span></span> <span data-ttu-id="893c7-120">Anote la hora en que se registró el mensaje.</span><span class="sxs-lookup"><span data-stu-id="893c7-120">Make a note of the time that the message was logged.</span></span>  
  
 <span data-ttu-id="893c7-121">**Principal actividad '', DisplayName: '', InstanceId: '' secundaria programada actividad 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span><span class="sxs-lookup"><span data-stu-id="893c7-121">**Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span></span>  
  
7.  <span data-ttu-id="893c7-122">Busque otro evento reciente con identificador 1001 y un mensaje similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="893c7-122">Find another recent event with ID 1001 and a message similar to the following.</span></span>  <span data-ttu-id="893c7-123">Reste el tiempo del mensaje anterior del valor Logged de este mensaje para determinarla duración de ejecución de flujo de trabajo, que debería ser alrededor de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="893c7-123">Subtract the previous message time from this message’s Logged value to determine workflow execution duration, which should be around 10 seconds.</span></span>  
  
 <span data-ttu-id="893c7-124">**WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' se completó en el estado cerrado.**</span><span class="sxs-lookup"><span data-stu-id="893c7-124">**WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' has completed in the Closed state.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893c7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="893c7-125">See Also</span></span>  
 [<span data-ttu-id="893c7-126">Traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="893c7-126">Workflow Tracing</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [<span data-ttu-id="893c7-127">Supervisión de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="893c7-127">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="893c7-128">Supervisión de aplicaciones con App Fabric</span><span class="sxs-lookup"><span data-stu-id="893c7-128">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
