---
title: "&lt;msmqTransportSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;msmqTransportSecurity&gt;
Especifica la configuración de seguridad de transporte MSMQ para un enlace personalizado.  
  
## Sintaxis  
  
```  
  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`msmqAuthenticationMode`|Especifica cómo el transporte de MSMQ debe autenticar el mensaje.  Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -   None: sin autenticación<br />-   Windows: el mecanismo de autenticación usa Active Directory para obtener el certificado X.509 para el SID asociado al mensaje.  Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />-   Certificate: el canal recupera el certificado del almacén de certificados.<br /><br /> El valor predeterminado es Windows.  Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes.  Los valores válidos son los siguientes:<br /><br /> -   RC4Stream<br />-   AES<br /><br /> El valor predeterminado RC4Stream.  Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ.  El cifrado asegura la integridad del mensaje mientras EncryptAndSign asegura la integridad del mensaje y el no repudio; es decir, el mensaje procede de hecho del remitente y el remitente es quien dice que es.  Los valores válidos son los siguientes:<br /><br /> -   None: sin protección.<br />-   Sign: se firman los mensajes.<br />-   EncryptAndSign: Los mensajes se cifran y firman.<br /><br /> El valor predeterminado es Sign.  Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Especifica el algoritmo que se va a utilizar para calcular el resumen como parte de las firmas.  Los valores válidos son los siguientes:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> El valor predeterminado es SHA1.  Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<msmqIntegration\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|Especifica valores requeridos para la interacción con un remitente o receptor de Message Queuing \(MSMQ\).|  
|[\<msmqTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|Especifica las propiedades de comunicación de uso de colas de un servicio Windows Communication Foundation \(WCF\) que usa el protocolo MSMQ nativo.|  
  
## Comentarios  
 Para obtener más información acerca de la seguridad de los transportes, vea [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
## Vea también  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>   
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Colas en WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Seguridad de transporte](../../../../../docs/framework/wcf/feature-details/transport-security.md)