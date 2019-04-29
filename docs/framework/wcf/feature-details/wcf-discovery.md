---
title: Detección de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768698"
---
# <a name="wcf-discovery"></a>Detección de WCF
Windows Communication Foundation (WCF) proporciona compatibilidad para habilitar los servicios que se pueda detectar en tiempo de ejecución de una manera interoperable mediante el protocolo WS-Discovery. Los servicios de WCF pueden anunciar su disponibilidad a la red mediante un mensaje de multidifusión o a un servidor proxy de detección. Las aplicaciones cliente pueden buscar en la red o en un servidor proxy de detección para encontrar servicios que cumplan un conjunto de criterios. Los temas de esta sección proporcionan información general y describen el modelo de programación para esta característica de forma detallada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general de Detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 Proporciona información general de compatibilidad de WS-Discovery proporcionado por WCF.  
  
 [Modelo de objetos de detección de WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 Describe las clases de modelo de objetos y extensibilidad del soporte de WS-Discovery.  
  
 [Cómo: Agregar detectabilidad mediante programación a un cliente y servicio WCF](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Se muestra cómo hacer que un servicio de Windows Communication Foundation (WCF) que pueda detectar.  
  
 [Implementación de un proxy de detección](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 Describe los pasos necesarios para implementar un proxy de detección, un servicio reconocible que se registra con el proxy de detección, y un cliente que usa el proxy de detección para encontrar el servicio reconocible.  
  
 [Versión de la detección](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 Proporciona información general breve sobre una implementación del prototipo de algunas nuevas características de detección. También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.  
  
 [Configuración de la detección en un archivo de configuración](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 Muestra cómo configurar detección en la configuración.  
  
 [Uso del canal del cliente de detección](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 Muestra cómo utilizar un canal de cliente de detección al escribir una aplicación de cliente WCF.
