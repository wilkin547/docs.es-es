---
title: Propiedades de ejecución
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 4906c2ad11c8b5822764435d2b39a5b51f2673ba
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43409094"
---
# <a name="execution-properties"></a><span data-ttu-id="704c1-102">Propiedades de ejecución</span><span class="sxs-lookup"><span data-stu-id="704c1-102">Execution Properties</span></span>
<span data-ttu-id="704c1-103">En este ejemplo se muestra cómo definir y utilizar una propiedad de ejecución en una actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="704c1-103">This sample shows how to define and use an execution property in a custom activity.</span></span> <span data-ttu-id="704c1-104">En este ejemplo, la propiedad de ejecución determina el color de primer plano de la consola.</span><span class="sxs-lookup"><span data-stu-id="704c1-104">In this example, the execution property determines the console's foreground color.</span></span> <span data-ttu-id="704c1-105">Un flujo de trabajo de ejemplo muestra cómo diferentes rutas de acceso lógicas de ejecución (bifurcaciones de una actividad <xref:System.Activities.Statements.Parallel>) pueden mantener diferentes colores de consola a pesar de la ejecución intercalada de actividades (en las bifurcaciones de la actividad <xref:System.Activities.Statements.Parallel>).</span><span class="sxs-lookup"><span data-stu-id="704c1-105">An example workflow shows how different logical paths of execution (branches of a <xref:System.Activities.Statements.Parallel> activity) can maintain different console colors despite interleaved execution of activities (across the branches of the <xref:System.Activities.Statements.Parallel> activity).</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="704c1-106">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="704c1-106">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="704c1-107">Abra la solución de ejemplo ExecutionProperties.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="704c1-107">Open the ExecutionProperties.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="704c1-108">La visualización de ThreeColors.xaml antes de compilar la solución se muestra un error, porque las actividades personalizadas utilizadas se deben compilar al mismo tiempo que la solución.</span><span class="sxs-lookup"><span data-stu-id="704c1-108">Viewing ThreeColors.xaml before building the solution displays an error, because the custom activities used must be built at the same time as the solution.</span></span>  
  
2.  <span data-ttu-id="704c1-109">Compile y ejecute la solución.</span><span class="sxs-lookup"><span data-stu-id="704c1-109">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="704c1-110">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="704c1-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="704c1-111">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="704c1-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="704c1-112">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="704c1-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="704c1-113">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="704c1-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`