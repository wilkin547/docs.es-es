---
title: "Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
caps.latest.revision: 11
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 11
---
# Elemento &lt;security&gt; de &lt;netNamedPipeBinding&gt;
Define la configuración de seguridad de un enlace.  
  
## Sintaxis  
  
```  
  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|modo|Especifica el tipo de seguridad que se aplica a este enlace.  Los valores válidos son los siguientes:<br /><br /> -   Ninguno: esto deshabilita la seguridad.<br />-   Transport: La seguridad se proporciona utilizando seguridad basada en el transporte subyacente.  Es posible controlar el nivel de protección con este modo.<br />-   El valor predeterminado es Transport.  Este atributo es del tipo <xref:System.ServiceModel.NetNamedPipeSecurityMode>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|transporte|Define la configuración de seguridad para el transporte.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|enlace|El elemento de enlace del [\<netNamedPipeBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.NetNamedPipeSecurity>   
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Selección de tipos de credenciales](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)