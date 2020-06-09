---
title: Alteración
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: e618ab369a46d403aa8db26c4b472e2be3634785
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600716"
---
# <a name="tampering"></a><span data-ttu-id="7875c-102">Alteración</span><span class="sxs-lookup"><span data-stu-id="7875c-102">Tampering</span></span>
<span data-ttu-id="7875c-103">La *manipulación* es la acción de alterar un mensaje o la entrega de un mensaje, y el uso del mensaje modificado para un fin distinto de su propósito.</span><span class="sxs-lookup"><span data-stu-id="7875c-103">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="7875c-104">No deshabilite WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="7875c-104">Do Not Disable WS-Addressing</span></span>  
 <span data-ttu-id="7875c-105">La especificación WS-Addressing proporciona encabezados de dirección en cada mensaje, lo que permite a un destinatario del mensaje comprobar el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="7875c-105">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="7875c-106">Puede deshabilitar esta característica estableciendo la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="7875c-106">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="7875c-107">Cuando el modo de seguridad está establecido en Mensaje, y si WS-Addressing está deshabilitado, un atacante podría tomar una solicitud de un cliente y enviarla a otro servicio, y el segundo servicio no tiene ninguna manera de detectar que el mensaje procedía del cliente original.</span><span class="sxs-lookup"><span data-stu-id="7875c-107">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="7875c-108">En efecto, el primer servicio puede pretender que es un cliente al hablar con el segundo servicio.</span><span class="sxs-lookup"><span data-stu-id="7875c-108">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="7875c-109">Para mitigar esto, nunca establezca la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>y evite el uso de <xref:System.ServiceModel.Channels.MessageVersion>, como la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> estática, que establece la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="7875c-109">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7875c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7875c-110">See also</span></span>

- [<span data-ttu-id="7875c-111">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="7875c-111">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="7875c-112">Divulgación de información</span><span class="sxs-lookup"><span data-stu-id="7875c-112">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="7875c-113">Elevación de privilegios</span><span class="sxs-lookup"><span data-stu-id="7875c-113">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="7875c-114">Denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="7875c-114">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="7875c-115">Escenarios no admitidos</span><span class="sxs-lookup"><span data-stu-id="7875c-115">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="7875c-116">Ataques por repetición</span><span class="sxs-lookup"><span data-stu-id="7875c-116">Replay Attacks</span></span>](replay-attacks.md)
