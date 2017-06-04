---
title: "Elemento &lt;transport&gt; de &lt;netTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Elemento &lt;transport&gt; de &lt;netTcpBinding&gt;
Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con el [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
## Sintaxis  
  
```  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"  
             sslProtocols="Ssl3|Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|clientCredentialType|Opcional.  Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad de transporte.<br /><br /> -   El valor predeterminado es `Windows`.<br />-   Este atributo es del tipo <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Opcional.  Define la seguridad en el nivel del transporte del TCP.  Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.  El cifrado proporciona privacidad de nivel de datos durante el transporte.<br /><br /> El valor predeterminado es `EncryptAndSign`.|  
|sslProtocols|Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.  El valor predeterminado es Ssl3&#124;Tls&#124;Tls11&#124;Tls12.|  
|policyEnforcement|Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtectionPolicy>.<br /><br /> 1.  Never: la directiva nunca se aplica \(la protección extendida está deshabilitada\).<br />2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.<br />3.  Always: la directiva siempre se aplica.  Los clientes que no admitan la protección extendida no podrán autenticarse.|  
  
## Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|El cliente es anónimo.  Esto requiere un certificado para el servicio.|  
|Windows|Especifica la autenticación de Windows del cliente utilizando Negotiation de SP \(negociación de Kerberos\).|  
|Certificado|El cliente se autentica utilizando un certificado.  Esto utiliza Negotiation de SSL y requiere un certificado para el servicio.|  
  
## Atributo protectionLevel  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|Ninguna protección|  
|Signo|Se firman los mensajes.|  
|EncryptAndSign|-   Los mensajes se cifran y firman.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Especifica las funciones de seguridad del [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).|  
  
## Comentarios  
 Utilice la seguridad de transporte para la integridad y confidencialidad del mensaje SOAP y para la autenticación mutua.  Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura utilizando un transporte seguro y los mensajes SOAP se protegen utilizando la seguridad de transporte, como Windows \(Negotiate\) o SSL sobre TCP.  
  
## Vea también  
 <xref:System.ServiceModel.TcpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.NetTcpTransportSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)