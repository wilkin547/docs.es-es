---
title: Elemento &lt;transport&gt; de &lt;netMsmqBinding&gt;
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 611d6730695c2e353782d11cb74d391107c02c35
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="lttransportgt-of-ltnetmsmqbindinggt"></a>Elemento &lt;transport&gt; de &lt;netMsmqBinding&gt;
Define la configuración de seguridad para el transporte.  
  
 \<system.ServiceModel>  
\<enlaces >  
\<netMsmqBinding>  
\<binding>  
\<seguridad >  
\<transport>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|msmqAuthenticationMode|Especifica cómo el transporte de MSMQ debe autenticar el mensaje. Los valores válidos son los siguientes:<br /><br /> -None: Sin autenticación.<br />-WindowsDomain: El mecanismo de autenticación utiliza Active Directory para recuperar el certificado X.509 para el identificador de seguridad asociado al mensaje. Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />-Certificate: El canal recupera el certificado del almacén de certificados.<br /><br /> De manera predeterminada, es `WindowsDomain`.<br /><br /> Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`. Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes. Los valores válidos son los siguientes:<br /><br /> -   RC4Stream<br />-AES<br />-El valor predeterminado es `RC4Stream`. Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ. El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio. Es decir, el mensaje procedió del remitente y el remitente es quien dice ser. Los valores válidos son los siguientes:<br /><br /> -None: Sin protección.<br />-Sign: Se firman los mensajes.<br />-EncryptAndSign: Los mensajes se cifrarán y firmarán.<br />-El valor predeterminado es `Sign`.|  
|msmqSecureHashAlgorithm|Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje. Los valores válidos son los siguientes:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> De manera predeterminada, es `SHA1`. Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Define los valores de seguridad de transporte para transportes en cola.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>  
 <xref:System.ServiceModel.MsmqTransportSecurity>  
 [Colas en WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)  
 [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
