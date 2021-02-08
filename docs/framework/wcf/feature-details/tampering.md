---
description: Más información acerca de la manipulación
title: Alteración
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 3b14fef66e5c98737d8d2f6a8b889f16c83020f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793329"
---
# <a name="tampering"></a><span data-ttu-id="57c94-103">Alteración</span><span class="sxs-lookup"><span data-stu-id="57c94-103">Tampering</span></span>

<span data-ttu-id="57c94-104">La *manipulación* es la acción de alterar un mensaje o la entrega de un mensaje, y el uso del mensaje modificado para un fin distinto de su propósito.</span><span class="sxs-lookup"><span data-stu-id="57c94-104">*Tampering* is the act of altering a message, or the delivery of a message, and using the altered message for a purpose other than what it was intended for.</span></span>  
  
## <a name="do-not-disable-ws-addressing"></a><span data-ttu-id="57c94-105">No deshabilite WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="57c94-105">Do Not Disable WS-Addressing</span></span>  

 <span data-ttu-id="57c94-106">La especificación WS-Addressing proporciona encabezados de dirección en cada mensaje, lo que permite a un destinatario del mensaje comprobar el remitente del mensaje.</span><span class="sxs-lookup"><span data-stu-id="57c94-106">The WS-Addressing specification provides address headers on each message, allowing a message recipient to verify the sender of the message.</span></span> <span data-ttu-id="57c94-107">Puede deshabilitar esta característica estableciendo la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="57c94-107">You can disable this feature by setting the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="57c94-108">Cuando el modo de seguridad está establecido en Mensaje, y si WS-Addressing está deshabilitado, un atacante podría tomar una solicitud de un cliente y enviarla a otro servicio, y el segundo servicio no tiene ninguna manera de detectar que el mensaje procedía del cliente original.</span><span class="sxs-lookup"><span data-stu-id="57c94-108">When the security mode is set to Message, and if WS-Addressing is disabled, an attacker could take a request from a client and send it to another service, and the second service has no way of detecting that the message came from the original client.</span></span> <span data-ttu-id="57c94-109">En efecto, el primer servicio puede pretender que es un cliente al hablar con el segundo servicio.</span><span class="sxs-lookup"><span data-stu-id="57c94-109">In effect, the first service can pretend that it is a client when talking to the second service.</span></span>  
  
 <span data-ttu-id="57c94-110">Para mitigar esto, nunca establezca la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>y evite el uso de <xref:System.ServiceModel.Channels.MessageVersion>, como la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> estática, que establece la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span><span class="sxs-lookup"><span data-stu-id="57c94-110">To mitigate this, never set the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>, and avoid the use of <xref:System.ServiceModel.Channels.MessageVersion>, such as the static <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> property, which sets the <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> property to <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c94-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="57c94-111">See also</span></span>

- [<span data-ttu-id="57c94-112">Consideraciones sobre la seguridad</span><span class="sxs-lookup"><span data-stu-id="57c94-112">Security Considerations</span></span>](security-considerations-in-wcf.md)
- [<span data-ttu-id="57c94-113">Divulgación de información</span><span class="sxs-lookup"><span data-stu-id="57c94-113">Information Disclosure</span></span>](information-disclosure.md)
- [<span data-ttu-id="57c94-114">Elevación de privilegios</span><span class="sxs-lookup"><span data-stu-id="57c94-114">Elevation of Privilege</span></span>](elevation-of-privilege.md)
- [<span data-ttu-id="57c94-115">Denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="57c94-115">Denial of Service</span></span>](denial-of-service.md)
- [<span data-ttu-id="57c94-116">Escenarios no admitidos</span><span class="sxs-lookup"><span data-stu-id="57c94-116">Unsupported Scenarios</span></span>](unsupported-scenarios.md)
- [<span data-ttu-id="57c94-117">Ataques por repetición</span><span class="sxs-lookup"><span data-stu-id="57c94-117">Replay Attacks</span></span>](replay-attacks.md)
