---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 9be3bf980c3756678d26d8652271113d4daaba43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943708"
---
# <a name="sessionsecuritytokencache"></a><span data-ttu-id="8a05f-101">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="8a05f-101">\<sessionSecurityTokenCache></span></span>
<span data-ttu-id="8a05f-102">Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a05f-102">Registers a cache for session tokens with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="8a05f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8a05f-103">\<system.identityModel></span></span>  
<span data-ttu-id="8a05f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8a05f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="8a05f-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="8a05f-105">\<caches></span></span>  
<span data-ttu-id="8a05f-106">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="8a05f-106">\<sessionSecurityTokenCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a05f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a05f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a05f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a05f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8a05f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a05f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a05f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a05f-110">Attributes</span></span>  
  
|<span data-ttu-id="8a05f-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a05f-111">Attribute</span></span>|<span data-ttu-id="8a05f-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a05f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a05f-113">type</span><span class="sxs-lookup"><span data-stu-id="8a05f-113">type</span></span>|<span data-ttu-id="8a05f-114">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.</span><span class="sxs-lookup"><span data-stu-id="8a05f-114">A type that derives from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a05f-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a05f-115">Child Elements</span></span>  
 <span data-ttu-id="8a05f-116">None</span><span class="sxs-lookup"><span data-stu-id="8a05f-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a05f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a05f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8a05f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a05f-118">Element</span></span>|<span data-ttu-id="8a05f-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8a05f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a05f-120">\<caches></span><span class="sxs-lookup"><span data-stu-id="8a05f-120">\<caches></span></span>](caches.md)|<span data-ttu-id="8a05f-121">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8a05f-121">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a05f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a05f-122">Example</span></span>  
 <span data-ttu-id="8a05f-123">El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad<xref:System.IdentityModel.Tokens.SessionSecurityToken>de la sesión ().</span><span class="sxs-lookup"><span data-stu-id="8a05f-123">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="8a05f-124">La configuración se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8a05f-124">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span> <span data-ttu-id="8a05f-125">Para obtener más información sobre este ejemplo, consulte [Índice de ejemplo de código WIF](../../../security/wif-code-sample-index.md).</span><span class="sxs-lookup"><span data-stu-id="8a05f-125">For more information about this sample, see [WIF Code Sample Index](../../../security/wif-code-sample-index.md).</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a05f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a05f-126">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
