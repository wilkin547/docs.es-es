---
title: "Propiedades de ejecución"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a394ff136464dd2e69f8c38f07b1b2542bf4a87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="execution-properties"></a><span data-ttu-id="84ead-102">Propiedades de ejecución</span><span class="sxs-lookup"><span data-stu-id="84ead-102">Execution Properties</span></span>
<span data-ttu-id="84ead-103">En este ejemplo se muestra cómo definir y utilizar una propiedad de ejecución en una actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="84ead-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="84ead-104">En este ejemplo, la propiedad de ejecución determina el color de primer plano de la consola.</span><span class="sxs-lookup"><span data-stu-id="84ead-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="84ead-105">Un flujo de trabajo de ejemplo muestra cómo diferentes rutas de acceso lógicas de ejecución (bifurcaciones de una actividad <xref:System.Activities.Statements.Parallel>) pueden mantener diferentes colores de consola a pesar de la ejecución intercalada de actividades (en las bifurcaciones de la actividad <xref:System.Activities.Statements.Parallel>).</span><span class="sxs-lookup"><span data-stu-id="84ead-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="84ead-106">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="84ead-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="84ead-107">Abra la solución de ejemplo ExecutionProperties.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84ead-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84ead-108">La visualización de ThreeColors.xaml antes de compilar la solución se muestra un error, porque las actividades personalizadas utilizadas se deben compilar al mismo tiempo que la solución.</span><span class="sxs-lookup"><span data-stu-id="84ead-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="84ead-109">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="84ead-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84ead-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="84ead-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="84ead-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="84ead-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="84ead-112">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84ead-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="84ead-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="84ead-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`  
  
## <a name="see-also"></a><span data-ttu-id="84ead-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="84ead-114">See Also</span></span>
