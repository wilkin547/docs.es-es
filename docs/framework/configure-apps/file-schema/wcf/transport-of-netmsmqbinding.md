---
title: <transport> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ede4103f9c8f2f73ac34036fe7a58242e32350e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934690"
---
# <a name="transport-of-netmsmqbinding"></a>\<> de transporte \<de netMsmqBinding >
Define la configuración de seguridad para el transporte.  
  
 \<system.ServiceModel>  
\<bindings>  
\<netMsmqBinding>  
\<binding>  
\<> de seguridad  
\<> de transporte  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|msmqAuthenticationMode|Especifica cómo el transporte de MSMQ debe autenticar el mensaje. Los valores válidos son los siguientes:<br /><br /> Ninguna Sin autenticación.<br />-   WindowsDomain: El mecanismo de autenticación utiliza Active Directory para recuperar el certificado X. 509 para el identificador de seguridad asociado al mensaje. Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />Certificado El canal recupera el certificado del almacén de certificados.<br /><br /> El valor predeterminado es `WindowsDomain`.<br /><br /> Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`. Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes. Los valores válidos son los siguientes:<br /><br /> -RC4Stream<br />-AES<br />-El valor predeterminado es `RC4Stream`. Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ. El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio. Es decir, el mensaje procedió del remitente y el remitente es quien dice ser. Los valores válidos son los siguientes:<br /><br /> Ninguna Ninguna protección<br />Sesión Se firman los mensajes.<br />-   EncryptAndSign: Los mensajes se cifran y firman.<br />-El valor predeterminado `Sign`es.|  
|msmqSecureHashAlgorithm|Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje. Los valores válidos son los siguientes:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> El valor predeterminado es `SHA1`. Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|Define los valores de seguridad de transporte para transportes en cola.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Colas en WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
