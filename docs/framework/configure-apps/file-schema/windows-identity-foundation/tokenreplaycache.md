---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1e89afc5764dbdb86e87d2307425299dff57c686
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525176"
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="3825d-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="3825d-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="3825d-103">Registra una caché de reproducción de tokens con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3825d-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="3825d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3825d-104">\<system.identityModel></span></span>  
<span data-ttu-id="3825d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3825d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3825d-106">\<caches></span><span class="sxs-lookup"><span data-stu-id="3825d-106">\<caches></span></span>  
<span data-ttu-id="3825d-107">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="3825d-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3825d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3825d-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3825d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3825d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3825d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3825d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3825d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3825d-111">Attributes</span></span>  
  
|<span data-ttu-id="3825d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3825d-112">Attribute</span></span>|<span data-ttu-id="3825d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3825d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3825d-114">type</span><span class="sxs-lookup"><span data-stu-id="3825d-114">type</span></span>|<span data-ttu-id="3825d-115">Un tipo que deriva la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="3825d-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="3825d-116">Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="3825d-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3825d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3825d-117">Child Elements</span></span>  
 <span data-ttu-id="3825d-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3825d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3825d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3825d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3825d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3825d-120">Element</span></span>|<span data-ttu-id="3825d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3825d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3825d-122">\<caches></span><span class="sxs-lookup"><span data-stu-id="3825d-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="3825d-123">Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3825d-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3825d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3825d-124">Remarks</span></span>  
 <span data-ttu-id="3825d-125">La caché de reproducción de tokens se usa para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="3825d-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="3825d-126">Detección de reproducción de tokens está habilitada por la [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento, que también especifica la hora de expiración máximo para los tokens.</span><span class="sxs-lookup"><span data-stu-id="3825d-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3825d-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3825d-127">Example</span></span>  
 <span data-ttu-id="3825d-128">El siguiente XML muestra la configuración de una caché personalizada para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="3825d-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3825d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3825d-129">See also</span></span>
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="3825d-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="3825d-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
