---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5e695bb56b59da40ce9e83f9f4f77d0d22d0b40f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202427"
---
# \<tokenReplayCache>

<span data-ttu-id="b307f-101">Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b307f-101">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
## <a name="syntax"></a><span data-ttu-id="b307f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b307f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b307f-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b307f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b307f-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b307f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b307f-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="b307f-105">Attributes</span></span>  
  
|<span data-ttu-id="b307f-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="b307f-106">Attribute</span></span>|<span data-ttu-id="b307f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b307f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b307f-108">type</span><span class="sxs-lookup"><span data-stu-id="b307f-108">type</span></span>|<span data-ttu-id="b307f-109">Tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase.</span><span class="sxs-lookup"><span data-stu-id="b307f-109">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="b307f-110">Para obtener más información sobre cómo especificar un personalizado `type` , vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="b307f-110">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b307f-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b307f-111">Child Elements</span></span>  

 <span data-ttu-id="b307f-112">None</span><span class="sxs-lookup"><span data-stu-id="b307f-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b307f-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b307f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="b307f-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b307f-114">Element</span></span>|<span data-ttu-id="b307f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b307f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<caches>](caches.md)|<span data-ttu-id="b307f-116">Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b307f-116">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b307f-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b307f-117">Remarks</span></span>  

 <span data-ttu-id="b307f-118">La memoria caché de reproducción de tokens se usa para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="b307f-118">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="b307f-119">La detección de la reproducción de tokens está habilitada por el [\<tokenReplayDetection>](tokenreplaydetection.md) elemento, que también especifica el tiempo de expiración máximo para los tokens.</span><span class="sxs-lookup"><span data-stu-id="b307f-119">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b307f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b307f-120">Example</span></span>  

 <span data-ttu-id="b307f-121">El siguiente XML muestra la configuración de una memoria caché personalizada para detectar tokens reproducidos.</span><span class="sxs-lookup"><span data-stu-id="b307f-121">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b307f-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b307f-122">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
