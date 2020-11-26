---
title: Procedimiento para crear un flujo de trabajo
description: Complete una de las tres opciones de esta sección para crear un flujo de trabajo como parte de este tutorial de Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 1b2b03d672f86a351bcf36343d6a17e351d40ed0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248791"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="62e5d-103">Procedimiento para crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="62e5d-103">How to: Create a Workflow</span></span>

<span data-ttu-id="62e5d-104">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="62e5d-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="62e5d-105">En los temas de esta sección se describe la creación de un flujo de trabajo que usa tanto actividades integradas, como la <xref:System.Activities.Statements.Flowchart> actividad, como actividades personalizadas del tema [Cómo: crear una actividad](how-to-create-an-activity.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="62e5d-105">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="62e5d-106">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="62e5d-106">The workflow models a number guessing game.</span></span> <span data-ttu-id="62e5d-107">Solo se necesita uno de los temas de esta sección para completar el tutorial; debe elegir el estilo que le interese y seguir ese paso.</span><span class="sxs-lookup"><span data-stu-id="62e5d-107">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="62e5d-108">Sin embargo, puede completar todos los temas si lo desea.</span><span class="sxs-lookup"><span data-stu-id="62e5d-108">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62e5d-109">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="62e5d-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="62e5d-110">Para completar este tema, primero debe completar [Cómo: crear una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="62e5d-110">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62e5d-111">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="62e5d-111">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62e5d-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="62e5d-112">In This Section</span></span>  

 [<span data-ttu-id="62e5d-113">Procedimiento para crear un flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="62e5d-113">How to: Create a Sequential Workflow</span></span>](how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="62e5d-114">Describe cómo crear un flujo de trabajo secuencial usando la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="62e5d-114">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="62e5d-115">Procedimiento para crear un flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="62e5d-115">How to: Create a Flowchart Workflow</span></span>](how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="62e5d-116">Describe cómo crear un flujo de trabajo de diagrama de flujo usando la actividad <xref:System.Activities.Statements.Flowchart> .</span><span class="sxs-lookup"><span data-stu-id="62e5d-116">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="62e5d-117">Procedimiento para crear un flujo de trabajo de máquina de estados</span><span class="sxs-lookup"><span data-stu-id="62e5d-117">How to: Create a State Machine Workflow</span></span>](how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="62e5d-118">Describe cómo crear un flujo de trabajo de máquina de estados usando la actividad <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="62e5d-118">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e5d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="62e5d-119">See also</span></span>

- [<span data-ttu-id="62e5d-120">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="62e5d-120">Windows Workflow Foundation Programming</span></span>](programming.md)
