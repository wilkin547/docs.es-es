---
title: Procedimiento para iniciar servicios
description: Aprenda varias formas de iniciar servicios. Después de instalar un servicio, debe iniciarse. Al iniciarse, llama al método OnStart en la clase de servicio.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
ms.openlocfilehash: 4a2f9b291e60b12b1465fbb6bbbd1604572359a7
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925727"
---
# <a name="how-to-start-services"></a><span data-ttu-id="6e643-105">Procedimiento para iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="6e643-105">How to: Start Services</span></span>

<span data-ttu-id="6e643-106">Después de instalar un servicio, debe iniciarse.</span><span class="sxs-lookup"><span data-stu-id="6e643-106">After a service is installed, it must be started.</span></span> <span data-ttu-id="6e643-107">Al iniciarse, llama al método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> en la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="6e643-107">Starting calls the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method on the service class.</span></span> <span data-ttu-id="6e643-108">Normalmente, el método <xref:System.ServiceProcess.ServiceBase.OnStart%2A> define el trabajo útil que realizará el servicio.</span><span class="sxs-lookup"><span data-stu-id="6e643-108">Usually, the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method defines the useful work the service will perform.</span></span> <span data-ttu-id="6e643-109">Después de que se inicia un servicio, este permanece activo hasta que se pausa o se detiene manualmente.</span><span class="sxs-lookup"><span data-stu-id="6e643-109">After a service starts, it remains active until it is manually paused or stopped.</span></span>

<span data-ttu-id="6e643-110">Los servicios se pueden configurar para que se inicien automática o manualmente.</span><span class="sxs-lookup"><span data-stu-id="6e643-110">Services can be set up to start automatically or manually.</span></span> <span data-ttu-id="6e643-111">Un servicio que se inicia automáticamente se iniciará cuando se reinicie o encienda por primera vez el equipo en el que está instalado.</span><span class="sxs-lookup"><span data-stu-id="6e643-111">A service that starts automatically will be started when the computer on which it is installed is rebooted or first turned on.</span></span> <span data-ttu-id="6e643-112">El usuario debe iniciar un servicio que se inicia manualmente.</span><span class="sxs-lookup"><span data-stu-id="6e643-112">A user must start a service that starts manually.</span></span>

> [!NOTE]
> <span data-ttu-id="6e643-113">De forma predeterminada, los servicios creados con Visual Studio se inician manualmente.</span><span class="sxs-lookup"><span data-stu-id="6e643-113">By default, services created with Visual Studio are set to start manually.</span></span>

<span data-ttu-id="6e643-114">Hay varias maneras de iniciar un servicio manualmente: desde el **Explorador de servidores**, desde el **Administrador de control de servicios** o desde el código con un componente llamado <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="6e643-114">There are several ways you can manually start a service — from **Server Explorer**, from the **Services Control Manager**, or from code using a component called the <xref:System.ServiceProcess.ServiceController>.</span></span>

<span data-ttu-id="6e643-115">Establece la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en la clase <xref:System.ServiceProcess.ServiceInstaller> para determinar si un servicio debe iniciarse manual o automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6e643-115">You set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property on the <xref:System.ServiceProcess.ServiceInstaller> class to determine whether a service should be started manually or automatically.</span></span>

### <a name="to-specify-how-a-service-should-start"></a><span data-ttu-id="6e643-116">Para especificar cómo debe iniciarse un servicio</span><span class="sxs-lookup"><span data-stu-id="6e643-116">To specify how a service should start</span></span>

1. <span data-ttu-id="6e643-117">Después de crear su servicio, agregue los instaladores necesarios para ello.</span><span class="sxs-lookup"><span data-stu-id="6e643-117">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="6e643-118">Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="6e643-118">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>

2. <span data-ttu-id="6e643-119">En el diseñador, haga clic en el instalador del servicio para el servicio con el que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="6e643-119">In the designer, click the service installer for the service you are working with.</span></span>

3. <span data-ttu-id="6e643-120">En la ventana **Propiedades**, establezca la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en blanco:</span><span class="sxs-lookup"><span data-stu-id="6e643-120">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to one of the following:</span></span>

    |<span data-ttu-id="6e643-121">Para que el servicio se instale</span><span class="sxs-lookup"><span data-stu-id="6e643-121">To have your service install</span></span>|<span data-ttu-id="6e643-122">Establezca ese valor</span><span class="sxs-lookup"><span data-stu-id="6e643-122">Set this value</span></span>|
    |----------------------------------|--------------------|
    |<span data-ttu-id="6e643-123">Cuando se reinicia el equipo</span><span class="sxs-lookup"><span data-stu-id="6e643-123">When the computer is restarted</span></span>|<span data-ttu-id="6e643-124">**Automático**</span><span class="sxs-lookup"><span data-stu-id="6e643-124">**Automatic**</span></span>|
    |<span data-ttu-id="6e643-125">Cuando una acción explícita del usuario inicia el servicio</span><span class="sxs-lookup"><span data-stu-id="6e643-125">When an explicit user action starts the service</span></span>|<span data-ttu-id="6e643-126">**Manual**</span><span class="sxs-lookup"><span data-stu-id="6e643-126">**Manual**</span></span>|

    > [!TIP]
    > <span data-ttu-id="6e643-127">Para evitar que se inicie el servicio, puede establecer la propiedad <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="6e643-127">To prevent your service from being started at all, you can set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to **Disabled**.</span></span> <span data-ttu-id="6e643-128">Puede hacer esto si va a reiniciar un servidor varias veces y quiere ahorrar tiempo evitando que se inicien los servicios que normalmente se iniciarían.</span><span class="sxs-lookup"><span data-stu-id="6e643-128">You might do this if you are going to reboot a server several times and want to save time by preventing the services that would normally start from starting up.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e643-129">Estas y otras propiedades se pueden cambiar después de instalar el servicio.</span><span class="sxs-lookup"><span data-stu-id="6e643-129">These and other properties can be changed after your service is installed.</span></span>

    <span data-ttu-id="6e643-130">Hay varias formas de iniciar un servicio que tiene el proceso <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> establecido en **Manual**: desde el **Explorador de servidores**, desde el **Administrador de control de servicios**, o desde el código.</span><span class="sxs-lookup"><span data-stu-id="6e643-130">There are several ways you can start a service that has its <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> process set to **Manual** — from **Server Explorer**, from the **Windows Services Control Manager**, or from code.</span></span> <span data-ttu-id="6e643-131">Es importante indicar que no todos estos métodos inician realmente el servicio en el contexto del **Administrador de control de servicios**, **Explorador de servidores** y los métodos mediante programación para iniciar el servicio manipulan realmente el controlador.</span><span class="sxs-lookup"><span data-stu-id="6e643-131">It is important to note that not all of these methods actually start the service in the context of the **Services Control Manager**; **Server Explorer** and programmatic methods of starting the service actually manipulate the controller.</span></span>

