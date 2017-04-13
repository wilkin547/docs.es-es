---
title: "Configuraci&#243;n de los comportamientos del cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Configuraci&#243;n de los comportamientos del cliente
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] configura los comportamientos de dos maneras: haciendo referencia a las configuraciones de comportamiento \(que se definen en la sección `<behavior>` de un archivo de configuración de la aplicación cliente\) o mediante programación, en la aplicación que realiza la llamada.  En este tema se describen ambos métodos.  
  
 Al usar un archivo de configuración, la configuración del comportamiento es una colección con nombre de valores de configuración.  El nombre de cada configuración de comportamiento debe ser único.  Esta cadena se usa en el atributo `behaviorConfiguration` de una configuración de extremo para vincular el extremo al comportamiento.  
  
## Ejemplo  
 El código de configuración siguiente define un comportamiento llamado `myBehavior`.  El extremo de cliente hace referencia a este comportamiento en el atributo `behaviorConfiguration`.  
  
```  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## Uso de comportamientos mediante programación  
 También puede configurar o insertar los comportamientos mediante programación buscando la propiedad `Behaviors` adecuada en el objeto de cliente [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] o en el objeto de generador de canal de cliente antes de abrir el cliente.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo insertar un comportamiento mediante programación teniendo acceso a la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> en el <xref:System.ServiceModel.Description.ServiceEndpoint> devuelto por la propiedad <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> antes de la creación del objeto del canal.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## Vea también  
 [\<comportamientos\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)