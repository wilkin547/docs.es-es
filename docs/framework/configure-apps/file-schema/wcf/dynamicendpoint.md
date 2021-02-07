---
description: 'Más información acerca de: <dynamicEndpoint>'
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 0fe30492e1daeecca5e27aef844f5f6977396049
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725901"
---
# \<dynamicEndpoint>

<span data-ttu-id="30109-102">Este elemento de configuración define un punto de conexión estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del punto de conexión dinámicamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="30109-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="30109-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30109-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30109-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="30109-104">Attributes and Elements</span></span>  

 <span data-ttu-id="30109-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="30109-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30109-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="30109-106">Attributes</span></span>  

 <span data-ttu-id="30109-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="30109-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30109-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="30109-108">Child Elements</span></span>  
  
|<span data-ttu-id="30109-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="30109-109">Element</span></span>|<span data-ttu-id="30109-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="30109-110">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="30109-111">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="30109-111">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30109-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="30109-112">Parent Elements</span></span>  
  
|<span data-ttu-id="30109-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="30109-113">Element</span></span>|<span data-ttu-id="30109-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="30109-114">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="30109-115">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="30109-115">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30109-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="30109-116">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
