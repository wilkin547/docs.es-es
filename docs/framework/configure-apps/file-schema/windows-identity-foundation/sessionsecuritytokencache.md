---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: e949b16f76f20191b84bbbbb6e8b019d913316f0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251832"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="89c1c-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="89c1c-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="89c1c-102">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="89c1c-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="89c1c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89c1c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89c1c-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="89c1c-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="89c1c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="89c1c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="89c1c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<almacena en caché >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="89c1c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="89c1c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sessionSecurityTokenCache**</span><span class="sxs-lookup"><span data-stu-id="89c1c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c1c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89c1c-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89c1c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="89c1c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89c1c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="89c1c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89c1c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="89c1c-111">Attributes</span></span>  
  
|<span data-ttu-id="89c1c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="89c1c-112">Attribute</span></span>|<span data-ttu-id="89c1c-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="89c1c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89c1c-114">type</span><span class="sxs-lookup"><span data-stu-id="89c1c-114">type</span></span>|<span data-ttu-id="89c1c-115">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="89c1c-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89c1c-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="89c1c-116">Child Elements</span></span>  
 <span data-ttu-id="89c1c-117">None</span><span class="sxs-lookup"><span data-stu-id="89c1c-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89c1c-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="89c1c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="89c1c-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="89c1c-119">Element</span></span>|<span data-ttu-id="89c1c-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="89c1c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89c1c-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="89c1c-121">\<caches></span></span>](caches.md)|<span data-ttu-id="89c1c-122">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="89c1c-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89c1c-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89c1c-123">Example</span></span>  
 <span data-ttu-id="89c1c-124">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad<xref:System.IdentityModel.Tokens.SessionSecurityToken>de la sesión ().</span><span class="sxs-lookup"><span data-stu-id="89c1c-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="89c1c-125">La configuración se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="89c1c-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="89c1c-126">Para obtener más información sobre este ejemplo, consulte [Índice de ejemplo de código WIF](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="89c1c-126">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89c1c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="89c1c-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
