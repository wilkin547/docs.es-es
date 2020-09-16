---
title: Ejemplo de integración de SystemWebRouting
ms.date: 03/30/2017
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
ms.openlocfilehash: 58d720f164c4c35f3de4c282e9aa983d11e4040b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555229"
---
# <a name="systemwebrouting-integration-sample"></a><span data-ttu-id="0a343-102">Ejemplo de integración de SystemWebRouting</span><span class="sxs-lookup"><span data-stu-id="0a343-102">SystemWebRouting Integration Sample</span></span>
<span data-ttu-id="0a343-103">Este ejemplo muestra la integración de nivel de hospedaje con las clases en el espacio de nombres <xref:System.Web.Routing>.</span><span class="sxs-lookup"><span data-stu-id="0a343-103">This sample demonstrates the hosting layer’s integration with the classes in the <xref:System.Web.Routing> namespace.</span></span> <span data-ttu-id="0a343-104">Las clases en el espacio de nombres <xref:System.Web.Routing> permiten a una aplicación utilizar direcciones URL que no se corresponden directamente con un recurso físico.</span><span class="sxs-lookup"><span data-stu-id="0a343-104">The classes in the <xref:System.Web.Routing> namespace allow an application to use URLs that do not directly correspond to a physical resource.</span></span> <span data-ttu-id="0a343-105">El uso del enrutamiento web permite al desarrollador crear direcciones virtuales para HTTP que se asignan a los servicios WCF reales.</span><span class="sxs-lookup"><span data-stu-id="0a343-105">Using Web routing allows the developer to create virtual addresses for HTTP that are then mapped back to actual WCF services.</span></span> <span data-ttu-id="0a343-106">Esto es útil cuando un servicio WCF se debe hospedar sin requerir un archivo físico ni un recurso, o cuando se debe tener acceso a los servicios con direcciones URL que no contienen archivos como .html o .aspx.</span><span class="sxs-lookup"><span data-stu-id="0a343-106">This is useful when a WCF service must be hosted without requiring a physical file or resource, or when services must be accessed with URLs that do not contain files such as .html or .aspx.</span></span> <span data-ttu-id="0a343-107">En este ejemplo se muestra cómo utilizar la clase <xref:System.Web.Routing.RouteTable> para crear URI virtuales que se asignan a servicios en ejecución definidos en global.asax.</span><span class="sxs-lookup"><span data-stu-id="0a343-107">This sample demonstrates how to utilize the <xref:System.Web.Routing.RouteTable> class to create virtual URIs that map to running services defined in global.asax.</span></span>

> [!NOTE]
> <span data-ttu-id="0a343-108">Las clases en el espacio de nombres <xref:System.Web.Routing> solo funcionan para los servicios hospedados sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="0a343-108">The classes in the <xref:System.Web.Routing> namespace only work for services hosted over HTTP.</span></span>  
  
<span data-ttu-id="0a343-109">En este ejemplo se usa WCF para crear dos fuentes RSS: una `movies` fuente y una `channels` fuente.</span><span class="sxs-lookup"><span data-stu-id="0a343-109">This example uses WCF to create two RSS feeds: a `movies` feed and a `channels` feed.</span></span> <span data-ttu-id="0a343-110">Las direcciones URL para activar los servicios no contienen una extensión y se registran en el `Application_Start` método de la `Global` clase derivada de la <xref:System.Web.HttpApplication> clase.</span><span class="sxs-lookup"><span data-stu-id="0a343-110">The URLs to activate the services do not contain an extension and are registered in the `Application_Start` method of the `Global` class derived from the <xref:System.Web.HttpApplication> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a343-111">Este ejemplo solo funciona en Internet Information Services (IIS) 7,0 y versiones posteriores, ya que IIS 6,0 usa un método diferente para admitir direcciones URL sin extensión.</span><span class="sxs-lookup"><span data-stu-id="0a343-111">This sample only works in Internet Information Services (IIS) 7.0 and later, as IIS 6.0 uses a different method for supporting extension-less URLs.</span></span>  

#### <a name="to-download-this-sample"></a><span data-ttu-id="0a343-112">Para descargar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a343-112">To download this sample</span></span>
  
<span data-ttu-id="0a343-113">Es posible que este ejemplo ya esté instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0a343-113">This sample may already be installed on your computer.</span></span> <span data-ttu-id="0a343-114">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0a343-114">Check for the following (default) directory before continuing.</span></span>  

`<InstallDrive>:\WF_WCF_Samples`  

 <span data-ttu-id="0a343-115">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0a343-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0a343-116">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="0a343-116">This sample is located in the following directory.</span></span>  

`<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0a343-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a343-117">To use this sample</span></span>  
  
1. <span data-ttu-id="0a343-118">Con Visual Studio, abra el archivo WebRoutingIntegration. sln.</span><span class="sxs-lookup"><span data-stu-id="0a343-118">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="0a343-119">Para ejecutar la solución e iniciar el servidor de desarrollo web, presione F5.</span><span class="sxs-lookup"><span data-stu-id="0a343-119">To run the solution and start the Web development server, press F5.</span></span>  
  
     <span data-ttu-id="0a343-120">Aparece una lista de directorios para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0a343-120">A directory listing for the sample appears.</span></span> <span data-ttu-id="0a343-121">Observe que no hay ningún archivo con la extensión de archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="0a343-121">Note that there are no files with an .svc file extension.</span></span>  
  
3. <span data-ttu-id="0a343-122">En la barra de direcciones, agregue `movies` a la dirección URL para que lea `http://localhost:[port]/movies` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0a343-122">In the address bar, add `movies` to the URL, so that it reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="0a343-123">Las fuentes de películas aparecen en el explorador.</span><span class="sxs-lookup"><span data-stu-id="0a343-123">The movies feed appears in the browser.</span></span>  
  
