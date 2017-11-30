---
title: "Cómo: Iniciar servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
caps.latest.revision: "16"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: e4f93da8a2a5be00d798d64caba0f54bfd71ceb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-start-services"></a><span data-ttu-id="fd7ca-102">Cómo: Iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="fd7ca-102">How to: Start Services</span></span>
<span data-ttu-id="fd7ca-103">Después de instala un servicio, debe estar iniciado.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-103">After a service is installed, it must be started.</span></span> <span data-ttu-id="fd7ca-104">A partir de las llamadas del <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método en la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-104">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="fd7ca-105">Por lo general, la <xref:System.ServiceProcess.ServiceBase.OnStart%2A> método define el trabajo útil que realizará el servicio.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-105">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="fd7ca-106">Una vez iniciado un servicio, permanece activo hasta que se está pausado o detenido manualmente.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-106">After a service starts, it remains active until it is manually paused or stopped.</span></span>  
  
 <span data-ttu-id="fd7ca-107">Los servicios se pueden configurar para iniciar automática o manualmente.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-107">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="fd7ca-108">Se iniciará un servicio que se inicia automáticamente cuando se reinicia el equipo en el que está instalado o se activa por primera vez.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-108">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="fd7ca-109">Un usuario debe iniciar un servicio que inicia de forma manual.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-109">A user must start a service that starts manually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd7ca-110">De forma predeterminada, los servicios creados con [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] están configurados para iniciarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-110">By default, services created with [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] are set to start manually.</span></span>  
  
 <span data-ttu-id="fd7ca-111">Puede iniciar manualmente un servicio de varias maneras: desde **Explorador de servidores**, desde el **Administrador de Control de servicios**, o desde el código mediante un componente denominado el <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-111">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>  
  
 <span data-ttu-id="fd7ca-112">Establece el <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad en la <xref:System.ServiceProcess.ServiceInstaller> clase para determinar si se debería iniciar un servicio de forma manual o automática.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-112">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>  
  
### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="fd7ca-113">Para especificar cómo debe iniciar un servicio</span><span class="sxs-lookup"><span data-stu-id="fd7ca-113">To specify how a service should start</span></span>  
  
