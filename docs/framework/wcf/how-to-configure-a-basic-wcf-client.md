---
title: "Configuraci&#243;n de un cliente b&#225;sico de Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "clientes de WCF [WCF], configurar"
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# Configuraci&#243;n de un cliente b&#225;sico de Windows Communication Foundation
Es la quinta de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 Este tema explica el archivo de configuración del cliente generado mediante la funcionalidad de Agregar referencia de servicio de [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] o la [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  La configuración del cliente consiste en especificar el extremo que utiliza el cliente para obtener acceso al servicio.  Un extremo tiene una dirección, un enlace y un contrato y cada uno de estos elementos debe especificarse en el proceso de configuración del cliente.  
  
### Configuración de un cliente de Windows Communication Foundation  
  
1.  Abra el archivo de configuración generado \(App.config\) del proyecto GettingStartedClient.  El siguiente ejemplo es una vista del archivo de configuración generado.  Bajo la sección [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md), busque el elemento [\<endpoint\>](http://msdn.microsoft.com/es-es/13aa23b7-2f08-4add-8dbf-a99f8127c017).  
  
    ```  
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
    </configuration><?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
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
  
     Este ejemplo configura el extremo que usa el cliente para tener acceso al servicio que se ubica en la siguiente dirección: http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService  
  
     El elemento de extremo especifica que el contrato de servicio de `ServiceReference1.ICalculator` se usa para la comunicación entre el cliente y el servicio de WCF.  El canal de WCF se configura con el <xref:System.ServiceModel.WsHttpBinding> proporcionado por el sistema.  Este contrato se generó mediante Agregar referencia de servicio en Visual Studio.  Es básicamente una copia del contrato que se definió en el proyecto GettingStartedLib.  El enlace <xref:System.ServiceModel.WsHttpBinding> especifica HTTP como el transporte, la seguridad interoperable y otros detalles de configuración.  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] uso del cliente generado con esta configuración, vea [Cómo utilizar un cliente](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## Vea también  
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Introducción:](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Autohospedaje](../../../docs/framework/wcf/samples/self-host.md)