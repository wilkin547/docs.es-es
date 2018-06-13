---
title: Tipos de restricción
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 53e5975017c3a27ede8ad07cd93f78f71df2d3e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517513"
---
# <a name="constraint-types"></a><span data-ttu-id="0a7d9-102">Tipos de restricción</span><span class="sxs-lookup"><span data-stu-id="0a7d9-102">Constraint Types</span></span>
<span data-ttu-id="0a7d9-103">Este ejemplo muestra dos formas diferentes de aplicar restricciones a un flujo de trabajo: desde dentro de la actividad (compilación) y desde fuera de ella (directiva).</span><span class="sxs-lookup"><span data-stu-id="0a7d9-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="0a7d9-104">En este escenario, un autor de actividad (de una compañía de software de terceros) desea validar la relación entre dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="0a7d9-105">En este caso, el coste debe ser menor o igual que al precio.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="0a7d9-106">Esta es una restricción de compilación de validación general.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="0a7d9-107">A continuación, un propietario de tienda desea agregar alguna validación a esta actividad genérica.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="0a7d9-108">En su caso, desea que el precio de la mayoría de sus productos sea $ 9,99 o menos.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="0a7d9-109">Por lo tanto, utiliza una restricción de directiva que está en la parte superior de la actividad `CreateProduct`.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="0a7d9-110">En el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0a7d9-110">In the sample:</span></span>  
  
 <span data-ttu-id="0a7d9-111">El autor de actividad (compilación) debe:</span><span class="sxs-lookup"><span data-stu-id="0a7d9-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="0a7d9-112">Crear una restricción (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="0a7d9-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="0a7d9-113">Aquí es donde reside toda la lógica de validación.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="0a7d9-114">Invalidar `System.Activities.CodeActivity.OnGetConstraints()` y agregar la restricción (`PriceGreaterThanCost`) a las restricciones <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="0a7d9-115">El autor del flujo de trabajo (directiva) debe:</span><span class="sxs-lookup"><span data-stu-id="0a7d9-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="0a7d9-116">Crear un flujo de trabajo con una instancia de la actividad para validar (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="0a7d9-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="0a7d9-117">Crear una restricción (`MaxPrice`).</span><span class="sxs-lookup"><span data-stu-id="0a7d9-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="0a7d9-118">Crear una instancia de <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) y agregar la restricción (`MaxPrice`) a la colección `AdditionalConstraints`.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="0a7d9-119">Aquí el autor del flujo de trabajo puede agregar restricciones de directiva a cualquier actividad, como una secuencia o paralela.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="0a7d9-120">Llamar a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de objetos <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="0a7d9-121">(Opcional) Imprimir los objetos <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0a7d9-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a7d9-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0a7d9-123">Abra la solución de ejemplo ConstraintTypes.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7d9-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0a7d9-124">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a7d9-125">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0a7d9-126">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0a7d9-127">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0a7d9-128">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="0a7d9-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`