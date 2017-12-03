---
title: "Configuración de un cliente básico de Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c9ee75734349210ac9379aaf30523a98c4a14f94
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Configuración de un cliente básico de Windows Communication Foundation
Es la quinta de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.  
  
 Este archivo de configuración de cliente que se ha generado mediante la funcionalidad Agregar referencia de servicio de disuccess de tema [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] o [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La configuración del cliente consiste en especificar el punto de conexión que utiliza el cliente para obtener acceso al servicio. Un extremo tiene una dirección, un enlace y un contrato y cada uno de estos elementos debe especificarse en el proceso de configuración del cliente.  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a>Configuración de un cliente de Windows Communication Foundation  
  
1.  Abra el archivo de configuración generado (App.config) del proyecto GettingStartedClient. El siguiente ejemplo es una vista del archivo de configuración generado. En el [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, busque la [ \<extremo >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     Este ejemplo configura el punto de conexión que usa el cliente para tener acceso al servicio que se ubica en la siguiente dirección: http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
  
     El elemento de extremo especifica que el contrato de servicio de `ServiceReference1.ICalculator` se usa para la comunicación entre el cliente y el servicio de WCF. Se configura el canal WCF con los proporcionados por el sistema <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>. Este contrato se generó mediante Agregar referencia de servicio en Visual Studio. Es básicamente una copia del contrato que se definió en el proyecto GettingStartedLib. El <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> enlace especifica HTTP como el transporte, seguridad interoperable y otros detalles de configuración.  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]cómo usar el cliente generado con esta configuración, consulte [Cómo: usar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Autohospedaje](../../../docs/framework/wcf/samples/self-host.md)
