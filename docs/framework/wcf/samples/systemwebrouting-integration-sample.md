---
title: Ejemplo de integración de SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 2f12d80085e3ac27dac8ce80b6bb09f69337bfd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143959"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="dd2d2-102">Ejemplo de integración de SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="dd2d2-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="dd2d2-103">Este ejemplo muestra la integración de nivel de hospedaje con las clases en el espacio de nombres <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="dd2d2-104">Las clases en el espacio de nombres <xref:System.Web.Routing> permiten a una aplicación utilizar direcciones URL que no se corresponden directamente con un recurso físico.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="dd2d2-105">El uso de enrutamiento web permite al desarrollador crear direcciones virtuales para HTTP que, a continuación, se asignan de nuevo a los servicios WCF reales.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="dd2d2-106">Esto es útil cuando un servicio WCF se debe hospedar sin requerir un archivo físico ni un recurso, o cuando se debe tener acceso a los servicios con direcciones URL que no contienen archivos como .html o .aspx.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="dd2d2-107">En este ejemplo se muestra cómo utilizar la clase <xref:System.Web.Routing.RouteTable> para crear URI virtuales que se asignan a servicios en ejecución definidos en global.asax.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span>

> [!NOTE]
> <span data-ttu-id="dd2d2-108">Las clases en el espacio de nombres <xref:System.Web.Routing> solo funcionan para los servicios hospedados sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="dd2d2-109">En este ejemplo se usa WCF para `movies` crear dos `channels` fuentes RSS: una fuente y una fuente.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="dd2d2-110">Las direcciones URL para activar los servicios no contienen una extensión y se registran en el `Application_Start` método de la `Global` clase derivada de la <xref:System.Web.HttpApplication> clase.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd2d2-111">Este ejemplo solo funciona en Internet Information Services (IIS) 7.0 y versiones posteriores, ya que IIS 6.0 usa un método diferente para admitir direcciones URL sin extensión.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="dd2d2-112">Para descargar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd2d2-112">To download this sample</span></span>
  
<span data-ttu-id="dd2d2-113">Es posible que este ejemplo ya esté instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="dd2d2-114">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-114">Check for the following (default) directory before continuing.</span></span>  

`<InstallDrive>:\WF_WCF_Samples`  

 <span data-ttu-id="dd2d2-115">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="dd2d2-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd2d2-116">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-116">This sample is located in the following directory.</span></span>  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="dd2d2-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd2d2-117">To use this sample</span></span>  
  
1. <span data-ttu-id="dd2d2-118">Con Visual Studio, abra el archivo WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="dd2d2-119">Para ejecutar la solución e iniciar el servidor de desarrollo web, presione F5.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="dd2d2-120">Aparece una lista de directorios para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="dd2d2-121">Observe que no hay ningún archivo con la extensión de archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="dd2d2-122">En la barra `movies` de direcciones, `http://localhost:[port]/movies` agregue a la dirección URL, para que lea y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="dd2d2-123">Las fuentes de películas aparecen en el explorador.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="dd2d2-124">En la barra `channels` de direcciones, agregue a `http://localhost:[port]/channels` la dirección URL, por lo que se lee y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="dd2d2-125">La fuente de canales aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="dd2d2-126">Presione ALT+F4 para cerrar el explorador web.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="dd2d2-127">Si el servidor de desarrollo no se ha salido, haga clic con el botón derecho en el icono del área de notificación y seleccione **Detener**.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="dd2d2-128">Para utilizar este ejemplo cuando se hospeda en IIS</span><span class="sxs-lookup"><span data-stu-id="dd2d2-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="dd2d2-129">Con Visual Studio, abra el archivo WebRoutingIntegration.sln.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="dd2d2-130">Compile el proyecto presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="dd2d2-131">Cree una aplicación web en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="dd2d2-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="dd2d2-132">En el Administrador de IIS, haga clic con el botón derecho en el **sitio Web predeterminado** y seleccione Agregar una **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="dd2d2-133">Para el **alias** `WebRoutingIntegration`, escriba .</span><span class="sxs-lookup"><span data-stu-id="dd2d2-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="dd2d2-134">Para la **ruta de acceso física**, seleccione la carpeta Servicio dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="dd2d2-135">Presione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="dd2d2-136">Inicie la aplicación haciendo clic con el botón derecho en la aplicación web y seleccionando **Administrar aplicación** y, a continuación, **examinar**.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="dd2d2-137">En la barra `movies` de direcciones, agregue a `http://localhost:[port]/movies` la dirección URL, por lo que se lee y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="dd2d2-138">Las fuentes de películas aparecen en el explorador.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="dd2d2-139">En la barra `channels` de direcciones, agregue a `http://localhost:[port]/channels` la dirección URL, por lo que se lee y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="dd2d2-140">La fuente de canales aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="dd2d2-141">Presione ALT+F4 para cerrar el explorador web.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="dd2d2-142">En este ejemplo se muestra que el nivel de hospedaje es capaz de crear las clases en el espacio de nombres <xref:System.Web.Routing> para enrutar las solicitudes de servicios hospedados a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd2d2-143">Debe actualizar la versión predeterminada del grupo de aplicaciones a .NET Framework 4 si está establecida en la versión 2.</span><span class="sxs-lookup"><span data-stu-id="dd2d2-143">You must update the default application pool version to .NET Framework 4 if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd2d2-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd2d2-144">See also</span></span>

- <span data-ttu-id="dd2d2-145">[Ejemplos de hospedaje y persistencia de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="dd2d2-145">[AppFabric Hosting and Persistence Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
