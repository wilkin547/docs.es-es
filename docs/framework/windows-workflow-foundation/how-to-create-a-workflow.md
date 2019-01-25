---
title: Procedimiento Crear un flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: 75af0e1dae43cb424dcd13f9f2540d65fbdca126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559003"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="1c77e-102">Procedimiento Crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1c77e-102">How to: Create a Workflow</span></span>
<span data-ttu-id="1c77e-103">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="1c77e-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="1c77e-104">Los temas de esta sección paso a través de la creación de un flujo de trabajo que usa tanto las actividades integradas, como el <xref:System.Activities.Statements.Flowchart> actividad y las actividades personalizadas del anterior [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) tema.</span><span class="sxs-lookup"><span data-stu-id="1c77e-104">The topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="1c77e-105">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="1c77e-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="1c77e-106">Solo se necesita uno de los temas de esta sección para completar el tutorial; debe elegir el estilo que le interese y seguir ese paso.</span><span class="sxs-lookup"><span data-stu-id="1c77e-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="1c77e-107">Sin embargo, puede completar todos los temas si lo desea.</span><span class="sxs-lookup"><span data-stu-id="1c77e-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c77e-108">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="1c77e-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="1c77e-109">Para completar este tema, primero debe completar [Cómo: Crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="1c77e-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c77e-110">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="1c77e-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c77e-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1c77e-111">In This Section</span></span>  
 [<span data-ttu-id="1c77e-112">Cómo: Crear un flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="1c77e-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="1c77e-113">Describe cómo crear un flujo de trabajo secuencial usando la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="1c77e-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="1c77e-114">Cómo: Crear un flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="1c77e-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="1c77e-115">Describe cómo crear un flujo de trabajo de diagrama de flujo usando la actividad <xref:System.Activities.Statements.Flowchart> .</span><span class="sxs-lookup"><span data-stu-id="1c77e-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="1c77e-116">Cómo: Crear un flujo de trabajo de equipo de estado</span><span class="sxs-lookup"><span data-stu-id="1c77e-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="1c77e-117">Describe cómo crear un flujo de trabajo de máquina de estados usando la actividad <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="1c77e-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c77e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c77e-118">See also</span></span>
- [<span data-ttu-id="1c77e-119">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="1c77e-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
