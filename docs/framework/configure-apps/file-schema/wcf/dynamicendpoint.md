---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: dcb52143c874b14c9241940f9b326a07b3fa6a82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540262"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="66a6e-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="66a6e-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="66a6e-103">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="66a6e-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="66a6e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="66a6e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="66a6e-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="66a6e-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a6e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66a6e-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66a6e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="66a6e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="66a6e-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="66a6e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66a6e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="66a6e-109">Attributes</span></span>  
 <span data-ttu-id="66a6e-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="66a6e-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66a6e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="66a6e-111">Child Elements</span></span>  
  
|<span data-ttu-id="66a6e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="66a6e-112">Element</span></span>|<span data-ttu-id="66a6e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="66a6e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66a6e-114">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="66a6e-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="66a6e-115">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="66a6e-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66a6e-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="66a6e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="66a6e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="66a6e-117">Element</span></span>|<span data-ttu-id="66a6e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="66a6e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66a6e-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="66a6e-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="66a6e-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="66a6e-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66a6e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="66a6e-121">See also</span></span>
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
