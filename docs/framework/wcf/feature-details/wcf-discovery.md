---
title: Detección de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 175f79096d2bbda81a602d38e027d5a6d871fa12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497963"
---
# <a name="wcf-discovery"></a><span data-ttu-id="11ead-102">Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="11ead-102">WCF Discovery</span></span>
<span data-ttu-id="11ead-103">Windows Communication Foundation (WCF) proporciona compatibilidad para habilitar los servicios para que sea reconocible en tiempo de ejecución de una manera interoperable mediante el protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="11ead-103">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="11ead-104">Los servicios de WCF pueden anunciar su disponibilidad a la red mediante un mensaje de multidifusión o a un servidor de proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="11ead-104">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="11ead-105">Las aplicaciones cliente pueden buscar en la red o en un servidor proxy de detección para encontrar servicios que cumplan un conjunto de criterios.</span><span class="sxs-lookup"><span data-stu-id="11ead-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="11ead-106">Los temas de esta sección proporcionan información general y describen el modelo de programación para esta característica de forma detallada.</span><span class="sxs-lookup"><span data-stu-id="11ead-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11ead-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11ead-107">In This Section</span></span>  
 [<span data-ttu-id="11ead-108">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="11ead-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="11ead-109">Proporciona información general sobre la compatibilidad de WS-Discovery proporcionada por WCF.</span><span class="sxs-lookup"><span data-stu-id="11ead-109">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="11ead-110">Modelo de objetos de detección de WCF</span><span class="sxs-lookup"><span data-stu-id="11ead-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="11ead-111">Describe las clases de modelo de objetos y extensibilidad del soporte de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="11ead-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="11ead-112">Adición de detectabilidad mediante programación a un cliente y un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="11ead-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="11ead-113">Muestra cómo hacer que un servicio de Windows Communication Foundation (WCF) pueda detectar.</span><span class="sxs-lookup"><span data-stu-id="11ead-113">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="11ead-114">Implementación de un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="11ead-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="11ead-115">Describe los pasos necesarios para implementar un proxy de detección, un servicio reconocible que se registra con el proxy de detección, y un cliente que usa el proxy de detección para encontrar el servicio reconocible.</span><span class="sxs-lookup"><span data-stu-id="11ead-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="11ead-116">Versión de la detección</span><span class="sxs-lookup"><span data-stu-id="11ead-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="11ead-117">Proporciona información general breve sobre una implementación del prototipo de algunas nuevas características de detección.</span><span class="sxs-lookup"><span data-stu-id="11ead-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="11ead-118">También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.</span><span class="sxs-lookup"><span data-stu-id="11ead-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="11ead-119">Configuración de la detección en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="11ead-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="11ead-120">Muestra cómo configurar detección en la configuración.</span><span class="sxs-lookup"><span data-stu-id="11ead-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="11ead-121">Uso del canal del cliente de detección</span><span class="sxs-lookup"><span data-stu-id="11ead-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="11ead-122">Muestra cómo utilizar un canal de cliente de detección al escribir una aplicación de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="11ead-122">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
