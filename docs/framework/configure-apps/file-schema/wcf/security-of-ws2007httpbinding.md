---
title: "&lt;security&gt; de &lt;ws2007HttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;security&gt; de &lt;ws2007HttpBinding&gt;
Representa la configuración de seguridad utilizada con el elemento [\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`mode`|-   Opcional.  Especifica el tipo de seguridad que se aplica.  De manera predeterminada, es `Message`.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.|  
  
## Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Transport`|La seguridad se proporciona utilizando HTTPS.  El servicio se debe configurar con certificados de Capa de sockets seguros \(SSL\).  El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.  La autenticación del cliente se controla a través del atributo `ClientCredentials` del elemento [\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md).|  
|`Message`|La seguridad se proporciona mediante la seguridad del mensaje SOAP.  De forma predeterminada, el cuerpo SOAP se cifra y firma.  Este modo ofrece diversas características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se van a usar y qué nivel de protección se aplica al cuerpo del mensaje a través de <xref:System.ServiceModel.Security.SecurityMessageProperty>.  Se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.|  
|`TransportWithMessageCredential`|En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.  De manera predeterminada, se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|Define la configuración de seguridad para el transporte.  Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.  Esta configuración se aplica sólo cuando el modo se establece en Transporte.|  
|[\<message\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|Define la configuración de seguridad del mensaje.  Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.  Esta configuración no se aplica cuando el modo se establece en Transporte.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Un enlace seguro para las aplicaciones de transporte HTTP.|  
  
## Comentarios  
 Este elemento está diseñado para la interoperación con servicios que implementan las especificaciones de WS\-\*.  La seguridad de transporte para este enlace es Capa de sockets seguros \(SSL\) sobre HTTP o HTTPS.  
  
## Vea también  
 <xref:System.ServiceModel.WSHttpSecurity>   
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 <xref:System.ServiceModel.BasicHttpSecurity>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)