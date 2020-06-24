---
title: Procedimiento para hospedar un servicio WCF en un servicio administrado de Windows
description: Obtenga información sobre cómo crear un servicio WCF que esté hospedado en un servicio de Windows. Esta opción de hospedaje está disponible en todas las versiones de Windows.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 4e07aa7aac82fae5cfd1bfc759ef724cf87a873a
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246941"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="073ab-104">Procedimiento para hospedar un servicio WCF en un servicio administrado de Windows</span><span class="sxs-lookup"><span data-stu-id="073ab-104">How to: Host a WCF Service in a Managed Windows Service</span></span>

<span data-ttu-id="073ab-105">En este tema se describen los pasos básicos necesarios para crear un servicio de Windows Communication Foundation (WCF) que esté hospedado en un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="073ab-105">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="073ab-106">El escenario se habilita mediante la opción de hospedaje del servicio administrado de Windows, que es un servicio WCF de ejecución prolongada hospedado fuera de Internet Information Services (IIS) en un entorno seguro que no está activado por mensaje.</span><span class="sxs-lookup"><span data-stu-id="073ab-106">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="073ab-107">En su lugar, el sistema operativo controla la duración del servicio.</span><span class="sxs-lookup"><span data-stu-id="073ab-107">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="073ab-108">Esta opción de hospedaje está disponible en todas las versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="073ab-108">This hosting option is available in all versions of Windows.</span></span>

<span data-ttu-id="073ab-109">Los servicios de Windows se pueden administrar con Microsoft.ManagementConsole.SnapIn en Microsoft Management Console (MMC) y pueden configurarse automáticamente para iniciar cuando el sistema arranca.</span><span class="sxs-lookup"><span data-stu-id="073ab-109">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="073ab-110">Esta opción de hospedaje consiste en registrar el dominio de aplicación (AppDomain) que hospeda un servicio WCF como servicio administrado de Windows para que la duración del proceso del servicio se controle mediante el administrador de control de servicios (SCM) para servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="073ab-110">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>

<span data-ttu-id="073ab-111">El código del servicio incluye una implementación del contrato de servicios, una clase de Windows Service y una clase del instalador.</span><span class="sxs-lookup"><span data-stu-id="073ab-111">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="073ab-112">La clase de implementación de servicio, `CalculatorService` , es un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="073ab-112">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="073ab-113">`CalculatorWindowsService` es un servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="073ab-113">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="073ab-114">Para poder calificarse como servicio de Windows, la clase hereda de `ServiceBase` e implementa los métodos `OnStart` y `OnStop`.</span><span class="sxs-lookup"><span data-stu-id="073ab-114">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="073ab-115">En `OnStart`, se crea <xref:System.ServiceModel.ServiceHost> para el tipo `CalculatorService` y se abre.</span><span class="sxs-lookup"><span data-stu-id="073ab-115">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="073ab-116">En `OnStop`, el servicio se detiene y se elimina.</span><span class="sxs-lookup"><span data-stu-id="073ab-116">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="073ab-117">El host también es responsable de proporcionar una dirección base al host de servicio, que se ha configurado en los valores de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="073ab-117">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="073ab-118">La clase del instalador, que hereda de <xref:System.Configuration.Install.Installer>, permite instalar el programa como un servicio de Windows mediante la herramienta Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="073ab-118">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>

## <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="073ab-119">Construya el servicio y proporcione el código del hospedaje</span><span class="sxs-lookup"><span data-stu-id="073ab-119">Construct the service and provide the hosting code</span></span>

1. <span data-ttu-id="073ab-120">Cree un nuevo proyecto de **aplicación de consola** de Visual Studio denominado **Service**.</span><span class="sxs-lookup"><span data-stu-id="073ab-120">Create a new Visual Studio **Console app** project called **Service**.</span></span>

