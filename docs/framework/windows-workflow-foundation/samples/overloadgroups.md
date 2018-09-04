---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 0773e76d36b25ad5485cc8912c7012815412de9f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514141"
---
# <a name="overloadgroups"></a><span data-ttu-id="9b5d6-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="9b5d6-102">OverloadGroups</span></span>
<span data-ttu-id="9b5d6-103">Este ejemplo consta de una actividad (`CreateLocation`), que tiene dos características interesantes:</span><span class="sxs-lookup"><span data-stu-id="9b5d6-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="9b5d6-104">Tiene algunos argumentos necesarios y algunos opcionales.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="9b5d6-105">Permite al usuario optar por uno de dos conjuntos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="9b5d6-106">Estos comportamientos se logran utilizando estas dos características:</span><span class="sxs-lookup"><span data-stu-id="9b5d6-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="9b5d6-107">`[isRequired]` valida si se ha asignado una propiedad de una actividad concreta, y si no, produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="9b5d6-108">`[OverloadGroup]` reúne un conjunto de argumentos para que el usuario de la actividad pueda elegir entre utilizar un conjunto u otro.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="9b5d6-109">El usuario no puede utilizar argumentos de diferentes grupos de sobrecarga en la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="9b5d6-110">Después de configurar diferentes flujos de trabajo, llame al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de <xref:System.Activities.Validation.Constraint>.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="9b5d6-111">Imprima los objetos <xref:System.Activities.Validation.Constraint> en la consola.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9b5d6-112">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b5d6-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9b5d6-113">Abra el **OverloadGroups.sln** solución de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b5d6-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="9b5d6-114">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9b5d6-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9b5d6-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9b5d6-117">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9b5d6-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9b5d6-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
