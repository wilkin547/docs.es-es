---
description: Más información acerca de los puntos de conexión SOAP y HTTP
title: Extremos SOAP y HTTP
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: e07f2d33656b6f697d25a684e49e60d748badc2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703541"
---
# <a name="soap-and-http-endpoints"></a><span data-ttu-id="81e8b-103">Extremos SOAP y HTTP</span><span class="sxs-lookup"><span data-stu-id="81e8b-103">SOAP and HTTP Endpoints</span></span>

<span data-ttu-id="81e8b-104">Este ejemplo muestra cómo implementar un servicio basado en RPC y exponerlo en el formato SOAP y en el formato POX (XML sin formato) mediante el modelo de programación web de WCF.</span><span class="sxs-lookup"><span data-stu-id="81e8b-104">This sample demonstrates how to implement an RPC-based service and expose it in the SOAP format and the "Plain Old XML" (POX) format using the WCF Web Programming model.</span></span> <span data-ttu-id="81e8b-105">Vea el ejemplo de [servicio http básico](basic-http-service.md) para obtener más detalles sobre el enlace http para el servicio.</span><span class="sxs-lookup"><span data-stu-id="81e8b-105">See the [Basic HTTP Service](basic-http-service.md) sample for more details about the HTTP binding for the service.</span></span> <span data-ttu-id="81e8b-106">Este ejemplo se centra en los detalles relativos a la exposición del mismo servicio a través de SOAP y HTTP utilizando enlaces diferentes.</span><span class="sxs-lookup"><span data-stu-id="81e8b-106">This sample focuses on the details that pertain to exposing the same service over SOAP and HTTP using different bindings.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="81e8b-107">Muestra</span><span class="sxs-lookup"><span data-stu-id="81e8b-107">Demonstrates</span></span>  

 <span data-ttu-id="81e8b-108">Exponer un servicio RPC a través de SOAP y HTTP mediante WCF.</span><span class="sxs-lookup"><span data-stu-id="81e8b-108">Exposing an RPC service over SOAP and HTTP using WCF.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="81e8b-109">Debate</span><span class="sxs-lookup"><span data-stu-id="81e8b-109">Discussion</span></span>  

 <span data-ttu-id="81e8b-110">Este ejemplo consta de dos componentes: un proyecto de aplicación web (servicio) que contiene un servicio WCF y una aplicación de consola (cliente) que invoca operaciones de servicio mediante enlaces HTTP y SOAP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-110">This sample consists of two components: a Web Application project (Service) that contains a WCF service and a console application (Client) that invokes service operations using SOAP and HTTP bindings.</span></span>  
  
 <span data-ttu-id="81e8b-111">El servicio WCF expone dos operaciones, `GetData` y, que devuelven `PutData` la cadena que se pasó como entrada.</span><span class="sxs-lookup"><span data-stu-id="81e8b-111">The WCF service exposes 2 operations –`GetData` and `PutData` – that echo the string that was passed as input.</span></span> <span data-ttu-id="81e8b-112">A las operaciones de servicio se les anotan los objetos <xref:System.ServiceModel.Web.WebGetAttribute> y <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="81e8b-112">The service operations are annotated with <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute>.</span></span> <span data-ttu-id="81e8b-113">Estos atributos controlan la proyección HTTP de estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="81e8b-113">These attributes control the HTTP projection of these operations.</span></span> <span data-ttu-id="81e8b-114">Además, se les anota el objeto <xref:System.ServiceModel.OperationContractAttribute>, que les permite ser expuestos a través de enlaces SOAP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-114">In addition, they are annotated with <xref:System.ServiceModel.OperationContractAttribute>, which enables them to be exposed over SOAP bindings.</span></span> <span data-ttu-id="81e8b-115">El método `PutData` del servicio inicia una excepción <xref:System.ServiceModel.Web.WebFaultException>, que se devuelve a través de HTTP utilizando el código de estado HTTP y se devuelve a través de SOAP como un error de SOAP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-115">The service’s `PutData` method throws a <xref:System.ServiceModel.Web.WebFaultException>, which gets sent back over HTTP using the HTTP status code and gets sent back over SOAP as a SOAP fault.</span></span>  
  
 <span data-ttu-id="81e8b-116">El archivo Web.config configura el servicio WCF con 3 puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="81e8b-116">The Web.config file configures the WCF service with 3 endpoints:</span></span>  
  
- <span data-ttu-id="81e8b-117">El punto de conexión ~/service.svc/mex que expone los metadatos del servicio para el acceso de los clientes basados en SOAP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-117">The ~/service.svc/mex endpoint that exposes the service metadata for access by SOAP-based clients.</span></span>  
  
- <span data-ttu-id="81e8b-118">El punto de conexión ~/service.svc/http que permite a los clientes tener acceso al servicio utilizando el enlace HTTP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-118">The ~/service.svc/http endpoint that enables clients to access the service using the HTTP binding.</span></span>  
  
