---
title: Federación y confianza
ms.date: 03/30/2017
helpviewer_keywords:
- federation [WCF], and trust
ms.assetid: 4bdec4f2-f8a2-4512-bdcf-14ef54b5877a
ms.openlocfilehash: 4e1529db6cc52b6b8cc8881d2b2a35a754b4b311
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225344"
---
# <a name="federation-and-trust"></a>Federación y confianza
En este tema se trata diversos aspectos relacionados con las aplicaciones federadas, los límites de confianza y configuración y uso de tokens emitidos en Windows Communication Foundation (WCF).  
  
## <a name="services-security-token-services-and-trust"></a>Servicios, servicios de tokens de seguridad y confianza  
 Los servicios que exponen puntos de conexión federados esperan por lo general que los clientes se autentiquen utilizando un token proporcionado por un emisor concreto. Es importante que el servicio se configure con las credenciales correctas del emisor; de lo contrario, no podrá comprobar las signaturas sobre los tokens emitidos y el cliente no podrá comunicarse con el servicio. Para obtener más información sobre cómo configurar las credenciales del emisor en el servicio, vea [Cómo: Configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
 De manera similar, al utilizar las claves simétricas, las claves se cifran para el servicio de destino, por lo que debe configurar el servicio de tokens de seguridad con las credenciales correctas para el servicio de destino; de lo contrario, no podrá cifrar la clave para el servicio de destino y, de nuevo, el cliente no podrá comunicarse con el servicio.  
  
 Servicios WCF usan el valor de la <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> propiedad en el [SecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md) para permitir el reloj desfase entre el cliente y el servicio. En la federación, el valor `MaxClockSkew` se aplica a los desfases temporales entre el cliente y el servicio de tokens de seguridad de donde el cliente obtuvo el token emitido. Por consiguiente, los servicios de tokens de seguridad no necesitan realizar concesiones de sesgo de reloj al establecer los tiempos de inicio y expiración del token emitido.  
  
> [!NOTE]
>  La importancia de sesgo de reloj aumenta a medida que se reduce la vida del token emitido. En la mayoría de los casos, el sesgo del reloj no es un problema significativo si la duración del token es de 30 minutos o más. Los escenarios con duraciones más cortas o donde la hora de validez exacta del token es importante deberían estar diseñados para tener en cuenta el sesgo del reloj.  
  
## <a name="federated-endpoints-and-time-outs"></a>Extremos federados y tiempos de espera  
 Cuando un cliente se comunica con un punto de conexión federado, debe adquirir primero un token adecuado de un servicio de tokens de seguridad. Si el servicio de tokens de seguridad expone un punto de conexión federado, el cliente debe obtener primero un token del emisor para ese punto de conexión. Cada adquisición del token lleva tiempo y ese tiempo está sujeto al tiempo de espera total para enviar el mensaje real al extremo final.  
  
 Por ejemplo, el tiempo de espera en el canal del lado de cliente está establecido en 30 segundos. Se ha de llamar a dos emisores de tokens para recuperar los tokens antes de enviar el mensaje al último punto de conexión y cada uno tarda 15 segundos en emitir un token. En este caso, no se realizará el intento correctamente y se produce una <xref:System.TimeoutException>. Por tanto, debe establecer el valor <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> en el canal de cliente en un valor lo suficientemente grande como para incluir el tiempo que se tarda en recuperar todos los tokens emitidos. En el caso en el que no se especifique un valor para la propiedad <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A>, la propiedad <xref:System.ServiceModel.Channels.Binding.OpenTimeout%2A> o la propiedad (o ambas) <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A> han de establecerse en un valor lo suficientemente grande como para incluir el tiempo invertido en recuperar todos los tokens emitidos.  
  
## <a name="token-lifetime-and-renewal"></a>Duración y renovación del token  
 Los clientes de WCF no comprueban el token emitido al realizar una solicitud inicial a un servicio.  En su lugar, WCF confía en el servicio de token de seguridad para emitir un token con tiempos de inicio y expiración adecuados. Si el cliente almacena el token en memoria caché y lo reutiliza, la duración del token se comprueba en las solicitudes subsiguientes y el cliente renueva automáticamente el token si fuese necesario. Para obtener más información sobre almacenamiento en caché de tokens, vea [Cómo: Crear un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
 Especificar una duración más corta, del orden de 30 segundos o menos para tokens emitidos o tokens de contexto de seguridad, puede dar lugar a tiempos de espera de negociación o de otras excepciones iniciadas por clientes de WCF al solicitar los tokens emitidos o al negociar o renovar la seguridad tokens de contexto.  
  
## <a name="issued-tokens-and-inclusionmode"></a>Tokens emitidos e InclusionMode  
 Que un token emitido se serialice o no en un mensaje enviado desde un cliente hasta un extremo federado, se controla estableciendo la propiedad <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InclusionMode%2A> de la clase <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>. Esta propiedad puede estar establecida en uno de los <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> valores de enumeración, pero no es útil en la mayoría de los escenarios federados. Los valores `SecurityTokenInclusionMode.Never` y `SecurityTokenInclusionMode.AlwaysToInitiator` hacen que el cliente envíe una referencia al token emitido por el servicio de tokens de seguridad al usuario de confianza. A menos que el usuario de confianza posea una copia del token emitido, se producirá un error en la autenticación porque la referencia del token no se puede resolver. WCF trata `SecurityTokenInclusionMode.Once` como equivalente a `SecurityTokenInclusionMode.AlwaysToRecipient`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>
- [Filtrar para crear un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Filtrar para configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Filtrar para crear un WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
