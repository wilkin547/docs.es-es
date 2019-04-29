---
title: <secureConversationBootstrap>
ms.date: 03/30/2017
ms.assetid: 66b46f95-fa2d-4b5b-b6ce-0572ab0cdd50
ms.openlocfilehash: e39458e7e0bac15429ad3d34c4fbba0f55d254f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670604"
---
# <a name="secureconversationbootstrap"></a>\<secureConversationBootstrap>
Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<security>  
\<secureConversationBootstrap>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<secureConversationBootstrap allowSerializedSigningTokenOnReply="Boolean"
                             authenticationMode="AuthenticationMode"
                             defaultAlgorithmSuite="SecurityAlgorithmSuite"
                             includeTimestamp="Boolean"
                             requireDerivedKeys="Boolean"
                             keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
                             messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
                             messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"
                             requireDerivedKeys="Boolean"
                             requireSecurityContextCancellation="Boolean"
                             requireSignatureConfirmation="Boolean"
                             securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"
                             includeTimestamp="Boolean" />
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`allowSerializedSigningTokenOnReply`|Opcional. Valor booleano que especifica si un token serializado se puede usar como respuesta. El valor predeterminado es `false`. Cuando use un enlace dual, el valor de la configuración predeterminada es `true`. Se ignorarán los cambios de configuración realizados.|  
|`authenticationMode`|Especifica el modo de autenticación de SOAP utilizado entre el iniciador y el respondedor.<br /><br /> El valor predeterminado es sspiNegotiated.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Configuration.AuthenticationMode>.|  
|`defaultAlgorithmSuite`|El conjunto de algoritmos de seguridad define una variedad de algoritmos como la canonización, resumen, encapsulado de claves, firma, cifrado y derivación de claves. Cada uno de los conjuntos de algoritmo de seguridad define los valores para estos parámetros diferentes. La seguridad basada en mensaje se logra utilizando estos algoritmos.<br /><br /> Se utiliza este atributo al trabajar con una plataforma diferente que opta por un conjunto de algoritmos diferente que el valor predeterminado. Debe tener presentes las ventajas y desventajas de los algoritmos relevantes al efectuar modificaciones en esta configuración. Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>. De manera predeterminada, es `Basic256`.|  
|`includeTimestamp`|Valor booleano que especifica si las marcas de tiempo se incluyen en cada mensaje. De manera predeterminada, es `true`.|  
|`keyEntropyMode`|Especifica la manera en que se calculan las claves para proteger mensajes. Las claves pueden estar basadas en el material de clave de cliente únicamente, en el servicio de material clave, o en una combinación de ambos. Los valores válidos son:<br /><br /> -ClientEntropy: La clave de sesión se basa en el cliente proporcionado material de clave.<br />-ServerEntropy: La clave de sesión se basa en el servicio que proporciona material de clave.<br />-CombinedEntropy: La clave de sesión se basa en el cliente y servicio material clave proporcionado.<br /><br /> El valor predeterminado es CombinedEntropy.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`messageProtectionOrder`|Establece el orden en el que los algoritmos de seguridad de nivel de mensaje se aplican al mensaje. Los valores válidos son los siguientes:<br /><br /> -   SignBeforeEncrypt: Inicie sesión en primer lugar, a continuación, cifre.<br />-   SignBeforeEncryptAndEncryptSignature: Firmar, cifrar y cifre la firma.<br />-   EncryptBeforeSign: Cifre primero, a continuación, inicio de sesión.<br /><br /> SignBeforeEncryptAndEncryptSignature es el valor predeterminado cuando se usan certificados mutuos con WS-Security 1.1.  SignBeforeEncrypt es el valor predeterminado con WS-Security 1.0.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|`messageSecurityVersion`|Establece la versión de WS-Security que se utiliza. Los valores válidos son los siguientes:<br /><br /> -   WSSecurityJan2004<br />-   WSSecurityXXX2005<br /><br /> El valor predeterminado es WSSecurityXXX2005. Este atributo es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.|  
|`requireDerivedKeys`|Un valor booleano que especifica si las claves se pueden derivar de las claves de prueba originales. De manera predeterminada, es `true`.|  
|`requireSecurityContextCancellation`|Un valor booleano que especifica si el contexto de seguridad debería ser cancelado y finalizado cuando no sea necesario. De manera predeterminada, es `true`.|  
|`requireSignatureConfirmation`|Un valor booleano que especifica si la confirmación de la firma de Seguridad del WS está habilitada. Cuando se establece en `true`, el respondedor confirma las firmas del mensaje. De manera predeterminada, es `false`.<br /><br /> La confirmación de la firma se utiliza para confirmar que el servicio está respondiendo perfectamente a una solicitud.|  
|`securityHeaderLayout`|Especifica la clasificación de los elementos en el encabezado de seguridad. Los valores válidos son:<br /><br /> -Estrictos. Se agregan elementos al encabezado de seguridad según el principio general de "declarar antes de usar".<br />-Lax. Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: Message Security de SOAP.<br />-LaxWithTimestampFirst. Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: Message Security de SOAP, solo que el primer elemento en el encabezado de seguridad debe ser un elemento wsse:Timestamp.<br />-LaxWithTimestampLast. Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: Message Security de SOAP, solo que el último elemento en el encabezado de seguridad debe ser un elemento wsse:Timestamp.<br /><br /> El valor predeterminado es Strict.<br /><br /> Este elemento es del tipo <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Especifica un token emitido actual. Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings>](../../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)|Especifica la configuración de seguridad de un cliente local para este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings>](../../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)|Especifica la configuración de seguridad de un servicio local para este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|Especifica las opciones de seguridad de un enlace personalizado.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Seguridad de enlace personalizado](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
