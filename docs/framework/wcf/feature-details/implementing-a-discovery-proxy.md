---
title: Implementar un proxy de detección
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 5d9296d8ba70d4c9e8d8339fa3a032d9c4c62826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047066"
---
# <a name="implementing-a-discovery-proxy"></a>Implementar un proxy de detección
Esta sección describe los pasos necesarios para implementar un proxy de detección. Un proxy de detección es un servicio independiente que contiene un repositorio de servicios. Los clientes pueden consultar un proxy de detección para buscar servicios reconocibles que el proxy conoce. El modo en que un proxy se rellena con servicios depende del implementador. Por ejemplo, un proxy de detección puede conectarse a un repositorio de servicio existente y hacer que esa información sea reconocible, un administrador puede utilizar una API de administración para agregar servicios reconocibles a un proxy, o un proxy de detección puede utilizar la funcionalidad de anuncio para actualizar su memoria caché interna.  
  
 La implementación WCF proporciona clases base que le permiten compilar un proxy con facilidad. Puede utilizar estas API para compilar un proxy de detección encima de un repositorio existente.  
  
 El proxy de detección implementado aquí es como cualquier otro servicio de WCF y también puede hacer que el proxy de detección se pueda detectar y que los clientes busquen sus puntos de conexión.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Implementar a un Proxy de detección](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 Describe cómo implementar un proxy de detección.  
  
 [Cómo: Implementar un servicio reconocible que se registra con el Proxy de detección](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Describe cómo implementar un servicio WCF reconocible que se registra con el proxy de detección.  
  
 [Cómo: Implementar una aplicación cliente que utiliza al Proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 Describe cómo implementar una aplicación de cliente WCF que utiliza al proxy de detección para buscar un servicio.  
  
 [Cómo: Probar al Proxy de detección](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 Describe cómo probar el código escrito en los tres temas los anteriores.  
  
## <a name="see-also"></a>Vea también

- [Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)
- [Cómo: Agregar detectabilidad mediante programación a un cliente y servicio WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
