---
description: 'Más información acerca de cómo: habilitar la detección de reproducción de mensajes'
title: Procedimiento para habilitar la detección de repetición de mensajes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF security
- replay detection [WCF]
- WCF, custom bindings
- WCF, security
ms.assetid: 8b847e91-69a3-49e1-9e5f-0c455e50d804
ms.openlocfilehash: 743452195d5bf78360909a22ea81997c2712dd06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704672"
---
# <a name="how-to-enable-message-replay-detection"></a><span data-ttu-id="3ded6-103">Procedimiento para habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="3ded6-103">How to: Enable Message Replay Detection</span></span>

<span data-ttu-id="3ded6-104">Un ataque de reproducción se produce cuando un atacante copia una secuencia de mensajes entre dos partes y reproduce la secuencia a una o más partes.</span><span class="sxs-lookup"><span data-stu-id="3ded6-104">A replay attack occurs when an attacker copies a stream of messages between two parties and replays the stream to one or more of the parties.</span></span> <span data-ttu-id="3ded6-105">A menos que se mitigue, los equipos sujetos al ataque procesarán el flujo como mensajes legítimos, generando un intervalo de consecuencias erróneas, como las órdenes redundantes de un elemento.</span><span class="sxs-lookup"><span data-stu-id="3ded6-105">Unless mitigated, the computers subject to the attack will process the stream as legitimate messages, resulting in a range of bad consequences, such as redundant orders of an item.</span></span>  
  
 <span data-ttu-id="3ded6-106">Para obtener más información acerca de la detección de reproducción de mensajes, vea [detección de reproducción de mensajes](/previous-versions/msp-n-p/ff649371(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="3ded6-106">For more information about message replay detection, see [Message Replay Detection](/previous-versions/msp-n-p/ff649371(v=pandp.10)).</span></span>  
  
 <span data-ttu-id="3ded6-107">En el procedimiento siguiente se muestran varias propiedades que puede usar para controlar la detección de reproducción mediante Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3ded6-107">The following procedure demonstrates various properties that you can use to control replay detection using Windows Communication Foundation (WCF).</span></span>  
  
### <a name="to-control-replay-detection-on-the-client-using-code"></a><span data-ttu-id="3ded6-108">Para controlar la detección de reproducción en el cliente utilizando código</span><span class="sxs-lookup"><span data-stu-id="3ded6-108">To control replay detection on the client using code</span></span>  
  
1. <span data-ttu-id="3ded6-109">Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> para utilizar en <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="3ded6-109">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="3ded6-110">Para obtener más información, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="3ded6-110">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span> <span data-ttu-id="3ded6-111">En el siguiente ejemplo se utiliza <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> creado con <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="3ded6-111">The following example uses a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> created with the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span>  
  
2. <span data-ttu-id="3ded6-112">Utilizar la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> para devolver una referencia a la clase <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> y establecer cualquiera de las propiedades siguientes, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="3ded6-112">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class and set any of the following properties, as appropriate:</span></span>  
  
    1. <span data-ttu-id="3ded6-113">`DetectReplay`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-113">`DetectReplay`.</span></span> <span data-ttu-id="3ded6-114">Valor booleano.</span><span class="sxs-lookup"><span data-stu-id="3ded6-114">A Boolean value.</span></span> <span data-ttu-id="3ded6-115">Esto rige si el cliente debería detectar las reproducciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="3ded6-115">This governs whether the client should detect replays from the server.</span></span> <span data-ttu-id="3ded6-116">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-116">The default is `true`.</span></span>  
  
    2. <span data-ttu-id="3ded6-117">`MaxClockSkew`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-117">`MaxClockSkew`.</span></span> <span data-ttu-id="3ded6-118">Valor <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="3ded6-118">A <xref:System.TimeSpan> value.</span></span> <span data-ttu-id="3ded6-119">Rige qué sesgo temporal puede tolerar el mecanismo de reproducción entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="3ded6-119">Governs how much time skew the replay mechanism can tolerate between the client and the server.</span></span> <span data-ttu-id="3ded6-120">El mecanismo de seguridad examina la marca de tiempo enviada y determina si se fue enviada demasiado lejos en el pasado.</span><span class="sxs-lookup"><span data-stu-id="3ded6-120">The security mechanism examines the time stamp sent and determines whether it was sent too far back in the past.</span></span> <span data-ttu-id="3ded6-121">El valor predeterminado es 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="3ded6-121">The default is 5 minutes.</span></span>  
  
    3. <span data-ttu-id="3ded6-122">`ReplayWindow`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-122">`ReplayWindow`.</span></span> <span data-ttu-id="3ded6-123">Valor `TimeSpan`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-123">A `TimeSpan` value.</span></span> <span data-ttu-id="3ded6-124">Esto rige cuánto tiempo un mensaje puede vivir en la red después de que el servidor lo envíe (a través de los intermediarios) antes de alcanzar el cliente.</span><span class="sxs-lookup"><span data-stu-id="3ded6-124">This governs how long a message can live in the network after the server sends it (through intermediaries) before reaching the client.</span></span> <span data-ttu-id="3ded6-125">El cliente realiza el seguimiento de las firmas de los mensajes enviados dentro del `ReplayWindow` último para los propósitos de detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="3ded6-125">The client tracks the signatures of the messages sent within the latest `ReplayWindow` for the purposes of replay detection.</span></span>  
  
    4. <span data-ttu-id="3ded6-126">`ReplayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-126">`ReplayCacheSize`.</span></span> <span data-ttu-id="3ded6-127">Valor de entero.</span><span class="sxs-lookup"><span data-stu-id="3ded6-127">An integer value.</span></span> <span data-ttu-id="3ded6-128">El cliente almacena las firmas del mensaje en una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3ded6-128">The client stores the signatures of the message in a cache.</span></span> <span data-ttu-id="3ded6-129">Este valor especifica cuántas firmas que puede almacenar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3ded6-129">This setting specifies how many signatures the cache can store.</span></span> <span data-ttu-id="3ded6-130">Si el número de mensajes enviado dentro de la última ventana de reproducción alcanza el límite de la memoria caché, se rechazan los nuevos mensajes hasta que las firmas almacenadas en memoria caché más antiguas alcancen el límite horario.</span><span class="sxs-lookup"><span data-stu-id="3ded6-130">If the number of messages sent within the last replay window reaches the cache limit, new messages are rejected until the oldest cached signatures reach the time limit.</span></span> <span data-ttu-id="3ded6-131">El valor predeterminado es 500000.</span><span class="sxs-lookup"><span data-stu-id="3ded6-131">The default is 500000.</span></span>  
  
### <a name="to-control-replay-detection-on-the-service-using-code"></a><span data-ttu-id="3ded6-132">Para controlar la detección de reproducción en el servicio utilizando código</span><span class="sxs-lookup"><span data-stu-id="3ded6-132">To control replay detection on the service using code</span></span>  
  
1. <span data-ttu-id="3ded6-133">Cree <xref:System.ServiceModel.Channels.SecurityBindingElement> para utilizar en <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="3ded6-133">Create a <xref:System.ServiceModel.Channels.SecurityBindingElement> to use in a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
2. <span data-ttu-id="3ded6-134">Utilice la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> para devolver una referencia a la clase <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> y establezca las propiedades como descrito previamente.</span><span class="sxs-lookup"><span data-stu-id="3ded6-134">Use the <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A> property to return a reference to the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class, and set the properties as described previously.</span></span>  
  
### <a name="to-control-replay-detection-in-configuration-for-the-client-or-service"></a><span data-ttu-id="3ded6-135">Para controlar la detección de reproducción en configuración para el cliente o servicio</span><span class="sxs-lookup"><span data-stu-id="3ded6-135">To control replay detection in configuration for the client or service</span></span>  
  
1. <span data-ttu-id="3ded6-136">Cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3ded6-136">Create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
2. <span data-ttu-id="3ded6-137">Cree un elemento `<security>`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-137">Create a `<security>` element.</span></span>  
  
3. <span data-ttu-id="3ded6-138">Cree un [\<localClientSettings>](../../configure-apps/file-schema/wcf/localclientsettings-element.md) o [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md) .</span><span class="sxs-lookup"><span data-stu-id="3ded6-138">Create a [\<localClientSettings>](../../configure-apps/file-schema/wcf/localclientsettings-element.md) or [\<localServiceSettings>](../../configure-apps/file-schema/wcf/localservicesettings-element.md).</span></span>  
  
4. <span data-ttu-id="3ded6-139">Establezca los siguientes valores de atributo según sea apropiado: `detectReplays`, `maxClockSkew`, `replayWindow`, y `replayCacheSize`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-139">Set the following attribute values, as appropriate: `detectReplays`, `maxClockSkew`, `replayWindow`, and `replayCacheSize`.</span></span> <span data-ttu-id="3ded6-140">El ejemplo siguiente establece los atributos de `<localServiceSettings>`:</span><span class="sxs-lookup"><span data-stu-id="3ded6-140">The following example sets the attributes of both a `<localServiceSettings>` and a `<localClientSettings>` element:</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="NewBinding0">  
       <textMessageEncoding />  
        <security>  
         <localClientSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
         <localServiceSettings
          replayCacheSize="800000"
          maxClockSkew="00:03:00"  
          replayWindow="00:03:00" />  
        <secureConversationBootstrap />  
       </security>  
      <httpTransport />  
     </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="3ded6-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ded6-141">Example</span></span>  

 <span data-ttu-id="3ded6-142">El ejemplo siguiente crea <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mediante el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> y establece las propiedades de reproducción del enlace.</span><span class="sxs-lookup"><span data-stu-id="3ded6-142">The following example creates a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> using the <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> method, and sets the replay properties of the binding.</span></span>  
  
 [!code-csharp[c_ReplayDetection#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_replaydetection/cs/source.cs#1)]
 [!code-vb[c_ReplayDetection#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_replaydetection/vb/source.vb#1)]  
  
## <a name="scope-of-replay-message-security-only"></a><span data-ttu-id="3ded6-143">Ámbito de reproducción: Solo seguridad del mensaje</span><span class="sxs-lookup"><span data-stu-id="3ded6-143">Scope of Replay: Message Security Only</span></span>  

 <span data-ttu-id="3ded6-144">Observe que los procedimientos siguientes solo se aplican al modo de seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3ded6-144">Note that the following procedures apply only to Message security mode.</span></span> <span data-ttu-id="3ded6-145">Para Transporte y Transporte con modos de credencial de mensaje, los mecanismos de transporte detectan las reproducciones.</span><span class="sxs-lookup"><span data-stu-id="3ded6-145">For Transport and Transport with Message Credential modes, the transport mechanisms detect replays.</span></span>  
  
## <a name="secure-conversation-notes"></a><span data-ttu-id="3ded6-146">Notas de conversación seguras</span><span class="sxs-lookup"><span data-stu-id="3ded6-146">Secure Conversation Notes</span></span>  

 <span data-ttu-id="3ded6-147">Para los enlaces que habilitan las conversaciones seguras, puede ajustar estos valores tanto para la aplicación como para el enlace de arranque de conversación segura.</span><span class="sxs-lookup"><span data-stu-id="3ded6-147">For bindings that enable secure conversations, you can adjust these settings both for the application channel as well as for the secure conversation bootstrap binding.</span></span> <span data-ttu-id="3ded6-148">Por ejemplo, se pueden desactivar las reproducciones para el canal de la aplicación pero habilitarlas para el canal de arranque que establece la conversación segura.</span><span class="sxs-lookup"><span data-stu-id="3ded6-148">For example, you can turn off replays for the application channel but enable them for the bootstrap channel that establishes the secure conversation.</span></span>  
  
 <span data-ttu-id="3ded6-149">Si no utiliza las sesiones de conversación seguras, la detección de reproducción no garantiza la detección de reproducciones en escenarios de granja de servidores y cuando se recicla el proceso.</span><span class="sxs-lookup"><span data-stu-id="3ded6-149">If you do not use secure conversation sessions, replay detection does not guarantee detecting replays in server farm scenarios and when the process is recycled.</span></span> <span data-ttu-id="3ded6-150">Esto se aplica a los enlaces siguientes proporcionados por el sistema:</span><span class="sxs-lookup"><span data-stu-id="3ded6-150">This applies to the following system-provided bindings:</span></span>  
  
- <span data-ttu-id="3ded6-151"><xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="3ded6-151"><xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
- <span data-ttu-id="3ded6-152"><xref:System.ServiceModel.WSHttpBinding> con la propiedad <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> establecida en `false`.</span><span class="sxs-lookup"><span data-stu-id="3ded6-152"><xref:System.ServiceModel.WSHttpBinding> with the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property set to `false`.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ded6-153">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3ded6-153">Compiling the Code</span></span>  
  
- <span data-ttu-id="3ded6-154">Los espacios de nombres siguientes son necesarios para compilar el código:</span><span class="sxs-lookup"><span data-stu-id="3ded6-154">The following namespaces are required to compile the code:</span></span>  
  
- <xref:System>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
## <a name="see-also"></a><span data-ttu-id="3ded6-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ded6-155">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="3ded6-156">Conversaciones y sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="3ded6-156">Secure Conversations and Secure Sessions</span></span>](secure-conversations-and-secure-sessions.md)
- [\<localClientSettings>](../../configure-apps/file-schema/wcf/localclientsettings-element.md)
- [<span data-ttu-id="3ded6-157">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3ded6-157">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
