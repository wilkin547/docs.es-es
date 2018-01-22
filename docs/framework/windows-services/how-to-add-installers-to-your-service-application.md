---
title: "Cómo: Agregar instaladores a una aplicación de servicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 15487d4311f896aa09c1c7712292058086a49b50
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="92adc-102">Cómo: Agregar instaladores a una aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="92adc-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="92adc-103">Visual Studio incluye componentes de instalación que pueden instalar recursos asociados con las aplicaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="92adc-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="92adc-104">Componentes de instalación registran un servicio individual en el sistema al que se va a instalar y que el Administrador de Control de servicios sepan que existe el servicio.</span><span class="sxs-lookup"><span data-stu-id="92adc-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="92adc-105">Cuando se trabaja con una aplicación de servicio, puede seleccionar un vínculo en la ventana Propiedades para agregar automáticamente los instaladores adecuados al proyecto.</span><span class="sxs-lookup"><span data-stu-id="92adc-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92adc-106">Los valores de propiedad para el servicio se copian de la clase de servicio a la clase del instalador.</span><span class="sxs-lookup"><span data-stu-id="92adc-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="92adc-107">Si actualiza los valores de propiedad en la clase de servicio, no se actualizan automáticamente en el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="92adc-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="92adc-108">Al agregar un instalador al proyecto, una nueva clase (que, de forma predeterminada, se denomina `ProjectInstaller`) se crea en el proyecto y las instancias de la instalación adecuada componentes se crean dentro de él.</span><span class="sxs-lookup"><span data-stu-id="92adc-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="92adc-109">Esta clase actúa como punto central para todos los componentes de instalación de su proyecto necesite.</span><span class="sxs-lookup"><span data-stu-id="92adc-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="92adc-110">Por ejemplo, si agrega un segundo servicio a la aplicación y haga clic en el vínculo Agregar instalador, no se crea una segunda clase del instalador; en su lugar, el componente de instalación adicional necesario para el segundo servicio se agrega a la clase existente.</span><span class="sxs-lookup"><span data-stu-id="92adc-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="92adc-111">No es necesario hacer ninguna codificación especial dentro de los instaladores para hacer que los servicios se instale correctamente.</span><span class="sxs-lookup"><span data-stu-id="92adc-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="92adc-112">Sin embargo, en ocasiones, necesite modificar el contenido de los instaladores si necesita agregar funcionalidad especial al proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="92adc-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92adc-113">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="92adc-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="92adc-114">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="92adc-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="92adc-115">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="92adc-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="92adc-116">Para agregar a instaladores a la aplicación de servicio</span><span class="sxs-lookup"><span data-stu-id="92adc-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="92adc-117">En **el Explorador de soluciones**, acceso **diseño** vista para el servicio para el que desea agregar un componente de instalación.</span><span class="sxs-lookup"><span data-stu-id="92adc-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="92adc-118">Haga clic en el fondo del diseñador para seleccionar el servicio de sí mismo, en lugar de su contenido.</span><span class="sxs-lookup"><span data-stu-id="92adc-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="92adc-119">Con el diseñador en foco, el menú contextual y, a continuación, haga clic en **Agregar instalador**.</span><span class="sxs-lookup"><span data-stu-id="92adc-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="92adc-120">Una nueva clase, `ProjectInstaller`y dos componentes de instalación, <xref:System.ServiceProcess.ServiceProcessInstaller> y <xref:System.ServiceProcess.ServiceInstaller>, se agregan a su proyecto y los valores de propiedad para el servicio se copian en los componentes.</span><span class="sxs-lookup"><span data-stu-id="92adc-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="92adc-121">Haga clic en el <xref:System.ServiceProcess.ServiceInstaller> componente y compruebe que el valor de la <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> propiedad se establece en el mismo valor que el <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> propiedad en el propio servicio.</span><span class="sxs-lookup"><span data-stu-id="92adc-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="92adc-122">Para determinar cómo se iniciará el servicio, haga clic en el <xref:System.ServiceProcess.ServiceInstaller> componente y establezca el <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> propiedad en el valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="92adc-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="92adc-123">Valor</span><span class="sxs-lookup"><span data-stu-id="92adc-123">Value</span></span>|<span data-ttu-id="92adc-124">Resultado</span><span class="sxs-lookup"><span data-stu-id="92adc-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="92adc-125">El servicio debe iniciarse manualmente después de la instalación.</span><span class="sxs-lookup"><span data-stu-id="92adc-125">The service must be manually started after installation.</span></span> <span data-ttu-id="92adc-126">Para obtener más información, consulte [Cómo: iniciar servicios](../../../docs/framework/windows-services/how-to-start-services.md).</span><span class="sxs-lookup"><span data-stu-id="92adc-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="92adc-127">El servicio se iniciará por sí mismo cada vez que el equipo se reinicia.</span><span class="sxs-lookup"><span data-stu-id="92adc-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="92adc-128">No se puede iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="92adc-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="92adc-129">Para determinar el contexto de seguridad en el que se ejecutará el servicio, haga clic en el <xref:System.ServiceProcess.ServiceProcessInstaller> componente y establezca los valores de propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="92adc-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="92adc-130">Para obtener más información, consulte [Cómo: especificar el contexto de seguridad para los servicios](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span><span class="sxs-lookup"><span data-stu-id="92adc-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="92adc-131">Reemplace los métodos para la que necesita realizar el procesamiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="92adc-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="92adc-132">Realice los pasos del 1 al 7 para cada servicio adicional en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="92adc-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92adc-133">Para cada servicio adicional en el proyecto, debe agregar otro <xref:System.ServiceProcess.ServiceInstaller> componente para el proyecto `ProjectInstaller` clase.</span><span class="sxs-lookup"><span data-stu-id="92adc-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="92adc-134">El <xref:System.ServiceProcess.ServiceProcessInstaller> el componente se agregó en el paso tres funciona con todos los instaladores de servicio individuales en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="92adc-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92adc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="92adc-135">See Also</span></span>  
 [<span data-ttu-id="92adc-136">Introducción a las aplicaciones de servicios de Windows</span><span class="sxs-lookup"><span data-stu-id="92adc-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="92adc-137">Instalación y desinstalación de servicios</span><span class="sxs-lookup"><span data-stu-id="92adc-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="92adc-138">Inicio de servicios</span><span class="sxs-lookup"><span data-stu-id="92adc-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="92adc-139">Definición del contexto de seguridad de los servicios</span><span class="sxs-lookup"><span data-stu-id="92adc-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
