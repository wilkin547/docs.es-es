---
title: '&lt;localClientSettings&gt; (elemento)'
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: a960a18c472bed64609947220dffedf9ec90945c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750952"
---
# <a name="ltlocalclientsettingsgt-element"></a>&lt;localClientSettings&gt; (elemento)
Especifica la configuración de seguridad de un cliente local para este enlace.  
  
 \<system.serviceModel>  
\<enlaces >  
\<customBinding >  
\<enlace >  
\<seguridad >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security>  
   <localClientSettings cacheCookies="Boolean"  
      cookieRenewalThresholdPercentage="Integer"  
      detectReplays="Boolean"  
      maxClockSkew="TimeSpan"  
      maxCookieCachingTime="TimeSpan"  
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
|`cacheCookies`|Un valor booleano que especifica si el almacenamiento en caché de cookies está habilitado. De manera predeterminada, es `false`.|  
|`cookieRenewalThresholdPercentage`|Un entero que especifica el porcentaje máximo de cookies que se pueden renovar. Este valor debe estar comprendido entre 0 y 100, ambos inclusive. El valor predeterminado es 90.|  
|`detectReplays`|Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente. De manera predeterminada, es `false`.|  
|`maxClockSkew`|Un <xref:System.TimeSpan> que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación. El valor predeterminado es "00:05:00".<br /><br /> Cuando este valor se establece en el valor predeterminado, el receptor acepta los mensajes con marcas de tiempo de envío de hasta cinco minutos antes o después de que se haya recibido el mensaje. Se rechazan los mensajes que no pasan las pruebas de hora de envío. Esta configuración se usa junto con la atributo `replayWindow`.|  
|`maxCookieCachingTime`|<xref:System.TimeSpan> que especifica la duración máxima de las cookies. El valor predeterminado es "10675199.02:48:05.4775807".|  
|`reconnectTransportOnFailure`|Un valor booleano que especifica si las conexiones que usan mensajería WS de confianza intentan volverse a conectar después de los errores de transporte. El valor predeterminado es `true`, que significa que habrá intentos infinitos de volverse a conectar. El ciclo sólo se rompe mediante el tiempo de espera de inactividad, que hace que el canal inicie una excepción si no se puede volver a conectar.|  
|`replayCacheSize`|Un entero positivo que especifica el número de nonces almacenado en memoria caché utilizado para la detección de la repetición. Si se supera este límite, se quita el nonce más viejo y se crea uno nuevo para el nuevo mensaje. El valor predeterminado es 500000.|  
|`replayWindow`|Un <xref:System.TimeSpan> que especifica la duración en la que los nonces de mensajes particulares son válidos.<br /><br /> Después de esta duración, no se aceptará un mensaje enviado con el mismo nonce que le mensaje enviado anteriormente. Este atributo se utiliza junto con el atributo `maxClockSkew` para evitar los ataques de la repetición. Un atacante podría reproducir un mensaje después de que su ventana de reproducción haya expirado. Sin embargo, este mensaje no pasaría la prueba `maxClockSkew` que rechaza los mensajes con marcas de tiempo de hora de envío con un tiempo especificado posterior o anterior a la hora en la que se recibió el mensaje.|  
|`sessionKeyRenewalInterval`|Un <xref:System.TimeSpan> que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad. El valor predeterminado es "10:00:00".|  
|`sessionKeyRolloverInterval`|<xref:System.TimeSpan> que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave. El valor predeterminado es "00:05:00".<br /><br /> Durante una renovación de clave, el cliente y el servidor tienen que enviar siempre mensajes mediante la clave disponible más actual. Ambas partes aceptarán mensajes entrantes protegidos con la clave de sesión anterior hasta que expire el tiempo de sustitución.|  
|`timestampValidityDuration`|Un <xref:System.TimeSpan> positivo que especifica la duración en la que una marca de tiempo es válida. El valor predeterminado es "00:15:00".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|Especifica las opciones de seguridad de un enlace personalizado.|  
|[\<secureConversationBootstrap >](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.|  
  
## <a name="remarks"></a>Comentarios  
 La configuración es local en el sentido que no es la configuración derivada de la directiva de seguridad del servicio.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Creación de un enlace personalizado mediante SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Seguridad de enlace personalizado](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
