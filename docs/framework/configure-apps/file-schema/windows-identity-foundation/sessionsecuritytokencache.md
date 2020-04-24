---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: a0db10ceb75a470dbf799d717b2059355dd104bb
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646063"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="728ec-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="728ec-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="728ec-102">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="728ec-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="728ec-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="728ec-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="728ec-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="728ec-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="728ec-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="728ec-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="728ec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<almacena en caché>**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="728ec-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="728ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span><span class="sxs-lookup"><span data-stu-id="728ec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="728ec-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="728ec-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="728ec-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="728ec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="728ec-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="728ec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="728ec-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="728ec-111">Attributes</span></span>  
  
|<span data-ttu-id="728ec-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="728ec-112">Attribute</span></span>|<span data-ttu-id="728ec-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="728ec-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="728ec-114">type</span><span class="sxs-lookup"><span data-stu-id="728ec-114">type</span></span>|<span data-ttu-id="728ec-115">Un tipo que deriva <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> de la clase.</span><span class="sxs-lookup"><span data-stu-id="728ec-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="728ec-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="728ec-116">Child Elements</span></span>  
 <span data-ttu-id="728ec-117">None</span><span class="sxs-lookup"><span data-stu-id="728ec-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="728ec-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="728ec-118">Parent Elements</span></span>  
  
|<span data-ttu-id="728ec-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="728ec-119">Element</span></span>|<span data-ttu-id="728ec-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="728ec-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="728ec-121">\<almacena en caché></span><span class="sxs-lookup"><span data-stu-id="728ec-121">\<caches></span></span>](caches.md)|<span data-ttu-id="728ec-122">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="728ec-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="728ec-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="728ec-123">Example</span></span>  
 <span data-ttu-id="728ec-124">El siguiente XML muestra la configuración de una<xref:System.IdentityModel.Tokens.SessionSecurityToken>memoria caché personalizada para contener tokens de seguridad de sesión ( ).</span><span class="sxs-lookup"><span data-stu-id="728ec-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="728ec-125">La configuración se `ClaimsAwareWebFarm` toma de la muestra.</span><span class="sxs-lookup"><span data-stu-id="728ec-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="728ec-126">Para obtener más información acerca de este ejemplo, vea Índice de ejemplo de [código WIF](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span><span class="sxs-lookup"><span data-stu-id="728ec-126">For more information about this sample, see [WIF Code Sample Index](https://docs.microsoft.com/previous-versions/dotnet/framework/security/wif-code-sample-index).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="728ec-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="728ec-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
