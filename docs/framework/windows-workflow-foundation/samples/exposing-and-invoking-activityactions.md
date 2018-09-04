---
title: Exponer e invocar ActivityActions
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: f36d88fc54e5150927113ed8825fbccad84129d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520128"
---
# <a name="exposing-and-invoking-activityactions"></a><span data-ttu-id="f997d-102">Exponer e invocar ActivityActions</span><span class="sxs-lookup"><span data-stu-id="f997d-102">Exposing and Invoking ActivityActions</span></span>
<span data-ttu-id="f997d-103">En este ejemplo se muestra cómo desarrollar una actividad personalizada que tiene un objeto <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="f997d-103">This sample demonstrates how to develop a custom activity that has an <xref:System.Activities.ActivityAction>.</span></span> <span data-ttu-id="f997d-104">También muestra cómo utilizar esta actividad proporcionando una implementación de <xref:System.Activities.ActivityAction>.</span><span class="sxs-lookup"><span data-stu-id="f997d-104">It also demonstrates how to use this activity by providing an implementation of the <xref:System.Activities.ActivityAction>.</span></span>  
  
 <span data-ttu-id="f997d-105">Un <xref:System.Activities.ActivityAction> permite que un autor de actividad exponen "agujeros" con firmas específicas donde el usuario de la actividad puede conectar un comportamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="f997d-105">An <xref:System.Activities.ActivityAction> allows an activity author to expose "holes" with specific signatures where the activity user can plug in a custom behavior.</span></span> <span data-ttu-id="f997d-106">Por ejemplo, el <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` actividad, (que actúa sobre una colección de elementos), tiene un <xref:System.Activities.ActivityAction> que permite al usuario de la actividad agregar un comportamiento que actúa sobre el elemento de iteración actual.</span><span class="sxs-lookup"><span data-stu-id="f997d-106">For example, the <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` activity, (which operates over a collection of items), has an <xref:System.Activities.ActivityAction> that allows the activity user to plug in behavior that operates on the current iteration item.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f997d-107">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f997d-107">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f997d-108">Abra el **ActivityAction.sln** solución de ejemplo [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f997d-108">Open the **ActivityAction.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f997d-109">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="f997d-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f997d-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f997d-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f997d-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f997d-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f997d-112">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f997d-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f997d-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f997d-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`