---
title: "C&#243;mo: Probar el proxy de detecci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# C&#243;mo: Probar el proxy de detecci&#243;n
Este es el cuarto de cuatro temas que indica cómo implementar un proxy de detección.  En el tema anterior, [Cómo: Implementar una aplicación cliente que utiliza el proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), implementó una aplicación cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utiliza el proxy de detección para encontrar un servicio y, a continuación, llama al servicio.  Este tema describe cómo comprobar el proxy de detección, el servicio y el trabajo de la aplicación cliente según se espera.  
  
### Ejecución del proxy de detección  
  
1.  Abra un símbolo del sistema como administrador.  
  
2.  Puede que aparezca un cuadro diálogo que dice: Firewall de Windows bloqueó algunas características de este programa.  Si ve este mensaje, haga clic en el botón **Desbloquear**.  
  
3.  Dentro del símbolo del sistema, ejecute el proxy de detección, DiscoveryProxy.exe.  
  
4.  La aplicación debería mostrar el siguiente texto: `Proxy started. Hit Enter to exit`.  
  
### Ejecución del servicio reconocible  
  
1.  Abra un símbolo del sistema como administrador.  
  
2.  Desde el símbolo del sistema, ejecute el servicio reconocible Service.exe.  
  
3.  DiscoveryProxy.exe debería mostrar el siguiente texto: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### Ejecución de la aplicación cliente  
  
1.  Abra un símbolo del sistema.  
  
2.  Dentro del símbolo del sistema, ejecute la aplicación client.exe.  
  
3.  Después de unos segundos, la aplicación cliente muestra el siguiente texto: Conectando con \[servicio\-extremo\].  
  
4.  A continuación, service.exe debería mostrar el siguiente texto: Solicitud de saludo recibida, responderé.  
  
5.  A continuación, client.exe debería mostrar el siguiente texto: Hola, cliente.  
  
### Cierre de las aplicaciones  
  
1.  Cierre la aplicación cliente.  
  
2.  Cierre el servicio.  El proxy de detección muestra el siguiente texto: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3.  Cierre el proxy de detección.  
  
## Vea también  
 [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [Cómo: Implementar un proxy de detección](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)   
 [Cómo: Implementar un servicio reconocible que se registra con el proxy de detección](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)   
 [Cómo: Implementar una aplicación cliente que utiliza el proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)