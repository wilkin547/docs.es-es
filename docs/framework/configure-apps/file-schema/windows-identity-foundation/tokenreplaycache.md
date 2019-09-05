---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251781"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="f49f1-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f49f1-101">\<tokenReplayCache></span></span>
<span data-ttu-id="f49f1-102">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f49f1-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="f49f1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f49f1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f49f1-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f49f1-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f49f1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f49f1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f49f1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<almacena en caché >** ](caches.md)</span><span class="sxs-lookup"><span data-stu-id="f49f1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="f49f1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> tokenReplayCache**</span><span class="sxs-lookup"><span data-stu-id="f49f1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f49f1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f49f1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f49f1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f49f1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f49f1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f49f1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f49f1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f49f1-111">Attributes</span></span>  
  
|<span data-ttu-id="f49f1-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="f49f1-112">Attribute</span></span>|<span data-ttu-id="f49f1-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f49f1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f49f1-114">type</span><span class="sxs-lookup"><span data-stu-id="f49f1-114">type</span></span>|<span data-ttu-id="f49f1-115">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="f49f1-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f49f1-116">Para obtener más información sobre cómo especificar un personalizado `type`, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="f49f1-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f49f1-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f49f1-117">Child Elements</span></span>  
 <span data-ttu-id="f49f1-118">None</span><span class="sxs-lookup"><span data-stu-id="f49f1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f49f1-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f49f1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f49f1-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f49f1-120">Element</span></span>|<span data-ttu-id="f49f1-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f49f1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f49f1-122">\<caches></span><span class="sxs-lookup"><span data-stu-id="f49f1-122">\<caches></span></span>](caches.md)|<span data-ttu-id="f49f1-123">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f49f1-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f49f1-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f49f1-124">Remarks</span></span>  
 <span data-ttu-id="f49f1-125">La memoria caché de reproducción de tokens se usa para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="f49f1-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f49f1-126">La detección de la reproducción de tokens [ \<](tokenreplaydetection.md) está habilitada por el elemento > de tokenReplayDetection, que también especifica el tiempo de expiración máximo para los tokens.</span><span class="sxs-lookup"><span data-stu-id="f49f1-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f49f1-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f49f1-127">Example</span></span>  
 <span data-ttu-id="f49f1-128">El siguiente XML muestra la configuración de una memoria caché personalizada para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="f49f1-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f49f1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f49f1-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="f49f1-130">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f49f1-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