4. <span data-ttu-id="0a343-124">En la barra de direcciones, agregue `channels` a la dirección URL, de modo que sea lectura `http://localhost:[port]/channels` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0a343-124">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="0a343-125">La fuente de canales aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="0a343-125">The channels feed appears in the browser.</span></span>  
  
5. <span data-ttu-id="0a343-126">Presione ALT+F4 para cerrar el explorador web.</span><span class="sxs-lookup"><span data-stu-id="0a343-126">Close the Web browser, by pressing ALT+F4.</span></span>  
  
     <span data-ttu-id="0a343-127">Si el servidor de desarrollo no se ha cerrado, haga clic con el botón secundario en el icono del área de notificación y seleccione **detener**.</span><span class="sxs-lookup"><span data-stu-id="0a343-127">If the development server has not exited, right-click the notification area icon and select **Stop**.</span></span>  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a><span data-ttu-id="0a343-128">Para utilizar este ejemplo cuando se hospeda en IIS</span><span class="sxs-lookup"><span data-stu-id="0a343-128">To use this sample when hosted in IIS</span></span>  
  
1. <span data-ttu-id="0a343-129">Con Visual Studio, abra el archivo WebRoutingIntegration. sln.</span><span class="sxs-lookup"><span data-stu-id="0a343-129">Using Visual Studio, open the WebRoutingIntegration.sln file.</span></span>  
  
2. <span data-ttu-id="0a343-130">Compile el proyecto presionando CTRL+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="0a343-130">Build the project, by pressing CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="0a343-131">Cree una aplicación web en el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="0a343-131">Create a Web application in Internet Information Services (IIS) Manager.</span></span>  
  
    1. <span data-ttu-id="0a343-132">En el administrador de IIS, haga clic con el botón secundario en el **sitio web predeterminado** y seleccione **Agregar una aplicación**.</span><span class="sxs-lookup"><span data-stu-id="0a343-132">In IIS Manager, right click the **Default Web Site** and select **Add an Application**.</span></span>  
  
    2. <span data-ttu-id="0a343-133">Para el **alias**, escriba `WebRoutingIntegration` .</span><span class="sxs-lookup"><span data-stu-id="0a343-133">For the **alias**, type in `WebRoutingIntegration`.</span></span>  
  
    3. <span data-ttu-id="0a343-134">Para la **ruta de acceso física**, seleccione la carpeta de servicio dentro del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0a343-134">For the **Physical Path**, select the Service folder inside the project.</span></span>  
  
    4. <span data-ttu-id="0a343-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a343-135">Press **OK**.</span></span>  
  
4. <span data-ttu-id="0a343-136">Inicie la aplicación, haciendo clic con el botón secundario en la aplicación web y seleccionando **administrar aplicación** y, a continuación, **examinar**.</span><span class="sxs-lookup"><span data-stu-id="0a343-136">Start the application, by right-clicking the Web application and selecting **Manage Application** and then **Browse**.</span></span>  
  
5. <span data-ttu-id="0a343-137">En la barra de direcciones, agregue `movies` a la dirección URL, de modo que sea lectura `http://localhost:[port]/movies` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0a343-137">In the address bar, add `movies` to the URL, so that is reads `http://localhost:[port]/movies` and press ENTER.</span></span>  
  
     <span data-ttu-id="0a343-138">Las fuentes de películas aparecen en el explorador.</span><span class="sxs-lookup"><span data-stu-id="0a343-138">The movies feed appears in the browser.</span></span>  
  
6. <span data-ttu-id="0a343-139">En la barra de direcciones, agregue `channels` a la dirección URL, de modo que sea lectura `http://localhost:[port]/channels` y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0a343-139">In the address bar, add `channels` to the URL, so that is reads `http://localhost:[port]/channels` and press ENTER.</span></span>  
  
     <span data-ttu-id="0a343-140">La fuente de canales aparece en el explorador.</span><span class="sxs-lookup"><span data-stu-id="0a343-140">The channels feed appears in the browser.</span></span>  
  
7. <span data-ttu-id="0a343-141">Presione ALT+F4 para cerrar el explorador web.</span><span class="sxs-lookup"><span data-stu-id="0a343-141">Close the Web browser, by pressing ALT+F4.</span></span>  
  
 <span data-ttu-id="0a343-142">En este ejemplo se muestra que el nivel de hospedaje es capaz de crear las clases en el espacio de nombres <xref:System.Web.Routing> para enrutar las solicitudes de servicios hospedados a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="0a343-142">This sample demonstrates that the hosting layer is capable of composing with the classes in the <xref:System.Web.Routing> namespace for routing the requests of services hosted over HTTP.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a343-143">Debe actualizar la versión predeterminada del grupo de aplicaciones a .NET Framework 4 Si está establecida en la versión 2.</span><span class="sxs-lookup"><span data-stu-id="0a343-143">You must update the default application pool version to .NET Framework 4 if it’s set to version 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a343-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a343-144">See also</span></span>

- <span data-ttu-id="0a343-145">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0a343-145">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
