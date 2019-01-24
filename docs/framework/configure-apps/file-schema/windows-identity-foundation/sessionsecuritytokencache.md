---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 024375cb114bb080c576ea033e5588526350ecdf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510096"
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="5a832-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="5a832-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="5a832-103">Registra una memoria caché de tokens de sesión con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5a832-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="5a832-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5a832-104">\<system.identityModel></span></span>  
<span data-ttu-id="5a832-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5a832-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5a832-106">\<caches></span><span class="sxs-lookup"><span data-stu-id="5a832-106">\<caches></span></span>  
<span data-ttu-id="5a832-107">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="5a832-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a832-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a832-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a832-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5a832-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5a832-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5a832-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a832-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5a832-111">Attributes</span></span>  
  
|<span data-ttu-id="5a832-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5a832-112">Attribute</span></span>|<span data-ttu-id="5a832-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a832-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a832-114">type</span><span class="sxs-lookup"><span data-stu-id="5a832-114">type</span></span>|<span data-ttu-id="5a832-115">Un tipo que deriva la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="5a832-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a832-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5a832-116">Child Elements</span></span>  
 <span data-ttu-id="5a832-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5a832-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a832-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5a832-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5a832-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5a832-119">Element</span></span>|<span data-ttu-id="5a832-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a832-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a832-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="5a832-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="5a832-122">Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5a832-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5a832-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a832-123">Example</span></span>  
 <span data-ttu-id="5a832-124">El siguiente XML muestra la configuración de una caché personalizada para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="5a832-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="5a832-125">La configuración se toma de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5a832-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="5a832-126">Para obtener más información acerca de este ejemplo, vea [índice de ejemplo de código WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="5a832-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a832-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a832-127">See also</span></span>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
