---
title: "&lt;dns&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;dns&gt;
Especifica la identidad esperada del servidor.  Esta identidad es válida para el modo de autenticación de certificado X509 si el certificado del servidor contiene un DNS con el mismo valor.  También es válido para el modo de autenticación de Windows si el SPN tiene el mismo valor.  
  
 Para obtener más información sobre la configuración del valor del elemento, vea [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Sintaxis  
  
```  
  
<dns value = "String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|value|DNS del certificado.  DNS es un protocolo de estándar de la industria usado para buscar equipos en una red basada en IP.  Los usuarios pueden recordar nombres para mostrar como [http:\/\/go.microsoft.com\/fwlink\/?prd\=10929](http://go.microsoft.com/fwlink/?prd=10929) o [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=96165](http://go.microsoft.com/fwlink/?LinkID=96165), con más facilidad que direcciones basadas en números como 207.46.131.137.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica la identidad del servicio que va a autenticar el cliente.|  
  
## Ejemplo  
 El código de configuración siguiente especifica el DNS de un certificado X.509 que se usa para autenticar un servidor.  
  
```  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.DnsEndpointIdentity>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)