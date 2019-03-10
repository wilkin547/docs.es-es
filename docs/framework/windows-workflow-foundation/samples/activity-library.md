---
title: Biblioteca de actividades
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709849"
---
# <a name="activity-library"></a><span data-ttu-id="f3e45-102">Biblioteca de actividades</span><span class="sxs-lookup"><span data-stu-id="f3e45-102">Activity Library</span></span>
<span data-ttu-id="f3e45-103">Esta sección contiene ejemplos que muestran las actividades personalizadas avanzadas en Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="f3e45-103">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3e45-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f3e45-104">In This Section</span></span>

 [<span data-ttu-id="f3e45-105">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="f3e45-105">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="f3e45-106">Muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo mediante SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f3e45-106">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="f3e45-107">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="f3e45-107">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="f3e45-108">Muestra cómo la actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="f3e45-108">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="f3e45-109">Actividades de acceso a bases de datos</span><span class="sxs-lookup"><span data-stu-id="f3e45-109">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="f3e45-110">Muestra cómo crear actividades que permiten tener acceso a las bases de datos para recuperar o modificar información y usar [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) para tener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f3e45-110">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) to access the database.</span></span>  
  
 [<span data-ttu-id="f3e45-111">Actividad Externalized Policy en .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="f3e45-111">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="f3e45-112">Muestra cómo la actividad ExternalizedPolicy4 permite ejecutar Windows Workflow Foundation existente en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objetos de Windows Workflow Foundation en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directamente utilizando el motor de reglas que es se distribuye con WF 3.5.</span><span class="sxs-lookup"><span data-stu-id="f3e45-112">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span> 
  
 [<span data-ttu-id="f3e45-113">ForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="f3e45-113">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="f3e45-114">Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="f3e45-114">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="f3e45-115">ParallelForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="f3e45-115">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="f3e45-116">Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="f3e45-116">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="f3e45-117">Get WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f3e45-117">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="f3e45-118">Muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f3e45-118">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
