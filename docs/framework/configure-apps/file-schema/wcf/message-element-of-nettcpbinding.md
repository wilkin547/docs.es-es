---
title: "Elemento &lt;message&gt; de &lt;netTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Elemento &lt;message&gt; de &lt;netTcpBinding&gt;
Define el tipo de requisitos de seguridad del nivel de mensaje para un extremo configurado con [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
## Sintaxis  
  
```  
  
<message   
      algorithmSuite=System.Servicemodel.Security.SecurityAlgorithmsuite  
    clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`algorithmSuite`|Establece el cifrado de mensajes y los algoritmos de encapsulado de claves.  La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave.  Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad \(WS\-SecurityPolicy\).<br /><br /> En la siguiente tabla se muestran los valores posibles.  El valor predeterminado es `Basic256`.<br /><br /> Si el enlace de servicio especifica un valor `algorithmSuite` que no es igual al valor predeterminado, y genera el archivo de configuración mediante Svcutil.exe, éste no se genera correctamente y debe editar manualmente el archivo de configuración  para establecer este atributo con el valor deseado.|  
|`clientCredentialType`|Especifica el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante seguridad basada en mensaje.  En la siguiente tabla se muestran los valores posibles.  El valor predeterminado es `UserName`.  Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.|  
  
## atributo algorithmSuite  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Basic128|Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic192|Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic256|Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el cifrado de claves.|  
|Basic256Rsa15|Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Rsa15|Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDes|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic128Rsa15|Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesRsa15|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic128Sha256|Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic192Sha256|Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic256Sha256|Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|TripleDesSha256|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa\-oaep\-mgf1p para el encapsulado de claves.|  
|Basic128Sha256Rsa15|Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Sha256Rsa15|Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic256Sha256Rsa15|Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesSha256Rsa15|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
  
## Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|Ninguna|Esto permite al servicio interactuar con clientes anónimos.  En el servicio, esto indica que el servicio no requiere ninguna credencial del cliente.  En el cliente, esto indica que el cliente no proporciona ninguna credencial del cliente.|  
|Windows|Permite a los intercambios de SOAP estar bajo el contexto autenticado de una credencial de Windows.|  
|UserName|Permite que el servicio requiera que el cliente se autentique con una credencial UserName.  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] no permite enviar un resumen de contraseña ni derivar claves mediante una contraseña, así como tampoco usar dichas claves para seguridad de mensajes.  Como tal, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] garantiza que el transporte sea seguro al usar credenciales UserName.  Este modo de credencial produce o bien un intercambio interoperable o bien una negociación no interoperable basada en el atributo `negotiateServiceCredential`.|  
|Certificado|Permite al servicio exigir la autenticación del cliente mediante un certificado.  Si se utiliza el modo de seguridad del mensaje y el atributo `negotiateServiceCredential` está establecido en `false`, se debe proporcionar al cliente el certificado de servicio.|  
|IssuedToken|Especifica un token personalizado, normalmente emitido por un servicio de token de seguridad \(STS\).|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Define las funciones de seguridad para <xref:System.ServiceModel.Configuration.NetTcpBindingElement>.|  
  
## Comentarios  
 Seguridad de nivel del mensaje para la integridad y confidencialidad del mensaje SOAP, así como para la autenticación mutua de los sistemas de comunicación del mismo nivel.  Si este modo de seguridad está seleccionado en un enlace, la pila del canal se configura con elementos de enlace de seguridad de mensaje. Los mensajes SOAP se protegen conforme a los estándares de WS\-Security\*.  
  
## Vea también  
 <xref:System.ServiceModel.MessageSecurityOverTcp>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetTcpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>   
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/es-es/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<enlace\>](../../../../../docs/framework/misc/binding.md)