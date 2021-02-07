---
description: 'Más información acerca de: control de versiones de detección'
title: Versión de la detección
ms.date: 03/30/2017
ms.assetid: f91c6d0a-3af2-45c5-9a5c-e75390619836
ms.openlocfilehash: 075fefce0477810336c8b857343984070ed89b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743192"
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

Proporcionar <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> como un parámetro de constructor hace que la implementación use la versión April2005 del protocolo WS-Discovery. Esta versión corresponde a la versión publicada de la especificación de protocolo de WS-Discovery. Esta versión se debería utilizar para interoperar con la aplicación heredada que utiliza la versión April2005 de WS-Discovery.

### <a name="discoveryversionwsdiscovery11"></a>DiscoveryVersion.WSDiscovery11

La versión de detección predeterminada que usan las API es <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11> . Ésta es la versión actual normalizada del protocolo de WS-Discovery.

## <a name="discoveryversionwsdiscoverycd1"></a>DiscoveryVersion.WSDiscoveryCD1

Proporcionar <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> como un parámetro de constructor hace que la implementación use la versión del borrador del comité 1 del protocolo de WS-Discovery. Esta versión del protocolo se debería utilizar para interoperar con implementaciones que ejecutan la versión de CD1 del protocolo de WS-Discovery.

## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a>Admitir varios extremos de detección de UDP para diversas versiones de detección en un host de servicio único

Puede desear exponer varios extremos de detección de UDP para las diversas versiones de detección en un único host de servicio. Para ello, debe especificar una dirección única para cada extremo de detección de UDP. El ejemplo siguiente muestra cómo hacerlo.

```csharp
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);

newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionApril2005");

serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);
```
