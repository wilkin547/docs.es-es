---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 5b60c7281b92a487ba3ee275f7405cb82bd6cd87
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282248"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="fefb9-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="fefb9-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="fefb9-102">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="fefb9-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="fefb9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fefb9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fefb9-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fefb9-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fefb9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fefb9-105">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fefb9-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fefb9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fefb9-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fefb9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fefb9-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="fefb9-108">Attributes</span></span>  
  
|<span data-ttu-id="fefb9-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="fefb9-109">Attribute</span></span>|<span data-ttu-id="fefb9-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fefb9-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fefb9-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="fefb9-111">discoveryEndpoint</span></span>|<span data-ttu-id="fefb9-112">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fefb9-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fefb9-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fefb9-113">Child Elements</span></span>  
  
|<span data-ttu-id="fefb9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="fefb9-114">Element</span></span>|<span data-ttu-id="fefb9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fefb9-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fefb9-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fefb9-116">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fefb9-117">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="fefb9-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="fefb9-118">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="fefb9-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fefb9-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fefb9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fefb9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fefb9-120">Element</span></span>|<span data-ttu-id="fefb9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fefb9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fefb9-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fefb9-122">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fefb9-123">Define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fefb9-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fefb9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="fefb9-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
