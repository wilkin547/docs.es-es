---
title: Procedimiento para probar el proxy de detección
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: b08e8561ceff9f0a427a9ea9acb2309772579853
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294669"
---
# <a name="how-to-test-the-discovery-proxy"></a>Procedimiento para probar el proxy de detección

Este es el cuarto de cuatro temas que indica cómo implementar un proxy de detección. En el tema anterior, [Cómo: implementar una aplicación cliente que utiliza el proxy de detección para buscar un servicio](client-app-discovery-proxy-to-find-a-service.md), ha implementado una aplicación cliente de WCF que usa el proxy de detección para buscar un servicio y, a continuación, llama al servicio. Este tema describe cómo comprobar el proxy de detección, el servicio y el trabajo de la aplicación cliente según se espera.  
  
### <a name="run-the-discovery-proxy"></a>Ejecución del proxy de detección  
  
1. Abra un símbolo del sistema como administrador.  
  
2. Puede que aparezca un cuadro diálogo que dice: Firewall de Windows bloqueó algunas características de este programa. Si ve este mensaje, haga clic en el botón **desbloquear** .  
  
3. Dentro del símbolo del sistema, ejecute el proxy de detección, DiscoveryProxy.exe.  
  
4. La aplicación debería mostrar el siguiente texto: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Ejecución del servicio reconocible  
  
1. Abra un símbolo del sistema como administrador.  
  
2. Desde el símbolo del sistema, ejecute el servicio reconocible Service.exe.  
  
3. El DiscoveryProxy.exe debe mostrar el siguiente texto: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Ejecución de la aplicación cliente  
  
1. Abra un símbolo del sistema.  
  
2. Dentro del símbolo del sistema, ejecute la aplicación client.exe.  
  
3. Después de unos segundos, la aplicación cliente muestra el siguiente texto: Conectando con [servicio-extremo].  
  
4. A continuación, service.exe debería mostrar el siguiente texto: Solicitud de saludo recibida, responderé.  
  
5. A continuación, client.exe debería mostrar el siguiente texto: Hola, cliente.  
  
### <a name="shut-down-the-applications"></a>Cierre de las aplicaciones  
  
1. Cierre la aplicación cliente.  
  
2. Cierre el servicio. El proxy de detección muestra el siguiente texto: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3. Cierre el proxy de detección.  
  
## <a name="see-also"></a>Vea también

- [Información general de Detección de WCF](wcf-discovery-overview.md)
- [Procedimiento para implementar un proxy de detección](how-to-implement-a-discovery-proxy.md)
- [Procedimiento para implementar un servicio reconocible que se registra con el proxy de detección](discoverable-service-that-registers-with-the-discovery-proxy.md)
- [Procedimiento para implementar una aplicación cliente que usa el proxy de detección para buscar un servicio](client-app-discovery-proxy-to-find-a-service.md)
