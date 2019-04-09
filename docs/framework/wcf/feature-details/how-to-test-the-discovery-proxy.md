---
title: Filtrar para probar el proxy de detección
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 13d2e8ca46e634e3b27c8eb967d89d860df1c72d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176285"
---
# <a name="how-to-test-the-discovery-proxy"></a>Filtrar para probar el proxy de detección
Este es el cuarto de cuatro temas que indica cómo implementar un proxy de detección. En el tema anterior, [Cómo: Implementar una aplicación cliente que utiliza el Proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), implementa una aplicación de cliente WCF que usa el proxy de detección para buscar un servicio y, a continuación, llama al servicio. Este tema describe cómo comprobar el proxy de detección, el servicio y el trabajo de la aplicación cliente según se espera.  
  
### <a name="run-the-discovery-proxy"></a>Ejecución del proxy de detección  
  
1.  Abra un símbolo del sistema como administrador.  
  
2.  Es posible que vea un cuadro de diálogo que dice: Firewall de Windows bloqueó algunas características de este programa. Si ve este mensaje, haga clic en el **desbloquear** botón.  
  
3.  Dentro del símbolo del sistema, ejecute el proxy de detección, DiscoveryProxy.exe.  
  
4.  La aplicación debería mostrar el siguiente texto: `Proxy started. Hit Enter to exit`.  
  
### <a name="run-the-discoverable-service"></a>Ejecución del servicio reconocible  
  
1.  Abra un símbolo del sistema como administrador.  
  
2.  Desde el símbolo del sistema, ejecute el servicio reconocible Service.exe.  
  
3.  DiscoveryProxy.exe debería mostrar el siguiente texto: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .  
  
### <a name="run-the-client-application"></a>Ejecución de la aplicación cliente  
  
1.  Abra un símbolo del sistema.  
  
2.  Dentro del símbolo del sistema, ejecute la aplicación client.exe.  
  
3.  Después de unos segundos, la aplicación cliente muestra el texto siguiente: Conectando con [servicio-punto de conexión].  
  
4.  Service.exe, a continuación, se debe mostrar el texto siguiente: Solicitud de saludo recibida, responderé.  
  
5.  Client.exe, a continuación, se debe mostrar el texto siguiente: ¡Cliente de Hello!  
  
### <a name="shut-down-the-applications"></a>Cierre de las aplicaciones  
  
1.  Cierre la aplicación cliente.  
  
2.  Cierre el servicio. El proxy de detección muestra el siguiente texto: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.  
  
3.  Cierre el proxy de detección.  
  
## <a name="see-also"></a>Vea también

- [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Filtrar para implementar un proxy de detección](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [Filtrar para implementar un servicio reconocible que se registra con el proxy de detección](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [Filtrar para implementar una aplicación cliente que usa el proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