### <a name="to-manually-start-a-service-from-server-explorer"></a><span data-ttu-id="6e643-132">Para iniciar manualmente un servicio desde el Explorador de servidores</span><span class="sxs-lookup"><span data-stu-id="6e643-132">To manually start a service from Server Explorer</span></span>

1. <span data-ttu-id="6e643-133">En el **Explorador de servidores**, agregue el servidor que desea si no aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="6e643-133">In **Server Explorer**, add the server you want if it is not already listed.</span></span> <span data-ttu-id="6e643-134">Para obtener más información, vea el artículo sobre cómo acceder al Explorador de servidores y al Explorador de bases de datos e inicializarlos.</span><span class="sxs-lookup"><span data-stu-id="6e643-134">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>

2. <span data-ttu-id="6e643-135">Expanda el nodo **Servicios** y, después, busque el servicio que desea iniciar.</span><span class="sxs-lookup"><span data-stu-id="6e643-135">Expand the **Services** node, and then locate the service you want to start.</span></span>

3. <span data-ttu-id="6e643-136">Haga clic con el botón derecho en el servicio y, después, haga clic en **Detener**.</span><span class="sxs-lookup"><span data-stu-id="6e643-136">Right-click the name of the service, and click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-services-control-manager"></a><span data-ttu-id="6e643-137">Para iniciar manualmente un servicio desde el Administrador de control de servicios</span><span class="sxs-lookup"><span data-stu-id="6e643-137">To manually start a service from Services Control Manager</span></span>

1. <span data-ttu-id="6e643-138">Abra el **Administrador de control de servicios** llevando a cabo una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="6e643-138">Open the **Services Control Manager** by doing one of the following:</span></span>

    - <span data-ttu-id="6e643-139">En Windows XP y 2000 Professional, haga clic en **Mi PC** en el escritorio y, después, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="6e643-139">In Windows XP and 2000 Professional, right-click **My Computer** on the desktop, and then click **Manage**.</span></span> <span data-ttu-id="6e643-140">En el cuadro de diálogo que aparece, expanda el nodo **Servicios y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6e643-140">In the dialog box that appears, expand the **Services and Applications** node.</span></span>

      <span data-ttu-id="6e643-141">\- o -</span><span class="sxs-lookup"><span data-stu-id="6e643-141">\- or -</span></span>

    - <span data-ttu-id="6e643-142">En Windows Server 2003 y Windows 2000 Server, haga clic en **Iniciar**, seleccione **Programas**, haga clic en **Herramientas administrativas** y, a continuación, haga clic en **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="6e643-142">In Windows Server 2003 and Windows 2000 Server, click **Start**, point to **Programs**, click **Administrative Tools**, and then click **Services**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="6e643-143">En Windows NT versión 4.0, puede abrir este cuadro de diálogo desde el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="6e643-143">In Windows NT version 4.0, you can open this dialog box from **Control Panel**.</span></span>

    <span data-ttu-id="6e643-144">Podrá ver su servicio en la lista de la sección **Servicios** de la ventana.</span><span class="sxs-lookup"><span data-stu-id="6e643-144">You should now see your service listed in the **Services** section of the window.</span></span>

2. <span data-ttu-id="6e643-145">Seleccione su servicio en la lista, haga clic en él con el botón secundario y luego haga clic en **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="6e643-145">Select your service in the list, right-click it, and then click **Start**.</span></span>

### <a name="to-manually-start-a-service-from-code"></a><span data-ttu-id="6e643-146">Para iniciar manualmente un servicio desde el código</span><span class="sxs-lookup"><span data-stu-id="6e643-146">To manually start a service from code</span></span>

1. <span data-ttu-id="6e643-147">Cree una instancia de la clase <xref:System.ServiceProcess.ServiceController> y configúrela para que interactúe con el servicio que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="6e643-147">Create an instance of the <xref:System.ServiceProcess.ServiceController> class, and configure it to interact with the service you want to administer.</span></span>

2. <span data-ttu-id="6e643-148">Llame al método <xref:System.ServiceProcess.ServiceController.Start%2A> para iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="6e643-148">Call the <xref:System.ServiceProcess.ServiceController.Start%2A> method to start the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e643-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e643-149">See also</span></span>

- [<span data-ttu-id="6e643-150">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="6e643-150">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="6e643-151">Cómo: Creación de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="6e643-151">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="6e643-152">Cómo: Adición de instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="6e643-152">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
