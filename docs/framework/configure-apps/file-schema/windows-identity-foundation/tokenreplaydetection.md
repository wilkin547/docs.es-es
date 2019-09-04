---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251769"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="4d08d-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="4d08d-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="4d08d-102">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="4d08d-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="4d08d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4d08d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4d08d-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4d08d-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4d08d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4d08d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4d08d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> tokenReplayDetection**</span><span class="sxs-lookup"><span data-stu-id="4d08d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d08d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d08d-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="4d08d-108">Type</span><span class="sxs-lookup"><span data-stu-id="4d08d-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d08d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d08d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4d08d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d08d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d08d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d08d-111">Attributes</span></span>  
  
|<span data-ttu-id="4d08d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="4d08d-112">Attribute</span></span>|<span data-ttu-id="4d08d-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4d08d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d08d-114">enabled</span><span class="sxs-lookup"><span data-stu-id="4d08d-114">enabled</span></span>|<span data-ttu-id="4d08d-115">Valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="4d08d-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="4d08d-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="4d08d-116">expirationPeriod</span></span>|<span data-ttu-id="4d08d-117"><xref:System.TimeSpan> Que especifica la cantidad máxima de tiempo antes de que un elemento se considere expirado y se quite de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4d08d-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="4d08d-118">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d08d-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d08d-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d08d-119">Child Elements</span></span>  
 <span data-ttu-id="4d08d-120">None</span><span class="sxs-lookup"><span data-stu-id="4d08d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d08d-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d08d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4d08d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d08d-122">Element</span></span>|<span data-ttu-id="4d08d-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4d08d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d08d-124">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4d08d-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="4d08d-125">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="4d08d-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="4d08d-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="4d08d-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="4d08d-127">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d08d-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d08d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d08d-128">Remarks</span></span>  
 <span data-ttu-id="4d08d-129">Un `<tokenReplayDetection>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento.</span><span class="sxs-lookup"><span data-stu-id="4d08d-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="4d08d-130">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="4d08d-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="4d08d-131">El tipo de la memoria caché de reproducción de tokens se [ \<](tokenreplaycache.md) especifica mediante el elemento > de tokenReplayCache.</span><span class="sxs-lookup"><span data-stu-id="4d08d-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
