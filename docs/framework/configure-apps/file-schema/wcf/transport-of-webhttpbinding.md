---
title: "&lt;transport&gt; de &lt;webHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;transport&gt; de &lt;webHttpBinding&gt;
Define los valores de seguridad a nivel de transporte para un extremo de servicio configurado para recibir solicitudes HTTP.  
  
## Sintaxis  
  
```  
<webHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</WebHttpBinding>  
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
|`Certificate`|Utiliza los certificados X.509 para autenticar al cliente.|  
|`Digest`|Usa la autenticación implícita.|  
|`Ntlm`|Utiliza la autenticación NTLM como reserva con un dominio de Windows.|  
|`Windows`|Utiliza la autenticación de Windows integrada.|  
  
## Atributo proxyCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|La seguridad está deshabilitada.|  
|`Basic`|Usa la autenticación básica.|  
|`Digest`|Usa la autenticación implícita.|  
|`Ntlm`|Utiliza NTLM como reserva con un dominio de Windows.|  
|`Windows`|Utiliza la autenticación de Windows integrada.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|Representa las funciones de seguridad del elemento [\<wsHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).|  
  
## Vea también  
 <xref:System.ServiceModel.HttpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)   
 [Modelo de programación de web HTTP de WCF](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)