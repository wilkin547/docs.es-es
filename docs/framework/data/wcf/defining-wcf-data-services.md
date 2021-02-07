---
description: Más información acerca de cómo definir Servicios de datos de WCF
title: Definir Servicios de datos de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: 43a4887226b03e80c4a966a118f210fe8a28000d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766093"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="314c9-103">Definir Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="314c9-103">Defining WCF Data Services</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="314c9-104">En esta sección se describe cómo crear y configurar Servicios de datos de WCF para exponer datos como una fuente de Open Data Protocol (OData).</span><span class="sxs-lookup"><span data-stu-id="314c9-104">This section describes how to create and configure WCF Data Services to expose data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="314c9-105">Para obtener más información sobre los pasos básicos necesarios para crear un servicio de datos, vea [exponer los datos como un servicio](exposing-your-data-as-a-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="314c9-105">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="314c9-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="314c9-106">In This Section</span></span>

 [<span data-ttu-id="314c9-107">Configuración del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="314c9-107">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="314c9-108">Describe las opciones de configuración del servicio de datos proporcionadas por Servicios de datos de WCF.</span><span class="sxs-lookup"><span data-stu-id="314c9-108">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="314c9-109">Proveedores de Data Services</span><span class="sxs-lookup"><span data-stu-id="314c9-109">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)

 <span data-ttu-id="314c9-110">Describe los modelos de proveedor para exponer datos como un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="314c9-110">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="314c9-111">Operaciones del servicio</span><span class="sxs-lookup"><span data-stu-id="314c9-111">Service Operations</span></span>](service-operations-wcf-data-services.md)

 <span data-ttu-id="314c9-112">Describe cómo definir operaciones de servicio que exponen métodos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="314c9-112">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="314c9-113">Personalización de fuentes</span><span class="sxs-lookup"><span data-stu-id="314c9-113">Feed Customization</span></span>](feed-customization-wcf-data-services.md)

 <span data-ttu-id="314c9-114">Describe cómo crear una asignación entre las entidades del modelo de datos definidas por el proveedor del servicio de datos y los elementos de la fuente de distribución de datos.</span><span class="sxs-lookup"><span data-stu-id="314c9-114">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="314c9-115">Interceptores</span><span class="sxs-lookup"><span data-stu-id="314c9-115">Interceptors</span></span>](interceptors-wcf-data-services.md)

 <span data-ttu-id="314c9-116">Describe cómo definir métodos de interceptor para ejecutar lógica de negocios personalizada en solicitudes al servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="314c9-116">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="314c9-117">Desarrollo e implementación de Servicios de datos de WCF</span><span class="sxs-lookup"><span data-stu-id="314c9-117">Developing and Deploying WCF Data Services</span></span>](developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="314c9-118">Describe cómo desarrollar e implementar un servicio de datos con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="314c9-118">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="314c9-119">Proteger WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="314c9-119">Securing WCF Data Services</span></span>](securing-wcf-data-services.md)

 <span data-ttu-id="314c9-120">Describe la autenticación y la autorización del servicio de datos y otras consideraciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="314c9-120">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="314c9-121">Hospedaje del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="314c9-121">Hosting the Data Service</span></span>](hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="314c9-122">Describe cómo seleccionar un host para un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="314c9-122">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="314c9-123">Control de versiones del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="314c9-123">Data Service Versioning</span></span>](data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="314c9-124">Describe cómo trabajar con versiones diferentes de OData.</span><span class="sxs-lookup"><span data-stu-id="314c9-124">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="314c9-125">Detalles de implementación del protocolo WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="314c9-125">WCF Data Services Protocol Implementation Details</span></span>](wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="314c9-126">Describe las funcionalidades opcionales del protocolo OData que no implementa actualmente Servicios de datos de WCF.</span><span class="sxs-lookup"><span data-stu-id="314c9-126">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="314c9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="314c9-127">See also</span></span>

- [<span data-ttu-id="314c9-128">Biblioteca cliente de Data Services de WCF</span><span class="sxs-lookup"><span data-stu-id="314c9-128">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="314c9-129">Acceso a recursos de servicios de datos</span><span class="sxs-lookup"><span data-stu-id="314c9-129">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="314c9-130">Introducción</span><span class="sxs-lookup"><span data-stu-id="314c9-130">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
