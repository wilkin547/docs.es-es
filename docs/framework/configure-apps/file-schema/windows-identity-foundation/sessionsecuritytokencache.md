---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0b0d3c01a81f110f79f64d75aa2ab2ff2873fedd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsessionsecuritytokencachegt"></a><span data-ttu-id="284a3-102">&lt;sessionSecurityTokenCache&gt;</span><span class="sxs-lookup"><span data-stu-id="284a3-102">&lt;sessionSecurityTokenCache&gt;</span></span>
<span data-ttu-id="284a3-103">Registra una memoria caché de símbolos de sesión con un servicio o una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="284a3-103">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="284a3-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="284a3-104">\<system.identityModel></span></span>  
<span data-ttu-id="284a3-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="284a3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="284a3-106">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="284a3-106">\<caches></span></span>  
<span data-ttu-id="284a3-107">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="284a3-107">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="284a3-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="284a3-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="284a3-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="284a3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="284a3-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="284a3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="284a3-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="284a3-111">Attributes</span></span>  
  
|<span data-ttu-id="284a3-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="284a3-112">Attribute</span></span>|<span data-ttu-id="284a3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="284a3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="284a3-114">type</span><span class="sxs-lookup"><span data-stu-id="284a3-114">type</span></span>|<span data-ttu-id="284a3-115">Un tipo que deriva de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="284a3-115">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="284a3-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="284a3-116">Child Elements</span></span>  
 <span data-ttu-id="284a3-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="284a3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="284a3-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="284a3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="284a3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="284a3-119">Element</span></span>|<span data-ttu-id="284a3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="284a3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="284a3-121">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="284a3-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="284a3-122">Registra las memorias caché usadas por un servicio o una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="284a3-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="284a3-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="284a3-123">Example</span></span>  
 <span data-ttu-id="284a3-124">El siguiente código XML muestra la configuración de una caché personalizado para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="284a3-124">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="284a3-125">La configuración se toma de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="284a3-125">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="284a3-126">Para obtener más información acerca de este ejemplo, vea [índice de ejemplo de código WIF](../../../../../docs/framework/security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="284a3-126">For more information about this sample, see [WIF Code Sample Index](../../../../../docs/framework/security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="284a3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="284a3-127">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
