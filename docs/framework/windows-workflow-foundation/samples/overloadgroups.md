---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a5ab416dc484dddc0b6aa0ec25757921815c723
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="overloadgroups"></a><span data-ttu-id="a8d54-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="a8d54-102">OverloadGroups</span></span>
<span data-ttu-id="a8d54-103">Este ejemplo consta de una actividad (`CreateLocation`), que tiene dos características interesantes:</span><span class="sxs-lookup"><span data-stu-id="a8d54-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="a8d54-104">Tiene algunos argumentos necesarios y algunos opcionales.</span><span class="sxs-lookup"><span data-stu-id="a8d54-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="a8d54-105">Permite al usuario optar por uno de dos conjuntos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="a8d54-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="a8d54-106">Estos comportamientos se logran utilizando estas dos características:</span><span class="sxs-lookup"><span data-stu-id="a8d54-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="a8d54-107">`[isRequired]` valida si se ha asignado una propiedad de una actividad concreta, y si no, produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a8d54-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="a8d54-108">`[OverloadGroup]` reúne un conjunto de argumentos para que el usuario de la actividad pueda elegir entre utilizar un conjunto u otro.</span><span class="sxs-lookup"><span data-stu-id="a8d54-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="a8d54-109">El usuario no puede utilizar argumentos de diferentes grupos de sobrecarga en la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="a8d54-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="a8d54-110">Después de configurar diferentes flujos de trabajo, llame a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> que devuelve un <xref:System.Activities.Validation.ValidationResults> colección de <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`.</span><span class="sxs-lookup"><span data-stu-id="a8d54-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation`.</span></span> <span data-ttu-id="a8d54-111">Imprimir el <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` objetos en la consola.</span><span class="sxs-lookup"><span data-stu-id="a8d54-111">Print the <!--zz <xref:System.Activities.Validation.ConstraintViolation>--> `System.Activities.Validation.ConstraintViolation` objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a8d54-112">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8d54-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a8d54-113">Abra la **OverloadGroups.sln** solución en de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8d54-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="a8d54-114">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="a8d54-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8d54-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a8d54-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a8d54-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a8d54-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a8d54-117">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a8d54-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a8d54-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a8d54-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## <a name="see-also"></a><span data-ttu-id="a8d54-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8d54-119">See Also</span></span>
