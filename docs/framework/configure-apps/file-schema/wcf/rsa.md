---
title: "&lt;rsa&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;rsa&gt;
Un cliente WCF seguro que se conecta a un extremo con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.  
  
## Sintaxis  
  
```  
  
<rsa value = "String" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|value|Cadena opcional.  El valor de clave pública de RSA con la que se va a comparar en el cliente.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Especifica la identidad del servicio que va a autenticar el cliente.|  
  
## Comentarios  
 Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.  Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.  
  
 Para obtener más información sobre cómo usar la identidad para validar un servicio a un cliente, consulte [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
## Ejemplo  
 El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.  
  
```  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.RsaEndpointIdentity>   
 [Identidad del servicio y autenticación](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)