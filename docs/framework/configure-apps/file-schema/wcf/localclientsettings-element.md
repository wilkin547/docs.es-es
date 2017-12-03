---
title: '&lt;localClientSettings&gt; (elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cabde7eb9dd122c2f7060b2f2e2c16f5949dc1f3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltlocalclientsettingsgt-element"></a><span data-ttu-id="6729b-102">&lt;localClientSettings&gt; (elemento)</span><span class="sxs-lookup"><span data-stu-id="6729b-102">&lt;localClientSettings&gt; element</span></span>
<span data-ttu-id="6729b-103">Especifica la configuración de seguridad de un cliente local para este enlace.</span><span class="sxs-lookup"><span data-stu-id="6729b-103">Specifies the security settings of a local client for this binding.</span></span>  
  
 <span data-ttu-id="6729b-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6729b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6729b-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="6729b-105">\<bindings></span></span>  
<span data-ttu-id="6729b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6729b-106">\<customBinding></span></span>  
<span data-ttu-id="6729b-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="6729b-107">\<binding></span></span>  
<span data-ttu-id="6729b-108">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="6729b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6729b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6729b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6729b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6729b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6729b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6729b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6729b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="6729b-112">Attributes</span></span>  
  
|<span data-ttu-id="6729b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="6729b-113">Attribute</span></span>|<span data-ttu-id="6729b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6729b-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="6729b-115">Un valor booleano que especifica si el almacenamiento en caché de cookies está habilitado.</span><span class="sxs-lookup"><span data-stu-id="6729b-115">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="6729b-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="6729b-116">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="6729b-117">Un entero que especifica el porcentaje máximo de cookies que se pueden renovar.</span><span class="sxs-lookup"><span data-stu-id="6729b-117">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="6729b-118">Este valor debe estar comprendido entre 0 y 100, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="6729b-118">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="6729b-119">El valor predeterminado es 90.</span><span class="sxs-lookup"><span data-stu-id="6729b-119">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="6729b-120">Un valor booleano que especifica si se detectan ataques de reproducción en el canal y si se abordan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6729b-120">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="6729b-121">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="6729b-121">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="6729b-122">Un <xref:System.TimeSpan> que especifica la diferencia máxima de tiempo entre los relojes del sistema de las dos partes en comunicación.</span><span class="sxs-lookup"><span data-stu-id="6729b-122">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="6729b-123">El valor predeterminado es "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="6729b-123">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="6729b-124">Cuando este valor se establece en el valor predeterminado, el receptor acepta los mensajes con marcas de tiempo de envío de hasta cinco minutos antes o después de que se haya recibido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6729b-124">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="6729b-125">Se rechazan los mensajes que no pasan las pruebas de hora de envío.</span><span class="sxs-lookup"><span data-stu-id="6729b-125">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="6729b-126">Esta configuración se usa junto con la atributo `replayWindow`.</span><span class="sxs-lookup"><span data-stu-id="6729b-126">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="6729b-127"><xref:System.TimeSpan> que especifica la duración máxima de las cookies.</span><span class="sxs-lookup"><span data-stu-id="6729b-127">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="6729b-128">El valor predeterminado es "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="6729b-128">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="6729b-129">Un valor booleano que especifica si las conexiones que usan mensajería WS de confianza intentan volverse a conectar después de los errores de transporte.</span><span class="sxs-lookup"><span data-stu-id="6729b-129">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="6729b-130">El valor predeterminado es `true`, que significa que habrá intentos infinitos de volverse a conectar.</span><span class="sxs-lookup"><span data-stu-id="6729b-130">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="6729b-131">El ciclo sólo se rompe mediante el tiempo de espera de inactividad, que hace que el canal inicie una excepción si no se puede volver a conectar.</span><span class="sxs-lookup"><span data-stu-id="6729b-131">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="6729b-132">Un entero positivo que especifica el número de nonces almacenado en memoria caché utilizado para la detección de la repetición.</span><span class="sxs-lookup"><span data-stu-id="6729b-132">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="6729b-133">Si se supera este límite, se quita el nonce más viejo y se crea uno nuevo para el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="6729b-133">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="6729b-134">El valor predeterminado es 500000.</span><span class="sxs-lookup"><span data-stu-id="6729b-134">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="6729b-135">Un <xref:System.TimeSpan> que especifica la duración en la que los nonces de mensajes particulares son válidos.</span><span class="sxs-lookup"><span data-stu-id="6729b-135">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="6729b-136">Después de esta duración, no se aceptará un mensaje enviado con el mismo nonce que le mensaje enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6729b-136">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="6729b-137">Este atributo se utiliza junto con el atributo `maxClockSkew` para evitar los ataques de la repetición.</span><span class="sxs-lookup"><span data-stu-id="6729b-137">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="6729b-138">Un atacante podría reproducir un mensaje después de que su ventana de reproducción haya expirado.</span><span class="sxs-lookup"><span data-stu-id="6729b-138">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="6729b-139">Sin embargo, este mensaje no pasaría la prueba `maxClockSkew` que rechaza los mensajes con marcas de tiempo de hora de envío con un tiempo especificado posterior o anterior a la hora en la que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="6729b-139">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="6729b-140">Un <xref:System.TimeSpan> que especifica la duración después de la cual el iniciador renueva la clave para la sesión de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6729b-140">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="6729b-141">El valor predeterminado es "10:00:00".</span><span class="sxs-lookup"><span data-stu-id="6729b-141">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="6729b-142"><xref:System.TimeSpan> que especifica el intervalo de tiempo durante el cual una clave de sesión anterior es válida en mensajes entrantes durante una renovación de clave.</span><span class="sxs-lookup"><span data-stu-id="6729b-142">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="6729b-143">El valor predeterminado es "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="6729b-143">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="6729b-144">Durante una renovación de clave, el cliente y el servidor tienen que enviar siempre mensajes mediante la clave disponible más actual.</span><span class="sxs-lookup"><span data-stu-id="6729b-144">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="6729b-145">Ambas partes aceptarán mensajes entrantes protegidos con la clave de sesión anterior hasta que expire el tiempo de sustitución.</span><span class="sxs-lookup"><span data-stu-id="6729b-145">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="6729b-146">Un <xref:System.TimeSpan> positivo que especifica la duración en la que una marca de tiempo es válida.</span><span class="sxs-lookup"><span data-stu-id="6729b-146">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="6729b-147">El valor predeterminado es "00:15:00".</span><span class="sxs-lookup"><span data-stu-id="6729b-147">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6729b-148">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6729b-148">Child Elements</span></span>  
 <span data-ttu-id="6729b-149">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6729b-149">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6729b-150">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6729b-150">Parent Elements</span></span>  
  
|<span data-ttu-id="6729b-151">Elemento</span><span class="sxs-lookup"><span data-stu-id="6729b-151">Element</span></span>|<span data-ttu-id="6729b-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="6729b-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6729b-153">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="6729b-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="6729b-154">Especifica las opciones de seguridad de un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="6729b-154">Specifies the security options for a custom binding.</span></span>|  
|[<span data-ttu-id="6729b-155">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="6729b-155">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="6729b-156">Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.</span><span class="sxs-lookup"><span data-stu-id="6729b-156">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6729b-157">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6729b-157">Remarks</span></span>  
 <span data-ttu-id="6729b-158">La configuración es local en el sentido que no es la configuración derivada de la directiva de seguridad del servicio.</span><span class="sxs-lookup"><span data-stu-id="6729b-158">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6729b-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="6729b-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6729b-160">Enlaces</span><span class="sxs-lookup"><span data-stu-id="6729b-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6729b-161">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="6729b-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6729b-162">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="6729b-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6729b-163">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6729b-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="6729b-164">Cómo: crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6729b-164">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="6729b-165">Seguridad de enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="6729b-165">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
