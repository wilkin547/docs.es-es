---
title: "Validación básica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d388b3d6acad28e4ff952f72aa64a607d745f307
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="basic-validation"></a><span data-ttu-id="2a7d1-102">Validación básica</span><span class="sxs-lookup"><span data-stu-id="2a7d1-102">Basic Validation</span></span>
<span data-ttu-id="2a7d1-103">Este ejemplo consta de una actividad, `CreateProduct`, que valida que su argumento `Cost` es menor o igual que su argumento `Price`.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="2a7d1-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a7d1-104">Sample Details</span></span>  
 <span data-ttu-id="2a7d1-105">Hay dos autores que utilizan la validación: el autor de actividad (crea la lógica de validación de la actividad) y el autor del flujo de trabajo que llama a los servicios de validación en un flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="2a7d1-106">En este escenario, el autor de actividad desea exigir que cada instancia de su actividad tenga un costo menor o igual que el del precio.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="2a7d1-107">El autor de actividad (dentro de la actividad) debe:</span><span class="sxs-lookup"><span data-stu-id="2a7d1-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="2a7d1-108">Crear una restricción (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="2a7d1-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="2a7d1-109">Aquí es donde reside toda la lógica de validación.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="2a7d1-110">Invalidar `System.Activities.CodeActivity.OnGetConstraints()` y agregar la restricción (`PriceGreaterThanCost`) a las restricciones <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="2a7d1-111">El autor del flujo de trabajo (programa general) debe:</span><span class="sxs-lookup"><span data-stu-id="2a7d1-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="2a7d1-112">Crear un flujo de trabajo con una instancia de la actividad para validar (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="2a7d1-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="2a7d1-113">Llamar a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="2a7d1-114">(Opcional) Imprimir los objetos <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a7d1-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a7d1-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2a7d1-116">Abra la solución de ejemplo BasicValidation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a7d1-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="2a7d1-117">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a7d1-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a7d1-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a7d1-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2a7d1-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a7d1-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2a7d1-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`  
  
## <a name="see-also"></a><span data-ttu-id="2a7d1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a7d1-122">See Also</span></span>
