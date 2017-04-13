---
title: "C&#243;mo: Implementar una aplicaci&#243;n de integraci&#243;n de COM+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# C&#243;mo: Implementar una aplicaci&#243;n de integraci&#243;n de COM+
Cuando ha escrito una aplicación de integración de COM\+, puede que desee implementarla en otro equipo.En este tema se describe cómo mover una aplicación de integración de COM\+ de un equipo a otro.  
  
### Mover una aplicación de integración alojada por COM\+  
  
1.  Asegúrese de que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se instala en ambos equipos.  
  
2.  Exportar la aplicación desde el equipo A.  
  
3.  Importar la aplicación en el equipo B.  
  
4.  Establezca el directorio raíz de la aplicación.Por convención, éste es %PROGRAMFILES%\/ComPlus Applications\/{AppGUID}.  
  
5.  Copie los archivos Application.config y Application.manifest del directorio raíz de la aplicación en el equipo A en el directorio raíz de la aplicación en el equipo B.  
  
6.  Modifique las direcciones del extremo de servicio en el archivo Application.config en el equipo B para identificar el equipo adecuado.Por ejemplo, cambie http:\/\/machineA\/MyService a http:\/\/machineB\/MyService.  
  
### Mover una aplicación de integración alojada en Web  
  
1.  Asegúrese de que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se instala en ambos equipos.  
  
2.  Exportar la aplicación desde el equipo A.  
  
3.  Importar la aplicación en el equipo B.  
  
4.  Cree un vroot de IIS en el equipo B.  
  
5.  Copie el archivo .svc \(componentName.svc\) y el archivo Web.config de vroot en el equipo A al vroot recientemente creado en el equipo B.  
  
## Vea también  
 [Integración en la información general de las aplicaciones COM\+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)   
 [Cómo configurar los parámetros de los servicios COM\+](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)   
 [Cómo: Utilizar la herramienta configuración de modelos de servicio COM\+](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)