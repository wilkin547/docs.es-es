---
title: "Federación y confianza"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: federation [WCF], and trust
ms.assetid: 4bdec4f2-f8a2-4512-bdcf-14ef54b5877a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5228ffaab43e24849d461080cdf3ef09b2fa6c0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="federation-and-trust"></a>Federación y confianza
En este tema se cubren varios aspectos relacionados con las aplicaciones federadas, los límites de confianza y configuración y el uso de tokens emitidos en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="services-security-token-services-and-trust"></a>Servicios, servicios de tokens de seguridad y confianza  
 Los servicios que exponen extremos federados esperan por lo general que los clientes se autentiquen utilizando un token proporcionado por un emisor concreto. Es importante que el servicio se configure con las credenciales correctas del emisor; de lo contrario, no podrá comprobar las signaturas sobre los tokens emitidos y el cliente no podrá comunicarse con el servicio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Configurar credenciales de emisor en el servicio, consulte [Cómo: configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
 De manera similar, al utilizar las claves simétricas, las claves se cifran para el servicio de destino, por lo que debe configurar el servicio de tokens de seguridad con las credenciales correctas para el servicio de destino; de lo contrario, no podrá cifrar la clave para el servicio de destino y, de nuevo, el cliente no podrá comunicarse con el servicio.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]los servicios utilizan el valor de la <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> propiedad en el [SecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md) para permitir el reloj desfase entre el cliente y el servicio. En la federación, el valor `MaxClockSkew` se aplica a los desfases temporales entre el cliente y el servicio de tokens de seguridad de donde el cliente obtuvo el token emitido. Por consiguiente, los servicios de tokens de seguridad no necesitan realizar concesiones de sesgo de reloj al establecer los tiempos de inicio y expiración del token emitido.  
  
> [!NOTE]
>  La importancia de sesgo de reloj aumenta a medida que se reduce la vida del token emitido. En la mayoría de los casos, el sesgo del reloj no es un problema significativo si la duración del token es de 30 minutos o más. Los escenarios con duraciones más cortas o donde la hora de validez exacta del token es importante deberían estar diseñados para tener en cuenta el sesgo del reloj.  
  
## <a name="federated-endpoints-and-time-outs"></a>Extremos federados y tiempos de espera  
 Cuando un cliente se comunica con un extremo federado, debe adquirir primero un token adecuado de un servicio de tokens de seguridad. Si el servicio de tokens de seguridad expone un extremo federado, el cliente debe obtener primero un token del emisor para ese extremo. Cada adquisición del token lleva tiempo y ese tiempo está sujeto al tiempo de espera total para enviar el mensaje real al extremo final.  
  
 Por ejemplo, el tiempo de espera en el canal del lado de cliente está establecido en 30 segundos. Se ha de llamar a dos emisores de tokens para recuperar los tokens antes de enviar el mensaje al último extremo y cada uno tarda 15 segundos en emitir un token. En este caso, no se realizará el intento correctamente y se produce una <xref:System.TimeoutException>. Por tanto, debe establecer el valor <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> en el canal de cliente en un valor lo suficientemente grande como para incluir el tiempo que se tarda en recuperar todos los tokens emitidos. En el caso en el que no se especifique un valor para la propiedad <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A>, la propiedad <xref:System.ServiceModel.Channels.Binding.OpenTimeout%2A> o la propiedad (o ambas) <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A> han de establecerse en un valor lo suficientemente grande como para incluir el tiempo invertido en recuperar todos los tokens emitidos.  
  
## <a name="token-lifetime-and-renewal"></a>Duración y renovación del token  
 Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no comprueban el token emitido al hacer una solicitud inicial a un servicio.  En su lugar, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] confía en el servicio de tokens de seguridad para emitir un token con tiempos adecuados de inicio y expiración. Si el cliente almacena el token en memoria caché y lo reutiliza, la duración del token se comprueba en las solicitudes subsiguientes y el cliente renueva automáticamente el token si fuese necesario. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]símbolo (token) de almacenamiento en caché, vea [Cómo: crear un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
 Si se especifican duraciones cortas, del orden de 30 segundos o menos para tokens emitidos o tokens de contextos de seguridad, puede provocar que se agoten los tiempos de espera de las negociaciones o que los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produzcan excepciones al solicitar tokens emitidos al negociar o renovar los tokens de contexto de seguridad.  
  
## <a name="issued-tokens-and-inclusionmode"></a>Tokens emitidos e InclusionMode  
 Que un token emitido se serialice o no en un mensaje enviado desde un cliente hasta un extremo federado, se controla estableciendo la propiedad <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InclusionMode%2A> de la clase <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>. Esta propiedad puede estar establecida en uno de los <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> valores de enumeración, pero no es útil en la mayoría de los escenarios federados. Los valores `SecurityTokenInclusionMode.Never` y `SecurityTokenInclusionMode.AlwaysToInitiator` hacen que el cliente envíe una referencia al token emitido por el servicio de tokens de seguridad al usuario de confianza. A menos que el usuario de confianza posea una copia del token emitido, se producirá un error en la autenticación porque la referencia del token no se puede resolver. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] trata `SecurityTokenInclusionMode.Once` como un equivalente a `SecurityTokenInclusionMode.AlwaysToRecipient`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>  
 [Cómo: crear un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Cómo: configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Cómo: crear un WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
