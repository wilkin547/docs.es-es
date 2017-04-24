---
title: "Procedimiento para hospedar un servicio WCF en IIS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Procedimiento para hospedar un servicio WCF en IIS
Este tema describe los pasos básicos necesarios para crear un servicio de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que se hospeda en Internet Information Services (IIS). Este tema da por hecho que está familiarizado con IIS y sabe cómo usar la herramienta de administración de IIS para crear y administrar aplicaciones IIS. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]IIS vea [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449) A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio que se ejecuta en el entorno de IIS aprovecha al máximo las características IIS, como el reciclaje de procesos, cierre por inactividad, supervisión de estado de proceso y activación basada en mensajes. Esta opción de hospedaje requiere que se configure correctamente IIS, pero no requiere que se escriba ningún código de hospedaje como parte de la aplicación. Sólo puede utilizar el hospedaje de IIS con un transporte HTTP.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]cómo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interactuar, consulte [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]configuración de seguridad, consulte [seguridad](../../../../docs/framework/wcf/feature-details/security.md).  
  
 Para la copia original de este ejemplo, vea [IIS aloja mediante insertado código](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).  
  
### <a name="to-create-a-service-hosted-by-iis"></a>Para crear un servicio hospedado por IIS  
  
1.  Confirme que IIS está instalado y ejecutándose en su equipo. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Consulte instalación y configuración de IIS [instalación y configuración de IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)  
  
2.  Cree una nueva carpeta para los archivos de la aplicación denominada "IISHostedCalcService", asegúrese de que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] tiene acceso al contenido de la carpeta, y use la herramienta de administración de IIS para crear una nueva aplicación IIS que se ubique físicamente en este directorio de la aplicación. Cuando cree un alias para el directorio de la aplicación, use "IISHostedCalc".  
  
3.  Cree un nuevo archivo denominado "service.svc" en el directorio de la aplicación. Editar este archivo agregando la siguiente @ServiceHost elemento.  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  Cree un subdirectorio App_Code dentro del directorio de la aplicación.  
  
5.  Cree un archivo de código denominado Service.cs en el subdirectorio App_Code.  
  
6.  Agregue las siguientes instrucciones using a la parte superior del archivo Service.cs.  
  
    ```  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  Agregue la declaración de espacio de nombres siguiente después de las instrucciones using.  
  
    ```  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  Defina el contrato de servicio dentro de la declaración de espacio de nombres, tal y como se muestra en el código siguiente.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Implemente el contrato de servicio después de la definición de contrato de servicio, tal como se muestra en el código siguiente.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Cree un archivo denominado "Web.config" en el directorio de la aplicación y agregue el código de configuración siguiente a dicho archivo. En tiempo de ejecución, la infraestructura de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa la información para construir un extremo con el que las aplicaciones cliente se pueden comunicar.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <!-- This section is optional with the default configuration  
            model introduced in .NET Framework 4 -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService">  
  
            <!-- This endpoint is exposed at the base address provided by host:                                        http://localhost/servicemodelsamples/service.svc  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  
            <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
     Este ejemplo especifica extremos explícitamente en el archivo de configuración. Si no agrega ningún punto de conexión al servicio, el tiempo de ejecución agregará los puntos de conexión predeterminados. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]extremos, enlaces y comportamientos predeterminados, vea [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
11. Para asegurarse de que el servicio está hospedado correctamente, abra una instancia de Internet Explorer y vaya a la dirección URL del servicio: `http://localhost/IISHostedCalc/Service.svc`  
  
## <a name="example"></a>Ejemplo  
 A continuación, se muestra el código completo del servicio de calculadora hospedado en IIS.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]  
  
 <!-- TODO: review snippet reference [!code[c_HowTo_HostInIIS#100](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  -->  
  
## <a name="see-also"></a>Vea también  
 [Hospedaje en Internet Information Services](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)   
 [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)   
 [Servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)   
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)   
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)