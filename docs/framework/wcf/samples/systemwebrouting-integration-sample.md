---
title: "Ejemplo de integración de SystemWebRouting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1718ea9c6ea1e029b66955e88fd54e20db1a3527
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="c6f04-102">Ejemplo de integración de SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="c6f04-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="c6f04-103">Este ejemplo muestra la integración de nivel de hospedaje con las clases en el espacio de nombres <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="c6f04-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="c6f04-104">Las clases en el espacio de nombres <xref:System.Web.Routing> permiten a una aplicación utilizar direcciones URL que no se corresponden directamente con un recurso físico.</span><span class="sxs-lookup"><span data-stu-id="c6f04-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="c6f04-105">El uso de enrutamiento web permite al desarrollador de software crear direcciones virtuales para HTTO que se asignan a continuación a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reales.</span><span class="sxs-lookup"><span data-stu-id="c6f04-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="c6f04-106">Esto es útil cuando un servicio WCF se debe hospedar sin requerir un archivo físico ni un recurso, o cuando se debe tener acceso a los servicios con direcciones URL que no contienen archivos como .html o .aspx.</span><span class="sxs-lookup"><span data-stu-id="c6f04-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="c6f04-107">En este ejemplo se muestra cómo utilizar la clase <xref:System.Web.Routing.RouteTable> para crear URI virtuales que se asignan a servicios en ejecución definidos en global.asax.</span><span class="sxs-lookup"><span data-stu-id="c6f04-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span> <span data-ttu-id="c6f04-108">En este ejemplo hay dos fuentes RSS creadas con WCF: una fuente `movies` y una fuente `channels`.</span><span class="sxs-lookup"><span data-stu-id="c6f04-108">For this example, there are two RSS feeds created using WCF: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="c6f04-109">Las direcciones URL para activar los servicios no contienen una extensión y se registran en el `Application_Start` método de la `Global` clase derivada de la <xref:System.Web.HttpApplication.Application_Start> clase.</span><span class="sxs-lookup"><span data-stu-id="c6f04-109">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication.Application_Start> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6f04-110">Las clases en el espacio de nombres <xref:System.Web.Routing> solo funcionan para los servicios hospedados sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="c6f04-110">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6f04-111">Este ejemplo solo funciona en [!INCLUDE[iisver](../../../../includes/iisver-md.md)], porque [!INCLUDE[iis60](../../../../includes/iis60-md.md)] usa un método diferente para admitir las direcciones URL sin extensión.</span><span class="sxs-lookup"><span data-stu-id="c6f04-111">This sample only works in [!INCLUDE[iisver](../../../../includes/iisver-md.md)], as [!INCLUDE[iis60](../../../../includes/iis60-md.md)] uses a different method for supporting extension-less URLs.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c6f04-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-112">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c6f04-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="c6f04-113">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c6f04-114">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6f04-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c6f04-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="c6f04-115">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="c6f04-116">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6f04-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="c6f04-117">Abra el archivo WebRoutingIntegration.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6f04-117">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="c6f04-118">Para ejecutar la solución e iniciar el servidor de desarrollo web, presione F5.</span><span class="sxs-lookup"><span data-stu-id="c6f04-118">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="c6f04-119">Aparece una lista de directorios para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c6f04-119">A directory listing for the sample appears.</span></span> <span data-ttu-id="c6f04-120">Observe que no hay ningún archivo con la extensión de archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="c6f04-120">Note that there are no files with an .svc file extension.</span></span>  
  
3.  <span data-ttu-id="c6f04-121">En la barra de direcciones, agregue `movies` a la dirección URL, de modo que se lea http://localhost:[puerto]/movies y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c6f04-121">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="c6f04-122">Las fuentes de películas aparecen en el explorador.</span><span class="sxs-lookup"><span data-stu-id="c6f04-122">The movies feed appears in the browser.</span></span>  
  
