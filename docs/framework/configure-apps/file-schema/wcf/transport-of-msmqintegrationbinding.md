---
title: <transport> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 1cb165fed9266307335482166116c4c1d62efe7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152962"
---
# <a name="transport-of-msmqintegrationbinding"></a>\<> de \<transporte de msmqIntegrationBinding>
Define la configuración de seguridad para el transporte de integración de Message Queuing.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<encuadernaciones>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>de msmqIntegrationBinding**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enlace>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>de seguridad**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transporte>**  
  
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
|`msmqAuthenticationMode`|Especifica cómo el transporte de MSMQ debe autenticar el mensaje. Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.<br /><br /> Los valores válidos incluyen los siguientes:<br /><br /> - Ninguno: No hay autenticación.<br />- WindowsDomain: el mecanismo de autenticación utiliza Active Directory para obtener el certificado X.509 para el SID asociado al mensaje. Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />- Certificado: El canal obtiene el certificado del almacén de certificados.<br /><br /> El valor predeterminado es WindowsDomain. Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes. Los valores válidos incluyen los siguientes:<br /><br /> - RC4Stream<br />- AES<br /><br /> El valor predeterminado RC4Stream. Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ. El cifrado garantiza la integridad del mensaje, mientras que EncryptAndSign garantiza la integridad del mensaje y la no repudio; es decir, el mensaje de hecho proviene del remitente y el remitente es quien dicen ser.<br /><br /> - Los valores válidos incluyen lo siguiente:<br />- Ninguno: Sin protección.<br />- Signo: Los mensajes están firmados.<br />- EncryptAndSign: Los mensajes están cifrados y firmados.<br /><br /> El valor predeterminado es Sign. Este atributo es del tipo ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|: especifica el algoritmo que se utilizará para calcular el resumen como parte de las firmas. Los valores válidos incluyen los siguientes:<br />- MD5<br />- SHA1<br />- SHA256<br />- SHA512<br /><br /> El valor predeterminado es SHA1. Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<>de seguridad](security-of-basichttpbinding.md)|Define la configuración de seguridad de un enlace MSMQ.|  
  
## <a name="remarks"></a>Observaciones  
 Este elemento encapsula la configuración de seguridad para el transporte de integración de Message Queuing. La configuración es la misma para la integración de Message Queuing y los transportes en cola. Le permite establecer el Modo de autenticación, Algoritmo de cifrado, Algoritmo hash seguro y Nivel de protección.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [Securing Services and Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<enlace>](bindings.md)
