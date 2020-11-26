---
title: Procedimiento para hospedar un servicio WCF en WAS
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 640cfdd7525fb9877c6f3551a1456fed29c99b8a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244410"
---
# <a name="how-to-host-a-wcf-service-in-was"></a>Procedimiento para hospedar un servicio WCF en WAS

En este tema se describen los pasos básicos necesarios para crear un servicio Windows Communication Foundation hospedado de Windows Process Activation Services (también conocido como WAS). WAS es el nuevo servicio de activación de procesos que es una generalización de las características de Internet Information Services (IIS) que funcionan con protocolos de transporte no HTTP. WCF usa la interfaz del adaptador de escucha para comunicar las solicitudes de activación que se reciben a través de los protocolos no HTTP admitidos por WCF, como TCP, canalizaciones con nombre y Message Queue Server.  
  
 Esta opción de hospedaje necesita que los componentes de activación WAS se instalen y configuren correctamente, pero no necesita que se escriba ningún código de hospedaje como parte de la aplicación. Para obtener más información acerca de cómo instalar y configurar WAS, consulte [Cómo: instalar y configurar los componentes de activación de WCF](how-to-install-and-configure-wcf-activation-components.md).  
  
> [!WARNING]
> La activación de WAS no se admite si la canalización de procesamiento de solicitudes del servidor web está establecida en el modo clásico. La canalización de procesamiento de solicitudes del servidor web debe estar establecida en el modo integrado si debe usarse la activación de WAS.  
  
 Cuando un servicio WCF se hospeda en WAS, se usan los enlaces estándar de la manera habitual. Sin embargo, al utilizar <xref:System.ServiceModel.NetTcpBinding> y <xref:System.ServiceModel.NetNamedPipeBinding> para configurar un servicio hospedado en WAS, se debe satisfacer una restricción. Cuando extremos diferentes utilizan el mismo transporte, las configuraciones del enlace tienen que coincidir en las siete propiedades siguientes:  
  
- ConnectionBufferSize  
  
- ChannelInitializationTimeout  
  
- MaxPendingConnections  
  
- MaxOutputDelay  
  
- MaxPendingAccepts  
  
- ConnectionPoolSettings.IdleTimeout  
  
- ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint  
  
 De lo contrario, el extremo que se inicializa primero siempre determina los valores de estas propiedades y los extremos agregados después producen una <xref:System.ServiceModel.ServiceActivationException> si no coinciden con esos valores.  
  
 Para la copia de origen de este ejemplo, consulte [activación de TCP](../samples/tcp-activation.md).  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a>Creación de un servicio básico hospedado por WAS  
  
1. Defina un contrato de servicios para el tipo de servicio.  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2. Implemente el contrato de servicios en una clase de servicio. Observe que la información de enlace o dirección no se especifica en ninguna parte de la implementación del servicio. Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3. Cree un archivo Web.config para definir el enlace <xref:System.ServiceModel.NetTcpBinding> que van a usar los extremos `CalculatorService`.  
  
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
  
4. Cree un archivo Service.svc que contenga el código siguiente.  
  
   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```
  
5. Coloque el archivo Service.svc en su directorio virtual de IIS.  
  
### <a name="to-create-a-client-to-use-the-service"></a>Creación de un cliente para que utilice el servicio  
  
1. Use la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código a partir de los metadatos del servicio.  
  
    ```console
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3. La aplicación de cliente generada también contiene la implementación de `ClientCalculator`. Observe que la información de enlace y dirección no se especifica en ninguna parte de la implementación del servicio. Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4. Svcutil.exe también genera la configuración del cliente que utiliza el <xref:System.ServiceModel.NetTcpBinding>. Este archivo se debería nombrar en el archivo App.config al utilizar Visual Studio.  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]
  
5. Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6. Compile y ejecute el cliente.  
  
## <a name="see-also"></a>Vea también

- [Activación TCP](../samples/tcp-activation.md)
- [Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))