2. <span data-ttu-id="073ab-121">Cambie el nombre del archivo Program.cs a Service.cs.</span><span class="sxs-lookup"><span data-stu-id="073ab-121">Rename Program.cs to Service.cs.</span></span>

3. <span data-ttu-id="073ab-122">Cambie el espacio de nombres a `Microsoft.ServiceModel.Samples` .</span><span class="sxs-lookup"><span data-stu-id="073ab-122">Change the namespace to `Microsoft.ServiceModel.Samples`.</span></span>

4. <span data-ttu-id="073ab-123">Agregue referencias a los siguientes ensamblados:</span><span class="sxs-lookup"><span data-stu-id="073ab-123">Add references to the following assemblies:</span></span>

    - <span data-ttu-id="073ab-124">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="073ab-124">System.ServiceModel.dll</span></span>

    - <span data-ttu-id="073ab-125">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="073ab-125">System.ServiceProcess.dll</span></span>

    - <span data-ttu-id="073ab-126">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="073ab-126">System.Configuration.Install.dll</span></span>

5. <span data-ttu-id="073ab-127">Agregue las siguientes instrucciones Using a Service.cs.</span><span class="sxs-lookup"><span data-stu-id="073ab-127">Add the following using statements to Service.cs.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. <span data-ttu-id="073ab-128">Defina el contrato de servicio `ICalculator`, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="073ab-128">Define the `ICalculator` service contract as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. <span data-ttu-id="073ab-129">Implemente el contrato de servicio en una clase denominada `CalculatorService`, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="073ab-129">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. <span data-ttu-id="073ab-130">Cree una nueva clase denominada `CalculatorWindowsService` que herede de la clase <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="073ab-130">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="073ab-131">Agregue una variable local denominada `serviceHost` para hacer referencia a la instancia de <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="073ab-131">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="073ab-132">Defina el método `Main` que llama a `ServiceBase.Run(new CalculatorWindowsService)`.</span><span class="sxs-lookup"><span data-stu-id="073ab-132">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. <span data-ttu-id="073ab-133">Invalide el método <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> creando y abriendo una nueva instancia de <xref:System.ServiceModel.ServiceHost>, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="073ab-133">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. <span data-ttu-id="073ab-134">Invalide el método <xref:System.ServiceProcess.ServiceBase.OnStop%2A> cerrando <xref:System.ServiceModel.ServiceHost>, tal como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="073ab-134">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. <span data-ttu-id="073ab-135">Cree una nueva clase denominada `ProjectInstaller` que herede de <xref:System.Configuration.Install.Installer> y que esté marcada con el <xref:System.ComponentModel.RunInstallerAttribute> establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="073ab-135">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="073ab-136">Esto permite a la herramienta Installutil.exe instalar el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="073ab-136">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. <span data-ttu-id="073ab-137">Quite la clase `Service` generada al crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="073ab-137">Remove the `Service` class that was generated when you created the project.</span></span>

13. <span data-ttu-id="073ab-138">Agregue un archivo de configuración de aplicación al proyecto.</span><span class="sxs-lookup"><span data-stu-id="073ab-138">Add an application configuration file to the project.</span></span> <span data-ttu-id="073ab-139">Reemplace el contenido del archivo por el XML de configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="073ab-139">Replace the contents of the file with the following configuration XML.</span></span>

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

     <span data-ttu-id="073ab-140">Haga clic con el botón derecho en el archivo App.config en el **Explorador de soluciones** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="073ab-140">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="073ab-141">En **Copiar en el directorio de salida** , seleccione **copiar si es posterior**.</span><span class="sxs-lookup"><span data-stu-id="073ab-141">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>

     <span data-ttu-id="073ab-142">Este ejemplo especifica puntos de conexión explícitamente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="073ab-142">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="073ab-143">Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="073ab-143">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="073ab-144">En este ejemplo, dado que el servicio tiene un <xref:System.ServiceModel.Description.ServiceMetadataBehavior> establecido en `true`, el servicio también tiene habilitada la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="073ab-144">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="073ab-145">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="073ab-145">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>

