---
title: "Comunicaciones básicas: Compatibilidad de Webhost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 707b97c49d6a6f5262719e91f8cb38fe7da53601
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="core-communications-webhost-support"></a>Comunicaciones básicas: Compatibilidad de Webhost
En este tema se muestran todas las excepciones generadas por la compatibilidad de Webhost.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|Este servicio requiere compatibilidad con ASP.NET. También se debe hospedar en IIS. Hospede el servicio en IIS con la compatibilidad de ASP.NET activada en Web.config o establezca la propiedad AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode en un valor distinto de Requerido.|  
|Hosting_ListenerNotFoundForActivationInRecycling|Ningún canal está realizando escuchas activamente en la dirección especificada. Si se está reciclando una aplicación, se cerrará el servicio.|  
|Hosting_NonHTTPInCompatibilityMode|Los únicos protocolos que se admiten con la compatibilidad de ASP.NET son HTTP y HTTPS. Quite el extremo especificado o deshabilite la compatibilidad de ASP.NET para la aplicación.|  
|Hosting_ProcessNotExecutingUnderHostedContext|No se puede invocar el proceso de alojamiento especificado en el entorno de alojamiento actual. Esta API requiere que la aplicación que realiza la llamada se hospede en Internet Information Services o en el Servicio de activación de procesos de Windows.|  
|Hosting_ServiceCompatibilityRequire|No se puede activar el servicio porque requiere la compatibilidad de ASP.NET. La compatibilidad de ASP.NET no está habilitada para esta aplicación. Habilite la compatibilidad de ASP.NET en archivo Web.config o establezca AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
