---
title: Procedimiento para crear servicios de Windows
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
author: ghogen
ms.openlocfilehash: 514675b3c3ce1f6701dff571361df672fb520c6a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053665"
---
# <a name="how-to-create-windows-services"></a><span data-ttu-id="716c2-102">Procedimiento para crear servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="716c2-102">How to: Create Windows Services</span></span>
<span data-ttu-id="716c2-103">Al crear un servicio, puede usar una plantilla de proyecto de Visual Studio denominada **Servicio de Windows**.</span><span class="sxs-lookup"><span data-stu-id="716c2-103">When you create a service, you can use a Visual Studio project template called **Windows Service**.</span></span> <span data-ttu-id="716c2-104">Esta plantilla realiza automáticamente gran parte del trabajo: hace referencia a las clases y los espacios de nombres correctos, configura la herencia de la clase base para los servicios y reemplazar algunos de los métodos que es probable que desee reemplazar.</span><span class="sxs-lookup"><span data-stu-id="716c2-104">This template automatically does much of the work for you by referencing the appropriate classes and namespaces, setting up the inheritance from the base class for services, and overriding several of the methods you're likely to want to override.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="716c2-105">La plantilla de proyecto Servicios de Windows no está disponible en la edición Express de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="716c2-105">The Windows Services project template is not available in the Express edition of Visual Studio.</span></span>  
  
 <span data-ttu-id="716c2-106">Como mínimo, para crear un servicio funcional, deberá:</span><span class="sxs-lookup"><span data-stu-id="716c2-106">At a minimum, to create a functional service you must:</span></span>  
  
- <span data-ttu-id="716c2-107">Establecer la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A>.</span><span class="sxs-lookup"><span data-stu-id="716c2-107">Set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property.</span></span>  
  
- <span data-ttu-id="716c2-108">Crear los instaladores necesarios para la aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-108">Create the necessary installers for your service application.</span></span>  
  
- <span data-ttu-id="716c2-109">Reemplazar y especificar el código para los métodos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A> para personalizar el modo en que se comporta el servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-109">Override and specify code for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods to customize the ways in which your service behaves.</span></span>  
  
### <a name="to-create-a-windows-service-application"></a><span data-ttu-id="716c2-110">Para crear una aplicación de servicio de Windows</span><span class="sxs-lookup"><span data-stu-id="716c2-110">To create a Windows Service application</span></span>  
  
