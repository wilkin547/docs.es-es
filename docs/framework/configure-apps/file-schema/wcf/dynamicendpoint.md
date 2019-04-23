---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187751"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="a569d-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="a569d-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="a569d-102">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a569d-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="a569d-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a569d-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a569d-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a569d-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a569d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a569d-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a569d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a569d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a569d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a569d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a569d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a569d-108">Attributes</span></span>  
 <span data-ttu-id="a569d-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a569d-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a569d-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a569d-110">Child Elements</span></span>  
  
|<span data-ttu-id="a569d-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a569d-111">Element</span></span>|<span data-ttu-id="a569d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a569d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a569d-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="a569d-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="a569d-114">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="a569d-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a569d-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a569d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a569d-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a569d-116">Element</span></span>|<span data-ttu-id="a569d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a569d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a569d-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="a569d-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="a569d-119">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="a569d-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a569d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a569d-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
