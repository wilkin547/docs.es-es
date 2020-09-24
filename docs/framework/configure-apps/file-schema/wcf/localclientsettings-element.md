---
title: <localClientSettings> (elemento)
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: 19eaea71fdaad1b945524cca5cf15634e0b0fa14
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158739"
---
# <a name="localclientsettings-element"></a><span data-ttu-id="7955d-102">Elemento \<localClientSettings></span><span class="sxs-lookup"><span data-stu-id="7955d-102">\<localClientSettings> element</span></span>

<span data-ttu-id="7955d-103">Especifica la configuración de seguridad de un cliente local para este enlace.</span><span class="sxs-lookup"><span data-stu-id="7955d-103">Specifies the security settings of a local client for this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="7955d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7955d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7955d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7955d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="7955d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7955d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7955d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="7955d-107">Attributes</span></span>  
  
|<span data-ttu-id="7955d-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="7955d-108">Attribute</span></span>|<span data-ttu-id="7955d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7955d-109">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="7955d-110">Un valor booleano que especifica si el almacenamiento en caché de cookies está habilitado.</span><span class="sxs-lookup"><span data-stu-id="7955d-110">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="7955d-111">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="7955d-111">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="7955d-112">Un entero que especifica el porcentaje máximo de cookies que se pueden renovar.</span><span class="sxs-lookup"><span data-stu-id="7955d-112">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="7955d-113">Este valor debe estar comprendido entre 0 y 100, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="7955d-113">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="7955d-114">El valor predeterminado es 90.</span><span class="sxs-lookup"><span data-stu-id="7955d-114">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="7955d-115">Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7955d-115">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="7955d-116">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="7955d-116">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="7955d-117">Un <xref:System.TimeSpan> que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación.</span><span class="sxs-lookup"><span data-stu-id="7955d-117">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="7955d-118">El valor predeterminado es "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="7955d-118">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="7955d-119">Cuando este valor se establece en el valor predeterminado, el receptor acepta los mensajes con marcas de tiempo de envío de hasta cinco minutos antes o después de que se haya recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7955d-119">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="7955d-120">Se rechazan los mensajes que no pasan las pruebas de hora de envío.</span><span class="sxs-lookup"><span data-stu-id="7955d-120">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="7955d-121">Esta configuración se usa junto con la atributo `replayWindow`.</span><span class="sxs-lookup"><span data-stu-id="7955d-121">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="7955d-122"><xref:System.TimeSpan> que especifica la duración máxima de las cookies.</span><span class="sxs-lookup"><span data-stu-id="7955d-122">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="7955d-123">El valor predeterminado es "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="7955d-123">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="7955d-124">Un valor booleano que especifica si las conexiones que usan mensajería WS de confianza intentan volverse a conectar después de los errores de transporte.</span><span class="sxs-lookup"><span data-stu-id="7955d-124">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="7955d-125">El valor predeterminado es `true`, que significa que habrá intentos infinitos de volverse a conectar.</span><span class="sxs-lookup"><span data-stu-id="7955d-125">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="7955d-126">El ciclo sólo se rompe mediante el tiempo de espera de inactividad, que hace que el canal inicie una excepción si no se puede volver a conectar.</span><span class="sxs-lookup"><span data-stu-id="7955d-126">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="7955d-127">Un entero positivo que especifica el número de nonces almacenado en memoria caché utilizado para la detección de la repetición.</span><span class="sxs-lookup"><span data-stu-id="7955d-127">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="7955d-128">Si se supera este límite, se quita el nonce más viejo y se crea uno nuevo para el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="7955d-128">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="7955d-129">El valor predeterminado es 500000.</span><span class="sxs-lookup"><span data-stu-id="7955d-129">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="7955d-130">Un <xref:System.TimeSpan> que especifica la duración en la que los nonces de mensajes particulares son válidos.</span><span class="sxs-lookup"><span data-stu-id="7955d-130">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="7955d-131">Después de esta duración, no se aceptará un mensaje enviado con el mismo nonce que le mensaje enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7955d-131">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="7955d-132">Este atributo se utiliza junto con el atributo `maxClockSkew` para evitar los ataques de la repetición.</span><span class="sxs-lookup"><span data-stu-id="7955d-132">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="7955d-133">Un atacante podría reproducir un mensaje después de que su ventana de reproducción haya expirado.</span><span class="sxs-lookup"><span data-stu-id="7955d-133">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="7955d-134">Sin embargo, este mensaje no pasaría la prueba `maxClockSkew` que rechaza los mensajes con marcas de tiempo de hora de envío con un tiempo especificado posterior o anterior a la hora en la que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="7955d-134">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="7955d-135">Un <xref:System.TimeSpan> que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7955d-135">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="7955d-136">El valor predeterminado es "10:00:00".</span><span class="sxs-lookup"><span data-stu-id="7955d-136">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="7955d-137"><xref:System.TimeSpan> que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave.</span><span class="sxs-lookup"><span data-stu-id="7955d-137">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="7955d-138">El valor predeterminado es "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="7955d-138">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="7955d-139">Durante una renovación de clave, el cliente y el servidor tienen que enviar siempre mensajes mediante la clave disponible más actual.</span><span class="sxs-lookup"><span data-stu-id="7955d-139">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="7955d-140">Ambas partes aceptarán mensajes entrantes protegidos con la clave de sesión anterior hasta que expire el tiempo de sustitución.</span><span class="sxs-lookup"><span data-stu-id="7955d-140">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="7955d-141">Un <xref:System.TimeSpan> positivo que especifica la duración en la que una marca de tiempo es válida.</span><span class="sxs-lookup"><span data-stu-id="7955d-141">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="7955d-142">El valor predeterminado es "00:15:00".</span><span class="sxs-lookup"><span data-stu-id="7955d-142">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7955d-143">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7955d-143">Child Elements</span></span>  

 <span data-ttu-id="7955d-144">None</span><span class="sxs-lookup"><span data-stu-id="7955d-144">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7955d-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7955d-145">Parent Elements</span></span>  
  
|<span data-ttu-id="7955d-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="7955d-146">Element</span></span>|<span data-ttu-id="7955d-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="7955d-147">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="7955d-148">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="7955d-148">Specifies the security options for a custom binding.</span></span>|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="7955d-149">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="7955d-149">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7955d-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7955d-150">Remarks</span></span>  

 <span data-ttu-id="7955d-151">La configuración es local en el sentido que no es la configuración derivada de la directiva de seguridad del servicio.</span><span class="sxs-lookup"><span data-stu-id="7955d-151">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7955d-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="7955d-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="7955d-153">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7955d-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7955d-154">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="7955d-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="7955d-155">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="7955d-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="7955d-156">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="7955d-156">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="7955d-157">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="7955d-157">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