- <span data-ttu-id="81e8b-119">El punto de conexión ~/service.svc/soap que permite a los clientes tener acceso al servicio utilizando el enlace SOAP sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-119">The ~/service.svc/soap endpoint that allows the clients to access the service using the SOAP over HTTP binding.</span></span>  
  
 <span data-ttu-id="81e8b-120">El extremo HTTP se configura con un <`webHttp`> extremo estándar que tiene `helpEnabled` establecido en `true` .</span><span class="sxs-lookup"><span data-stu-id="81e8b-120">The HTTP endpoint is configured with a <`webHttp`> standard endpoint which has `helpEnabled` set to `true`.</span></span> <span data-ttu-id="81e8b-121">Como resultado, el servicio expone XHTML basado en la página de Ayuda en ~/service.svc/http/help que los clientes basados en HTTP pueden utilizar para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="81e8b-121">As a result, the service exposes an XHTML based help page at ~/service.svc/http/help that HTTP-based clients can use to access the service.</span></span>  
  
 <span data-ttu-id="81e8b-122">El proyecto de cliente muestra el acceso al servicio mediante un proxy SOAP (generado a través de **Agregar referencia de servicio**) y el acceso al servicio mediante <xref:System.Net.WebClient> .</span><span class="sxs-lookup"><span data-stu-id="81e8b-122">The client project demonstrates accessing the service using a SOAP proxy (generated through **Add Service Reference**) and accessing the service using <xref:System.Net.WebClient>.</span></span>  
  
 <span data-ttu-id="81e8b-123">El ejemplo está compuesto de un servicio hospedado en web y una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="81e8b-123">The sample consists of a Web-hosted service and a console application.</span></span> <span data-ttu-id="81e8b-124">A medida que se ejecuta la aplicación de consola, el cliente realiza solicitudes al servicio y escribe la información pertinente de las respuestas en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="81e8b-124">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="81e8b-125">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="81e8b-125">To run the sample</span></span>  
  
1. <span data-ttu-id="81e8b-126">Abra la solución para obtener el ejemplo de extremos HTTP y SOAP.</span><span class="sxs-lookup"><span data-stu-id="81e8b-126">Open the solution for the SOAP and HTTP Endpoints Sample.</span></span>  
  
2. <span data-ttu-id="81e8b-127">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="81e8b-127">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3. <span data-ttu-id="81e8b-128">Si aún no está abierto, presione CTRL + W, S para abrir la ventana de **Explorador de soluciones** .</span><span class="sxs-lookup"><span data-stu-id="81e8b-128">If it is not already open, press CTRL+W, S to open the **Solution Explorer** window.</span></span>  
  
4. <span data-ttu-id="81e8b-129">En la ventana de **Explorador de soluciones** , haga clic con el botón secundario en el proyecto de **servicio** y coloque el cursor sobre la opción de menú contextual **depurar** para que aparezca el menú contextual **Iniciar nueva instancia** .</span><span class="sxs-lookup"><span data-stu-id="81e8b-129">From the **Solution Explorer** window, right-click the **Service** project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="81e8b-130">Haga clic en **Iniciar nueva instancia**.</span><span class="sxs-lookup"><span data-stu-id="81e8b-130">Click **Start New Instance**.</span></span> <span data-ttu-id="81e8b-131">De esta forma se inicia el servidor de desarrollo de ASP.NET, que hospeda el servicio.</span><span class="sxs-lookup"><span data-stu-id="81e8b-131">This launches the ASP.NET development server, which hosts the service.</span></span>  
  
5. <span data-ttu-id="81e8b-132">En el Explorador de soluciones ventanas, haga clic con el botón secundario en el proyecto de cliente y coloque el cursor sobre la opción de menú contextual **depurar** para que aparezca el menú contextual **Iniciar nueva instancia** .</span><span class="sxs-lookup"><span data-stu-id="81e8b-132">From the Solution Explorer windows, right-click the Client project and place the cursor over the **Debug** context menu option so that the **Start New Instance** context menu appears.</span></span> <span data-ttu-id="81e8b-133">Haga clic en **Iniciar nueva instancia**.</span><span class="sxs-lookup"><span data-stu-id="81e8b-133">Click **Start New Instance**.</span></span>  
  
6. <span data-ttu-id="81e8b-134">La ventana de la consola del cliente aparece y proporciona el URI del servicio en ejecución y el URI de la página de Ayuda HTML para este.</span><span class="sxs-lookup"><span data-stu-id="81e8b-134">The client console window appears and provides the URI of the running service and the URI of the HTML help page for the running service.</span></span> <span data-ttu-id="81e8b-135">Puede ver la página de Ayuda HTML en cualquier momento escribiendo su URI en un explorador.</span><span class="sxs-lookup"><span data-stu-id="81e8b-135">At any point in time you can view the HTML help page by typing the URI of the help page in a browser.</span></span>  
  
7. <span data-ttu-id="81e8b-136">A medida que el ejemplo se ejecuta, el cliente escribe el estado de la actividad actual.</span><span class="sxs-lookup"><span data-stu-id="81e8b-136">As the sample runs, the client writes the status of the current activity.</span></span>  
  
8. <span data-ttu-id="81e8b-137">Presione cualquier tecla para terminar la aplicación de consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="81e8b-137">Press any key to terminate the client console application.</span></span>  
  
9. <span data-ttu-id="81e8b-138">Presione MAYÚS+F5 para dejar de depurar el servicio.</span><span class="sxs-lookup"><span data-stu-id="81e8b-138">Press SHIFT+F5 to stop debugging the service.</span></span>  
  
10. <span data-ttu-id="81e8b-139">En el área de notificación de Windows, haga clic con el botón secundario en el icono del servidor de desarrollo ASP.NET y seleccione **detener** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="81e8b-139">In the Windows Notification Area, right-click the ASP.NET development server icon and select **Stop** from the context menu.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="81e8b-140">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="81e8b-140">The samples may already be installed on your machine.</span></span> <span data-ttu-id="81e8b-141">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="81e8b-141">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="81e8b-142">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="81e8b-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="81e8b-143">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="81e8b-143">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
