---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855346"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="504c0-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="504c0-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="504c0-102">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="504c0-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="504c0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="504c0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="504c0-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="504c0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="504c0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="504c0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="504c0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> dynamicEndpoint**</span><span class="sxs-lookup"><span data-stu-id="504c0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="504c0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="504c0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="504c0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="504c0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="504c0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="504c0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="504c0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="504c0-110">Attributes</span></span>  
 <span data-ttu-id="504c0-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="504c0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="504c0-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="504c0-112">Child Elements</span></span>  
  
|<span data-ttu-id="504c0-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="504c0-113">Element</span></span>|<span data-ttu-id="504c0-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="504c0-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="504c0-115">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="504c0-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="504c0-116">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="504c0-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="504c0-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="504c0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="504c0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="504c0-118">Element</span></span>|<span data-ttu-id="504c0-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="504c0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="504c0-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="504c0-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="504c0-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="504c0-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="504c0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="504c0-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
