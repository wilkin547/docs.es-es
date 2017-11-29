---
title: "Configurar la validación de actividades"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d17a640db012730ae8f5329f4e625823a4f5bff2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="0a33e-102">Configurar la validación de actividades</span><span class="sxs-lookup"><span data-stu-id="0a33e-102">Configuring Activity Validation</span></span>
<span data-ttu-id="0a33e-103">La validación de la actividad permite a los autores y usuarios de actividades identificar y notificar los errores en la configuración de una actividad antes de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="0a33e-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> [!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="0a33e-104"> proporciona los tres tipos siguientes de validación de actividad:</span><span class="sxs-lookup"><span data-stu-id="0a33e-104"> provides the following three types of activity validation:</span></span>  
  
-   <span data-ttu-id="0a33e-105">Atributos `RequiredArgument` y `OverloadGroup`.</span><span class="sxs-lookup"><span data-stu-id="0a33e-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
-   <span data-ttu-id="0a33e-106">Validación basada en código imperativo.</span><span class="sxs-lookup"><span data-stu-id="0a33e-106">Imperative code-based validation.</span></span>  
  
-   <span data-ttu-id="0a33e-107">Restricciones declarativas.</span><span class="sxs-lookup"><span data-stu-id="0a33e-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="0a33e-108">Los atributos `RequiredArgument` y `OverloadGroup` indican que se requieren ciertos argumentos en una actividad.</span><span class="sxs-lookup"><span data-stu-id="0a33e-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="0a33e-109">La validación imperativa basada en código proporciona un método simple para que una actividad proporcione la validación sobre sí misma. Las restricciones declarativas permiten la validación sobre la actividad y su relación con el flujo de trabajo que contiene.</span><span class="sxs-lookup"><span data-stu-id="0a33e-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="0a33e-110">Si una actividad no se configura correctamente según los requisitos de validación, se devuelven los errores de validación y las advertencias.</span><span class="sxs-lookup"><span data-stu-id="0a33e-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="0a33e-111">Si el flujo de trabajo que contiene se crea con el diseñador de flujo de trabajo, en el diseñador se mostrarán los errores y advertencias de validación.</span><span class="sxs-lookup"><span data-stu-id="0a33e-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="0a33e-112">Si el flujo de trabajo se crea fuera del diseñador de flujo de trabajo, se devuelven errores de validación cuando se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0a33e-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="0a33e-113">Independientemente de cómo se cree el flujo de trabajo, nunca se permite que se ejecute un flujo de trabajo con errores de validación.</span><span class="sxs-lookup"><span data-stu-id="0a33e-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="0a33e-114">En esta sección se proporciona una información general de estos tipos de validación de actividad y cómo se invoca la validación de actividad.</span><span class="sxs-lookup"><span data-stu-id="0a33e-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a33e-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0a33e-115">In This Section</span></span>  
 [<span data-ttu-id="0a33e-116">Argumentos necesarios y grupos de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="0a33e-116">Required Arguments and Overload Groups</span></span>](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 <span data-ttu-id="0a33e-117">Describe cómo usar los atributos `RequiredArgument` y `OverloadGroup` para proporcionar la validación.</span><span class="sxs-lookup"><span data-stu-id="0a33e-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="0a33e-118">Validación basada en código imperativo</span><span class="sxs-lookup"><span data-stu-id="0a33e-118">Imperative Code-Based Validation</span></span>](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 <span data-ttu-id="0a33e-119">Describe cómo usar la validación basada en código para las actividades basadas en <xref:System.Activities.CodeActivity> y <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="0a33e-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="0a33e-120">Restricciones declarativas</span><span class="sxs-lookup"><span data-stu-id="0a33e-120">Declarative Constraints</span></span>](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 <span data-ttu-id="0a33e-121">Describe cómo usar las restricciones declarativas para proporcionar la validación de actividad compleja.</span><span class="sxs-lookup"><span data-stu-id="0a33e-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="0a33e-122">Invocación de la validación de actividades</span><span class="sxs-lookup"><span data-stu-id="0a33e-122">Invoking Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 <span data-ttu-id="0a33e-123">Trata cuándo se invoca automáticamente la validación de la actividad y cómo invocarla de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="0a33e-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0a33e-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="0a33e-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0a33e-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="0a33e-125">Related Sections</span></span>