1.  <span data-ttu-id="fd7ca-114">Después de crear el servicio, agregar a los instaladores necesarios para él.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="fd7ca-115">Para obtener más información, consulte [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="fd7ca-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="fd7ca-116">En el diseñador, haga clic en el instalador del servicio para el servicio que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-116">In the designer, click the service installer for the service you are working with.</span></span>  
  
3.  <span data-ttu-id="fd7ca-117">En el **propiedades** ventana, establezca el <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad en uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd7ca-117">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>  
  
    |<span data-ttu-id="fd7ca-118">Para hacer que el servicio instale</span><span class="sxs-lookup"><span data-stu-id="fd7ca-118">To have your service install</span></span>|<span data-ttu-id="fd7ca-119">Establezca este valor</span><span class="sxs-lookup"><span data-stu-id="fd7ca-119">Set this value</span></span>|  
    |----------------------------------|--------------------|  
    |<span data-ttu-id="fd7ca-120">Cuando se reinicia el equipo</span><span class="sxs-lookup"><span data-stu-id="fd7ca-120">When the computer is restarted</span></span>|<span data-ttu-id="fd7ca-121">**Automático**</span><span class="sxs-lookup"><span data-stu-id="fd7ca-121">**Automatic**</span></span>|  
    |<span data-ttu-id="fd7ca-122">Cuando el servicio inicia una acción explícita del usuario</span><span class="sxs-lookup"><span data-stu-id="fd7ca-122">When an explicit user action starts the service</span></span>|<span data-ttu-id="fd7ca-123">**Manual**</span><span class="sxs-lookup"><span data-stu-id="fd7ca-123">**Manual**</span></span>|  
  
    > [!TIP]
    >  <span data-ttu-id="fd7ca-124">Para evitar que el servicio que se inicia en absoluto, puede establecer la <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad **deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-124">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="fd7ca-125">Podría hacer esto si va a reiniciar un servidor varias veces y desea ahorrar tiempo al impedir que los servicios que normalmente se iniciaría impedir que se inicie.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-125">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd7ca-126">Estas y otras propiedades se pueden cambiar después de instala el servicio.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-126">These and other properties can be changed after your service is installed.</span></span>  
  
     <span data-ttu-id="fd7ca-127">Hay varias formas de iniciar un servicio que tenga su <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> proceso definida en **Manual** : de **Explorador de servidores**, desde la **Administrador de Control de servicios de Windows**, o desde el código.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-127">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="fd7ca-128">Es importante tener en cuenta que no todos estos métodos inician realmente el servicio en el contexto de la **Administrador de Control de servicios**; **Explorador de servidores** y métodos de programación de inicio del servicio manipulan realmente el controlador.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-128">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="fd7ca-129">Para iniciar manualmente un servicio desde el Explorador de servidores</span><span class="sxs-lookup"><span data-stu-id="fd7ca-129">To manually start a service from Server Explorer</span></span>  
  
1.  <span data-ttu-id="fd7ca-130">En **Explorador de servidores**, agregue el servidor que desea si no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-130">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="fd7ca-131">Para obtener más información, vea Cómo: acceso e inicializar el Explorador de explorador de bases de datos de servidor.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-131">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
2.  <span data-ttu-id="fd7ca-132">Expanda el **servicios** nodo y, a continuación, busque el servicio que desea iniciar.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-132">Expand the **Services** node, and then locate the service you want to start.</span></span>  
  
3.  <span data-ttu-id="fd7ca-133">Haga clic en el nombre del servicio y haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-133">Right-click the name of the service, and click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="fd7ca-134">Para iniciar manualmente un servicio desde el Administrador de Control de servicios</span><span class="sxs-lookup"><span data-stu-id="fd7ca-134">To manually start a service from Services Control Manager</span></span>  
  
1.  <span data-ttu-id="fd7ca-135">Abra la **Administrador de Control de servicios** llevando a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="fd7ca-135">Open the **Services Control Manager** by doing one of the following:</span></span>  
  
    -   <span data-ttu-id="fd7ca-136">En Windows XP y 2000 Professional, haga clic en **Mi PC** en el escritorio y, a continuación, haga clic en **administrar**.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-136">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="fd7ca-137">En el cuadro de diálogo que aparece, expanda el **servicios y aplicaciones** nodo.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-137">In the dialog box that appears, expand the **Services and Applications** node.</span></span>  
  
         <span data-ttu-id="fd7ca-138">\- o -</span><span class="sxs-lookup"><span data-stu-id="fd7ca-138">\- or -</span></span>  
  
    -   <span data-ttu-id="fd7ca-139">En Windows Server 2003 y Windows 2000 Server, haga clic en **iniciar**, seleccione **programas**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **Services**.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-139">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="fd7ca-140">En Windows NT versión 4.0, puede abrir este cuadro de diálogo de **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-140">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>  
  
     <span data-ttu-id="fd7ca-141">Ahora debería ver su servicio incluidos en el **servicios** sección de la ventana.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-141">You should now see your service listed in the **Services** section of the window.</span></span>  
  
2.  <span data-ttu-id="fd7ca-142">Seleccione su servicio en la lista, haga clic en él y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-142">Select your service in the list, right-click it, and then click **Start**.</span></span>  
  
### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="fd7ca-143">Para iniciar manualmente un servicio desde el código</span><span class="sxs-lookup"><span data-stu-id="fd7ca-143">To manually start a service from code</span></span>  
  
1.  <span data-ttu-id="fd7ca-144">Cree una instancia de la <xref:System.ServiceProcess.ServiceController> clase y configurarlo para que interactúe con el servicio que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-144">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>  
  
2.  <span data-ttu-id="fd7ca-145">Llame al método <xref:System.ServiceProcess.ServiceController.Start%2A> para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="fd7ca-145">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7ca-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd7ca-146">See Also</span></span>  
 [<span data-ttu-id="fd7ca-147">Introducción a las aplicaciones de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="fd7ca-147">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="fd7ca-148">Cómo: crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="fd7ca-148">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="fd7ca-149">Cómo: agregar instaladores a la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="fd7ca-149">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
