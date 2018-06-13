---
title: Manipulación
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 519881a0813ac0b9f9218db42a42723a19a3089c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498636"
---
# <a name="tampering"></a>Manipulación
*Manipulación* es el acto de modificar un mensaje o la entrega de un mensaje y utilizar el mensaje modificado para un propósito distinto originariamente tenía.  
  
## <a name="do-not-disable-ws-addressing"></a>No deshabilite WS-Addressing  
 La especificación WS-Addressing proporciona encabezados de dirección en cada mensaje, lo que permite a un destinatario del mensaje comprobar el remitente del mensaje. Puede deshabilitar esta característica estableciendo la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Cuando el modo de seguridad está establecido en Mensaje, y si WS-Addressing está deshabilitado, un atacante podría tomar una solicitud de un cliente y enviarla a otro servicio, y el segundo servicio no tiene ninguna manera de detectar que el mensaje procedía del cliente original. En efecto, el primer servicio puede pretender que es un cliente al hablar con el segundo servicio.  
  
 Para mitigar esto, nunca establezca la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>y evite el uso de <xref:System.ServiceModel.Channels.MessageVersion>, como la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> estática, que establece la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Divulgación de información](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [Elevación de privilegios](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [Denegación de servicio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [Escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 [Ataques por repetición](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
