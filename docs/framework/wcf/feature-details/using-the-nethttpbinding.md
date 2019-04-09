---
title: Usar NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 5090cfdfeb068acda1e1092e408f3cd747c574c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121022"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="5e3c0-102">Usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="5e3c0-102">Using the NetHttpBinding</span></span>
<xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="5e3c0-103">es un enlace diseñado para consumir servicios HTTP o WebSocket y usa la codificación binaria de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-103">is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="5e3c0-104">detectará si se usa con un contrato de solicitud-respuesta o dúplex y cambiará su comportamiento para que coincida con; usará HTTP para los contratos de solicitud-respuesta y WebSockets para los contratos dúplex.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-104">will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="5e3c0-105">Este comportamiento puede invalidarse mediante la configuración <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:</span><span class="sxs-lookup"><span data-stu-id="5e3c0-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> <span data-ttu-id="5e3c0-106">-Esto fuerza WebSockets incluso para los contratos de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-106">- This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> <span data-ttu-id="5e3c0-107">-Esto impide que se utilice WebSockets.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-107">- This prevents WebSockets from being used.</span></span> <span data-ttu-id="5e3c0-108">Si se intenta usar un contrato dúplex con este valor se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> <span data-ttu-id="5e3c0-109">-Éste es el valor predeterminado y se comporta como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-109">- This is the default value and behaves as described above.</span></span>  
  
 <xref:System.ServiceModel.NetHttpBinding> <span data-ttu-id="5e3c0-110">admite sesiones confiables en modo HTTP y el modo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-110">supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="5e3c0-111">En el modo WebSocket, el transporte proporciona las sesiones.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5e3c0-112">Cuando se usa <xref:System.ServiceModel.NetHttpBinding> y TransferMode de enlace está establecido en TransferMode.Streamed, las grandes transmisiones pueden provocar un bloqueo interno y la llamada expirará.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="5e3c0-113">Para solucionar este problema envíe mensajes de menor tamaño o use TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="5e3c0-114">Configurar un servicio para usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="5e3c0-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="5e3c0-115"><xref:System.ServiceModel.NetHttpBinding> se puede configurar igual que cualquier otro enlace.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="5e3c0-116">El siguiente fragmento de código de configuración muestra cómo configurar un servicio WCF con <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 <span data-ttu-id="5e3c0-117">El fragmento de código siguiente muestra cómo agregar <xref:System.ServiceModel.NetHttpBinding> en el código.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e3c0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e3c0-118">See also</span></span>

- [<span data-ttu-id="5e3c0-119">Configuración de enlaces para los servicios</span><span class="sxs-lookup"><span data-stu-id="5e3c0-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="5e3c0-120">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5e3c0-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)
- [<span data-ttu-id="5e3c0-121">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="5e3c0-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="5e3c0-122">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="5e3c0-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
