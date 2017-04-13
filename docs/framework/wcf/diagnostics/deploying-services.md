---
title: "Desarrollo de servicios | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Desarrollo de servicios
Este tema describe cómo puede implementar una aplicación [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] a un entorno en tiempo de ejecución.  
  
## Elegir el entorno de alojamiento para su aplicación  
 Los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] están diseñados para ejecutarse en cualquier proceso de Windows que admite código administrado.Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración.Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server \(IIS\), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows \(WAS\).Para revisar las diferentes opciones de alojamiento para su aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], consulte [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
## Vea también  
 [Hospedaje](../../../../docs/framework/wcf/feature-details/hosting.md)   
 [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)