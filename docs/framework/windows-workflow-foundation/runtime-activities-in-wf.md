---
description: 'Más información sobre: actividades en tiempo de ejecución en WF'
title: Actividades de tiempo de ejecución en WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 5ff164539b9efd7b2b8a4e7cffd5239eae6145fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792640"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="dd00e-103">Actividades de tiempo de ejecución en WF</span><span class="sxs-lookup"><span data-stu-id="dd00e-103">Runtime Activities in WF</span></span>

[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="dd00e-104">ofrece varias actividades proporcionadas por el sistema para tener acceso a las características del tiempo de ejecución del flujo de trabajo, como persistencia y terminación.</span><span class="sxs-lookup"><span data-stu-id="dd00e-104">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="dd00e-105">Actividad</span><span class="sxs-lookup"><span data-stu-id="dd00e-105">Activity</span></span>|<span data-ttu-id="dd00e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd00e-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="dd00e-107">Solicita de manera explícita que el flujo de trabajo conserve su estado.</span><span class="sxs-lookup"><span data-stu-id="dd00e-107">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="dd00e-108">Finaliza la instancia de flujo de trabajo en ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd00e-108">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="dd00e-109">Una actividad de contenedor que evita que las actividades secundarias se conserven.</span><span class="sxs-lookup"><span data-stu-id="dd00e-109">A container activity that prevents child activities from persisting.</span></span>|
