---
title: Validar actividades externas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ebc79fa582a32ccc252e6c22b9b223870da7e44
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="external-activity-validation"></a><span data-ttu-id="2f7e7-102">Validar actividades externas</span><span class="sxs-lookup"><span data-stu-id="2f7e7-102">External Activity Validation</span></span>
<span data-ttu-id="2f7e7-103">Este ejemplo muestra cómo agregar la lógica de validación a una actividad integrada cuyo autor no es usted.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-103">This sample shows how to add validation logic to a built-in activity that you are not the author of.</span></span> <span data-ttu-id="2f7e7-104">La lógica de validación consiste en exigir que todas las actividades <xref:System.Activities.Statements.If> presentes en el flujo de trabajo tengan su propiedad <xref:System.Activities.Statements.If.Then%2A> establecida o su propiedad <xref:System.Activities.Statements.If.Else%2A> establecida.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-104">The validation logic consists of enforcing that all <xref:System.Activities.Statements.If> activities present in the workflow either have their <xref:System.Activities.Statements.If.Then%2A> property set or their <xref:System.Activities.Statements.If.Else%2A> property set.</span></span> <span data-ttu-id="2f7e7-105">Además, la lógica de validación incluye la comprobación de que todas las actividades <xref:System.Activities.Statements.Pick> presentes en el flujo de trabajo tienen más de una bifurcación; si no es así, se genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-105">Also, the validation logic includes checking that all <xref:System.Activities.Statements.Pick> activities present in the workflow have more than one branch, and if that is not the case, a warning is generated.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="2f7e7-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f7e7-106">Sample details</span></span>  
 <span data-ttu-id="2f7e7-107">En este ejemplo se crea un flujo de trabajo con una instancia de cada actividad que se va a validar: la actividad <xref:System.Activities.Statements.If> y la actividad <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-107">This sample creates a workflow with an instance of each activity to validate: the <xref:System.Activities.Statements.If> activity and the <xref:System.Activities.Statements.Pick> activity.</span></span> <span data-ttu-id="2f7e7-108">Se crea un nuevo objeto <xref:System.Activities.Validation.Constraint> para cada comportamiento de validación.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-108">A <xref:System.Activities.Validation.Constraint> is created for each validation behavior.</span></span> <span data-ttu-id="2f7e7-109">Las restricciones creadas en este ejemplo son `ConstraintError_IfShouldHaveThenOrElse` y `ConstraintWarning_PickHasOneBranch`.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-109">The constraints created in this sample are `ConstraintError_IfShouldHaveThenOrElse` and `ConstraintWarning_PickHasOneBranch`.</span></span> <span data-ttu-id="2f7e7-110">A continuación, estas restricciones se agregan a la colección `AdditionalConstraints` de una instancia <xref:System.Activities.Validation.ValidationSettings>.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-110">Next, these constraints are added to the `AdditionalConstraints` collection of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="2f7e7-111">Por último, se llama al método `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> de <xref:System.Activities.Validation.ActivityValidationServices> para validar las actividades del flujo de trabajo y el resultado de la validación se imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-111">Finally, the `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method of <xref:System.Activities.Validation.ActivityValidationServices> is called to validate the activities in the workflow and the validation results are printed out to the console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f7e7-112">Puede agregar restricciones de directiva a cualquier actividad.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-112">You can add policy constraints to any activity.</span></span> <span data-ttu-id="2f7e7-113">Por ejemplo, puede agregar una restricción de directiva a una actividad <xref:System.Activities.Statements.Sequence> o <xref:System.Activities.Statements.Parallel>.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-113">For example, you can add a policy constraint to a <xref:System.Activities.Statements.Sequence> or <xref:System.Activities.Statements.Parallel> activity.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2f7e7-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f7e7-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="2f7e7-115">Abra el archivo ExternalActivityValidation.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f7e7-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExternalActivityValidation.sln file.</span></span>  
  
2.  <span data-ttu-id="2f7e7-116">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2f7e7-117">Presione Ctrl + F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-117">To run the solution, press Ctrl+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2f7e7-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2f7e7-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2f7e7-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f7e7-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2f7e7-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2f7e7-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`