---
description: Más información acerca de la activación de UDP
title: Activación UDP
ms.date: 03/30/2017
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
ms.openlocfilehash: 8ee5e6363265ddc74d27884ef40354108da17581
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798230"
---
# <a name="udp-activation"></a><span data-ttu-id="e064d-103">Activación UDP</span><span class="sxs-lookup"><span data-stu-id="e064d-103">UDP Activation</span></span>

<span data-ttu-id="e064d-104">Este ejemplo se basa en el ejemplo [Transport: UDP](transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="e064d-104">This sample is based on the [Transport: UDP](transport-udp.md) sample.</span></span> <span data-ttu-id="e064d-105">Extiende el ejemplo [Transport: UDP](transport-udp.md) para admitir la activación de procesos mediante el servicio de activación de procesos de Windows (was).</span><span class="sxs-lookup"><span data-stu-id="e064d-105">It extends the [Transport: UDP](transport-udp.md) sample to support process activation using the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="e064d-106">El ejemplo está compuesto de tres partes principales:</span><span class="sxs-lookup"><span data-stu-id="e064d-106">The sample consists of three major pieces:</span></span>  
  
- <span data-ttu-id="e064d-107">Un activador del protocolo UDP, un proceso independiente que recibe los mensajes de UDP en nombre de las aplicaciones que se van a activar.</span><span class="sxs-lookup"><span data-stu-id="e064d-107">A UDP Protocol Activator, a standalone process that receives UDP messages on behalf of applications that are to be activated.</span></span>  
  
- <span data-ttu-id="e064d-108">Un cliente que utiliza el transporte personalizado de UDP para enviar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="e064d-108">A client that uses the UDP custom transport to send messages.</span></span>  
  
- <span data-ttu-id="e064d-109">Un servicio (hospedado en un proceso de trabajo activado por WAS) que recibe los mensajes sobre el transporte personalizado de UDP.</span><span class="sxs-lookup"><span data-stu-id="e064d-109">A service (hosted in a worker process activated by WAS) that receives messages over the UDP custom transport.</span></span>  
  
## <a name="udp-protocol-activator"></a><span data-ttu-id="e064d-110">Activador del protocolo UDP</span><span class="sxs-lookup"><span data-stu-id="e064d-110">UDP Protocol Activator</span></span>  

 <span data-ttu-id="e064d-111">El activador del protocolo UDP es un puente entre el cliente WCF y el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e064d-111">The UDP Protocol Activator is a bridge between the WCF client and the WCF service.</span></span> <span data-ttu-id="e064d-112">Proporciona la comunicación de datos a través del protocolo UDP en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="e064d-112">It provides data communication through the UDP protocol at the transport layer.</span></span> <span data-ttu-id="e064d-113">Tiene dos funciones principales:</span><span class="sxs-lookup"><span data-stu-id="e064d-113">It has two major functions:</span></span>  
  
- <span data-ttu-id="e064d-114">El Adaptador del agente de escucha (LA) de WAS, que colabora con WAS para activar los procesos como respuesta a los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e064d-114">WAS Listener Adapter (LA), which collaborates with WAS to activate processes in response to incoming messages.</span></span>  
  
- <span data-ttu-id="e064d-115">El Agente de escucha del protocolo UDP, que acepta los mensajes de UDP en nombre de las aplicaciones que se van a activar.</span><span class="sxs-lookup"><span data-stu-id="e064d-115">UDP Protocol Listener, which accepts UDP messages on behalf of applications that are to be activated.</span></span>  
  
 <span data-ttu-id="e064d-116">El activador se debe estar ejecutando como un programa independiente en el equipo del servidor.</span><span class="sxs-lookup"><span data-stu-id="e064d-116">The activator must be running as a standalone program on the server machine.</span></span> <span data-ttu-id="e064d-117">Normalmente, los adaptadores del agente de escucha de WAS (como NetTcpActivator y NetPipeActivator) se implementan en servicios de Windows de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="e064d-117">Normally, WAS listener adapters (such as the NetTcpActivator and the NetPipeActivator) are implemented in long-running Windows services.</span></span> <span data-ttu-id="e064d-118">Sin embargo, por motivos de simplicidad y claridad, este ejemplo implementa el activador de protocolo como una aplicación independiente.</span><span class="sxs-lookup"><span data-stu-id="e064d-118">However, for simplicity and clarity, this sample implements the protocol activator as a standalone application.</span></span>  
  
### <a name="was-listener-adapter"></a><span data-ttu-id="e064d-119">Adaptador del agente de escucha de WAS</span><span class="sxs-lookup"><span data-stu-id="e064d-119">WAS Listener Adapter</span></span>  

 <span data-ttu-id="e064d-120">El Adaptador del agente de escucha de WAS para UDP se implementa en la clase `UdpListenerAdapter`.</span><span class="sxs-lookup"><span data-stu-id="e064d-120">The WAS Listener Adapter for UDP is implemented in the `UdpListenerAdapter` class.</span></span> <span data-ttu-id="e064d-121">Es el módulo que interactúa con WAS para realizar la activación de la aplicación para el protocolo UDP.</span><span class="sxs-lookup"><span data-stu-id="e064d-121">It is the module that interacts with WAS to perform application activation for the UDP protocol.</span></span> <span data-ttu-id="e064d-122">Esto se logra llamando a las API de Webhost siguientes:</span><span class="sxs-lookup"><span data-stu-id="e064d-122">This is achieved by calling the following Webhost APIs:</span></span>  
  
- `WebhostRegisterProtocol`  
  
- `WebhostUnregisterProtocol`  
  
- `WebhostOpenListenerChannelInstance`  
  
- `WebhostCloseAllListenerChannelInstances`  
  
 <span data-ttu-id="e064d-123">Después de llamar inicialmente a `WebhostRegisterProtocol`, el adaptador del agente de escucha recibe `ApplicationCreated` de la devolución de la llamada desde WAS para todas las aplicaciones registradas en applicationHost.config (situado en %windir%\system32\inetsrv).</span><span class="sxs-lookup"><span data-stu-id="e064d-123">After initially calling `WebhostRegisterProtocol`, the listener adapter receives the callback `ApplicationCreated` from WAS for all of the applications registered in applicationHost.config (located in %windir%\system32\inetsrv).</span></span> <span data-ttu-id="e064d-124">En este ejemplo, administramos solo las aplicaciones con el protocolo UDP (con el id. de protocolo como "net.udp") habilitado.</span><span class="sxs-lookup"><span data-stu-id="e064d-124">In this sample, we only handle the applications with the UDP protocol (with the protocol id as "net.udp") enabled.</span></span> <span data-ttu-id="e064d-125">Otras implementaciones pueden administrar esto de manera diferente si tales implementaciones responden a los cambios de configuración dinámicos en la aplicación (por ejemplo, una transición de la aplicación de deshabilitada a habilitada).</span><span class="sxs-lookup"><span data-stu-id="e064d-125">Other implementations may handle this differently if such implementations respond to dynamic configuration changes to the application (for example, an application transition from disabled to enabled).</span></span>  
  
 <span data-ttu-id="e064d-126">Cuando se recibe `ConfigManagerInitializationCompleted` de devolución de llamada, indica que WAS ha terminado todas las notificaciones para la inicialización del protocolo.</span><span class="sxs-lookup"><span data-stu-id="e064d-126">When the callback `ConfigManagerInitializationCompleted` is received, it indicates that WAS has finished all of the notifications for the initialization of the protocol.</span></span> <span data-ttu-id="e064d-127">En este momento, el adaptador del agente de escucha está listo para procesar las solicitudes de activación del proceso.</span><span class="sxs-lookup"><span data-stu-id="e064d-127">At this time, the listener adapter is ready to process activation requests.</span></span>  
  
 <span data-ttu-id="e064d-128">Cuando una nueva solicitud entra por primera vez para una aplicación, el adaptador del agente de escucha llama a `WebhostOpenListenerChannelInstance` en WAS, lo que inicia el proceso de trabajo si no se ha iniciado aún.</span><span class="sxs-lookup"><span data-stu-id="e064d-128">When a new request comes in the first time for an application, the listener adapter calls `WebhostOpenListenerChannelInstance` into WAS, which starts the worker process if it is not started yet.</span></span> <span data-ttu-id="e064d-129">A continuación, se cargan los controladores de protocolo y se puede iniciar la comunicación entre el adaptador del agente de escucha y la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="e064d-129">Then the protocol handlers are loaded and the communication between the listener adapter and the virtual application can start.</span></span>  
  
 <span data-ttu-id="e064d-130">El adaptador del agente de escucha se registra en la \System32\inetsrv\ApplicationHost.config% SystemRoot% de la sección <> de la `listenerAdapters` siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e064d-130">The listener adapter is registered in the %SystemRoot%\System32\inetsrv\ApplicationHost.config in the <`listenerAdapters`> section as following:</span></span>  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a><span data-ttu-id="e064d-131">Agente de escucha de protocolo</span><span class="sxs-lookup"><span data-stu-id="e064d-131">Protocol Listener</span></span>  

 <span data-ttu-id="e064d-132">El agente de escucha del protocolo UDP es un módulo dentro del activador de protocolo que realiza escuchas en un extremo de UDP en nombre de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="e064d-132">The UDP protocol listener is a module inside the protocol activator that listens at a UDP endpoint on behalf of the virtual application.</span></span> <span data-ttu-id="e064d-133">Se implementa en la clase `UdpSocketListener`.</span><span class="sxs-lookup"><span data-stu-id="e064d-133">It is implemented in the class `UdpSocketListener`.</span></span> <span data-ttu-id="e064d-134">El punto de conexión se representa como `IPEndpoint` para lo que el número de puerto se extrae del enlace del protocolo para el sitio.</span><span class="sxs-lookup"><span data-stu-id="e064d-134">The endpoint is represented as `IPEndpoint` for which the port number is extracted from the binding of the protocol for the site.</span></span>  
  
### <a name="control-service"></a><span data-ttu-id="e064d-135">Servicio de control</span><span class="sxs-lookup"><span data-stu-id="e064d-135">Control Service</span></span>  

 <span data-ttu-id="e064d-136">En este ejemplo, usamos WCF para comunicarse entre el activador y el proceso de trabajo WAS.</span><span class="sxs-lookup"><span data-stu-id="e064d-136">In this sample, we use WCF to communicate between the activator and the WAS worker process.</span></span> <span data-ttu-id="e064d-137">El servicio que reside en el activador se denomina "servicio de control".</span><span class="sxs-lookup"><span data-stu-id="e064d-137">The service that resides in the activator is called the Control Service.</span></span>  
  
## <a name="protocol-handlers"></a><span data-ttu-id="e064d-138">Controladores de protocolo</span><span class="sxs-lookup"><span data-stu-id="e064d-138">Protocol Handlers</span></span>  

 <span data-ttu-id="e064d-139">Después de que el adaptador del agente de escucha llame a `WebhostOpenListenerChannelInstance`, el administrador del proceso de WAS inicia el proceso de trabajo si no comienza.</span><span class="sxs-lookup"><span data-stu-id="e064d-139">After the listener adapter calls `WebhostOpenListenerChannelInstance`, the WAS process manager starts the worker process if it is not started.</span></span> <span data-ttu-id="e064d-140">El administrador de la aplicación dentro del proceso de trabajo carga a continuación el controlador de protocolo de proceso UDP (PPH) con la solicitud para ese `ListenerChannelId`.</span><span class="sxs-lookup"><span data-stu-id="e064d-140">The application manager inside the worker process then loads the UDP Process Protocol Handler (PPH) with the request for that `ListenerChannelId`.</span></span> <span data-ttu-id="e064d-141">PPH a su vez llama a `IAdphManager` .`StartAppDomainProtocolListenerChannel`</span><span class="sxs-lookup"><span data-stu-id="e064d-141">The PPH in turns calls `IAdphManager`.`StartAppDomainProtocolListenerChannel`</span></span> <span data-ttu-id="e064d-142">para iniciar el controlador de protocolo AppDomain de UDP (ADPH).</span><span class="sxs-lookup"><span data-stu-id="e064d-142">to start the UDP AppDomain Protocol Handler (ADPH).</span></span>  
  
## <a name="hostedudptransportconfiguration"></a><span data-ttu-id="e064d-143">HostedUDPTransportConfiguration</span><span class="sxs-lookup"><span data-stu-id="e064d-143">HostedUDPTransportConfiguration</span></span>  

 <span data-ttu-id="e064d-144">La información se registra en Web.config de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e064d-144">The information is registered in the Web.config as follows:</span></span>  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a><span data-ttu-id="e064d-145">Instalación especial para este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e064d-145">Special Setup for This Sample</span></span>  

 <span data-ttu-id="e064d-146">Este ejemplo solo se puede compilar y ejecutar en Windows Vista, Windows Server 2008 o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e064d-146">This sample can be only built and run on Windows Vista, Windows Server 2008, or Windows 7.</span></span> <span data-ttu-id="e064d-147">Para ejecutar el ejemplo, debe tener primero todos los componentes configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="e064d-147">To run the sample, you must first get all of the components set up correctly.</span></span> <span data-ttu-id="e064d-148">Siga estos pasos para instalar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e064d-148">Use the following steps to install the sample.</span></span>  
  
#### <a name="to-set-up-this-sample"></a><span data-ttu-id="e064d-149">Para configurar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="e064d-149">To set up this sample</span></span>  
  
1. <span data-ttu-id="e064d-150">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="e064d-150">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="e064d-151">Compile el proyecto en Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="e064d-151">Build the project on Windows Vista.</span></span> <span data-ttu-id="e064d-152">Después de la compilación, realiza también las operaciones siguientes en la fase posterior a la compilación:</span><span class="sxs-lookup"><span data-stu-id="e064d-152">After compilation, it also performs the following operations in the post-build phase:</span></span>  
  
    - <span data-ttu-id="e064d-153">Instala el enlace de UDP para "Sitio web predeterminado" del sitio.</span><span class="sxs-lookup"><span data-stu-id="e064d-153">Installs the UDP binding to the site "Default Web Site".</span></span>  
  
    - <span data-ttu-id="e064d-154">Crea "ServiceModelSamples" de la aplicación virtual para señalar a la ruta de acceso física: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples."</span><span class="sxs-lookup"><span data-stu-id="e064d-154">Creates the virtual application "ServiceModelSamples" to point to the physical path: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span></span>  
  
    - <span data-ttu-id="e064d-155">También habilita el protocolo "net.udp" para esta aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="e064d-155">It also enables "net.udp" protocol for this virtual application.</span></span>  
  
3. <span data-ttu-id="e064d-156">Inicie "WasNetActivator.exe" de la aplicación de interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="e064d-156">Start the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="e064d-157">Haga clic en la pestaña **configuración** , active las casillas siguientes y, a continuación, haga clic en **instalar** para instalarlas:</span><span class="sxs-lookup"><span data-stu-id="e064d-157">Click the **Setup** tab, check the following check boxes and then click **Install** to install them:</span></span>  
  
    - <span data-ttu-id="e064d-158">Adaptador del agente de escucha de UDP</span><span class="sxs-lookup"><span data-stu-id="e064d-158">UDP Listener Adapter</span></span>  
  
    - <span data-ttu-id="e064d-159">Controladores de protocolo UDP</span><span class="sxs-lookup"><span data-stu-id="e064d-159">UDP Protocol Handlers</span></span>  
  
4. <span data-ttu-id="e064d-160">Haga clic en la pestaña **activación** de la aplicación de interfaz de usuario "WasNetActivator.exe".</span><span class="sxs-lookup"><span data-stu-id="e064d-160">Click the **Activation** tab of the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="e064d-161">Haga clic en el botón **iniciar** para iniciar el adaptador del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="e064d-161">Click the **Start** button to start the listener adapter.</span></span> <span data-ttu-id="e064d-162">Ahora ya está listo para ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="e064d-162">Now you are ready to run the program.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e064d-163">Cuando haya finalizado con este ejemplo, debe ejecutar Cleanup.bat para quitar el enlace net.udp del "Sitio Web predeterminado".</span><span class="sxs-lookup"><span data-stu-id="e064d-163">When you are finished with this sample, you must run Cleanup.bat to remove the net.udp binding from the "Default Web Site".</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="e064d-164">Ejemplo de uso</span><span class="sxs-lookup"><span data-stu-id="e064d-164">Sample Usage</span></span>  

 <span data-ttu-id="e064d-165">Después de la compilación, se han generador cuatro binarios diferentes:</span><span class="sxs-lookup"><span data-stu-id="e064d-165">After compilation, there are four different binaries generated:</span></span>  
  
- <span data-ttu-id="e064d-166">Client.exe: el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="e064d-166">Client.exe: The client code.</span></span> <span data-ttu-id="e064d-167">App.config está compilado en el archivo de configuración del cliente Client.exe.config.</span><span class="sxs-lookup"><span data-stu-id="e064d-167">The App.config is compiled into the client configuration file Client.exe.config.</span></span>  
  
- <span data-ttu-id="e064d-168">UDPActivation.dll: la biblioteca que contiene todas las implementaciones de UDP principales.</span><span class="sxs-lookup"><span data-stu-id="e064d-168">UDPActivation.dll: the library that contains all of the major UDP implementations.</span></span>  
  
- <span data-ttu-id="e064d-169">Service.dll: el código de servicio.</span><span class="sxs-lookup"><span data-stu-id="e064d-169">Service.dll: The service code.</span></span> <span data-ttu-id="e064d-170">Se copia en el directorio \bin de ServiceModelSamples de la aplicación virtual.</span><span class="sxs-lookup"><span data-stu-id="e064d-170">This is copied to the \bin directory of the virtual application ServiceModelSamples.</span></span> <span data-ttu-id="e064d-171">El archivo de servicio es Service. SVC y el archivo de configuración es Web.config. Después de la compilación, se copian en la siguiente ubicación:%SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="e064d-171">The service file is Service.svc and the configuration file is Web.config. After compilation, they are copied to the following location: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span></span>  
  
- <span data-ttu-id="e064d-172">WasNetActivator: el programa activador de UDP.</span><span class="sxs-lookup"><span data-stu-id="e064d-172">WasNetActivator: The UDP activator program.</span></span>  
  
- <span data-ttu-id="e064d-173">Asegúrese de que todas las piezas necesarias se instalan correctamente.</span><span class="sxs-lookup"><span data-stu-id="e064d-173">Ensure that all of the required pieces are installed correctly.</span></span> <span data-ttu-id="e064d-174">Los pasos siguientes muestran cómo ejecutar el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e064d-174">The following steps show how to run the sample:</span></span>  
  
1. <span data-ttu-id="e064d-175">Asegúrese que se hayan iniciado los siguientes servicios de Windows:</span><span class="sxs-lookup"><span data-stu-id="e064d-175">Ensure that the following Windows services have been started:</span></span>  
  
    - <span data-ttu-id="e064d-176">Servicio de activación de procesos de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="e064d-176">Windows Process Activation Service (WAS).</span></span>  
  
    - <span data-ttu-id="e064d-177">Internet Information Services (IIS): W3SVC.</span><span class="sxs-lookup"><span data-stu-id="e064d-177">Internet Information Services (IIS): W3SVC.</span></span>  
  
2. <span data-ttu-id="e064d-178">A continuación, inicie el activador, WasNetActivator.exe.</span><span class="sxs-lookup"><span data-stu-id="e064d-178">Then start the activator, WasNetActivator.exe.</span></span> <span data-ttu-id="e064d-179">En la pestaña **activación** , el único protocolo, **UDP**, está seleccionado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e064d-179">Under the **Activation** tab, the only protocol, **UDP**, is selected in the drop down list.</span></span> <span data-ttu-id="e064d-180">Haga clic en el botón **iniciar** para iniciar el activador.</span><span class="sxs-lookup"><span data-stu-id="e064d-180">Click the **Start** button to start the activator.</span></span>  
  
3. <span data-ttu-id="e064d-181">Una vez iniciado el activador, puede ejecutar el código de cliente ejecutando Client.exe desde una ventana de comandos.</span><span class="sxs-lookup"><span data-stu-id="e064d-181">Once the activator is started, you can run the client code by running Client.exe from a command window.</span></span> <span data-ttu-id="e064d-182">A continuación, se incluye la salida del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e064d-182">The following is the sample output:</span></span>  
  
    ```console  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
> <span data-ttu-id="e064d-183">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e064d-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e064d-184">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e064d-184">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e064d-185">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e064d-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e064d-186">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e064d-186">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
