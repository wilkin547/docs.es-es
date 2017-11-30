---
title: Usar NetHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 56528078895ea7c624afaf716e9a26eabe335d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="a2152-102">Usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a2152-102">Using the NetHttpBinding</span></span>
<span data-ttu-id="a2152-103"><xref:System.ServiceModel.NetHttpBinding> es un enlace diseñado para consumir servicios HTTP o WebSocket y usa la codificación binaria de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a2152-103"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="a2152-104"><xref:System.ServiceModel.NetHttpBinding> detectará si se usa con un contrato de solicitud-respuesta o dúplex y cambiará su comportamiento para que coincida; usará HTTP para los contratos de solicitud-respuesta y WebSockets para los contratos dúplex.</span><span class="sxs-lookup"><span data-stu-id="a2152-104"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="a2152-105">Este comportamiento puede invalidarse mediante el <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` configuración:</span><span class="sxs-lookup"><span data-stu-id="a2152-105">This behavior can be overridden using the <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` setting:</span></span>  
  
1.  <span data-ttu-id="a2152-106">Siempre: obliga a usar WebSockets incluso para los contratos de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="a2152-106">Always - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2.  <span data-ttu-id="a2152-107">Nunca: evita que se use WebSockets.</span><span class="sxs-lookup"><span data-stu-id="a2152-107">Never - This prevents WebSockets from being used.</span></span> <span data-ttu-id="a2152-108">Si se intenta usar un contrato dúplex con este valor se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="a2152-108">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3.  <span data-ttu-id="a2152-109">WhenDuplex: es el valor predeterminado y se comporta como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a2152-109">WhenDuplex - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="a2152-110"><xref:System.ServiceModel.NetHttpBinding> admite sesiones confiables en modo HTTP y en modo WebSocket.</span><span class="sxs-lookup"><span data-stu-id="a2152-110"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="a2152-111">En el modo WebSocket, el transporte proporciona las sesiones.</span><span class="sxs-lookup"><span data-stu-id="a2152-111">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a2152-112">Cuando se usa <xref:System.ServiceModel.NetHttpBinding> y TransferMode de enlace está establecido en TransferMode.Streamed, las grandes transmisiones pueden provocar un bloqueo interno y la llamada expirará.</span><span class="sxs-lookup"><span data-stu-id="a2152-112">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="a2152-113">Para solucionar este problema envíe mensajes de menor tamaño o use TransferMode.Buffered.</span><span class="sxs-lookup"><span data-stu-id="a2152-113">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="a2152-114">Configurar un servicio para usar NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a2152-114">Configuring a Service to use NetHttpBinding</span></span>  
 <span data-ttu-id="a2152-115"><xref:System.ServiceModel.NetHttpBinding> se puede configurar igual que cualquier otro enlace.</span><span class="sxs-lookup"><span data-stu-id="a2152-115">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="a2152-116">El siguiente fragmento de código de configuración muestra cómo configurar un servicio WCF con <xref:System.ServiceModel.NetHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a2152-116">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
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
    <!- ... -->   
  </system.serviceModel>  
```  
  
 <span data-ttu-id="a2152-117">El fragmento de código siguiente muestra cómo agregar <xref:System.ServiceModel.NetHttpBinding> en el código.</span><span class="sxs-lookup"><span data-stu-id="a2152-117">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2152-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2152-118">See Also</span></span>  
 [<span data-ttu-id="a2152-119">Configuración de enlaces para los servicios</span><span class="sxs-lookup"><span data-stu-id="a2152-119">Configuring Bindings for Services</span></span>](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [<span data-ttu-id="a2152-120">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a2152-120">Bindings</span></span>](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [<span data-ttu-id="a2152-121">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a2152-121">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="a2152-122">Servicios dúplex</span><span class="sxs-lookup"><span data-stu-id="a2152-122">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
