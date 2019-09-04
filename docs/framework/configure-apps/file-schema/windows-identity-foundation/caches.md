---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252160"
---
# <a name="caches"></a><span data-ttu-id="20fb4-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="20fb4-101">\<caches></span></span>
<span data-ttu-id="20fb4-102">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="20fb4-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
<span data-ttu-id="20fb4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="20fb4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="20fb4-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="20fb4-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="20fb4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="20fb4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="20fb4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<almacena en caché >**</span><span class="sxs-lookup"><span data-stu-id="20fb4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<caches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20fb4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20fb4-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20fb4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20fb4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="20fb4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20fb4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20fb4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="20fb4-110">Attributes</span></span>  
 <span data-ttu-id="20fb4-111">None</span><span class="sxs-lookup"><span data-stu-id="20fb4-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20fb4-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20fb4-112">Child Elements</span></span>  
  
|<span data-ttu-id="20fb4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="20fb4-113">Element</span></span>|<span data-ttu-id="20fb4-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="20fb4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20fb4-115">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="20fb4-115">\<sessionSecurityTokenCache></span></span>](sessionsecuritytokencache.md)|<span data-ttu-id="20fb4-116">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="20fb4-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="20fb4-117">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="20fb4-117">\<tokenReplayCache></span></span>](tokenreplaycache.md)|<span data-ttu-id="20fb4-118">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="20fb4-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20fb4-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20fb4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="20fb4-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="20fb4-120">Element</span></span>|<span data-ttu-id="20fb4-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="20fb4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20fb4-122">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="20fb4-122">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="20fb4-123">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="20fb4-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="20fb4-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="20fb4-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="20fb4-125">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="20fb4-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20fb4-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20fb4-126">Remarks</span></span>  
 <span data-ttu-id="20fb4-127">Un `<caches>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento.</span><span class="sxs-lookup"><span data-stu-id="20fb4-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="20fb4-128">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="20fb4-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="20fb4-129">El elemento se representa mediante la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase. `<caches>`</span><span class="sxs-lookup"><span data-stu-id="20fb4-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="20fb4-130">La <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase representa las memorias caché configuradas.</span><span class="sxs-lookup"><span data-stu-id="20fb4-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20fb4-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20fb4-131">Example</span></span>  
 <span data-ttu-id="20fb4-132">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad<xref:System.IdentityModel.Tokens.SessionSecurityToken>de la sesión ().</span><span class="sxs-lookup"><span data-stu-id="20fb4-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="20fb4-133">La configuración se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="20fb4-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
