---
title: Elemento &lt;transport&gt; de &lt;msmqIntegrationBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9def7fbd0082cc7fa9d9f18388604383cb71f9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltmsmqintegrationbindinggt"></a>Elemento &lt;transport&gt; de &lt;msmqIntegrationBinding&gt;
Define la configuración de seguridad para el transporte de integración de Message Queuing.  
  
 \<sistema. ServiceModel >  
\<enlaces >  
msmqIntegrationBinding  
\<enlace >  
\<seguridad >  
\<transporte >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Especifica cómo el transporte de MSMQ debe autenticar el mensaje. Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.<br /><br /> Los valores válidos son los siguientes:<br /><br /> -None: Sin autenticación.<br />-WindowsDomain: El mecanismo de autenticación utiliza Active Directory para obtener el certificado X.509 para el SID asociado al mensaje. Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />-Certificate: El canal recupera el certificado del almacén de certificados.<br /><br /> El valor predeterminado es WindowsDomain. Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes. Los valores válidos son los siguientes:<br /><br /> -RC4Stream<br />-AES<br /><br /> El valor predeterminado RC4Stream. Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ. El cifrado asegura la integridad del mensaje mientras EncryptAndSign asegura la integridad del mensaje y el no repudio; es decir, el mensaje procede de hecho del remitente y el remitente es quien dice que es.<br /><br /> -Valores válidos son los siguientes:<br />-None: Sin protección.<br />-Sign: Se firman los mensajes.<br />-EncryptAndSign: Los mensajes se cifrarán y firmarán.<br /><br /> El valor predeterminado es Sign. Este atributo es del tipo ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|: Especifica el algoritmo que se usará para calcular el resumen como parte de las firmas. Los valores válidos son los siguientes:<br />-MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> El valor predeterminado es SHA1. Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Define la configuración de seguridad de un enlace MSMQ.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento encapsula la configuración de seguridad para el transporte de integración de Message Queuing. La configuración es la misma para la integración de Message Queuing y los transportes en cola. Le permite establecer el Modo de autenticación, Algoritmo de cifrado, Algoritmo hash seguro y Nivel de protección.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<enlace >](../../../../../docs/framework/misc/binding.md)
