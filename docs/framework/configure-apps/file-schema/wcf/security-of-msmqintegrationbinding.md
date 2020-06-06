---
title: <security> de <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738683"
---
# <a name="security-of-msmqintegrationbinding"></a>\<security> de \<msmqIntegrationBinding>
Define la configuración de seguridad de transporte para el canal de integración de Message Queuing (MSMQ).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|mode|Especifica el tipo de seguridad que controla integridad, confidencialidad y autenticación con el canal de integración de Message Queuing. Los valores válidos incluyen los siguientes:<br /><br /> -None: Esto deshabilita la seguridad.<br />-Transport: el transporte ofrece protección y autenticación. Esto se aplica al modo de seguridad de mensajes entre los dos administradores de cola. No se proporciona seguridad entre la aplicación y el administrador de cola. Las aplicaciones Msmq existentes son funcionalmente equivalentes a este tipo de modo de seguridad.<br /><br /> El valor predeterminado es `Transport`. Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|Define la configuración de seguridad para el transporte de integración de Message Queuing. Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Elemento de enlace de [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [Colas en WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
