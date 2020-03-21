---
title: Usar NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 82222dbfa3f35ed00d0173f2bc927c32e9e98470
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184230"
---
# <a name="using-the-nethttpbinding"></a>Usar NetHttpBinding
<xref:System.ServiceModel.NetHttpBinding> es un enlace diseñado para consumir servicios HTTP o WebSocket y usa la codificación binaria de forma predeterminada. <xref:System.ServiceModel.NetHttpBinding> detectará si se usa con un contrato de solicitud-respuesta o dúplex y cambiará su comportamiento para que coincida; usará HTTP para los contratos de solicitud-respuesta y WebSockets para los contratos dúplex. Este comportamiento puede invalidarse mediante la configuración <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always>- Esto obliga a que WebSockets se utilice incluso para contratos de solicitud-respuesta.  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never>- Esto evita que se utilicen WebSockets. Si se intenta usar un contrato dúplex con este valor se producirá una excepción.  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex>- Este es el valor predeterminado y se comporta como se describió anteriormente.  
  
 <xref:System.ServiceModel.NetHttpBinding> admite sesiones confiables en modo HTTP y en modo WebSocket. En el modo WebSocket, el transporte proporciona las sesiones.  
  
> [!WARNING]
> Cuando se usa <xref:System.ServiceModel.NetHttpBinding> y TransferMode de enlace está establecido en TransferMode.Streamed, las grandes transmisiones pueden provocar un bloqueo interno y la llamada expirará. Para solucionar este problema envíe mensajes de menor tamaño o use TransferMode.Buffered.  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a>Configurar un servicio para usar NetHttpBinding  
 <xref:System.ServiceModel.NetHttpBinding> se puede configurar igual que cualquier otro enlace. El siguiente fragmento de código de configuración muestra cómo configurar un servicio WCF con <xref:System.ServiceModel.NetHttpBinding>.  
  
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
  
 El fragmento de código siguiente muestra cómo agregar <xref:System.ServiceModel.NetHttpBinding> en el código.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);
        }  
```  
  
## <a name="see-also"></a>Consulte también

- [Configurar enlaces para los servicios](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)
- [Enlaces](../../../../docs/framework/wcf/feature-details/bindings.md)
- [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Servicios dúplex](../../../../docs/framework/wcf/feature-details/duplex-services.md)
