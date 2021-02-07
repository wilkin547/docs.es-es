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
# <a name="discovery-versioning"></a><span data-ttu-id="f0e66-103">Versión de la detección</span><span class="sxs-lookup"><span data-stu-id="f0e66-103">Discovery Versioning</span></span>

<span data-ttu-id="f0e66-104">Este tema proporciona información general breve sobre la implementación de algunas nuevas características de detección.</span><span class="sxs-lookup"><span data-stu-id="f0e66-104">This topic provides a brief overview of the implementation of some new discovery features.</span></span> <span data-ttu-id="f0e66-105">También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.</span><span class="sxs-lookup"><span data-stu-id="f0e66-105">It also gives an overview on how to select the discovery version to use.</span></span>

## <a name="discovery-versioning"></a><span data-ttu-id="f0e66-106">Versión de la detección</span><span class="sxs-lookup"><span data-stu-id="f0e66-106">Discovery Versioning</span></span>

<span data-ttu-id="f0e66-107">La característica de detección incluye soporte para tres versiones del protocolo de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-107">The discovery feature includes support for three versions of the WS_Discovery protocol.</span></span> <span data-ttu-id="f0e66-108">Las API de detección le permiten seleccionar qué versión del protocolo desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="f0e66-108">The discovery APIs allow you to select which version of the protocol you want to use.</span></span> <span data-ttu-id="f0e66-109">Este documento describe brevemente la configuración relacionada con la versión.</span><span class="sxs-lookup"><span data-stu-id="f0e66-109">This document briefly describes the versioning-related settings.</span></span>

<span data-ttu-id="f0e66-110">Las siguientes clases de detección tienen una propiedad <xref:System.ServiceModel.Discovery.DiscoveryVersion> ahora y toman un argumento <xref:System.ServiceModel.Discovery.DiscoveryVersion> en sus constructores:</span><span class="sxs-lookup"><span data-stu-id="f0e66-110">The following Discovery classes now have a <xref:System.ServiceModel.Discovery.DiscoveryVersion> property and take a <xref:System.ServiceModel.Discovery.DiscoveryVersion> argument in their constructors:</span></span>

- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>

- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>

- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>

### <a name="discoveryversionwsdiscoveryapril2005"></a><span data-ttu-id="f0e66-111">DiscoveryVersion.WSDiscoveryApril2005</span><span class="sxs-lookup"><span data-stu-id="f0e66-111">DiscoveryVersion.WSDiscoveryApril2005</span></span>

<span data-ttu-id="f0e66-112">Proporcionar <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> como un parámetro de constructor hace que la implementación use la versión April2005 del protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-112">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryApril2005> as a constructor parameter makes the implementation use the April2005 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="f0e66-113">Esta versión corresponde a la versión publicada de la especificación de protocolo de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-113">This version corresponds to the published version of the WS-Discovery protocol specification.</span></span> <span data-ttu-id="f0e66-114">Esta versión se debería utilizar para interoperar con la aplicación heredada que utiliza la versión April2005 de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-114">This version should be used to interoperate with legacy application utilizing the April2005 version of WS-Discovery.</span></span>

### <a name="discoveryversionwsdiscovery11"></a><span data-ttu-id="f0e66-115">DiscoveryVersion.WSDiscovery11</span><span class="sxs-lookup"><span data-stu-id="f0e66-115">DiscoveryVersion.WSDiscovery11</span></span>

<span data-ttu-id="f0e66-116">La versión de detección predeterminada que usan las API es <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11> .</span><span class="sxs-lookup"><span data-stu-id="f0e66-116">The default discovery version used by the APIs is <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscovery11>.</span></span> <span data-ttu-id="f0e66-117">Ésta es la versión actual normalizada del protocolo de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-117">This is the current standardized version of the WS-Discovery protocol.</span></span>

## <a name="discoveryversionwsdiscoverycd1"></a><span data-ttu-id="f0e66-118">DiscoveryVersion.WSDiscoveryCD1</span><span class="sxs-lookup"><span data-stu-id="f0e66-118">DiscoveryVersion.WSDiscoveryCD1</span></span>

<span data-ttu-id="f0e66-119">Proporcionar <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> como un parámetro de constructor hace que la implementación use la versión del borrador del comité 1 del protocolo de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-119">Providing <xref:System.ServiceModel.Discovery.DiscoveryVersion.WSDiscoveryCD1> as a constructor parameter makes the implementation use the committee draft 1 version of the WS-Discovery protocol.</span></span> <span data-ttu-id="f0e66-120">Esta versión del protocolo se debería utilizar para interoperar con implementaciones que ejecutan la versión de CD1 del protocolo de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="f0e66-120">This version of the protocol should be used to interoperate with implementations running the CD1 version of the WS-Discovery protocol.</span></span>

## <a name="supporting-multiple-udp-discovery-endpoints-for-different-discovery-versions-on-a-single-service-host"></a><span data-ttu-id="f0e66-121">Admitir varios extremos de detección de UDP para diversas versiones de detección en un host de servicio único</span><span class="sxs-lookup"><span data-stu-id="f0e66-121">Supporting Multiple UDP Discovery Endpoints for Different Discovery Versions on a Single Service Host</span></span>

<span data-ttu-id="f0e66-122">Puede desear exponer varios extremos de detección de UDP para las diversas versiones de detección en un único host de servicio.</span><span class="sxs-lookup"><span data-stu-id="f0e66-122">You may want to expose multiple UDP Discovery Endpoints for different discovery versions on a single service host.</span></span> <span data-ttu-id="f0e66-123">Para ello, debe especificar una dirección única para cada extremo de detección de UDP.</span><span class="sxs-lookup"><span data-stu-id="f0e66-123">To do this you must specify a unique address for each UDP discovery endpoint.</span></span> <span data-ttu-id="f0e66-124">El ejemplo siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f0e66-124">The following example shows how to do this.</span></span>

```csharp
UdpDiscoveryEndpoint newVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscovery11);
UdpDiscoveryEndpoint oldVersionUdpEndpoint = new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);

newVersionUdpEndpoint.Address = new EndpointAddress(newVersionUdpEndpoint.Address.Uri.ToString() + "/version11");
oldVersionUdpEndpoint.Address = new EndpointAddress(oldVersionUdpEndpoint.Address.Uri.ToString() + "/versionApril2005");

serviceHost.AddServiceEndpoint(newVersionUdpEndpoint);
serviceHost.AddServiceEndpoint(oldVersionUdpEndpoint);
```
