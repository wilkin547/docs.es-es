---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 791c5be8aa48db2b17a42a216ad2bf5e7b5a4bc1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189882"
---
# \<caches>

<span data-ttu-id="42439-101">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="42439-101">Registers the caches used for session tokens and token replay detection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**  
  
## <a name="syntax"></a><span data-ttu-id="42439-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42439-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42439-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42439-103">Attributes and Elements</span></span>  

 <span data-ttu-id="42439-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42439-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42439-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="42439-105">Attributes</span></span>  

 <span data-ttu-id="42439-106">None</span><span class="sxs-lookup"><span data-stu-id="42439-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="42439-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42439-107">Child Elements</span></span>  
  
|<span data-ttu-id="42439-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="42439-108">Element</span></span>|<span data-ttu-id="42439-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="42439-109">Description</span></span>|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|<span data-ttu-id="42439-110">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42439-110">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[\<tokenReplayCache>](tokenreplaycache.md)|<span data-ttu-id="42439-111">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42439-111">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42439-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42439-112">Parent Elements</span></span>  
  
|<span data-ttu-id="42439-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="42439-113">Element</span></span>|<span data-ttu-id="42439-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="42439-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="42439-115">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="42439-115">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="42439-116">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="42439-116">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42439-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42439-117">Remarks</span></span>  

 <span data-ttu-id="42439-118">Un `<caches>` elemento se puede especificar en el nivel de servicio bajo el `<identityConfiguration>` elemento o en el nivel de colección de controladores de tokens de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="42439-118">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="42439-119">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="42439-119">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="42439-120">El `<caches>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase.</span><span class="sxs-lookup"><span data-stu-id="42439-120">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="42439-121">La clase representa las memorias caché configuradas <xref:System.IdentityModel.Configuration.IdentityModelCaches> .</span><span class="sxs-lookup"><span data-stu-id="42439-121">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42439-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="42439-122">Example</span></span>  

 <span data-ttu-id="42439-123">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad de la sesión ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ).</span><span class="sxs-lookup"><span data-stu-id="42439-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="42439-124">La configuración se toma del `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="42439-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
