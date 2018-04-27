---
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ee64ae3db9dbf98f2a62397075406c118a867bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="09ddd-102">Personalizar la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ddd-102">Customizing the Workflow Design Experience</span></span>
<span data-ttu-id="09ddd-103">Los escenarios para diseñar las actividades personalizadas y para re-hospedar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] se han simplificado enormemente en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09ddd-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="09ddd-104">El desarrollo y la implementación resultan ahora más fáciles y más flexibles.</span><span class="sxs-lookup"><span data-stu-id="09ddd-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="09ddd-105">El cambio infraestructural clave es que el nuevo modelo de programación Diseñador de actividad se compila en Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="09ddd-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="09ddd-106">Esto proporciona la capacidad de definir diseñadores de actividad mediante declaración y re-hospedar [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en otras aplicaciones con relativa facilidad.</span><span class="sxs-lookup"><span data-stu-id="09ddd-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="09ddd-107">Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado.</span><span class="sxs-lookup"><span data-stu-id="09ddd-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="09ddd-108">La integración con [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] se ha vuelto más uniforme con el uso de los servicios del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09ddd-108">The integration with [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] has become more seamless with use of workflow services.</span></span> <span data-ttu-id="09ddd-109">Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.</span><span class="sxs-lookup"><span data-stu-id="09ddd-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09ddd-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="09ddd-110">In This Section</span></span>  
 [<span data-ttu-id="09ddd-111">Uso de plantillas y diseñadores de actividad personalizados</span><span class="sxs-lookup"><span data-stu-id="09ddd-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 <span data-ttu-id="09ddd-112">Describe cómo crear diseñadores de actividad personalizados y plantillas.</span><span class="sxs-lookup"><span data-stu-id="09ddd-112">Describes how to create new custom activity designers and templates.</span></span>  
  
 [<span data-ttu-id="09ddd-113">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="09ddd-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 <span data-ttu-id="09ddd-114">Describe cómo re-hospedar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] fuera de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] y cómo mostrar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="09ddd-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and how to display validation errors.</span></span>  
  
 [<span data-ttu-id="09ddd-115">Utilización de un editor de expresiones personalizado</span><span class="sxs-lookup"><span data-stu-id="09ddd-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 <span data-ttu-id="09ddd-116">Describe cómo implementar un editor de expresiones personalizado para utilizar con los diseñadores de flujo de trabajo rehospedados fuera de [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09ddd-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="09ddd-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="09ddd-117">Reference</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a><span data-ttu-id="09ddd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="09ddd-118">See Also</span></span>  
 [<span data-ttu-id="09ddd-119">Extensión de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="09ddd-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [<span data-ttu-id="09ddd-120">Diseñador</span><span class="sxs-lookup"><span data-stu-id="09ddd-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [<span data-ttu-id="09ddd-121">Diseñadores de actividad personalizados</span><span class="sxs-lookup"><span data-stu-id="09ddd-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [<span data-ttu-id="09ddd-122">Rehospedaje del diseñador</span><span class="sxs-lookup"><span data-stu-id="09ddd-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
