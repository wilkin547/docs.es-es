---
title: "&lt;security&gt; de &lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;security&gt; de &lt;webHttpBinding&gt;
Especifica los requisitos de seguridad para un extremo configurado con [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
## Sintaxis  
  
```  
  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|modo|Especifica si un extremo usa la seguridad a nivel de transporte o no usa ninguna.  De manera predeterminada, es `None`.  Este atributo es del tipo <xref:System.ServiceModel.WebHttpSecurityMode>.|  
  
## Atributo de modo  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|La seguridad está deshabilitada.|  
|Transporte|La seguridad se proporciona utilizando HTTPS.  El servicio necesita ser configurado con certificados SSL.  El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.  La autenticación del cliente se controla a través del atributo `ClientCredentialType` de [\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).|  
|TransportCredentialOnly|Este modo no proporciona integridad del mensaje y confidencialidad.  Proporciona la autenticación del cliente basada en HTTP.  Este modo se debe utilizar con precaución.  Se debería utilizar en entornos donde otros recursos \(como IPSec\) están proporcionando la seguridad de transporte y la infraestructura [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] proporciona sólo la autenticación del cliente.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<transporte\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|Define la configuración de seguridad para el transporte.  Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Un elemento de enlace que se usa para configurar extremos para los servicios Web de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que responden a las solicitudes HTTP en lugar de a mensajes SOAP.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>   
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>   
 <xref:System.ServiceModel.WebHttpSecurity>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Selección de tipos de credenciales](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)   
 [Modelo de programación de web HTTP de WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)