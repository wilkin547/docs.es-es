---
title: Actividades de tiempo de ejecución en WF
ms.date: 03/30/2017
ms.assetid: e5ae8c31-19bc-4655-88b3-6b75cd6a1bd5
ms.openlocfilehash: 7981d3f75c8fd2d0ddd2ae0233f425c2907c270c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938104"
---
# <a name="runtime-activities-in-wf"></a><span data-ttu-id="8941a-102">Actividades de tiempo de ejecución en WF</span><span class="sxs-lookup"><span data-stu-id="8941a-102">Runtime Activities in WF</span></span>
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <span data-ttu-id="8941a-103">ofrece varias actividades proporcionadas por el sistema para tener acceso a las características del tiempo de ejecución del flujo de trabajo, como persistencia y terminación.</span><span class="sxs-lookup"><span data-stu-id="8941a-103">provides several system-provided activities for accessing the features of the workflow runtime, such as persistence and termination.</span></span>  
  
|<span data-ttu-id="8941a-104">Actividad</span><span class="sxs-lookup"><span data-stu-id="8941a-104">Activity</span></span>|<span data-ttu-id="8941a-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="8941a-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Persist>|<span data-ttu-id="8941a-106">Solicita de manera explícita que el flujo de trabajo conserve su estado.</span><span class="sxs-lookup"><span data-stu-id="8941a-106">Explicitly requests that the workflow persist its state.</span></span>|  
|<xref:System.Activities.Statements.TerminateWorkflow>|<span data-ttu-id="8941a-107">Finaliza la instancia de flujo de trabajo en ejecución.</span><span class="sxs-lookup"><span data-stu-id="8941a-107">Terminates the running workflow instance.</span></span>|  
|<xref:System.Activities.Statements.NoPersistScope>|<span data-ttu-id="8941a-108">Una actividad de contenedor que evita que las actividades secundarias se conserven.</span><span class="sxs-lookup"><span data-stu-id="8941a-108">A container activity that prevents child activities from persisting.</span></span>|
