---
description: 'Más información sobre: <transport> de <netMsmqBinding>'
title: <transport> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 04768f259629277abd758d102f3873bb28f16514
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773503"
---
# <a name="transport-of-netmsmqbinding"></a>\<transport> de \<netMsmqBinding>

Define la configuración de seguridad para el transporte.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
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
|msmqAuthenticationMode|Especifica cómo el transporte de MSMQ debe autenticar el mensaje. Los valores válidos incluyen los siguientes:<br /><br /> -None: sin autenticación.<br />-WindowsDomain: el mecanismo de autenticación usa Active Directory para recuperar el certificado X. 509 para el identificador de seguridad asociado al mensaje. Esto se utiliza a continuación para comprobar el ACL de la cola para asegurarse que el usuario tiene el permiso de escritura para la cola.<br />-Certificate: el canal recupera el certificado del almacén de certificados.<br /><br /> De manera predeterminada, es `WindowsDomain`.<br /><br /> Si este atributo se establece en `None`, el atributo `msmqProtectionLevel` también debe establecerse como `None`. Este atributo es del tipo <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Especifica el algoritmo que se va a utilizar para el cifrado de mensajes en la conexión al transferir los mensajes entre los administradores de la cola de mensajes. Los valores válidos incluyen los siguientes:<br /><br /> -RC4Stream<br />-AES<br />-El valor predeterminado es `RC4Stream` . Este atributo es del tipo <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqProtectionLevel|Especifica la manera en que los mensajes se protegen en el nivel de transporte de MSMQ. El cifrado asegura la integridad del mensaje, mientras que la firma y el cifrado aseguran la integridad del mensaje y el no repudio. Es decir, el mensaje procede realmente del remitente y el remitente es quien dicen ser. Los valores válidos incluyen los siguientes:<br /><br /> -None: sin protección.<br />-Sign: los mensajes se firman.<br />-EncryptAndSign: los mensajes se cifran y firman.<br />-El valor predeterminado es `Sign` .|  
|msmqSecureHashAlgorithm|Especifica el algoritmo hash que se va a utilizar para calcular la síntesis del mensaje. Los valores válidos incluyen los siguientes:<br /><br /> -MD5<br />-SHA1<br />-SHA256<br />-SHA512<br /><br /> De manera predeterminada, es `SHA1`. Este atributo es del tipo <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.<br>Debido a problemas de colisión con MD5 y SHA1, Microsoft recomienda SHA256 o superior.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
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
- [\<binding>](bindings.md)
