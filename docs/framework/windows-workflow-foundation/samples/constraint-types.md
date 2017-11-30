---
title: "Tipos de restricción"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f78337ebc643b584b89f26ca39e400fb8e6e9c26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="constraint-types"></a><span data-ttu-id="648ff-102">Tipos de restricción</span><span class="sxs-lookup"><span data-stu-id="648ff-102">Constraint Types</span></span>
<span data-ttu-id="648ff-103">Este ejemplo muestra dos formas diferentes de aplicar restricciones a un flujo de trabajo: desde dentro de la actividad (compilación) y desde fuera de ella (directiva).</span><span class="sxs-lookup"><span data-stu-id="648ff-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="648ff-104">En este escenario, un autor de actividad (de una compañía de software de terceros) desea validar la relación entre dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="648ff-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="648ff-105">En este caso, el coste debe ser menor o igual que al precio.</span><span class="sxs-lookup"><span data-stu-id="648ff-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="648ff-106">Esta es una restricción de compilación de validación general.</span><span class="sxs-lookup"><span data-stu-id="648ff-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="648ff-107">A continuación, un propietario de tienda desea agregar alguna validación a esta actividad genérica.</span><span class="sxs-lookup"><span data-stu-id="648ff-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="648ff-108">En su caso, desea que el precio de la mayoría de sus productos sea $ 9,99 o menos.</span><span class="sxs-lookup"><span data-stu-id="648ff-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="648ff-109">Por lo tanto, utiliza una restricción de directiva que está en la parte superior de la actividad `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="648ff-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="648ff-110">En el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="648ff-110">In the sample:</span></span>  
  
 <span data-ttu-id="648ff-111">El autor de actividad (compilación) debe:</span><span class="sxs-lookup"><span data-stu-id="648ff-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="648ff-112">Crear una restricción (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="648ff-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="648ff-113">Aquí es donde reside toda la lógica de validación.</span><span class="sxs-lookup"><span data-stu-id="648ff-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="648ff-114">Invalidar `System.Activities.CodeActivity.OnGetConstraints()` y agregar la restricción (`PriceGreaterThanCost`) a las restricciones <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="648ff-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="648ff-115">El autor del flujo de trabajo (directiva) debe:</span><span class="sxs-lookup"><span data-stu-id="648ff-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="648ff-116">Crear un flujo de trabajo con una instancia de la actividad para validar (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="648ff-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="648ff-117">Crear una restricción (`MaxPrice`).</span><span class="sxs-lookup"><span data-stu-id="648ff-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="648ff-118">Crear una instancia de <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) y agregar la restricción (`MaxPrice`) a la colección `AdditionalConstraints`.</span><span class="sxs-lookup"><span data-stu-id="648ff-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="648ff-119">Aquí el autor del flujo de trabajo puede agregar restricciones de directiva a cualquier actividad, como una secuencia o paralela.</span><span class="sxs-lookup"><span data-stu-id="648ff-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="648ff-120">Llamar a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de objetos <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="648ff-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="648ff-121">(Opcional) Imprimir los objetos <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="648ff-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="648ff-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="648ff-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="648ff-123">Abra la solución de ejemplo ConstraintTypes.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="648ff-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="648ff-124">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="648ff-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="648ff-125">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="648ff-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="648ff-126">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="648ff-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="648ff-127">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="648ff-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="648ff-128">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="648ff-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`  
  
## <a name="see-also"></a><span data-ttu-id="648ff-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="648ff-129">See Also</span></span>
