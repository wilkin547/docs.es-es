---
title: "Elemento &lt;transport&gt; de &lt;wsHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Elemento &lt;transport&gt; de &lt;wsHttpBinding&gt;
Define la configuración de autenticación del transporte HTTP.  
  
## Sintaxis  
  
```  
  
<wsHttpBinding>  
    <binding>  
        <security mode=”None|Transport|TransportWithMessageCredential|TransportCredentialOnly”>  
            <transport  
            clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"  
            proxyCredentialType="Basic|Digest|None|Ntlm|Windows"  
            realm="string" />  
                <extendedProtectionPolicy policyEnforcement=”Never|WhenSupported|Always” protectionScenario=”TransportSelected|TrustedProxy”>  
                    <customServiceNames></customServiceNames>  
                </extendedProtecutionPolicy>  
            </transport>  
        </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## Tipo  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`clientCredentialType`|Especifica la credencial utilizada para autenticar el cliente al servicio.  Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Especifica la credencial usada para autenticar al cliente en un proxy del dominio.  Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.  El valor predeterminado es una cadena vacía.<br /><br /> Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.  También puede especificar una colección de usuarios que tiene acceso.  Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.|  
|`policyEnforcement`|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtectionPolicy>.<br /><br /> 1.  Never: la directiva nunca se aplica \(la protección extendida está deshabilitada\).<br />2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.<br />3.  Always: la directiva siempre se aplica.  Los clientes que no admitan la protección extendida no podrán autenticarse.|  
  
## Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Basic`|Usa la autenticación básica.|  
|`Digest`|Usa la autenticación implícita.|  
|`Ntlm`|Utiliza la autenticación NTLM como reserva con un dominio de Windows.|  
|`Windows`|Utiliza la autenticación de Windows integrada.|  
|`Certificate`|Utiliza los certificados X.509 para autenticar al cliente.|  
  
## Atributo proxyCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Basic`|Usa la autenticación básica.|  
|`Digest`|Usa la autenticación implícita.|  
|`Ntlm`|Utiliza NTLM como reserva con un dominio de Windows.|  
|`Windows`|Utiliza la autenticación de Windows integrada.|  
|`Certificate`|Utiliza los certificados X.509 para autenticar al cliente.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|Representa las funcionalidades de seguridad de [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.HttpTransportSecurity>   
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)