---
title: "Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Elemento &lt;transport&gt; de &lt;netNamedPipeBinding&gt;
Define los valores de seguridad de transporte para una canalización con nombre.  
  
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
|protectionLevel|Define el nivel de protección de la canalización con nombre.  Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.  El cifrado proporciona privacidad de nivel de datos durante el transporte.  Los valores válidos son los siguientes:<br /><br /> -   None: sin protección.<br />-   Sign: se firman los mensajes.<br />-   EncryptAndSign: Los mensajes se cifran y firman.<br /><br /> El valor predeterminado es EncryptAndSign.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|Define la configuración de seguridad de un enlace.|  
  
## Vea también  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>   
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)