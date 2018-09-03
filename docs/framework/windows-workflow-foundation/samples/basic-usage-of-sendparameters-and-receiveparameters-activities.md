---
title: Uso básico de las actividades SendParameters y ReceiveParameters
ms.date: 03/30/2017
ms.assetid: 1b6b1681-3d41-403f-bfe2-3f600f24aa8c
ms.openlocfilehash: c13999ad1571a6413e30e801b6c642000f8e4654
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467700"
---
# <a name="basic-usage-of-sendparameters-and-receiveparameters-activities"></a><span data-ttu-id="27745-102">Uso básico de las actividades SendParameters y ReceiveParameters</span><span class="sxs-lookup"><span data-stu-id="27745-102">Basic Usage of SendParameters and ReceiveParameters Activities</span></span>
<span data-ttu-id="27745-103">En este ejemplo se muestra el uso de las actividades <xref:System.ServiceModel.Activities.SendParametersContent> y <xref:System.ServiceModel.Activities.ReceiveParametersContent>.</span><span class="sxs-lookup"><span data-stu-id="27745-103">This sample shows the use of <xref:System.ServiceModel.Activities.SendParametersContent> and <xref:System.ServiceModel.Activities.ReceiveParametersContent> activities.</span></span> <span data-ttu-id="27745-104">El servicio expone una operación que toma un argumento de cadena y devuelve la entrada al cliente.</span><span class="sxs-lookup"><span data-stu-id="27745-104">The service exposes one operation that takes a string argument and echoes the input back to the client.</span></span> <span data-ttu-id="27745-105">En el ejemplo se muestra cómo preparar los parámetros para estas actividades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="27745-105">The sample shows how to set up the parameters for these messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27745-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="27745-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="27745-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="27745-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="27745-108">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="27745-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="27745-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="27745-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\SendReceiveParameters`  
  
#### <a name="using-this-sample"></a><span data-ttu-id="27745-110">Utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="27745-110">Using this sample</span></span>  
  
1.  <span data-ttu-id="27745-111">Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="27745-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="27745-112">Primero, ejecute la aplicación EchoWorkflowService generada en [directorio base de la solución]\EchoWorkflowService\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="27745-112">First run the EchoWorkflowService application generated in [solution base directory]\EchoWorkflowService\bin\debug.</span></span>  
  
3.  <span data-ttu-id="27745-113">En segundo lugar, ejecute la aplicación EchoWorkflowClient generada en [directorio base de la solución] \EchoWorkflowClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="27745-113">Second, run the EchoWorkflowClient application generated in [solution base directory]\EchoWorkflowClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="27745-114">El cliente llama a la operación Echo en el servicio e imprime los resultados.</span><span class="sxs-lookup"><span data-stu-id="27745-114">The client calls Echo operation on the service and prints the results.</span></span> <span data-ttu-id="27745-115">Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.</span><span class="sxs-lookup"><span data-stu-id="27745-115">When complete, press ENTER to exit the client and then the service.</span></span>