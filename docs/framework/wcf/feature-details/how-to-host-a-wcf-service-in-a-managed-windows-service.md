---
title: Hospedaje de un servicio WCF en un servicio administrado de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 698a5134683341fedf2a37f7d6383770e14c232c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964803"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="07183-102">Hospedaje de un servicio WCF en un servicio administrado de Windows</span><span class="sxs-lookup"><span data-stu-id="07183-102">How to: Host a WCF Service in a Managed Windows Service</span></span>

<span data-ttu-id="07183-103">En este tema se describen los pasos básicos necesarios para crear un servicio de Windows Communication Foundation (WCF) que esté hospedado en un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="07183-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="07183-104">El escenario se habilita mediante la opción de hospedaje del servicio administrado de Windows, que es un servicio WCF de ejecución prolongada hospedado fuera de Internet Information Services (IIS) en un entorno seguro que no está activado por mensaje.</span><span class="sxs-lookup"><span data-stu-id="07183-104">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="07183-105">En su lugar, el sistema operativo controla la duración del servicio.</span><span class="sxs-lookup"><span data-stu-id="07183-105">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="07183-106">Esta opción de hospedaje está disponible en todas las versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="07183-106">This hosting option is available in all versions of Windows.</span></span>

<span data-ttu-id="07183-107">Los servicios de Windows se pueden administrar con Microsoft.ManagementConsole.SnapIn en Microsoft Management Console (MMC) y pueden configurarse automáticamente para iniciar cuando el sistema arranca.</span><span class="sxs-lookup"><span data-stu-id="07183-107">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="07183-108">Esta opción de hospedaje consiste en registrar el dominio de aplicación (AppDomain) que hospeda un servicio WCF como servicio administrado de Windows para que la duración del proceso del servicio se controle mediante el administrador de control de servicios (SCM) para servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="07183-108">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>

