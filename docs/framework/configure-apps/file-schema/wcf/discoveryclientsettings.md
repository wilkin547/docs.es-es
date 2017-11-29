---
title: '&lt;discoveryClientSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd2e9f3fd6d2cd0b99c6b63bc8ad0eefc9ff3e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="4a7f7-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="4a7f7-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="4a7f7-103">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="4a7f7-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="4a7f7-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4a7f7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4a7f7-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="4a7f7-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a7f7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a7f7-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" 
                        maxResults="Integer" 
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a7f7-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4a7f7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4a7f7-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4a7f7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a7f7-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="4a7f7-109">Attributes</span></span>  
  
|<span data-ttu-id="4a7f7-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="4a7f7-110">Attribute</span></span>|<span data-ttu-id="4a7f7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a7f7-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a7f7-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="4a7f7-112">discoveryEndpoint</span></span>|<span data-ttu-id="4a7f7-113">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4a7f7-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a7f7-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4a7f7-114">Child Elements</span></span>  
  
|<span data-ttu-id="4a7f7-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a7f7-115">Element</span></span>|<span data-ttu-id="4a7f7-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a7f7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a7f7-117">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="4a7f7-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="4a7f7-118">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="4a7f7-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="4a7f7-119">Criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="4a7f7-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4a7f7-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4a7f7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4a7f7-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a7f7-121">Element</span></span>|<span data-ttu-id="4a7f7-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a7f7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a7f7-123">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="4a7f7-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="4a7f7-124">Define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4a7f7-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a7f7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a7f7-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
