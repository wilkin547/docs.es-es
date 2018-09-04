---
title: Calculadora correlacionada
ms.date: 03/30/2017
ms.assetid: c365166e-6552-49a4-bf17-9f4e597d4d41
ms.openlocfilehash: 71cfdd0906ef20ec36b76ef5e508a4551b9fe3fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517318"
---
# <a name="correlated-calculator"></a><span data-ttu-id="a820f-102">Calculadora correlacionada</span><span class="sxs-lookup"><span data-stu-id="a820f-102">Correlated Calculator</span></span>
<span data-ttu-id="a820f-103">En este ejemplo se muestra cómo utilizar las actividades de mensajería (<xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply>) en el diseñador con correlación basada en contenidos en función de un parámetro en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a820f-103">This sample demonstrates how to use the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>) in the designer with content-based correlation based on a parameter in the message.</span></span> <span data-ttu-id="a820f-104">En este escenario, las operaciones de la calculadora se encuentran en un convoy paralelo.</span><span class="sxs-lookup"><span data-stu-id="a820f-104">In this scenario, the operations of the calculator are in a parallel convoy.</span></span> <span data-ttu-id="a820f-105">Se crean una instancia y una correlación (basadas en `CalculatorId`) cuando el primer mensaje se envía al flujo de trabajo, y los mensajes subsiguientes con el mismo `CalculatorId` se envían a esa instancia hasta que se llama a la operación de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="a820f-105">Both an instance and a correlation (based on `CalculatorId`) are created when the first message is sent to the workflow, and subsequent messages with the same `CalculatorId` are dispatched to that instance until the Reset operation is called.</span></span> <span data-ttu-id="a820f-106">El cliente se implementa como una aplicación WPF que utiliza un proxy de cliente basado en código para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="a820f-106">The client is implemented as a WPF application that uses a code-based client proxy to communicate with the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a820f-107">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a820f-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="a820f-108">Inicie [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con permisos elevados y abra el archivo de solución For.sln.</span><span class="sxs-lookup"><span data-stu-id="a820f-108">Start [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] in elevated permissions, open the For.sln solution file.</span></span>  
  
    1.  <span data-ttu-id="a820f-109">Navegue hasta la carpeta que contiene [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a820f-109">Navigate to the folder that contains [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
    2.  <span data-ttu-id="a820f-110">Haga clic en Devenv.exe y seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a820f-110">Right-click Devenv.exe and select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="a820f-111">Abra el archivo de solución de CorrelatedCalculator.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a820f-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CorrelatedCalculator.sln solution file.</span></span>  
  
3.  <span data-ttu-id="a820f-112">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="a820f-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
4.  <span data-ttu-id="a820f-113">Presione CTRL+F5 para ejecutar el proyecto de servicio.</span><span class="sxs-lookup"><span data-stu-id="a820f-113">To run the service project, press CTRL+F5.</span></span>  
  
5.  <span data-ttu-id="a820f-114">Cuando el servicio está listo y realizando escuchas para los mensajes, en el Explorador de soluciones, haga clic con el botón secundario en el proyecto Cliente y ejecútelo.</span><span class="sxs-lookup"><span data-stu-id="a820f-114">Once the service is ready and listening for messages, in Solution Explorer, right-click the Client project and run it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a820f-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a820f-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a820f-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a820f-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a820f-117">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a820f-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a820f-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a820f-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\CorellatedCalculator`