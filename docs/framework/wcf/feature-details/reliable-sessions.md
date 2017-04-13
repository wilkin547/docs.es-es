---
title: "Sesiones de confianza | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Windows Communication Foundation, sessions and instances"
  - "WCF, sessions and instances"
  - "sessions and instances [WCF]"
helpviewer_keywords: 
  - "instancias [WCF]"
  - "sesiones [WCF]"
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Sesiones de confianza
En esta sección se describe lo que es una sesión confiable de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], para qué se usa, cómo y cuándo usar una, qué configuraciones de enlace admite e indicaciones sobre procedimientos recomendados.La siguiente tabla resume los detalles sobre los puntos esenciales y temas relacionados de esta sección.  
  
 La sesión confiable que proporciona [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que los mensajes enviados entre extremos se transfieren mediante intermediarios de transporte o SOAP y se entregan una sola vez y, de manera opcional, en el mismo orden en el que se enviaron.  
  
 Para utilizar una sesión confiable con una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilice uno de los enlaces proporcionados por el sistema en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que admiten una sesión confiable de forma predeterminada u opcional, o cree su propio enlace personalizado que admita la sesión.  
  
## En esta sección  
 [Información general de sesiones confiables](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 Describe las sesiones confiables, cuándo utilizarlas, los diferentes enlaces que admiten las sesiones confiables y cómo funcionan.  
  
 [Intercambio de mensajes dentro de una sesión confiable](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)  
 Describe cómo crear una sesión confiable sobre HTTP utilizando un enlace personalizado especificado en la configuración.  
  
 [Protección de mensajes dentro de sesiones confiables](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)  
 Describe cómo proteger una sesión confiable.  
  
 [Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)  
 Describe cómo crear una sesión confiable sobre HTTPS.  
  
 [Procedimientos recomendados para lograr sesiones confiables](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)  
 Describe algunos de los procedimientos recomendados asociados al uso de una sesión confiable.  
  
## Referencia  
 <xref:System.ServiceModel.ReliableSession>  
  
## Vea también  
 [Colas y sesiones de confianza](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
 [Sesiones, creación de instancias y simultaneidad](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)