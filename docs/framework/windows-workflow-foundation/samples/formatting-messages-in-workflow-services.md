---
title: Dar formato a mensajes en servicios de flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 726ce98f3fe11bbc3cd13d90cdae335c0741efe6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="cbed9-102">Dar formato a mensajes en servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cbed9-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="cbed9-103">En este ejemplo se muestra cómo se pueden utilizar diferentes tipos de usuario en actividades de mensajería (servicios de WF).</span><span class="sxs-lookup"><span data-stu-id="cbed9-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="cbed9-104">El servicio del ejemplo es un servicio de aprobación de gastos simple y expone tres operaciones.</span><span class="sxs-lookup"><span data-stu-id="cbed9-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="cbed9-105">`ApproveExpense` toma un tipo de contrato de datos y muestra cómo usar tipos conocidos.</span><span class="sxs-lookup"><span data-stu-id="cbed9-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="cbed9-106">La operación devuelve `true` o `false` según la cantidad de gastos.</span><span class="sxs-lookup"><span data-stu-id="cbed9-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="cbed9-107">`ApprovePO`toma un tipo XmlSerializer y devuelve `true` o `false` en función de la cantidad de gastos.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="cbed9-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="cbed9-108">toma un tipo de contrato de mensaje y devuelve `true` o `false` si el proveedor está en la lista de proveedores autorizados o si la solicitud procede del departamento de finanzas (el departamento de finanzas puede usar cualquier proveedor).</span><span class="sxs-lookup"><span data-stu-id="cbed9-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="cbed9-109">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbed9-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="cbed9-110">Cargue la solución de proyecto en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] y compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="cbed9-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="cbed9-111">En primer lugar, ejecute el servicio generado en [directorio base de la solución] \FormatterService\bin\debug\\</span><span class="sxs-lookup"><span data-stu-id="cbed9-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="cbed9-112">En segundo lugar, ejecute la aplicación Client generada en [directorio base de la solución] \FormatterClient\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="cbed9-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="cbed9-113">El cliente llama a tres operaciones del servicio e imprime los resultados.</span><span class="sxs-lookup"><span data-stu-id="cbed9-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="cbed9-114">Cuando se haya completado, presione Entrar para salir del cliente y a continuación del servicio.</span><span class="sxs-lookup"><span data-stu-id="cbed9-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cbed9-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="cbed9-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbed9-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="cbed9-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cbed9-117">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cbed9-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbed9-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="cbed9-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`