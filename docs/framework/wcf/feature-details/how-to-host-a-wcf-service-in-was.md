---
title: "Procedimiento para hospedar un servicio WCF en WAS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Procedimiento para hospedar un servicio WCF en WAS
Este tema describe los pasos básicos requeridos para crear un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] hospedado de Windows Process Activation Services (también conocido como WAS). WAS es el nuevo servicio de activación de procesos que es una generalización de las características de Internet Information Services (IIS) que funcionan con protocolos de transporte no HTTP. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa la interfaz de adaptador de agentes de escucha para comunicar solicitudes de activación que se reciben a través de protocolos no HTTP admitidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], como TCP, canalizaciones con nombre y Message Queuing.  
  
 Esta opción de hospedaje necesita que los componentes de activación WAS se instalen y configuren correctamente, pero no necesita que se escriba ningún código de hospedaje como parte de la aplicación. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]instalación y configuración de WAS, consulte [Cómo: instalar y configurar componentes de activación de WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
> [!WARNING]
>  La activación de WAS no se admite si la canalización de procesamiento de solicitudes del servidor web está establecida en el modo clásico. La canalización de procesamiento de solicitudes del servidor web debe estar establecida en el modo integrado si debe usarse la activación de WAS.  
  
 Cuando un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se hospeda en WAS, los enlaces estándar se utilizan de la manera habitual. Sin embargo, cuando se usa el <xref:System.ServiceModel.NetTcpBinding> y <xref:System.ServiceModel.NetNamedPipeBinding> para configurar un servicio hospedado en WAS, se debe satisfacer una restricción. Cuando puntos de conexión diferentes utilizan el mismo transporte, las configuraciones del enlace tienen que coincidir en las siete propiedades siguientes:  
  
-   ConnectionBufferSize  
  
-   ChannelInitializationTimeout  
  
-   MaxPendingConnections  
  
-   MaxOutputDelay  
  
-   MaxPendingAccepts  
  
-   ConnectionPoolSettings.IdleTimeout  
  
-   ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint  
  
 De lo contrario, el extremo que se inicializa primero siempre determina los valores de estas propiedades y extremos agregados después producen una <xref:System.ServiceModel.ServiceActivationException> si no coinciden con dicha configuración.  
  
 Para la copia original de este ejemplo, vea [activación de TCP](../../../../docs/framework/wcf/samples/tcp-activation.md).  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a>Creación de un servicio básico hospedado por WAS  
  
1.  Defina un contrato de servicios para el tipo de servicio.  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2.  Implemente el contrato de servicios en una clase de servicio. Observe que la información de enlace o dirección no se especifica en ninguna parte de la implementación del servicio. Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3.  Cree un archivo Web.config para definir la <xref:System.ServiceModel.NetTcpBinding> enlace que será utilizado por el `CalculatorService` extremos.  
  
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
  
4.  Cree un archivo Service.svc que contenga el código siguiente.  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Coloque el archivo Service.svc en su directorio virtual de IIS.  
  
### <a name="to-create-a-client-to-use-the-service"></a>Creación de un cliente para que utilice el servicio  
  
1.  Utilice [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) desde la línea de comandos para generar código desde los metadatos del servicio.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  El cliente que se genera contiene la interfaz `ICalculator` que define el contrato de servicios que la implementación del cliente debe cumplir.  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3.  La aplicación de cliente generada también contiene la implementación de `ClientCalculator`. Observe que la información de enlace y dirección no se especifica en ninguna parte de la implementación del servicio. Además, el código tiene que escribirse para recuperar esa información del archivo de configuración.  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4.  La configuración para el cliente que utiliza el <xref:System.ServiceModel.NetTcpBinding> también genera Svcutil.exe. Este archivo se debería nombrar en el archivo App.config al utilizar Visual Studio.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_HostInWAS#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]  -->  
  
5.  Cree una instancia de `ClientCalculator` en una aplicación y, a continuación, llame a las operaciones del servicio.  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6.  Compile y ejecute el cliente.  
  
## <a name="see-also"></a>Vea también  
 [Activación de TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)   
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)