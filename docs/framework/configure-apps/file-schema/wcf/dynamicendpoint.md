---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 3dc7fb19c5c7729620a5d9f3df1111b2dbdacf78
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925833"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="b2e09-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="b2e09-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="b2e09-102">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b2e09-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="b2e09-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b2e09-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b2e09-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="b2e09-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2e09-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2e09-105">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2e09-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b2e09-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b2e09-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b2e09-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2e09-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b2e09-108">Attributes</span></span>  
 <span data-ttu-id="b2e09-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b2e09-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b2e09-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b2e09-110">Child Elements</span></span>  
  
|<span data-ttu-id="b2e09-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2e09-111">Element</span></span>|<span data-ttu-id="b2e09-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2e09-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2e09-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="b2e09-113">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="b2e09-114">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="b2e09-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b2e09-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b2e09-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b2e09-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b2e09-116">Element</span></span>|<span data-ttu-id="b2e09-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2e09-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b2e09-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="b2e09-118">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="b2e09-119">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="b2e09-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2e09-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2e09-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
