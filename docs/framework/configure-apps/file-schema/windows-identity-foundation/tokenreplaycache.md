---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f388369d4dc2e590473ad98189ade70b77551b10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="468c2-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="468c2-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="468c2-103">Registra una caché de respuesta de token con un servicio o una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="468c2-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="468c2-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="468c2-104">\<system.identityModel></span></span>  
<span data-ttu-id="468c2-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="468c2-105">\<identityConfiguration></span></span>  
<span data-ttu-id="468c2-106">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="468c2-106">\<caches></span></span>  
<span data-ttu-id="468c2-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="468c2-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="468c2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="468c2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="468c2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="468c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="468c2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="468c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="468c2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="468c2-111">Attributes</span></span>  
  
|<span data-ttu-id="468c2-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="468c2-112">Attribute</span></span>|<span data-ttu-id="468c2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="468c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="468c2-114">type</span><span class="sxs-lookup"><span data-stu-id="468c2-114">type</span></span>|<span data-ttu-id="468c2-115">Un tipo que deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="468c2-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="468c2-116">Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="468c2-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="468c2-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="468c2-117">Child Elements</span></span>  
 <span data-ttu-id="468c2-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="468c2-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="468c2-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="468c2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="468c2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="468c2-120">Element</span></span>|<span data-ttu-id="468c2-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="468c2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="468c2-122">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="468c2-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="468c2-123">Registra las memorias caché usadas por un servicio o una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="468c2-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="468c2-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="468c2-124">Remarks</span></span>  
 <span data-ttu-id="468c2-125">La memoria caché de la respuesta de token se utiliza para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="468c2-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="468c2-126">Detección de respuesta de token está habilitada por la [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento, que también especifica la hora de expiración máximo de tokens.</span><span class="sxs-lookup"><span data-stu-id="468c2-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="468c2-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="468c2-127">Example</span></span>  
 <span data-ttu-id="468c2-128">El siguiente código XML muestra la configuración de una caché personalizado para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="468c2-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="468c2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="468c2-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="468c2-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="468c2-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
