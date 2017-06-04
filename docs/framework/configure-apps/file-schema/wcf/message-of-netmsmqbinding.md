---
title: "Elemento &lt;message&gt; de &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Elemento &lt;message&gt; de &lt;netMsmqBinding&gt;
Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.  
  
## Sintaxis  
  
```  
  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|algorithmSuite|Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.<br /><br /> El valor predeterminado es `Aes256`.  Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ.  Los valores válidos son los siguientes:<br /><br /> -   None: esto permite al servicio interactuar con clientes anónimos.  Ni el servicio ni el cliente requieren una credencial.<br />-   Windows: esto permite a los intercambios de SOAP estar bajo el contexto autenticado de credenciales de Windows.  Esto siempre realiza una autenticación basada en Kerberos.<br />-   UserName: permite al servicio exigir que el cliente se autentique mediante credenciales UserName.  La credencial en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] no permite enviar un resumen de contraseña ni derivar claves mediante una contraseña, así como tampoco usar dichas claves para seguridad de mensajes.  Por lo tanto, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] garantiza que el intercambio sea seguro al usar credenciales UserName.  Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`. <br /><br /> -   Certificate: esto permite al servicio exigir que el cliente se autentique mediante un certificado.  Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`.  La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.<br />-   CardSpace: esto permite al servicio requerir que el cliente se autentique utilizando un CardSpace.  Se debe proporcionar `serviceCertiifcate` en el comportamiento `clientCredential`.<br /><br /> El valor predeterminado es `Windows`.  Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Define la configuración de seguridad de un enlace.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>   
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>   
 <xref:System.ServiceModel.MessageSecurityOverMsmq>   
 [Colas en WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)