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
# <a name="tampering"></a>Alteración

La *manipulación* es la acción de alterar un mensaje o la entrega de un mensaje, y el uso del mensaje modificado para un fin distinto de su propósito.  
  
## <a name="do-not-disable-ws-addressing"></a>No deshabilite WS-Addressing  

 La especificación WS-Addressing proporciona encabezados de dirección en cada mensaje, lo que permite a un destinatario del mensaje comprobar el remitente del mensaje. Puede deshabilitar esta característica estableciendo la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Cuando el modo de seguridad está establecido en Mensaje, y si WS-Addressing está deshabilitado, un atacante podría tomar una solicitud de un cliente y enviarla a otro servicio, y el segundo servicio no tiene ninguna manera de detectar que el mensaje procedía del cliente original. En efecto, el primer servicio puede pretender que es un cliente al hablar con el segundo servicio.  
  
 Para mitigar esto, nunca establezca la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>y evite el uso de <xref:System.ServiceModel.Channels.MessageVersion>, como la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> estática, que establece la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>Vea también

- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Divulgación de información](information-disclosure.md)
- [Elevación de privilegios](elevation-of-privilege.md)
- [Denegación de servicio](denial-of-service.md)
- [Escenarios no admitidos](unsupported-scenarios.md)
- [Ataques por repetición](replay-attacks.md)
