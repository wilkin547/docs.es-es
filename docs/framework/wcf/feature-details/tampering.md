---
title: "Manipulaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Manipulaci&#243;n
*Manipulación* es el acto de modificar un mensaje o la entrega de un mensaje y utilizar el mensaje modificado para un propósito distinto del que originariamente tenía.  
  
## No deshabilite WS\-Addressing  
 La especificación WS\-Addressing proporciona encabezados de dirección en cada mensaje, lo que permite a un destinatario del mensaje comprobar el remitente del mensaje.Puede deshabilitar esta característica estableciendo la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
 Cuando el modo de seguridad está establecido en Mensaje, y si WS\-Addressing está deshabilitado, un atacante podría tomar una solicitud de un cliente y enviarla a otro servicio, y el segundo servicio no tiene ninguna manera de detectar que el mensaje procedía del cliente original.En efecto, el primer servicio puede pretender que es un cliente al hablar con el segundo servicio.  
  
 Para mitigar esto, nunca establezca la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>y evite el uso de <xref:System.ServiceModel.Channels.MessageVersion>, como la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A> estática, que establece la propiedad <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> en <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>.  
  
## Vea también  
 [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Divulgación de información](../../../../docs/framework/wcf/feature-details/information-disclosure.md)   
 [Elevación de privilegio](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)   
 [Denegación de servicio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)   
 [Escenarios no admitidos](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)   
 [Ataques por repetición](../../../../docs/framework/wcf/feature-details/replay-attacks.md)