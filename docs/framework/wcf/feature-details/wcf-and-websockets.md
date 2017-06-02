---
title: "WCF y WebSockets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF y WebSockets
.NET Framework 4.5 presenta compatibilidad con WebSockets en Windows Communication Foundation.WebSockets es una tecnología eficaz basada en estándares que permite la comunicación bidireccional a través de los puertos estándar 80 y 443 de HTTP.El uso de los puertos HTTP estándar permite que WebSockets se comunique a través de la Web mediante intermediarios.Se han agregado dos nuevos enlaces estándar para admitir la comunicación a través de un transporte WebSocket.<xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>.Los valores específicos de WebSockets se pueden configurar en el elemento <xref:> System.ServiceModel.Channels.HttpTransportBinding?qualifyHint=False&autoUpgrade=True si se tiene acceso a la propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A>.  
  
## En esta sección  
 [Usar NetHttpBinding](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 Describe <xref:System.ServiceModel.NetHttpBinding> y su configuración.  
  
 [Cómo crear un servicio WCF que se comunique a través de WebSockets](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Describe cómo crear un servicio WCF que se comunique a través de Websockets.  
  
## Referencia  
  
## Secciones relacionadas