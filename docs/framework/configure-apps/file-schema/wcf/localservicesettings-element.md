---
title: <localServiceSettings> (elemento)
ms.date: 03/30/2017
ms.assetid: 0658549c-3f65-46dd-8c5c-9895441ed734
ms.openlocfilehash: 3043c07afd316d90cc5525a67bef144f33d9b136
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204936"
---
# <a name="localservicesettings-element"></a>Elemento \<localServiceSettings>

Especifica la configuración de seguridad de un servicio local para este enlace.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localServiceSettings>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security>
  <localServiceSettings detectReplays="Boolean"
                        inactivityTimeout="TimeSpan"
                        issuedCookieLifeTime="TimeSpan"
                        maxCachedCookies="Integer"
                        maxClockSkew="TimeSpan"
                        maxPendingSessions="Integer"
                        maxStatefulNegotiations="Integer"
                        negotiationTimeout="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`detectReplays`|Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente. El valor predeterminado es `false`.|  
|`inactivityTimeout`|Un positivo <xref:System.TimeSpan> que especifica la duración de inactividad que el canal espera antes de que se agote el tiempo de espera. El valor predeterminado es "01:00:00".|  
|`issuedCookieLifeTime`|<xref:System.TimeSpan> que especifica la duración emitida a todas las nuevas cookies de seguridad. Las cookies que superan su duración se reciclan y se negocian de nuevo. El valor predeterminado es "10:00:00".|  
|`maxCachedCookies`|Un entero positivo que especifica el número máximo de cookies que pueden estar almacenadas en memoria caché. El valor predeterminado es 1000.|  
|`maxClockSkew`|Un <xref:System.TimeSpan> que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación. El valor predeterminado es "00:05:00".<br /><br /> Cuando este valor se establece en el valor predeterminado, el receptor acepta los mensajes con marcas de tiempo de envío de hasta cinco minutos antes o después de que se haya recibido el mensaje. Se rechazan los mensajes que no pasan las pruebas de hora de envío. Esta configuración se usa junto con la atributo `replayWindow`.|  
|`maxPendingSessions`|Un entero positivo que especifica el número máximo de sesiones de seguridad pendientes que el servicio admite. Cuando se alcanza este límite, todos los nuevos clientes reciben errores SOAP. El valor predeterminado es 1000.|  
|`maxStatefulNegotiations`|Un entero positivo que especifica el número de negociaciones de seguridad que pueden estar activas de manera simultánea. Las sesiones de la negociación que exceden el límite se ponen en la cola y se completan sólo cuando vuelve a haber espacio disponible dentro del límite. El valor predeterminado es 1024.|  
|`negotiationTimeout`|<xref:System.TimeSpan> que especifica la duración de la directiva de seguridad utilizada por canal. Cuando la hora expira, el canal renegocia con el cliente para una nueva directiva de seguridad. El valor predeterminado es "00:02:00".|  
|`reconnectTransportOnFailure`|Un valor booleano que especifica si las conexiones que usan mensajería WS de confianza intentan volverse a conectar después de los errores de transporte. El valor predeterminado es `true`, que significa que habrá intentos infinitos de volverse a conectar. El ciclo sólo se rompe mediante el tiempo de espera de inactividad, que hace que el canal inicie una excepción si no se puede volver a conectar.|  
|`replayCacheSize`|Un entero positivo que especifica el número de nonces almacenado en memoria caché utilizado para la detección de la repetición. Si se supera este límite, se quita el nonce más viejo y se crea uno nuevo para el nuevo mensaje. El valor predeterminado es 500000.|  
|`replayWindow`|Un <xref:System.TimeSpan> que especifica la duración en la que los nonces de mensajes particulares son válidos.<br /><br /> Después de esta duración, no se aceptará un mensaje enviado con el mismo nonce que le mensaje enviado anteriormente. Este atributo se utiliza junto con el atributo `maxClockSkew` para evitar los ataques de la repetición. Un atacante podría reproducir un mensaje después de que su ventana de reproducción haya expirado. Sin embargo, este mensaje no pasaría la prueba `maxClockSkew` que rechaza los mensajes con marcas de tiempo de hora de envío con un tiempo especificado posterior o anterior a la hora en la que se recibió el mensaje.|  
|`sessionKeyRenewalInterval`|Un <xref:System.TimeSpan> que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad. El valor predeterminado es "10:00:00".|  
|`sessionKeyRolloverInterval`|<xref:System.TimeSpan> que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave. El valor predeterminado es "00:05:00".<br /><br /> Durante una renovación de clave, el cliente y el servidor tienen que enviar siempre mensajes mediante la clave disponible más actual. Ambas partes aceptarán mensajes entrantes protegidos con la clave de sesión anterior hasta que expire el tiempo de sustitución.|  
|`timestampValidityDuration`|Un <xref:System.TimeSpan> positivo que especifica la duración en la que una marca de tiempo es válida. El valor predeterminado es "00:15:00".|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|Especifica las opciones de seguridad de un enlace personalizado.|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.|  
  
## <a name="remarks"></a>Observaciones  

 La configuración es local porque no se publica como parte de la directiva de seguridad del servicio y no afecta al enlace del cliente.  
  
 Los siguientes atributos del elemento `localServiceSecuritySettings` pueden ayudar a mitigar un ataque de seguridad de denegación de servicio (DOS):  
  
- `maxCachedCookies`: controla el número máximo de SecurityContextTokens limitados por el tiempo que están almacenados en memoria caché por el servidor después de realizar una negociación SPNEGO o SSL.  
  
- `issuedCookieLifetime`: controla la duración de los SecurityContextTokens emitidos por el servidor tras la negociación SPNEGO o SSL. El servidor almacena en memoria caché los SecurityContextTokens durante este período de tiempo.  
  
- `maxPendingSessions`: controla el número máximo de conversaciones seguras que se establecen en el servidor pero para las que no se ha procesado ningún mensaje de aplicación. Esta cuota evita que los clientes establezcan conversaciones seguras en el servicio, por lo que el servicio mantiene el estado para cada cliente, pero sin usarlo nunca.  
  
- `inactivityTimeout`: controla el tiempo máximo que el servicio mantiene viva una conversación segura sin recibir un mensaje de aplicación. Esta cuota evita que los clientes establezcan conversaciones seguras en el servicio, por lo que el servicio mantiene el estado para cada cliente, pero sin usarlo nunca.  
  
 En una sesión de conversación segura, tenga en cuenta que tanto el atributo `inactivityTimeout` como el atributo `receiveTimeout` del enlace afectan al tiempo de espera de la sesión. El más corto de los dos determina cuándo se agota el tiempo de espera.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Procedimiento para crear un enlace personalizado mediante SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Seguridad de enlace personalizado](../../../wcf/samples/custom-binding-security.md)
