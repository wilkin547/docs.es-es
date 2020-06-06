---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5899c609b3cf52c4a275ba6fb10c5826fcf37f1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153014"
---
# \<msmqTransportSecurity>
Especifica la configuración de seguridad de transporte MSMQ para un enlace personalizado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Especifica cómo el transporte de MSMQ debe autenticar el mensaje. Si esto está establecido en `None`, el valor del atributo `msmqProtectionLevel` también debe estar establecido en `None`.<br /><br /> Los valores válidos incluyen los siguientes:<br /><br /> -None: sin autenticación.<br />-Windows: el mecanismo de autenticación usa Active Directory para obtener el certificado X. 509 para el SID asociado al mensaje. Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />-Certificate: el canal obtiene el certificado del almacén de certificados.<br /><br /> El valor predeterminado es Windows. Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes. Los valores válidos incluyen los siguientes:<br /><br /> -RC4Stream<br />-AES<br /><br /> El valor predeterminado RC4Stream. Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Especifica cómo el mensaje se protege en el nivel del transporte de MSMQ. El cifrado asegura la integridad del mensaje, mientras que EncryptAndSign garantiza la integridad del mensaje y el no rechazo; es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser. Los valores válidos incluyen los siguientes:<br /><br /> -None: sin protección.<br />-Sign: los mensajes se firman.<br />-EncryptAndSign: los mensajes se cifran y firman.<br /><br /> El valor predeterminado es Sign. Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Especifica el algoritmo que se va a utilizar para calcular el resumen como parte de las firmas. Los valores válidos incluyen los siguientes:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> El valor predeterminado es SHA1. Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|Especifica valores requeridos para la interacción con un remitente o receptor de Message Queuing (MSMQ).|  
|[\<msmqTransport>](msmqtransport.md)|Especifica las propiedades de comunicación de uso de colas de un servicio Windows Communication Foundation (WCF) que usa el protocolo MSMQ nativo.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre la seguridad de transporte, vea [seguridad de transporte](../../../wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Colas en WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Transportes](../../../wcf/feature-details/transports.md)
- [Elección del transporte](../../../wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Seguridad de transporte](../../../wcf/feature-details/transport-security.md)