4.  <span data-ttu-id="c6f04-123">En la barra de direcciones, agregue `channels` a la dirección URL, de modo que se lea http://localhost:[puerto]/channels y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c6f04-123">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="c6f04-124">La fuente de canales aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="c6f04-124">The channels feed appears in the browser.</span></span>  
  
5.  <span data-ttu-id="c6f04-125">Presione ALT+F4 para cerrar el explorador web.</span><span class="sxs-lookup"><span data-stu-id="c6f04-125">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="c6f04-126">Si no se ha salido del servidor de desarrollo, haga clic en el icono del área de notificación y seleccione **detener**.</span><span class="sxs-lookup"><span data-stu-id="c6f04-126">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="c6f04-127">Para utilizar este ejemplo cuando se hospeda en IIS</span><span class="sxs-lookup"><span data-stu-id="c6f04-127">To use this sample when hosted in IIS</span></span>  
  
1.  <span data-ttu-id="c6f04-128">Abra el archivo WebRoutingIntegration.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6f04-128">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WebRoutingIntegration.sln file.</span></span>  
  
2.  <span data-ttu-id="c6f04-129">Compile el proyecto presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="c6f04-129">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c6f04-130">Cree una aplicación web en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c6f04-130">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="c6f04-131">En el Administrador de IIS, haga clic con el **sitio Web predeterminado** y seleccione **agregar una aplicación**.</span><span class="sxs-lookup"><span data-stu-id="c6f04-131">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2.  <span data-ttu-id="c6f04-132">Para el **alias**, escriba `WebRoutingIntegration`.</span><span class="sxs-lookup"><span data-stu-id="c6f04-132">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3.  <span data-ttu-id="c6f04-133">Para el **ruta de acceso física**, seleccione la carpeta servicio dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c6f04-133">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4.  <span data-ttu-id="c6f04-134">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6f04-134">Press **OK**.</span></span>  
  
4.  <span data-ttu-id="c6f04-135">Iniciar la aplicación, haciendo clic en la aplicación Web y seleccione **administrar la aplicación** y, a continuación, **examinar**.</span><span class="sxs-lookup"><span data-stu-id="c6f04-135">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5.  <span data-ttu-id="c6f04-136">En la barra de direcciones, agregue `movies` a la dirección URL, de modo que se lea http://localhost:[puerto]/movies y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c6f04-136">In the address bar, add `movies` to the URL, so that is reads http://localhost:[port]/movies and press ENTER.</span></span>  
  
     <span data-ttu-id="c6f04-137">Las fuentes de películas aparecen en el explorador.</span><span class="sxs-lookup"><span data-stu-id="c6f04-137">The movies feed appears in the browser.</span></span>  
  
6.  <span data-ttu-id="c6f04-138">En la barra de direcciones, agregue `channels` a la dirección URL, de modo que se lea http://localhost:[puerto]/channels y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="c6f04-138">In the address bar, add `channels` to the URL, so that is reads http://localhost:[port]/channels and press ENTER.</span></span>  
  
     <span data-ttu-id="c6f04-139">La fuente de canales aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="c6f04-139">The channels feed appears in the browser.</span></span>  
  
7.  <span data-ttu-id="c6f04-140">Presione ALT+F4 para cerrar el explorador web.</span><span class="sxs-lookup"><span data-stu-id="c6f04-140">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="c6f04-141">En este ejemplo se muestra que el nivel de hospedaje es capaz de crear las clases en el espacio de nombres <xref:System.Web.Routing> para enrutar las solicitudes de servicios hospedados a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="c6f04-141">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6f04-142">Actualice la versión del grupo de aplicaciones predeterminado a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] si está establecido en la versión 2.</span><span class="sxs-lookup"><span data-stu-id="c6f04-142">Please update the default application pool version to [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f04-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6f04-143">See Also</span></span>  
 [<span data-ttu-id="c6f04-144">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="c6f04-144">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
