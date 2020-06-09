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
