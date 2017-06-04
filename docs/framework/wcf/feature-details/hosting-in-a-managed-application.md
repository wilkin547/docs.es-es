---
title: "Hospedaje en una aplicaci&#243;n administrada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: af70132d-e9e1-4f32-b20f-f0014629758a
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Hospedaje en una aplicaci&#243;n administrada
Los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden hospedar en cualquier aplicación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Los servicios autohospedados constituyen la opción de hospedaje más flexible porque es la que requiere una menor infraestructura para su implementación. Sin embargo, también es la opción de hospedaje menos robusta, porque las aplicaciones administradas no proporcionan las características de administración y hospedaje avanzadas de otras opciones de hospedaje de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], como Internet Information Services \(IIS\) y servicios de Windows.  
  
 Para crear un servicio autohospedado, cree y abra una instancia de <xref:System.ServiceModel.ServiceHost>, que inicia un servicio que realiza escuchas de mensajes.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Hospedaje de un servicio WCF en una aplicación administrada](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md).  
  
 Para obtener un ejemplo completo sobre cómo definir un contrato, implementarlo y hospedar un servicio dentro de una aplicación administrada, consulte los temas [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md) y [Autohospedaje](../../../../docs/framework/wcf/samples/self-host.md).  
  
 Las siguientes secciones describen escenarios comunes que utilizan esta opción de hospedaje.  
  
## Aplicaciones de consola  
 Los escenarios comunes que habilita el autohospedaje son servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se ejecutan dentro de las aplicaciones de consola. Hospedar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una aplicación de consola es útil, por lo general, durante la fase de desarrollo del servicio. Esto hace que sean fáciles de depurar, de obtener información de seguimiento para averiguar lo que está sucediendo dentro de la aplicación y fáciles de mover copiándolas en nuevas ubicaciones.  
  
## Aplicaciones de cliente complejas  
 Otro escenario común que habilita el autohospedaje es el de aplicaciones de cliente completas, como las basadas en [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] o Windows Forms \(Winforms\). Esta opción de hospedaje también facilita la comunicación de aplicaciones de cliente completas, como [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] y aplicaciones Winforms, con el mundo externo. Por ejemplo, un cliente de colaboración punto a punto que utiliza [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] para su interfaz de usuario y también hospeda un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que permite a otros clientes conectar con él y compartir información.  
  
## Vea también  
 [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)   
 [Tutorial de introducción](../../../../docs/framework/wcf/getting-started-tutorial.md)