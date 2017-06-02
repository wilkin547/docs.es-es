---
title: "Integraci&#243;n de AJAX y compatibilidad de JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Integración de AJAX y compatibilidad con JSON [WCF]"
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Integraci&#243;n de AJAX y compatibilidad de JSON
La compatibilidad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con JavaScript asincrónico y XML \(AJAX\) y el formato de datos de la notación de objetos JavaScript \(JSON\) permiten a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exponer operaciones a los clientes de AJAX.Los clientes de AJAX son páginas web que ejecutan código JavaScript y obtienen acceso a estos servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante solicitudes HTTP.Los temas de esta sección proporcionan información sobre esta compatibilidad y sobre cómo implementarla.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] AJAX de ASP.NET y su integración con ASP.NET 2.0, vea [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).  
  
## En esta sección  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 Describe cómo un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede exponer a clientes AJAX agregando el extremo de AJAX adecuado bien mediante configuración o bien mediante el uso de un generador de host de servicio personalizado para generar un host de servicio que configure automáticamente el extremo de AJAX.  
  
 [Creación de servicios AJAX WCF sin ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 Describe cómo crear un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin utilizar ASP.NET.  
  
 [Compatibilidad con JSON y otros formatos de transferencia de datos](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 Describe la compatibilidad del formato de JSON utilizada normalmente \(en lugar de XML\) para la mensajería con servicios de AJAX de ASP.NET.  
  
 [Cómo migrar servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Describe cómo migrar un servicio web de ASP.NET con AJAX habilitado a un servicio web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Vea también  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>   
 [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)