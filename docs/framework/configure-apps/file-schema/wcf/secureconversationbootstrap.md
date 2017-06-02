---
title: "&lt;secureConversationBootstrap&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 66b46f95-fa2d-4b5b-b6ce-0572ab0cdd50
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# &lt;secureConversationBootstrap&gt;
Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.  
  
## Sintaxis  
  
```  
  
<secureConversationBootstrap  
   allowSerializedSigningTokenOnReply="Boolean"  
   authenticationMode="AuthenticationMode"  
   defaultAlgorithmSuite="SecurityAlgorithmSuite"  
   includeTimestamp="Boolean"  
   requireDerivedKeys="Boolean"  
   keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"   
messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"  
   messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"  
   requireDerivedKeys="Boolean"  
   requireSecurityContextCancellation="Boolean"  
   requireSignatureConfirmation="Boolean" >  
   securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast"  
   includeTimestamp="Boolean" />  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`allowSerializedSigningTokenOnReply`|Opcional.  Valor booleano que especifica si un token serializado se puede usar como respuesta.  El valor predeterminado es `false`.  Cuando use un enlace dual, el valor de la configuración predeterminada es `true`. Se ignorarán los cambios de configuración realizados.|  
|`authenticationMode`|Especifica el modo de autenticación de SOAP utilizado entre el iniciador y el respondedor.<br /><br /> El valor predeterminado es sspiNegotiated.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Configuration.AuthenticationMode>.|  
|`defaultAlgorithmSuite`|El conjunto de algoritmos de seguridad define una variedad de algoritmos como la canonización, Digest, encapsulado de claves, firma, cifrado y derivación de claves.  Cada uno de los conjuntos de algoritmo de seguridad define los valores para estos parámetros diferentes.  La seguridad basada en mensaje se logra utilizando estos algoritmos.<br /><br /> Se utiliza este atributo al trabajar con una plataforma diferente que opta por un conjunto de algoritmos diferente que el valor predeterminado.  Debe tener presentes las ventajas y desventajas de los algoritmos relevantes al efectuar modificaciones en esta configuración.  Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.  De manera predeterminada, es `Basic256`.|  
|`includeTimestamp`|Valor booleano que especifica si las marcas de tiempo se incluyen en cada mensaje.  De manera predeterminada, es `true`.|  
|`keyEntropyMode`|Especifica la manera en que se calculan las claves para proteger mensajes.  Las claves pueden estar basadas en el material de clave de cliente únicamente, en el servicio de material clave, o en una combinación de ambos.  Los valores válidos son:<br /><br /> -   ClientEntropy: la clave de sesión está basada fuera del material clave proporcionado por el cliente.<br />-   ServerEntropy: la clave de sesión está basada fuera del material clave proporcionado por el servicio.<br />-   CombinedEntropy: la clave de sesión está basada fuera del material clave proporcionado por el cliente y el servicio.<br /><br /> El valor predeterminado es CombinedEntropy.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|`messageProtectionOrder`|Establece el orden en el que los algoritmos de seguridad de nivel de mensaje se aplican al mensaje.  Los valores válidos son los siguientes:<br /><br /> -   SignBeforeEncrypt: firme primero, a continuación, cifre.<br />-   SignBeforeEncryptAndEncryptSignature: firme, cifre y cifre la firma.<br />-   EncryptBeforeSign: cifre primero, a continuación, firme.<br /><br /> SignBeforeEncryptAndEncryptSignature es el valor predeterminado cuando se usan certificados mutuos con WS\-Security 1.1.  SignBeforeEncrypt es el valor predeterminado con WS\-Security 1.0.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|`messageSecurityVersion`|Establece la versión de WS\-Security que se utiliza.  Los valores válidos son los siguientes:<br /><br /> -   WSSecurityJan2004<br />-   WSSecurityXXX2005<br /><br /> El valor predeterminado es WSSecurityXXX2005.  Este atributo es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.|  
|`requireDerivedKeys`|Un valor booleano que especifica si las claves se pueden derivar de las claves de prueba originales.  De manera predeterminada, es `true`.|  
|`requireSecurityContextCancellation`|Un valor booleano que especifica si el contexto de seguridad debería ser cancelado y finalizado cuando no sea necesario.  De manera predeterminada, es `true`.|  
|`requireSignatureConfirmation`|Un valor booleano que especifica si la confirmación de la firma de Seguridad del WS está habilitada.  Cuando se establece en `true`, el respondedor confirma las firmas del mensaje.  De manera predeterminada, es `false`.<br /><br /> La confirmación de la firma se utiliza para confirmar que el servicio está respondiendo perfectamente a una solicitud.|  
|`securityHeaderLayout`|Especifica la clasificación de los elementos en el encabezado de seguridad.  Los valores válidos son:<br /><br /> -   Strict.  Los elementos se agregan al encabezado de seguridad según el principio general de "declarar antes de usar".<br />-   Lax.  Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: SOAP Message Security.<br />-   LaxWithTimestampFirst.  Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: SOAP Message Security, solo que el primer elemento en el encabezado de seguridad debe ser un elemento wsse:Timestamp.<br />-   LaxWithTimestampLast.  Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: SOAP Message Security, solo que el último elemento en el encabezado de seguridad debe ser un elemento wsse:Timestamp.<br /><br /> El valor predeterminado es Strict.<br /><br /> Este elemento es del tipo <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<IssuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Especifica un token emitido actual.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)|Especifica la configuración de seguridad de un cliente local para este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)|Especifica la configuración de seguridad de un servicio local para este enlace.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<seguridad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|Especifica las opciones de seguridad de un enlace personalizado.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>   
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>   
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Seguridad de enlace personalizado](../../../../../docs/framework/wcf/samples/custom-binding-security.md)