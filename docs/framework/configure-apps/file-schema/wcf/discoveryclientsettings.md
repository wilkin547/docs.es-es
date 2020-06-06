---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855415"
---
# \<discoveryClientSettings>
<span data-ttu-id="efb76-101">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="efb76-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="efb76-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efb76-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efb76-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="efb76-103">Attributes and Elements</span></span>  
 <span data-ttu-id="efb76-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="efb76-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efb76-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="efb76-105">Attributes</span></span>  
  
|<span data-ttu-id="efb76-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="efb76-106">Attribute</span></span>|<span data-ttu-id="efb76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="efb76-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="efb76-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="efb76-108">discoveryEndpoint</span></span>|<span data-ttu-id="efb76-109">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="efb76-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efb76-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="efb76-110">Child Elements</span></span>  
  
|<span data-ttu-id="efb76-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="efb76-111">Element</span></span>|<span data-ttu-id="efb76-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="efb76-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="efb76-113">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="efb76-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="efb76-114">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="efb76-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="efb76-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="efb76-115">Parent Elements</span></span>  
  
|<span data-ttu-id="efb76-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="efb76-116">Element</span></span>|<span data-ttu-id="efb76-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="efb76-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="efb76-118">Define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="efb76-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efb76-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efb76-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
