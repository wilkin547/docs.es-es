---
title: Validación básica
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408334"
---
# <a name="basic-validation"></a><span data-ttu-id="5833e-102">Validación básica</span><span class="sxs-lookup"><span data-stu-id="5833e-102">Basic Validation</span></span>
<span data-ttu-id="5833e-103">Este ejemplo consta de una actividad, `CreateProduct`, que valida que su argumento `Cost` es menor o igual que su argumento `Price`.</span><span class="sxs-lookup"><span data-stu-id="5833e-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="5833e-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="5833e-104">Sample Details</span></span>  
 <span data-ttu-id="5833e-105">Hay dos autores que utilizan la validación: el autor de actividad (crea la lógica de validación de la actividad) y el autor del flujo de trabajo que llama a los servicios de validación en un flujo de trabajo concreto.</span><span class="sxs-lookup"><span data-stu-id="5833e-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="5833e-106">En este escenario, el autor de actividad desea exigir que cada instancia de su actividad tenga un costo menor o igual que el del precio.</span><span class="sxs-lookup"><span data-stu-id="5833e-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="5833e-107">El autor de actividad (dentro de la actividad) debe:</span><span class="sxs-lookup"><span data-stu-id="5833e-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="5833e-108">Crear una restricción (`PriceGreaterThanCost`).</span><span class="sxs-lookup"><span data-stu-id="5833e-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="5833e-109">Aquí es donde reside toda la lógica de validación.</span><span class="sxs-lookup"><span data-stu-id="5833e-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="5833e-110">Invalidar `System.Activities.CodeActivity.OnGetConstraints()` y agregar la restricción (`PriceGreaterThanCost`) a las restricciones <xref:System.Collections.IList>.</span><span class="sxs-lookup"><span data-stu-id="5833e-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="5833e-111">El autor del flujo de trabajo (programa general) debe:</span><span class="sxs-lookup"><span data-stu-id="5833e-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="5833e-112">Crear un flujo de trabajo con una instancia de la actividad para validar (`CreateProduct`).</span><span class="sxs-lookup"><span data-stu-id="5833e-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="5833e-113">Llamar a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="5833e-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="5833e-114">(Opcional) Imprimir los objetos <xref:System.Activities.Validation.ValidationError>.</span><span class="sxs-lookup"><span data-stu-id="5833e-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="5833e-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="5833e-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="5833e-116">Abra la solución de ejemplo BasicValidation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5833e-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="5833e-117">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="5833e-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5833e-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5833e-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5833e-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5833e-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5833e-120">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5833e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5833e-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5833e-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`