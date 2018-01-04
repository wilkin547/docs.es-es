---
title: "Integración de AJAX y compatibilidad de JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd5c84250349f4adaaac68a302d771280328a4e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-integration-and-json-support"></a>Integración de AJAX y compatibilidad de JSON
La compatibilidad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con JavaScript asincrónico y XML (AJAX) de ASP.NET y el formato de datos de la notación de objetos JavaScript (JSON) permiten a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exponer las operaciones a los clientes de AJAX. Los clientes de AJAX son páginas web que ejecutan código JavaScript y obtienen acceso a estos servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando solicitudes HTTP. Los temas de esta sección proporcionan información sobre esta compatibilidad y sobre cómo implementarla.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]AJAX de ASP.NET y su integración con ASP.NET 2.0, vea [información general de AJAX de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=96725).  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de servicios WCF para AJAX de ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 Describe cómo un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede exponer a clientes AJAX agregando el extremo de AJAX adecuado bien mediante configuración o bien mediante el uso de un generador de host de servicio personalizado para generar un host de servicio que configure automáticamente el extremo de AJAX.  
  
 [Creación de servicios AJAX WCF sin ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 Describe cómo crear un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin utilizar ASP.NET.  
  
 [Compatibilidad con JSON y otros formatos de transferencia de datos](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 Describe la compatibilidad del formato de JSON utilizada normalmente (en lugar de XML) para la mensajería con servicios de AJAX de ASP.NET.  
  
 [Migración de servicios web de ASP.NET con AJAX habilitado a WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Describe cómo migrar un servicio web de ASP.NET con AJAX habilitado a un servicio web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [Modelo de programación de web HTTP de WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
