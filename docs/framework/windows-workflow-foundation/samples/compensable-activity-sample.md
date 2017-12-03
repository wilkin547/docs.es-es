---
title: Ejemplo de actividad compensable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b6b8eff89ebded7681a88cc4b1aee877828e021
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="compensable-activity-sample"></a><span data-ttu-id="eb29f-102">Ejemplo de actividad compensable</span><span class="sxs-lookup"><span data-stu-id="eb29f-102">Compensable Activity Sample</span></span>
<span data-ttu-id="eb29f-103">En este ejemplo se muestra cómo utilizar la actividad `CompensableActivity` para definir el trabajo que se va a realizar para una acción determinada durante la ejecución normal y el trabajo que es necesario realizar para compensar dicha acción, si es necesario en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="eb29f-103">This sample demonstrates how to use the `CompensableActivity` activity to define the work to be done for a given action during normal execution and the work that is necessary to be done to compensate that action, if necessary at a later time.</span></span>  <span data-ttu-id="eb29f-104">La primera parte del ejemplo muestra cómo se pueden definir las unidades de trabajo compensable en [!INCLUDE[wf](../../../../includes/wf-md.md)] utilizando una actividad `CompensableActivity` y cómo se ejecutan en una ejecución correcta.</span><span class="sxs-lookup"><span data-stu-id="eb29f-104">The first part of the sample shows how units of compensable work can be defined in [!INCLUDE[wf](../../../../includes/wf-md.md)] using a `CompensableActivity` activity and how they are executed in a successful run.</span></span>  <span data-ttu-id="eb29f-105">La segunda parte del ejemplo muestra cómo las mismas unidades de trabajo compensable se ocupan automáticamente de la compensación cuando se produce un evento inesperado y se cancela la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eb29f-105">The second part of the sample shows how the same units of compensable work automatically take care of compensation when an unexpected event is hit and the workflow instance is canceled.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eb29f-106">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb29f-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="eb29f-107">Con Visual Studio 2010, abra CompensableActivity.sln.</span><span class="sxs-lookup"><span data-stu-id="eb29f-107">Using Visual Studio 2010, open the CompensableActivity.sln.</span></span>  
  
2.  <span data-ttu-id="eb29f-108">Compile la solución presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="eb29f-108">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="eb29f-109">Ejecute la aplicación presionando F5.</span><span class="sxs-lookup"><span data-stu-id="eb29f-109">Run the application by pressing F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb29f-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="eb29f-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eb29f-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="eb29f-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eb29f-112">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb29f-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eb29f-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="eb29f-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`