---
description: Más información acerca de cómo configurar la validación de actividades
title: Configurar la validación de actividades
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: 9e40842a18dd2afd9a5ec0104d66e8971d691b5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792757"
---
# <a name="configuring-activity-validation"></a><span data-ttu-id="d5bd1-103">Configurar la validación de actividades</span><span class="sxs-lookup"><span data-stu-id="d5bd1-103">Configuring Activity Validation</span></span>

<span data-ttu-id="d5bd1-104">La validación de la actividad permite a los autores y usuarios de actividades identificar y notificar los errores en la configuración de una actividad antes de su ejecución.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-104">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> <span data-ttu-id="d5bd1-105">Windows Workflow Foundation (WF) proporciona los tres tipos de validación de actividad siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5bd1-105">Windows Workflow Foundation (WF) provides the following three types of activity validation:</span></span>  
  
- <span data-ttu-id="d5bd1-106">Atributos `RequiredArgument` y `OverloadGroup`.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-106">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
- <span data-ttu-id="d5bd1-107">Validación basada en código imperativo.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-107">Imperative code-based validation.</span></span>  
  
- <span data-ttu-id="d5bd1-108">Restricciones declarativas.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-108">Declarative constraints.</span></span>  
  
 <span data-ttu-id="d5bd1-109">Los atributos `RequiredArgument` y `OverloadGroup` indican que se requieren ciertos argumentos en una actividad.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-109">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="d5bd1-110">La validación imperativa basada en código proporciona un método simple para que una actividad proporcione la validación sobre sí misma. Las restricciones declarativas permiten la validación sobre la actividad y su relación con el flujo de trabajo que contiene.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-110">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="d5bd1-111">Si una actividad no se configura correctamente según los requisitos de validación, se devuelven los errores de validación y las advertencias.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-111">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="d5bd1-112">Si el flujo de trabajo que contiene se crea con el diseñador de flujo de trabajo, en el diseñador se mostrarán los errores y advertencias de validación.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-112">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="d5bd1-113">Si el flujo de trabajo se crea fuera del diseñador de flujo de trabajo, se devuelven errores de validación cuando se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-113">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="d5bd1-114">Independientemente de cómo se cree el flujo de trabajo, nunca se permite que se ejecute un flujo de trabajo con errores de validación.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-114">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="d5bd1-115">En esta sección se proporciona una información general de estos tipos de validación de actividad y cómo se invoca la validación de actividad.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-115">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5bd1-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5bd1-116">In This Section</span></span>  

 [<span data-ttu-id="d5bd1-117">Argumentos necesarios y grupos de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="d5bd1-117">Required Arguments and Overload Groups</span></span>](required-arguments-and-overload-groups.md)  
 <span data-ttu-id="d5bd1-118">Describe cómo usar los atributos `RequiredArgument` y `OverloadGroup` para proporcionar la validación.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-118">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="d5bd1-119">Validación imperativa basada en código</span><span class="sxs-lookup"><span data-stu-id="d5bd1-119">Imperative Code-Based Validation</span></span>](imperative-code-based-validation.md)  
 <span data-ttu-id="d5bd1-120">Describe cómo usar la validación basada en código para las actividades basadas en <xref:System.Activities.CodeActivity> y <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-120">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="d5bd1-121">Restricciones declarativas</span><span class="sxs-lookup"><span data-stu-id="d5bd1-121">Declarative Constraints</span></span>](declarative-constraints.md)  
 <span data-ttu-id="d5bd1-122">Describe cómo usar las restricciones declarativas para proporcionar la validación de actividad compleja.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-122">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="d5bd1-123">Invocar validación de actividad</span><span class="sxs-lookup"><span data-stu-id="d5bd1-123">Invoking Activity Validation</span></span>](invoking-activity-validation.md)  
 <span data-ttu-id="d5bd1-124">Trata cuándo se invoca automáticamente la validación de la actividad y cómo invocarla de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="d5bd1-124">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d5bd1-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="d5bd1-125">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5bd1-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d5bd1-126">Related Sections</span></span>
