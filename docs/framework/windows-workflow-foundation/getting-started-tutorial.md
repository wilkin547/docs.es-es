---
title: Introducción a Tutorial2
ms.date: 03/30/2017
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
ms.openlocfilehash: 540765c09dceef583798ceaf1abf9f191f444697
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217437"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="4cb16-102">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="4cb16-102">Getting Started Tutorial</span></span>
<span data-ttu-id="4cb16-103">Esta sección contiene un conjunto de temas de tutoriales que presentan a la programación de aplicaciones de Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="4cb16-103">This section contains a set of walkthrough topics that introduce you to programming Windows Workflow Foundation (WF) applications.</span></span> <span data-ttu-id="4cb16-104">Siguiendo los procedimientos incluidos en estos temas, compilará una aplicación que consiste en un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="4cb16-104">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="4cb16-105">El primer tema del tutorial le guía a través de los pasos necesarios para crear las actividades personalizadas que requiere el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4cb16-105">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="4cb16-106">En el segundo tema, estas actividades se ensamblan junto con actividades de flujo de trabajo integradas en un flujo de trabajo de diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="4cb16-106">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="4cb16-107">En el tercer tema, la aplicación host se configura para ejecutar el flujo de trabajo y en el último tema, se introduce la persistencia.</span><span class="sxs-lookup"><span data-stu-id="4cb16-107">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="4cb16-108">Cada paso de este proceso depende de los pasos anteriores, por lo que le recomendamos completarlos en orden.</span><span class="sxs-lookup"><span data-stu-id="4cb16-108">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4cb16-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4cb16-109">In This Section</span></span>  
 [<span data-ttu-id="4cb16-110">Filtrar para crear una actividad</span><span class="sxs-lookup"><span data-stu-id="4cb16-110">How to: Create an Activity</span></span>](how-to-create-an-activity.md)  
 <span data-ttu-id="4cb16-111">Describe cómo crear una actividad personalizada que deriva de <xref:System.Activities.NativeActivity%601> y cómo crear esta actividad junto con una actividad integrada en una actividad compuesta mediante el diseñador de actividad.</span><span class="sxs-lookup"><span data-stu-id="4cb16-111">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="4cb16-112">Filtrar para crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4cb16-112">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)  
 <span data-ttu-id="4cb16-113">Describe cómo crear flujos de trabajo de diagrama de flujo, secuenciales y de máquina de estados mediante actividades integradas y las actividades personalizadas del tutorial anterior.</span><span class="sxs-lookup"><span data-stu-id="4cb16-113">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="4cb16-114">Filtrar para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4cb16-114">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)  
 <span data-ttu-id="4cb16-115">Describe cómo invocar un flujo de trabajo de un entorno del host, cómo entran datos en un flujo de trabajo y salen de él, y cómo reanudar los marcadores.</span><span class="sxs-lookup"><span data-stu-id="4cb16-115">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="4cb16-116">Filtrar para crear y ejecutar un flujo de trabajo de larga duración</span><span class="sxs-lookup"><span data-stu-id="4cb16-116">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="4cb16-117">Describe cómo agregar la persistencia a una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4cb16-117">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="4cb16-118">Filtrar para crear un participante de seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="4cb16-118">How to: Create a Custom Tracking Participant</span></span>](how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="4cb16-119">Describe cómo crear el participante de seguimiento personalizado y el perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4cb16-119">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="4cb16-120">Filtrar para hospedar varias versiones de un flujo de trabajo en paralelo</span><span class="sxs-lookup"><span data-stu-id="4cb16-120">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="4cb16-121">Describe cómo usar `WorkflowIdentity` para hospedar varias versiones de un flujo de trabajo en paralelo.</span><span class="sxs-lookup"><span data-stu-id="4cb16-121">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="4cb16-122">Filtrar para actualizar la definición de una instancia de flujo de trabajo en ejecución</span><span class="sxs-lookup"><span data-stu-id="4cb16-122">How to: Update the Definition of a Running Workflow Instance</span></span>](how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="4cb16-123">Describe cómo usar la actualización dinámica para modificar las instancias de flujo de trabajo en ejecución.</span><span class="sxs-lookup"><span data-stu-id="4cb16-123">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb16-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cb16-124">See also</span></span>

- [<span data-ttu-id="4cb16-125">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="4cb16-125">Windows Workflow Foundation Programming</span></span>](programming.md)
