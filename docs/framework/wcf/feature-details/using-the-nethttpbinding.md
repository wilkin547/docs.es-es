---
title: Usar NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 85a81c353e779800a9aa371658f2f799365b759d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282033"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="f8753-102">Usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f8753-102">Using the NetHttpBinding</span></span>

<span data-ttu-id="f8753-103"><xref:System.ServiceModel.NetHttpBinding> es un enlace diseñado para consumir servicios HTTP o WebSocket y usa la codificación binaria de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f8753-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="f8753-104"><xref:System.ServiceModel.NetHttpBinding> detectará si se usa con un contrato de solicitud-respuesta o dúplex y cambiará su comportamiento para que coincida; usará HTTP para los contratos de solicitud-respuesta y WebSockets para los contratos dúplex.</span><span class="sxs-lookup"><span data-stu-id="f8753-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="f8753-105">Este comportamiento puede invalidarse mediante la configuración <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:</span><span class="sxs-lookup"><span data-stu-id="f8753-105">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <span data-ttu-id="f8753-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> : Fuerza el uso de WebSockets incluso para los contratos de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="f8753-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <span data-ttu-id="f8753-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> : Esto impide que se usen WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f8753-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> - This prevents WebSockets from being used.</span></span> <span data-ttu-id="f8753-108">Si se intenta usar un contrato dúplex con este valor se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="f8753-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <span data-ttu-id="f8753-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> : Este es el valor predeterminado y se comporta como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f8753-109"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="f8753-110"><xref:System.ServiceModel.NetHttpBinding> admite sesiones confiables en modo HTTP y en modo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="f8753-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="f8753-111">En el modo WebSocket, el transporte proporciona las sesiones.</span><span class="sxs-lookup"><span data-stu-id="f8753-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="f8753-112">Cuando se usa <xref:System.ServiceModel.NetHttpBinding> y TransferMode de enlace está establecido en TransferMode.Streamed, las grandes transmisiones pueden provocar un bloqueo interno y la llamada expirará.</span><span class="sxs-lookup"><span data-stu-id="f8753-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="f8753-113">Para solucionar este problema envíe mensajes de menor tamaño o use TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="f8753-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="f8753-114">Configurar un servicio para usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f8753-114">Configuring a Service to use NetHttpBinding</span></span>  

 <span data-ttu-id="f8753-115"><xref:System.ServiceModel.NetHttpBinding> se puede configurar igual que cualquier otro enlace.</span><span class="sxs-lookup"><span data-stu-id="f8753-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="f8753-116">El siguiente fragmento de código de configuración muestra cómo configurar un servicio WCF con <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="f8753-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
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
  
 <span data-ttu-id="f8753-117">El fragmento de código siguiente muestra cómo agregar <xref:System.ServiceModel.NetHttpBinding> en el código.</span><span class="sxs-lookup"><span data-stu-id="f8753-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8753-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8753-118">See also</span></span>

- [<span data-ttu-id="f8753-119">Configuración de enlaces para los servicios</span><span class="sxs-lookup"><span data-stu-id="f8753-119">Configuring Bindings for Services</span></span>](../configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="f8753-120">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f8753-120">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="f8753-121">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="f8753-121">System-Provided Bindings</span></span>](../system-provided-bindings.md)
- [<span data-ttu-id="f8753-122">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="f8753-122">Duplex Services</span></span>](duplex-services.md)
