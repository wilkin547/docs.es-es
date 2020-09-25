---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 6f9cb127deb5651ed27a0ef5802512fb5b6c7b54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190103"
---
# \<dynamicEndpoint>

<span data-ttu-id="7eee5-101">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7eee5-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="7eee5-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7eee5-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7eee5-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7eee5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="7eee5-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7eee5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7eee5-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="7eee5-105">Attributes</span></span>  

 <span data-ttu-id="7eee5-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7eee5-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7eee5-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7eee5-107">Child Elements</span></span>  
  
|<span data-ttu-id="7eee5-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="7eee5-108">Element</span></span>|<span data-ttu-id="7eee5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7eee5-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="7eee5-110">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="7eee5-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7eee5-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7eee5-111">Parent Elements</span></span>  
  
|<span data-ttu-id="7eee5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="7eee5-112">Element</span></span>|<span data-ttu-id="7eee5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7eee5-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="7eee5-114">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="7eee5-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7eee5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7eee5-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
