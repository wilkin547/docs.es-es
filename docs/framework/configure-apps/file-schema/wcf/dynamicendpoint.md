---
title: '&lt;DynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 78ec2d4639161f8e10105f205576f052c8a5567c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146841"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="e2ae3-102">&lt;DynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="e2ae3-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="e2ae3-103">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e2ae3-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="e2ae3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e2ae3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2ae3-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e2ae3-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ae3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2ae3-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2ae3-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e2ae3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e2ae3-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e2ae3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2ae3-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2ae3-109">Attributes</span></span>  
 <span data-ttu-id="e2ae3-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e2ae3-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2ae3-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e2ae3-111">Child Elements</span></span>  
  
|<span data-ttu-id="e2ae3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2ae3-112">Element</span></span>|<span data-ttu-id="e2ae3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2ae3-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2ae3-114">\<discoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="e2ae3-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="e2ae3-115">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="e2ae3-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2ae3-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e2ae3-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e2ae3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2ae3-117">Element</span></span>|<span data-ttu-id="e2ae3-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2ae3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2ae3-119">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e2ae3-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e2ae3-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="e2ae3-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2ae3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ae3-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