<span data-ttu-id="07183-109">El código del servicio incluye una implementación del contrato de servicios, una clase de Windows Service y una clase del instalador.</span><span class="sxs-lookup"><span data-stu-id="07183-109">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="07183-110">La clase de implementación de servicio, `CalculatorService`, es un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="07183-110">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="07183-111">`CalculatorWindowsService` es un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="07183-111">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="07183-112">Para poder calificarse como servicio de Windows, la clase hereda de `ServiceBase` e implementa los métodos `OnStart` y `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="07183-112">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="07183-113">En `OnStart`, se crea <xref:System.ServiceModel.ServiceHost> para el tipo `CalculatorService` y se abre.</span><span class="sxs-lookup"><span data-stu-id="07183-113">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="07183-114">En `OnStop`, el servicio se detiene y se elimina.</span><span class="sxs-lookup"><span data-stu-id="07183-114">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="07183-115">El host también es responsable de proporcionar una dirección base al host de servicio, que se ha configurado en los valores de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07183-115">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="07183-116">La clase del instalador, que hereda de <xref:System.Configuration.Install.Installer>, permite instalar el programa como un servicio de Windows mediante la herramienta Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="07183-116">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>

## <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="07183-117">Construya el servicio y proporcione el código del hospedaje</span><span class="sxs-lookup"><span data-stu-id="07183-117">Construct the service and provide the hosting code</span></span>

1. <span data-ttu-id="07183-118">Cree un nuevo proyecto de **aplicación de consola** de Visual Studio denominado **Service**.</span><span class="sxs-lookup"><span data-stu-id="07183-118">Create a new Visual Studio **Console app** project called **Service**.</span></span>

2. <span data-ttu-id="07183-119">Cambie el nombre del archivo Program.cs a Service.cs.</span><span class="sxs-lookup"><span data-stu-id="07183-119">Rename Program.cs to Service.cs.</span></span>

3. <span data-ttu-id="07183-120">Cambie el espacio de nombres a `Microsoft.ServiceModel.Samples`.</span><span class="sxs-lookup"><span data-stu-id="07183-120">Change the namespace to `Microsoft.ServiceModel.Samples`.</span></span>

4. <span data-ttu-id="07183-121">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="07183-121">Add references to the following assemblies:</span></span>

    - <span data-ttu-id="07183-122">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="07183-122">System.ServiceModel.dll</span></span>

    - <span data-ttu-id="07183-123">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="07183-123">System.ServiceProcess.dll</span></span>

    - <span data-ttu-id="07183-124">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="07183-124">System.Configuration.Install.dll</span></span>

5. <span data-ttu-id="07183-125">Agregue las siguientes instrucciones Using a Service.cs.</span><span class="sxs-lookup"><span data-stu-id="07183-125">Add the following using statements to Service.cs.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. <span data-ttu-id="07183-126">Defina el contrato de servicio `ICalculator`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="07183-126">Define the `ICalculator` service contract as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. <span data-ttu-id="07183-127">Implemente el contrato de servicio en una clase denominada `CalculatorService`, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="07183-127">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. <span data-ttu-id="07183-128">Cree una nueva clase denominada `CalculatorWindowsService` que herede de la clase <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="07183-128">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="07183-129">Agregue una variable local denominada `serviceHost` para hacer referencia a la instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="07183-129">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="07183-130">Defina el método `Main` que llama a `ServiceBase.Run(new CalculatorWindowsService)`.</span><span class="sxs-lookup"><span data-stu-id="07183-130">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. <span data-ttu-id="07183-131">Invalide el método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> creando y abriendo una nueva instancia de <xref:System.ServiceModel.ServiceHost>, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="07183-131">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. <span data-ttu-id="07183-132">Invalide el método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> cerrando <xref:System.ServiceModel.ServiceHost>, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="07183-132">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. <span data-ttu-id="07183-133">Cree una nueva clase denominada `ProjectInstaller` que herede de <xref:System.Configuration.Install.Installer> y que esté marcada con el <xref:System.ComponentModel.RunInstallerAttribute> establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="07183-133">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="07183-134">Esto permite a la herramienta Installutil.exe instalar el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="07183-134">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. <span data-ttu-id="07183-135">Quite la clase `Service` generada al crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="07183-135">Remove the `Service` class that was generated when you created the project.</span></span>

13. <span data-ttu-id="07183-136">Agregue un archivo de configuración de aplicación al proyecto.</span><span class="sxs-lookup"><span data-stu-id="07183-136">Add an application configuration file to the project.</span></span> <span data-ttu-id="07183-137">Reemplace el contenido del archivo por el XML de configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="07183-137">Replace the contents of the file with the following configuration XML.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     <span data-ttu-id="07183-138">Haga clic con el botón derecho en el archivo app. config en el **Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="07183-138">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="07183-139">En **Copiar en el directorio de salida** , seleccione **copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="07183-139">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>

     <span data-ttu-id="07183-140">Este ejemplo especifica puntos de conexión explícitamente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="07183-140">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="07183-141">Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="07183-141">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="07183-142">En este ejemplo, dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> establecido en `true`, el servicio también tiene habilitada la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="07183-142">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="07183-143">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="07183-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="install-and-run-the-service"></a><span data-ttu-id="07183-144">Instale y ejecute el servicio.</span><span class="sxs-lookup"><span data-stu-id="07183-144">Install and run the service</span></span>

1. <span data-ttu-id="07183-145">Compile la solución para crear el ejecutable `Service.exe`.</span><span class="sxs-lookup"><span data-stu-id="07183-145">Build the solution to create the `Service.exe` executable.</span></span>

2. <span data-ttu-id="07183-146">Abra Símbolo del sistema para desarrolladores para Visual Studio y navegue hasta el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="07183-146">Open Developer Command Prompt for Visual Studio and navigate to the project directory.</span></span> <span data-ttu-id="07183-147">Escriba `installutil bin\service.exe` en el símbolo del sistema para instalar el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="07183-147">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>

     <span data-ttu-id="07183-148">Escriba `services.msc` en el símbolo del sistema para tener acceso al Administrador de control de servicios (SCM).</span><span class="sxs-lookup"><span data-stu-id="07183-148">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="07183-149">El servicio de Windows debería aparecer en Servicios como "WCFWindowsServiceSample".</span><span class="sxs-lookup"><span data-stu-id="07183-149">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="07183-150">El servicio WCF solo puede responder a los clientes si el servicio de Windows se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="07183-150">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="07183-151">Para iniciar el servicio, haga clic con el botón secundario en el SCM y seleccione "iniciar" o escriba **net start WCFWindowsServiceSample** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="07183-151">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>

3. <span data-ttu-id="07183-152">Si realiza cambios en el servicio, debe detenerlo primero y desinstalarlo.</span><span class="sxs-lookup"><span data-stu-id="07183-152">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="07183-153">Para detener el servicio, haga clic con el botón secundario en el SCM y seleccione "STOP" o **escriba net stop WCFWindowsServiceSample** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="07183-153">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="07183-154">Tenga en cuenta que si detiene el servicio de Windows y, a continuación, ejecuta un cliente, se produce una excepción <xref:System.ServiceModel.EndpointNotFoundException> cuando un cliente intenta tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="07183-154">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="07183-155">Para desinstalar el tipo de servicio de Windows **InstallUtil/u bin\service.exe** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="07183-155">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>

## <a name="example"></a><span data-ttu-id="07183-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="07183-156">Example</span></span>

<span data-ttu-id="07183-157">A continuación se muestra una lista completa del código que se usa en este tema:</span><span class="sxs-lookup"><span data-stu-id="07183-157">The following is a complete listing of the code used by this topic:</span></span>

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

<span data-ttu-id="07183-158">Como la opción de "autohospedaje", el entorno de hospedaje de servicio de Windows requiere que algún código de hospedaje se escriba como parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07183-158">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="07183-159">El servicio se implementa como una aplicación de consola y contiene su propio código de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="07183-159">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="07183-160">En otros entornos de hospedaje, como el del Servicio de activación de procesos de Windows (WAS) en Internet Information Services (IIS), no es necesario que los programadores escriban código de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="07183-160">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>

## <a name="see-also"></a><span data-ttu-id="07183-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="07183-161">See also</span></span>

- [<span data-ttu-id="07183-162">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="07183-162">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
- [<span data-ttu-id="07183-163">Hospedaje en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="07183-163">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)
- [<span data-ttu-id="07183-164">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="07183-164">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- <span data-ttu-id="07183-165">[Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="07183-165">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
