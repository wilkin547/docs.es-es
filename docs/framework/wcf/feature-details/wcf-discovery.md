---
title: Detección de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 63c6589cb2ecff9f0a5e7c8bb61b454f6516c98c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600184"
---
# <a name="wcf-discovery"></a>Detección de WCF
Windows Communication Foundation (WCF) proporciona compatibilidad para permitir que los servicios se puedan detectar en tiempo de ejecución de forma interoperable mediante el protocolo WS-Discovery. Los servicios WCF pueden anunciar su disponibilidad a la red mediante un mensaje de multidifusión o un servidor proxy de detección. Las aplicaciones cliente pueden buscar en la red o en un servidor proxy de detección para encontrar servicios que cumplan un conjunto de criterios. Los temas de esta sección proporcionan información general y describen el modelo de programación para esta característica de forma detallada.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general de Detección de WCF](wcf-discovery-overview.md)  
 Proporciona información general sobre la compatibilidad de WS-Discovery proporcionada por WCF.  
  
 [Modelo de objetos de Detección de WCF](wcf-discovery-object-model.md)  
 Describe las clases de modelo de objetos y extensibilidad del soporte de WS-Discovery.  
  
 [Procedimiento para agregar detectabilidad mediante programación a un cliente y un servicio de WCF](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 Muestra cómo hacer que un servicio de Windows Communication Foundation (WCF) sea reconocible.  
  
 [Implementar un proxy de detección](implementing-a-discovery-proxy.md)  
 Describe los pasos necesarios para implementar un proxy de detección, un servicio reconocible que se registra con el proxy de detección, y un cliente que usa el proxy de detección para encontrar el servicio reconocible.  
  
 [Versión de la detección](discovery-versioning.md)  
 Proporciona información general breve sobre una implementación del prototipo de algunas nuevas características de detección. También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.  
  
 [Configurar la detección en un archivo de configuración](configuring-discovery-in-a-configuration-file.md)  
 Muestra cómo configurar detección en la configuración.  
  
 [Usar el canal del cliente de detección](using-the-discovery-client-channel.md)  
 Muestra cómo usar un canal de cliente de detección al escribir una aplicación cliente de WCF.
