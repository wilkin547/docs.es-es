---
title: Implementar un proxy de detección
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: 0c7086e0eecea6cc2d7494d6afda0abf056ba758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492224"
---
# <a name="implementing-a-discovery-proxy"></a>Implementar un proxy de detección
Esta sección describe los pasos necesarios para implementar un proxy de detección. Un proxy de detección es un servicio independiente que contiene un repositorio de servicios. Los clientes pueden consultar un proxy de detección para buscar servicios reconocibles que el proxy conoce. El modo en que un proxy se rellena con servicios depende del implementador. Por ejemplo, un proxy de detección puede conectarse a un repositorio de servicio existente y hacer que esa información sea reconocible, un administrador puede utilizar una API de administración para agregar servicios reconocibles a un proxy, o un proxy de detección puede utilizar la funcionalidad de anuncio para actualizar su memoria caché interna.  
  
 La implementación WCF proporciona clases base que le permiten compilar un proxy con facilidad. Puede utilizar estas API para compilar un proxy de detección encima de un repositorio existente.  
  
 El proxy de detección implementado aquí es como cualquier otro servicio de WCF y también puede hacer que el proxy de detección se pueda detectar y que los clientes busquen sus extremos.  
  
## <a name="in-this-section"></a>En esta sección  
 [Implementación de un proxy de detección](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 Describe cómo implementar un proxy de detección.  
  
 [Implementación de un servicio reconocible que se registra con el proxy de detección](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 Describe cómo implementar un servicio WCF reconocible que se registra con el proxy de detección.  
  
 [Implementación de una aplicación cliente que utiliza el proxy de detección para buscar un servicio](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 Describe cómo implementar una aplicación de cliente WCF que utiliza al proxy de detección para buscar un servicio.  
  
 [Prueba del proxy de detección](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 Describe cómo probar el código escrito en los tres temas los anteriores.  
  
## <a name="see-also"></a>Vea también  
 [Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 [Adición de detectabilidad mediante programación a un cliente y un servicio WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
