---
title: "Comunicaciones b&#225;sicas: Compatibilidad de Webhost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Comunicaciones b&#225;sicas: Compatibilidad de Webhost
En este tema se muestran todas las excepciones generadas por la compatibilidad de Webhost.  
  
## Lista de excepción  
  
|Código de recurso|Cadena de recurso|  
|-----------------------|-----------------------|  
|Hosting\_CompatibilityServiceNotHosted|Este servicio requiere compatibilidad con ASP.NET.También se debe hospedar en IIS.Hospede el servicio en IIS con la compatibilidad de ASP.NET activada en Web.config o establezca la propiedad AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode en un valor distinto de Requerido.|  
|Hosting\_ListenerNotFoundForActivationInRecycling|Ningún canal está realizando escuchas activamente en la dirección especificada.Si se está reciclando una aplicación, se cerrará el servicio.|  
|Hosting\_NonHTTPInCompatibilityMode|Los únicos protocolos que se admiten con la compatibilidad de ASP.NET son HTTP y HTTPS.Quite el extremo especificado o deshabilite la compatibilidad de ASP.NET para la aplicación.|  
|Hosting\_ProcessNotExecutingUnderHostedContext|No se puede invocar el proceso de alojamiento especificado en el entorno de alojamiento actual.Esta API requiere que la aplicación que realiza la llamada se hospede en Internet Information Services o en el Servicio de activación de procesos de Windows.|  
|Hosting\_ServiceCompatibilityRequire|No se puede activar el servicio porque requiere la compatibilidad de ASP.NET.La compatibilidad de ASP.NET no está habilitada para esta aplicación.Habilite la compatibilidad de ASP.NET en archivo Web.config o establezca AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|