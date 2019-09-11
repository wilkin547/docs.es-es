---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855415"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="ea05d-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="ea05d-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="ea05d-102">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="ea05d-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="ea05d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ea05d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ea05d-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ea05d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ea05d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="ea05d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="ea05d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="ea05d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="ea05d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="ea05d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="ea05d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> discoveryClientSettings**</span><span class="sxs-lookup"><span data-stu-id="ea05d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea05d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea05d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea05d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea05d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ea05d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea05d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea05d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea05d-112">Attributes</span></span>  
  
|<span data-ttu-id="ea05d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="ea05d-113">Attribute</span></span>|<span data-ttu-id="ea05d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ea05d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea05d-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="ea05d-115">discoveryEndpoint</span></span>|<span data-ttu-id="ea05d-116">Cadena que contiene el nombre del punto de conexión de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ea05d-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea05d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea05d-117">Child Elements</span></span>  
  
|<span data-ttu-id="ea05d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea05d-118">Element</span></span>|<span data-ttu-id="ea05d-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ea05d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea05d-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ea05d-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ea05d-121">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="ea05d-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="ea05d-122">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="ea05d-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ea05d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea05d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ea05d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea05d-124">Element</span></span>|<span data-ttu-id="ea05d-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ea05d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ea05d-126">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ea05d-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ea05d-127">Define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ea05d-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea05d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea05d-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
