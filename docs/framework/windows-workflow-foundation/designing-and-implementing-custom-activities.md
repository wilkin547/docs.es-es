---
title: Diseñar e implementar actividades personalizadas
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: b0d04572c65fd4e3e0ae96241217c9ae9aa0e2c5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915360"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="18a7a-102">Diseñar e implementar actividades personalizadas</span><span class="sxs-lookup"><span data-stu-id="18a7a-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="18a7a-103">Las actividades personalizadas en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se crean mediante el ensamblado de actividades proporcionadas por el sistema en actividades compuestas o mediante la creación de nuevos tipos que se deriven de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="18a7a-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="18a7a-104">En esta sección se describe cómo crear actividades personalizadas con cualquier método.</span><span class="sxs-lookup"><span data-stu-id="18a7a-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="18a7a-105">Las actividades personalizadas se muestran de forma predeterminada en el diseñador de flujo de trabajo como un simple rectángulo con el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="18a7a-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="18a7a-106">Para proporcionar una representación visual personalizada de la actividad en el diseñador de flujo de trabajo también debe crear un diseñador personalizado.</span><span class="sxs-lookup"><span data-stu-id="18a7a-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="18a7a-107">Para obtener más información, vea [uso de plantillas y diseñadores de actividad personalizados](using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="18a7a-107">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18a7a-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="18a7a-108">In This Section</span></span>  
 [<span data-ttu-id="18a7a-109">Opciones de creación de actividades</span><span class="sxs-lookup"><span data-stu-id="18a7a-109">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="18a7a-110">Trata los estilos de creación disponibles en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18a7a-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="18a7a-111">Uso de una actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="18a7a-111">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="18a7a-112">Describe cómo agregar una actividad personalizada a un proyecto de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="18a7a-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="18a7a-113">Creación de actividades asincrónicas</span><span class="sxs-lookup"><span data-stu-id="18a7a-113">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="18a7a-114">Describe cómo crear actividades asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="18a7a-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="18a7a-115">Configuración de la validación de actividades</span><span class="sxs-lookup"><span data-stu-id="18a7a-115">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="18a7a-116">Describe cómo se puede usar la validación de la actividad para identificar y notificar los errores en la configuración de actividad antes de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="18a7a-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="18a7a-117">Creación de una actividad en el tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="18a7a-117">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="18a7a-118">Describe cómo crear actividades en runtime mediante <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="18a7a-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="18a7a-119">Propiedades de ejecución de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="18a7a-119">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="18a7a-120">Describe cómo usar propiedades de ejecución del flujo de trabajo para agregar propiedades específicas del contexto al entorno de una actividad.</span><span class="sxs-lookup"><span data-stu-id="18a7a-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="18a7a-121">Uso de delegados de actividad</span><span class="sxs-lookup"><span data-stu-id="18a7a-121">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="18a7a-122">Describe cómo crear y usar actividades que contienen delegados de actividad.</span><span class="sxs-lookup"><span data-stu-id="18a7a-122">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="18a7a-123">Uso de extensiones de actividad</span><span class="sxs-lookup"><span data-stu-id="18a7a-123">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="18a7a-124">Describe cómo crear y usar extensiones de actividad.</span><span class="sxs-lookup"><span data-stu-id="18a7a-124">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="18a7a-125">Uso de fuentes de OData en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="18a7a-125">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="18a7a-126">Describe varios métodos para llamar a un servicio de datos de WCF desde un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="18a7a-126">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="18a7a-127">Ámbito y visibilidad de la definición de actividad</span><span class="sxs-lookup"><span data-stu-id="18a7a-127">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="18a7a-128">Describe las opciones y las reglas para definir el ámbito de los datos y la visibilidad de los miembros para actividades.</span><span class="sxs-lookup"><span data-stu-id="18a7a-128">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
