---
description: 'Más información acerca de: biblioteca de actividades'
title: Biblioteca de actividades
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 7e59846d34b63683266fed2c4ec1ad4ed5cb9566
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792614"
---
# <a name="activity-library"></a><span data-ttu-id="abb86-103">Biblioteca de actividades</span><span class="sxs-lookup"><span data-stu-id="abb86-103">Activity Library</span></span>

<span data-ttu-id="abb86-104">Esta sección contiene ejemplos que muestran las actividades personalizadas avanzadas en Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="abb86-104">This section contains samples that demonstrate advanced custom activities in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="abb86-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="abb86-105">In This Section</span></span>

 [<span data-ttu-id="abb86-106">Actividad personalizada SendMail</span><span class="sxs-lookup"><span data-stu-id="abb86-106">SendMail Custom Activity</span></span>](sendmail-custom-activity.md)  
 <span data-ttu-id="abb86-107">Muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo mediante SMTP para el uso dentro de una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="abb86-107">Demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span>  
  
 [<span data-ttu-id="abb86-108">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="abb86-108">Throttled Parallel ForEach</span></span>](throttled-parallel-foreach.md)  
 <span data-ttu-id="abb86-109">Muestra cómo la actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutarán.</span><span class="sxs-lookup"><span data-stu-id="abb86-109">Demonstrates how the `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span>
  
 [<span data-ttu-id="abb86-110">Actividades de acceso a bases de datos</span><span class="sxs-lookup"><span data-stu-id="abb86-110">Database Access Activities</span></span>](database-access-activities.md)  
 <span data-ttu-id="abb86-111">Muestra cómo crear actividades que permiten el acceso a las bases de datos para recuperar o modificar información y usar [ADO.net](../../data/adonet/index.md) para tener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="abb86-111">Demonstrates how to create activities that allow accessing databases to retrieve or modify information and use [ADO.NET](../../data/adonet/index.md) to access the database.</span></span>  
  
 [<span data-ttu-id="abb86-112">Actividad Externalized Policy en .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="abb86-112">Externalized Policy Activity in .NET Framework 4.5</span></span>](externalized-policy-activity-in-net-framework-4-5.md)  
 <span data-ttu-id="abb86-113">Muestra cómo la actividad ExternalizedPolicy4 permite ejecutar los Windows Workflow Foundation existentes en los objetos .NET Framework 3,5 (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> en Windows Workflow Foundation de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4,5) directamente mediante el motor de reglas que se incluye en WF 3,5.</span><span class="sxs-lookup"><span data-stu-id="abb86-113">Demonstrates how the ExternalizedPolicy4 activity allows executing existing Windows Workflow Foundation in .NET Framework 3.5 (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objects in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directly by using the rules engine that is shipped in WF 3.5.</span></span>
  
 [<span data-ttu-id="abb86-114">ForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="abb86-114">Non-Generic ForEach</span></span>](non-generic-foreach.md)  
 <span data-ttu-id="abb86-115">Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="abb86-115">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="abb86-116">ParallelForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="abb86-116">Non-Generic ParallelForEach</span></span>](non-generic-parallelforeach.md)  
 <span data-ttu-id="abb86-117">Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="abb86-117">Demonstrates how to create a non-generic version of the <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span>  
  
 [<span data-ttu-id="abb86-118">Get WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="abb86-118">Get WorkflowInstanceId</span></span>](get-workflowinstanceid.md)  
 <span data-ttu-id="abb86-119">Muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="abb86-119">Demonstrates how to use the custom activity, `GetWorkflowInstanceId`, to return the workflow instance ID.</span></span>
