---
title: "Consideraciones de seguridad para sesiones seguras | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Consideraciones de seguridad para sesiones seguras
Debe tener en cuenta los siguientes elementos que afectan a la seguridad al implementar sesiones seguras.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] las consideraciones de seguridad, vea [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) y [Procedimientos recomendados de seguridad](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## Sesiones seguras y metadatos  
 Cuando se establece una sesión segura y la propiedad <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> está establecida como `false`, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] envía una aserción `mssp:MustNotSendCancel` como parte de los metadatos en el documento de Lenguaje de descripción de servicios Web \(WSDL\) para el extremo del servicio.La aserción `mssp:MustNotSendCancel` informa a los clientes de que el servicio no responde a las solicitudes para cancelar la sesión segura.Cuando la propiedad <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> está establecida como `true`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no emite una aserción `mssp:MustNotSendCancel` en el documento WSDL.Se espera que los clientes envíen una solicitud de cancelación al servicio cuando dejen de necesitar la sesión segura.Cuando se genera un cliente con [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), el código de cliente reacciona adecuadamente a la presencia o ausencia de la aserción `mssp:MustNotSendCancel`.  
  
## Conversaciones seguras y tokens personalizados  
 Hay algunos problemas con la mezcla de tokens personalizados y claves derivadas debido a la manera en que se define en la especificación WS\-SecureConversation.La especificación dice que `wsse:SecurityTokenReference` es un elemento opcional que hace referencia al token derivado: “`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` Este elemento opcional se utiliza para especificar tokens de contexto de seguridad, tokens de seguridad o la clave compartida o el secreto que se utilizan para la derivación.Si no se especifica, se supone que el destinatario puede determinar la clave compartida a partir del contexto del mensaje.Si no se puede determinar el contexto, se debería generar un error tal como `wsc:UnknownDerivationSource`”.  
  
 Esto significa que, si se desea derivar un token personalizado, se debería incluir el tipo de cláusula en un elemento `SecurityTokenReference`.Hay una opción para desactivar la derivación, pero el valor predeterminado es derivar las claves.Si no se incluye la clave, la serialización del token de clave derivado se realiza correctamente, pero, al intentar deserializarlo, se produce una excepción.  
  
## Vea también  
 [Cómo deshabilitar sesiones seguras en WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)   
 [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Procedimientos recomendados de seguridad](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)