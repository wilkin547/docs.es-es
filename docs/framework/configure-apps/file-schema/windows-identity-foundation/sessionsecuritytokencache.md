---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 5c68fe618f965f364a3716c3bc65de5e165b12ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207804"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="317b9-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="317b9-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="317b9-102">Registra una memoria caché de tokens de sesión con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="317b9-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="317b9-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="317b9-103">\<system.identityModel></span></span>  
<span data-ttu-id="317b9-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="317b9-104">\<identityConfiguration></span></span>  
<span data-ttu-id="317b9-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="317b9-105">\<caches></span></span>  
<span data-ttu-id="317b9-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="317b9-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="317b9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="317b9-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="317b9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="317b9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="317b9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="317b9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="317b9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="317b9-110">Attributes</span></span>  
  
|<span data-ttu-id="317b9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="317b9-111">Attribute</span></span>|<span data-ttu-id="317b9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="317b9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="317b9-113">type</span><span class="sxs-lookup"><span data-stu-id="317b9-113">type</span></span>|<span data-ttu-id="317b9-114">Un tipo que deriva la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="317b9-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="317b9-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="317b9-115">Child Elements</span></span>  
 <span data-ttu-id="317b9-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="317b9-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="317b9-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="317b9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="317b9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="317b9-118">Element</span></span>|<span data-ttu-id="317b9-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="317b9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="317b9-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="317b9-120">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="317b9-121">Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="317b9-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="317b9-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="317b9-122">Example</span></span>  
 <span data-ttu-id="317b9-123">El siguiente XML muestra la configuración de una caché personalizada para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="317b9-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="317b9-124">La configuración se toma de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="317b9-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="317b9-125">Para obtener más información acerca de este ejemplo, vea [índice de ejemplo de código WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="317b9-125">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="317b9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="317b9-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
