---
title: Versión de la detección
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 3f90fc5183e974b9045c156e0ae74099abfbc41a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626959"
---
# <a name="discovery-versioning"></a>Versión de la detección
Este tema proporciona información general breve sobre la implementación de algunas nuevas características de detección. También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.  
  
## <a name="discovery-versioning"></a>Versión de la detección  
 La característica de detección incluye soporte para tres versiones del protocolo de WS-Discovery. Las API de detección le permiten seleccionar qué versión del protocolo desea utilizar. Este documento describe brevemente la configuración relacionada con la versión.  
  
 Las siguientes clases de detección tienen una propiedad <xref:System.ServiceModel.Discovery.DiscoveryVersion> ahora y toman un argumento <xref:System.ServiceModel.Discovery.DiscoveryVersion> en sus constructores:  
  
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
### <a name="discoveryversionwsdiscoveryapril2005"></a>DiscoveryVersion.WSDiscoveryApril2005  
 Proporcionar <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> como un constructor de parámetro hace que la implementación use la versión April2005 del protocolo WS-Discovery. Esta versión corresponde a la versión publicada de la especificación de protocolo de WS-Discovery. Esta versión se debería utilizar para interoperar con la aplicación heredada que utiliza la versión April2005 de WS-Discovery.  
  
### <a name="discoveryversionwsdiscovery11"></a>DiscoveryVersion.WSDiscovery11  
 Es la versión de detección predeterminada utilizada por las API <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>. Ésta es la versión actual normalizada del protocolo de WS-Discovery.  
  
## <a name="discoveryversionwsdiscoverycd1"></a>DiscoveryVersion.WSDiscoveryCD1  
 Proporcionar <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> como un parámetro de constructor hace que la implementación use la versión del borrador del comité 1 del protocolo de WS-Discovery. Esta versión del protocolo se debería utilizar para interoperar con implementaciones que ejecutan la versión de CD1 del protocolo de WS-Discovery.  
  
## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a>Admitir varios extremos de detección de UDP para diversas versiones de detección en un host de servicio único  
 Puede desear exponer varios extremos de detección de UDP para las diversas versiones de detección en un único host de servicio. Para ello, debe especificar una dirección única para cada extremo de detección de UDP. En el ejemplo siguiente se muestra cómo hacerlo.  
  
```  
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);  
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
  
newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");  
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionAril2005");  
  
serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);  
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);  
```
