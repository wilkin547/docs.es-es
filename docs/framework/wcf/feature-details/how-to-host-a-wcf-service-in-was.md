---
title: Procedimiento para hospedar un servicio WCF en WAS
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 8049b7961169c6ec7a8d80fb0e8747e99992247b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555977"
---
# <a name="how-to-host-a-wcf-service-in-was"></a><span data-ttu-id="99254-102">Procedimiento para hospedar un servicio WCF en WAS</span><span class="sxs-lookup"><span data-stu-id="99254-102">How to: Host a WCF Service in WAS</span></span>
<span data-ttu-id="99254-103">En este tema se describen los pasos básicos necesarios para crear un servicio Windows Communication Foundation hospedado de Windows Process Activation Services (también conocido como WAS).</span><span class="sxs-lookup"><span data-stu-id="99254-103">This topic outlines the basic steps required to create a Windows Process Activation Services (also known as WAS) hosted Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="99254-104">WAS es el nuevo servicio de activación de procesos que es una generalización de las características de Internet Information Services (IIS) que funcionan con protocolos de transporte no HTTP.</span><span class="sxs-lookup"><span data-stu-id="99254-104">WAS is the new process activation service that is a generalization of Internet Information Services (IIS) features that work with non-HTTP transport protocols.</span></span> <span data-ttu-id="99254-105">WCF usa la interfaz del adaptador de escucha para comunicar las solicitudes de activación que se reciben a través de los protocolos no HTTP admitidos por WCF, como TCP, canalizaciones con nombre y Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="99254-105">WCF uses the listener adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, named pipes, and Message Queuing.</span></span>  
  
 <span data-ttu-id="99254-106">Esta opción de hospedaje necesita que los componentes de activación WAS se instalen y configuren correctamente, pero no necesita que se escriba ningún código de hospedaje como parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="99254-106">This hosting option requires that WAS activation components are properly installed and configured, but it does not require any hosting code to be written as part of the application.</span></span> <span data-ttu-id="99254-107">Para obtener más información acerca de cómo instalar y configurar WAS, consulte [Cómo: instalar y configurar los componentes de activación de WCF](how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="99254-107">For more information about installing and configuring WAS, see [How to: Install and Configure WCF Activation Components](how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="99254-108">La activación de WAS no se admite si la canalización de procesamiento de solicitudes del servidor web está establecida en el modo clásico.</span><span class="sxs-lookup"><span data-stu-id="99254-108">WAS activation is not supported if the web server’s request processing pipeline is set to Classic mode.</span></span> <span data-ttu-id="99254-109">La canalización de procesamiento de solicitudes del servidor web debe estar establecida en el modo integrado si debe usarse la activación de WAS.</span><span class="sxs-lookup"><span data-stu-id="99254-109">The web server’s request processing pipeline must be set to Integrated mode if WAS activation is to be used.</span></span>  
  
 <span data-ttu-id="99254-110">Cuando un servicio WCF se hospeda en WAS, se usan los enlaces estándar de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="99254-110">When a WCF service is hosted in WAS, the standard bindings are used in the usual way.</span></span> <span data-ttu-id="99254-111">Sin embargo, al utilizar <xref:System.ServiceModel.NetTcpBinding> y <xref:System.ServiceModel.NetNamedPipeBinding> para configurar un servicio hospedado en WAS, se debe satisfacer una restricción.</span><span class="sxs-lookup"><span data-stu-id="99254-111">However, when using the <xref:System.ServiceModel.NetTcpBinding> and the <xref:System.ServiceModel.NetNamedPipeBinding> to configure a WAS-hosted service, a constraint must be satisfied.</span></span> <span data-ttu-id="99254-112">Cuando extremos diferentes utilizan el mismo transporte, las configuraciones del enlace tienen que coincidir en las siete propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="99254-112">When different endpoints use the same transport, the binding settings have to match on the following seven properties:</span></span>  
  
- <span data-ttu-id="99254-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="99254-113">ConnectionBufferSize</span></span>  
  
- <span data-ttu-id="99254-114">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="99254-114">ChannelInitializationTimeout</span></span>  
  
- <span data-ttu-id="99254-115">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="99254-115">MaxPendingConnections</span></span>  
  
- <span data-ttu-id="99254-116">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="99254-116">MaxOutputDelay</span></span>  
  
- <span data-ttu-id="99254-117">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="99254-117">MaxPendingAccepts</span></span>  
  
- <span data-ttu-id="99254-118">ConnectionPoolSettings.IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="99254-118">ConnectionPoolSettings.IdleTimeout</span></span>  
  
- <span data-ttu-id="99254-119">ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="99254-119">ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint</span></span>  
  
 <span data-ttu-id="99254-120">De lo contrario, el extremo que se inicializa primero siempre determina los valores de estas propiedades y los extremos agregados después producen una <xref:System.ServiceModel.ServiceActivationException> si no coinciden con esos valores.</span><span class="sxs-lookup"><span data-stu-id="99254-120">Otherwise, the endpoint that is initialized first always determines the values of these properties, and endpoints added later throw a <xref:System.ServiceModel.ServiceActivationException> if they do not match those settings.</span></span>  
  
 <span data-ttu-id="99254-121">Para la copia de origen de este ejemplo, consulte [activación de TCP](../samples/tcp-activation.md).</span><span class="sxs-lookup"><span data-stu-id="99254-121">For the source copy of this example, see [TCP Activation](../samples/tcp-activation.md).</span></span>  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a><span data-ttu-id="99254-122">Creación de un servicio básico hospedado por WAS</span><span class="sxs-lookup"><span data-stu-id="99254-122">To create a basic service hosted by WAS</span></span>  
  
1. <span data-ttu-id="99254-123">Defina un contrato de servicios para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="99254-123">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2. <span data-ttu-id="99254-124">Implemente el contrato de servicios en una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="99254-124">Implement the service contract in a service class.</span></span> <span data-ttu-id="99254-125">Observe que la información de enlace o dirección no se especifica en ninguna parte de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="99254-125">Note that address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="99254-126">Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="99254-126">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3. <span data-ttu-id="99254-127">Cree un archivo Web.config para definir el enlace <xref:System.ServiceModel.NetTcpBinding> que van a usar los extremos `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="99254-127">Create a Web.config file to define the <xref:System.ServiceModel.NetTcpBinding> binding to be used by the `CalculatorService` endpoints.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <bindings>  
          <netTcpBinding>  
            <binding portSharingEnabled="true">  
              <security mode="None" />  
            </binding>  
          </netTcpBinding>  
        </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="99254-128">Cree un archivo Service.svc que contenga el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="99254-128">Create a Service.svc file that contains the following code.</span></span>  
  
   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```
  
5. <span data-ttu-id="99254-129">Coloque el archivo Service.svc en su directorio virtual de IIS.</span><span class="sxs-lookup"><span data-stu-id="99254-129">Place the Service.svc file in your IIS virtual directory.</span></span>  
  
### <a name="to-create-a-client-to-use-the-service"></a><span data-ttu-id="99254-130">Creación de un cliente para que utilice el servicio</span><span class="sxs-lookup"><span data-stu-id="99254-130">To create a client to use the service</span></span>  
  
1. <span data-ttu-id="99254-131">Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="99254-131">Use [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>  
  
    ```console
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="99254-132">El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.</span><span class="sxs-lookup"><span data-stu-id="99254-132">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3. <span data-ttu-id="99254-133">La aplicación de cliente generada también contiene la implementación de `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="99254-133">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="99254-134">Observe que la información de enlace y dirección no se especifica en ninguna parte de la implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="99254-134">Note that the address and binding information is not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="99254-135">Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="99254-135">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4. <span data-ttu-id="99254-136">Svcutil.exe también genera la configuración del cliente que utiliza el <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="99254-136">The configuration for the client that uses the <xref:System.ServiceModel.NetTcpBinding> is also generated by Svcutil.exe.</span></span> <span data-ttu-id="99254-137">Este archivo se debería nombrar en el archivo App.config al utilizar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="99254-137">This file should be named in the App.config file when using Visual Studio.</span></span>  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]
  
5. <span data-ttu-id="99254-138">Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="99254-138">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6. <span data-ttu-id="99254-139">Compile y ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="99254-139">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99254-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="99254-140">See also</span></span>

- [<span data-ttu-id="99254-141">Activación de TCP</span><span class="sxs-lookup"><span data-stu-id="99254-141">TCP Activation</span></span>](../samples/tcp-activation.md)
- <span data-ttu-id="99254-142">[Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="99254-142">[Windows Server App Fabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
