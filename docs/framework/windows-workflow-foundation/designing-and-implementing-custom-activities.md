---
title: "Diseñar e implementar actividades personalizadas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f9243761803bc8b68ce37b3d3ad310e8bb7f93d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="c830c-102">Diseñar e implementar actividades personalizadas</span><span class="sxs-lookup"><span data-stu-id="c830c-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="c830c-103">Las actividades personalizadas en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se crean mediante el ensamblado de actividades proporcionadas por el sistema en actividades compuestas o mediante la creación de nuevos tipos que se deriven de <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="c830c-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="c830c-104">En esta sección se describe cómo crear actividades personalizadas con cualquier método.</span><span class="sxs-lookup"><span data-stu-id="c830c-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c830c-105">Las actividades personalizadas se muestran de forma predeterminada en el diseñador de flujo de trabajo como un simple rectángulo con el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="c830c-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="c830c-106">Para proporcionar una representación visual personalizada de la actividad en el diseñador de flujo de trabajo también debe crear un diseñador personalizado.</span><span class="sxs-lookup"><span data-stu-id="c830c-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="c830c-107">[Utilizando plantillas y diseñadores de actividad personalizados](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c830c-107"> [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c830c-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c830c-108">In This Section</span></span>  
 [<span data-ttu-id="c830c-109">Opciones de creación de actividades</span><span class="sxs-lookup"><span data-stu-id="c830c-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="c830c-110">Trata los estilos de creación disponibles en [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c830c-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="c830c-111">Uso de una actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="c830c-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="c830c-112">Describe cómo agregar una actividad personalizada a un proyecto de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c830c-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="c830c-113">Creación de actividades asincrónicas</span><span class="sxs-lookup"><span data-stu-id="c830c-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="c830c-114">Describe cómo crear actividades asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="c830c-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="c830c-115">Configuración de la validación de actividades</span><span class="sxs-lookup"><span data-stu-id="c830c-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="c830c-116">Describe cómo se puede usar la validación de la actividad para identificar y notificar los errores en la configuración de actividad antes de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="c830c-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="c830c-117">Creación de una actividad en el tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c830c-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="c830c-118">Describe cómo crear actividades en runtime mediante <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="c830c-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="c830c-119">Propiedades de ejecución de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c830c-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="c830c-120">Describe cómo usar propiedades de ejecución del flujo de trabajo para agregar propiedades específicas del contexto al entorno de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c830c-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="c830c-121">Uso de delegados de actividad</span><span class="sxs-lookup"><span data-stu-id="c830c-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="c830c-122">Describe cómo crear y usar actividades que contienen delegados de actividad.</span><span class="sxs-lookup"><span data-stu-id="c830c-122">Discusses how to author and use activities that contain activity delegates.</span></span>  
  
 [<span data-ttu-id="c830c-123">Adaptación de actividades</span><span class="sxs-lookup"><span data-stu-id="c830c-123">Activity Localization</span></span>](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 <span data-ttu-id="c830c-124">Describe cómo usar la localización de recursos de cadena en actividades.</span><span class="sxs-lookup"><span data-stu-id="c830c-124">Describes how to use localization of string resources in activities.</span></span>  
  
 [<span data-ttu-id="c830c-125">Uso de extensiones de actividad</span><span class="sxs-lookup"><span data-stu-id="c830c-125">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="c830c-126">Describe cómo crear y usar extensión de actividad.</span><span class="sxs-lookup"><span data-stu-id="c830c-126">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="c830c-127">Uso de fuentes de OData en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c830c-127">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="c830c-128">Describe varios métodos para llamar a un servicio de datos de WCF desde un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c830c-128">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="c830c-129">Ámbito y visibilidad de la definición de actividad</span><span class="sxs-lookup"><span data-stu-id="c830c-129">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="c830c-130">Describe las opciones y las reglas para definir el ámbito de los datos y la visibilidad de los miembros para actividades.</span><span class="sxs-lookup"><span data-stu-id="c830c-130">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