## <a name="install-and-run-the-service"></a><span data-ttu-id="073ab-146">Instale y ejecute el servicio.</span><span class="sxs-lookup"><span data-stu-id="073ab-146">Install and run the service</span></span>

1. <span data-ttu-id="073ab-147">Compile la solución para crear el ejecutable `Service.exe`.</span><span class="sxs-lookup"><span data-stu-id="073ab-147">Build the solution to create the `Service.exe` executable.</span></span>

2. <span data-ttu-id="073ab-148">Abra Símbolo del sistema para desarrolladores para Visual Studio y navegue hasta el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="073ab-148">Open Developer Command Prompt for Visual Studio and navigate to the project directory.</span></span> <span data-ttu-id="073ab-149">Escriba `installutil bin\service.exe` en el símbolo del sistema para instalar el servicio de Windows.</span><span class="sxs-lookup"><span data-stu-id="073ab-149">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>

     <span data-ttu-id="073ab-150">Escriba `services.msc` en el símbolo del sistema para tener acceso al Administrador de control de servicios (SCM).</span><span class="sxs-lookup"><span data-stu-id="073ab-150">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="073ab-151">El servicio de Windows debería aparecer en Servicios como "WCFWindowsServiceSample".</span><span class="sxs-lookup"><span data-stu-id="073ab-151">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="073ab-152">El servicio WCF solo puede responder a los clientes si el servicio de Windows se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="073ab-152">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="073ab-153">Para iniciar el servicio, haga clic con el botón secundario en el SCM y seleccione "iniciar" o escriba **net start WCFWindowsServiceSample** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="073ab-153">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>

3. <span data-ttu-id="073ab-154">Si realiza cambios en el servicio, debe detenerlo primero y desinstalarlo.</span><span class="sxs-lookup"><span data-stu-id="073ab-154">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="073ab-155">Para detener el servicio, haga clic con el botón secundario en el SCM y seleccione "STOP" o **escriba net stop WCFWindowsServiceSample** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="073ab-155">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="073ab-156">Tenga en cuenta que si detiene el servicio de Windows y, a continuación, ejecuta un cliente, se produce una excepción <xref:System.ServiceModel.EndpointNotFoundException> cuando un cliente intenta tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="073ab-156">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="073ab-157">Para desinstalar el tipo de servicio de Windows **InstallUtil/u bin\service.exe** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="073ab-157">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>

## <a name="example"></a><span data-ttu-id="073ab-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="073ab-158">Example</span></span>

<span data-ttu-id="073ab-159">A continuación se muestra una lista completa del código que se usa en este tema:</span><span class="sxs-lookup"><span data-stu-id="073ab-159">The following is a complete listing of the code used by this topic:</span></span>

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

<span data-ttu-id="073ab-160">Como la opción de "autohospedaje", el entorno de hospedaje de servicio de Windows requiere que algún código de hospedaje se escriba como parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="073ab-160">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="073ab-161">El servicio se implementa como una aplicación de consola y contiene su propio código de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="073ab-161">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="073ab-162">En otros entornos de hospedaje, como el del Servicio de activación de procesos de Windows (WAS) en Internet Information Services (IIS), no es necesario que los programadores escriban código de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="073ab-162">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>

## <a name="see-also"></a><span data-ttu-id="073ab-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="073ab-163">See also</span></span>

- [<span data-ttu-id="073ab-164">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="073ab-164">Simplified Configuration</span></span>](../simplified-configuration.md)
- [<span data-ttu-id="073ab-165">Hospedaje en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="073ab-165">Hosting in a Managed Application</span></span>](hosting-in-a-managed-application.md)
- [<span data-ttu-id="073ab-166">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="073ab-166">Hosting Services</span></span>](../hosting-services.md)
- <span data-ttu-id="073ab-167">[Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="073ab-167">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
