---
description: 'Más información acerca de: <discoveryClientSettings>'
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: c2fda0dea33ffd6dbca24881eefab2e54e361f92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802299"
---
# \<discoveryClientSettings>

<span data-ttu-id="4d50e-102">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="4d50e-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="4d50e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d50e-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d50e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d50e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="4d50e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d50e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d50e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d50e-106">Attributes</span></span>  
  
|<span data-ttu-id="4d50e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="4d50e-107">Attribute</span></span>|<span data-ttu-id="4d50e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d50e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d50e-109">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="4d50e-109">discoveryEndpoint</span></span>|<span data-ttu-id="4d50e-110">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4d50e-110">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d50e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d50e-111">Child Elements</span></span>  
  
|<span data-ttu-id="4d50e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d50e-112">Element</span></span>|<span data-ttu-id="4d50e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d50e-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="4d50e-114">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="4d50e-114">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="4d50e-115">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="4d50e-115">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4d50e-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d50e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4d50e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d50e-117">Element</span></span>|<span data-ttu-id="4d50e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d50e-118">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="4d50e-119">Define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4d50e-119">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d50e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d50e-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