1. <span data-ttu-id="716c2-111">Cree un proyecto de **Servicio Windows**.</span><span class="sxs-lookup"><span data-stu-id="716c2-111">Create a **Windows Service** project.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="716c2-112">Para obtener instrucciones sobre cómo escribir un servicio sin usar la plantilla, vea [Cómo: Escribir servicios mediante programación](how-to-write-services-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="716c2-112">For instructions on writing a service without using the template, see [How to: Write Services Programmatically](how-to-write-services-programmatically.md).</span></span>  
  
2. <span data-ttu-id="716c2-113">En la ventana **Propiedades**, establezca la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> para el servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-113">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for your service.</span></span>  
  
     <span data-ttu-id="716c2-114">![Establezca la propiedad ServiceName.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span><span class="sxs-lookup"><span data-stu-id="716c2-114">![Set the ServiceName property.](./media/windowsservice-servicename.PNG "WindowsService_ServiceName")</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="716c2-115">El valor de la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> siempre debe coincidir con el nombre registrado en las clases del instalador.</span><span class="sxs-lookup"><span data-stu-id="716c2-115">The value of the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property must always match the name recorded in the installer classes.</span></span> <span data-ttu-id="716c2-116">Si cambia esta propiedad, también debe actualizar la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> de las clases del instalador.</span><span class="sxs-lookup"><span data-stu-id="716c2-116">If you change this property, you must update the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property of installer classes as well.</span></span>  
  
3. <span data-ttu-id="716c2-117">Establezca cualquiera de las siguientes propiedades para determinar cómo funcionará el servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-117">Set any of the following properties to determine how your service will function.</span></span>  
  
    |<span data-ttu-id="716c2-118">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="716c2-118">Property</span></span>|<span data-ttu-id="716c2-119">Parámetro</span><span class="sxs-lookup"><span data-stu-id="716c2-119">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|<span data-ttu-id="716c2-120">`True` para indicar que el servicio aceptará solicitudes para detener la ejecución; `false` para impedir que el servicio se detenga.</span><span class="sxs-lookup"><span data-stu-id="716c2-120">`True` to indicate that the service will accept requests to stop running; `false` to prevent the service from being stopped.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|<span data-ttu-id="716c2-121">`True` para indicar que el servicio desea recibir una notificación cuando se apaga el equipo en que reside, lo que le permite llamar al procedimiento <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>.</span><span class="sxs-lookup"><span data-stu-id="716c2-121">`True` to indicate that the service wants to receive notification when the computer on which it lives shuts down, enabling it to call the <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> procedure.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|<span data-ttu-id="716c2-122">`True` para indicar que el servicio aceptará solicitudes para pausar o reanudar la ejecución; `false` para impedir que el servicio se pause y se reanude.</span><span class="sxs-lookup"><span data-stu-id="716c2-122">`True` to indicate that the service will accept requests to pause or to resume running; `false` to prevent the service from being paused and resumed.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|<span data-ttu-id="716c2-123">`True` para indicar que el servicio puede controlar la notificación de cambios en el estado de alimentación del equipo; `false` para impedir la notificación al servicio de estos cambios.</span><span class="sxs-lookup"><span data-stu-id="716c2-123">`True` to indicate that the service can handle notification of changes to the computer's power status; `false` to prevent the service from being notified of these changes.</span></span>|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|<span data-ttu-id="716c2-124">`True` para escribir entradas informativas en el registro de sucesos de aplicación cuando el servicio realice una acción; `false` para deshabilitar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="716c2-124">`True` to write informational entries to the Application event log when your service performs an action; `false` to disable this functionality.</span></span> <span data-ttu-id="716c2-125">Para obtener más información, vea [Cómo: Registrar información sobre servicios](how-to-log-information-about-services.md).</span><span class="sxs-lookup"><span data-stu-id="716c2-125">For more information, see [How to: Log Information About Services](how-to-log-information-about-services.md).</span></span> <span data-ttu-id="716c2-126">**Nota:**  De manera predeterminada, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="716c2-126">**Note:**  By default, <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> is set to `true`.</span></span>|  
  
    > [!NOTE]
    > <span data-ttu-id="716c2-127">Cuando <xref:System.ServiceProcess.ServiceBase.CanStop%2A> o <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> se establecen en `false`, el **Administrador de control de servicios** deshabilitará las opciones de menú correspondientes para detener, pausar o continuar el servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-127">When <xref:System.ServiceProcess.ServiceBase.CanStop%2A> or <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> are set to `false`, the **Service Control Manager** will disable the corresponding menu options to stop, pause, or continue the service.</span></span>  
  
4. <span data-ttu-id="716c2-128">Obtenga acceso al Editor de código y rellene el procesamiento que desee para los procedimientos <xref:System.ServiceProcess.ServiceBase.OnStart%2A> y <xref:System.ServiceProcess.ServiceBase.OnStop%2A>.</span><span class="sxs-lookup"><span data-stu-id="716c2-128">Access the Code Editor and fill in the processing you want for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures.</span></span>  
  
5. <span data-ttu-id="716c2-129">Reemplace los otros métodos para los que desee definir la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="716c2-129">Override any other methods for which you want to define functionality.</span></span>  
  
6. <span data-ttu-id="716c2-130">Agregar los instaladores necesarios para su aplicación de servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-130">Add the necessary installers for your service application.</span></span> <span data-ttu-id="716c2-131">Para obtener más información, vea [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="716c2-131">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
7. <span data-ttu-id="716c2-132">En el menú **Compilar**, seleccione **Compilar solución** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="716c2-132">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="716c2-133">No presione F5 para ejecutar el proyecto: no se puede ejecutar un proyecto de servicio de esta manera.</span><span class="sxs-lookup"><span data-stu-id="716c2-133">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
8. <span data-ttu-id="716c2-134">Instale el servicio.</span><span class="sxs-lookup"><span data-stu-id="716c2-134">Install the service.</span></span> <span data-ttu-id="716c2-135">Para obtener más información, vea [Cómo: Instalar y desinstalar servicios](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="716c2-135">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="716c2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="716c2-136">See also</span></span>

- [<span data-ttu-id="716c2-137">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="716c2-137">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="716c2-138">Cómo: Escribir servicios mediante programación</span><span class="sxs-lookup"><span data-stu-id="716c2-138">How to: Write Services Programmatically</span></span>](how-to-write-services-programmatically.md)
- [<span data-ttu-id="716c2-139">Cómo: Adición de instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="716c2-139">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="716c2-140">Cómo: Registrar información sobre servicios</span><span class="sxs-lookup"><span data-stu-id="716c2-140">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="716c2-141">Cómo: Iniciar servicios</span><span class="sxs-lookup"><span data-stu-id="716c2-141">How to: Start Services</span></span>](how-to-start-services.md)
- [<span data-ttu-id="716c2-142">Cómo: Especificar el contexto de seguridad de los servicios</span><span class="sxs-lookup"><span data-stu-id="716c2-142">How to: Specify the Security Context for Services</span></span>](how-to-specify-the-security-context-for-services.md)
- [<span data-ttu-id="716c2-143">Cómo: Instalar y desinstalar servicios</span><span class="sxs-lookup"><span data-stu-id="716c2-143">How to: Install and Uninstall Services</span></span>](how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="716c2-144">Tutorial: Creación de una aplicación de servicios de Windows en el Diseñador de componentes</span><span class="sxs-lookup"><span data-stu-id="716c2-144">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
