---
description: 'Más información acerca de: <tokenReplayCache>'
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 793b1f88a9eeb0ebce4cd440e248e81377f17e9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749004"
---
# \<tokenReplayCache>

<span data-ttu-id="e7494-102">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7494-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="e7494-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7494-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7494-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7494-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e7494-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7494-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7494-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7494-106">Attributes</span></span>  
  
|<span data-ttu-id="e7494-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="e7494-107">Attribute</span></span>|<span data-ttu-id="e7494-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7494-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7494-109">type</span><span class="sxs-lookup"><span data-stu-id="e7494-109">type</span></span>|<span data-ttu-id="e7494-110">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="e7494-110">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="e7494-111">Para obtener más información sobre cómo especificar un personalizado `type` , vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="e7494-111">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="e7494-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7494-112">Child Elements</span></span>  

 <span data-ttu-id="e7494-113">None</span><span class="sxs-lookup"><span data-stu-id="e7494-113">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7494-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7494-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e7494-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7494-115">Element</span></span>|<span data-ttu-id="e7494-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7494-116">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="e7494-117">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7494-117">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7494-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7494-118">Remarks</span></span>  

 <span data-ttu-id="e7494-119">La memoria caché de reproducción de tokens se usa para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="e7494-119">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="e7494-120">La detección de la reproducción de tokens está habilitada por el [\<tokenReplayDetection>](tokenreplaydetection.md) elemento, que también especifica el tiempo de expiración máximo para los tokens.</span><span class="sxs-lookup"><span data-stu-id="e7494-120">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7494-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e7494-121">Example</span></span>  

 <span data-ttu-id="e7494-122">El siguiente XML muestra la configuración de una memoria caché personalizada para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="e7494-122">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7494-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7494-123">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
