---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: dfa6c0d84582d55595f00f149adfdcaa9d554d6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271959"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="1ebfd-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="1ebfd-101">\<tokenReplayCache></span></span>
<span data-ttu-id="1ebfd-102">Registra una caché de reproducción de tokens con un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="1ebfd-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1ebfd-103">\<system.identityModel></span></span>  
<span data-ttu-id="1ebfd-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1ebfd-104">\<identityConfiguration></span></span>  
<span data-ttu-id="1ebfd-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="1ebfd-105">\<caches></span></span>  
<span data-ttu-id="1ebfd-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="1ebfd-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ebfd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ebfd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ebfd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ebfd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1ebfd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ebfd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ebfd-110">Attributes</span></span>  
  
|<span data-ttu-id="1ebfd-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1ebfd-111">Attribute</span></span>|<span data-ttu-id="1ebfd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ebfd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ebfd-113">type</span><span class="sxs-lookup"><span data-stu-id="1ebfd-113">type</span></span>|<span data-ttu-id="1ebfd-114">Un tipo que deriva la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="1ebfd-115">Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="1ebfd-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="1ebfd-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ebfd-116">Child Elements</span></span>  
 <span data-ttu-id="1ebfd-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="1ebfd-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ebfd-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ebfd-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1ebfd-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ebfd-119">Element</span></span>|<span data-ttu-id="1ebfd-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ebfd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ebfd-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="1ebfd-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="1ebfd-122">Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ebfd-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ebfd-123">Remarks</span></span>  
 <span data-ttu-id="1ebfd-124">La caché de reproducción de tokens se usa para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="1ebfd-125">Detección de reproducción de tokens está habilitada por la [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento, que también especifica la hora de expiración máximo para los tokens.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ebfd-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ebfd-126">Example</span></span>  
 <span data-ttu-id="1ebfd-127">El siguiente XML muestra la configuración de una caché personalizada para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="1ebfd-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ebfd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ebfd-128">See also</span></span>
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="1ebfd-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="1ebfd-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
