---
title: "Rehospedar el Diseñador de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bec1fc28-f902-4edb-86c5-436cec802c2b
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5ca7eec49dec0e9b8896b31147a3cd40ffeef5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="rehosting-the-workflow-designer"></a><span data-ttu-id="bd726-102">Rehospedar el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bd726-102">Rehosting the Workflow Designer</span></span>
<span data-ttu-id="bd726-103">[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] puede rehospedarse en entornos fuera de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] con el fin de crear, modificar y supervisar flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bd726-103">The [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] can be rehosted in environments outside of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] for the purposes of creating, modifying, and monitoring workflows.</span></span>  
  
 <span data-ttu-id="bd726-104">El tipo <xref:System.Activities.Presentation.WorkflowDesigner> es un contenedor del lienzo, cuadrícula de propiedad y otros elementos, y expone un modelo de programación básico para administrar la mayoría de escenarios de rehospedaje del diseñador.</span><span class="sxs-lookup"><span data-stu-id="bd726-104">The <xref:System.Activities.Presentation.WorkflowDesigner> type is a wrapper of the canvas, property grid, and other elements, and exposes a basic programming model to handle the majority of designer rehosting scenarios.</span></span> <span data-ttu-id="bd726-105">El hospedaje de <xref:System.Activities.Presentation.WorkflowDesigner> dentro de una aplicación [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] es un escenario de rehospedaje común para [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd726-105">Hosting the <xref:System.Activities.Presentation.WorkflowDesigner> inside a [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] application is a common rehosting scenario for [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bd726-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bd726-106">In This Section</span></span>  
 [<span data-ttu-id="bd726-107">Tarea 1: Crear una aplicación de Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="bd726-107">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
  
 [<span data-ttu-id="bd726-108">Tarea 2: Hospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bd726-108">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)  
  
 [<span data-ttu-id="bd726-109">Tarea 3: Crear los paneles de Cuadro de herramientas y PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="bd726-109">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)  
  
 [<span data-ttu-id="bd726-110">Compatibilidad para las nuevas características de Workflow Foundation 4.5 en el diseñador de flujo de trabajo rehospedado</span><span class="sxs-lookup"><span data-stu-id="bd726-110">Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/wf-features-in-the-rehosted-workflow-designer.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd726-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd726-111">See Also</span></span>  
 [<span data-ttu-id="bd726-112">Personalización de la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="bd726-112">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
