---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944074"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="f8afc-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f8afc-101">\<tokenReplayCache></span></span>
<span data-ttu-id="f8afc-102">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f8afc-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="f8afc-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f8afc-103">\<system.identityModel></span></span>  
<span data-ttu-id="f8afc-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f8afc-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f8afc-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="f8afc-105">\<caches></span></span>  
<span data-ttu-id="f8afc-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f8afc-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8afc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8afc-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8afc-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f8afc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f8afc-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f8afc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8afc-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f8afc-110">Attributes</span></span>  
  
|<span data-ttu-id="f8afc-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f8afc-111">Attribute</span></span>|<span data-ttu-id="f8afc-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f8afc-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8afc-113">type</span><span class="sxs-lookup"><span data-stu-id="f8afc-113">type</span></span>|<span data-ttu-id="f8afc-114">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="f8afc-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f8afc-115">Para obtener más información sobre cómo especificar un personalizado `type`, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="f8afc-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f8afc-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f8afc-116">Child Elements</span></span>  
 <span data-ttu-id="f8afc-117">None</span><span class="sxs-lookup"><span data-stu-id="f8afc-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8afc-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f8afc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f8afc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8afc-119">Element</span></span>|<span data-ttu-id="f8afc-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f8afc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8afc-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="f8afc-121">\<caches></span></span>](caches.md)|<span data-ttu-id="f8afc-122">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f8afc-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8afc-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f8afc-123">Remarks</span></span>  
 <span data-ttu-id="f8afc-124">La memoria caché de reproducción de tokens se usa para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="f8afc-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f8afc-125">La detección de la reproducción de tokens [ \<](tokenreplaydetection.md) está habilitada por el elemento > de tokenReplayDetection, que también especifica el tiempo de expiración máximo para los tokens.</span><span class="sxs-lookup"><span data-stu-id="f8afc-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8afc-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f8afc-126">Example</span></span>  
 <span data-ttu-id="f8afc-127">El siguiente XML muestra la configuración de una memoria caché personalizada para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="f8afc-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8afc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8afc-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="f8afc-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f8afc-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
