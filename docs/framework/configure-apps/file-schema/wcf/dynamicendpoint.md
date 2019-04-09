---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187751"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="0c879-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="0c879-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="0c879-102">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c879-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="0c879-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0c879-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0c879-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0c879-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c879-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c879-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c879-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c879-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0c879-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c879-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c879-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c879-108">Attributes</span></span>  
 <span data-ttu-id="0c879-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0c879-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c879-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c879-110">Child Elements</span></span>  
  
|<span data-ttu-id="0c879-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c879-111">Element</span></span>|<span data-ttu-id="0c879-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c879-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c879-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="0c879-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="0c879-114">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="0c879-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c879-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c879-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0c879-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c879-116">Element</span></span>|<span data-ttu-id="0c879-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c879-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c879-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0c879-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="0c879-119">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="0c879-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c879-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c879-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
