---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944295"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="a9457-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="a9457-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="a9457-102">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="a9457-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="a9457-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a9457-103">\<system.identityModel></span></span>  
<span data-ttu-id="a9457-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a9457-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a9457-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="a9457-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9457-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9457-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="a9457-107">Type</span><span class="sxs-lookup"><span data-stu-id="a9457-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9457-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a9457-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a9457-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a9457-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9457-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9457-110">Attributes</span></span>  
  
|<span data-ttu-id="a9457-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a9457-111">Attribute</span></span>|<span data-ttu-id="a9457-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a9457-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a9457-113">enabled</span><span class="sxs-lookup"><span data-stu-id="a9457-113">enabled</span></span>|<span data-ttu-id="a9457-114">Valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="a9457-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="a9457-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="a9457-115">expirationPeriod</span></span>|<span data-ttu-id="a9457-116"><xref:System.TimeSpan> Que especifica la cantidad máxima de tiempo antes de que un elemento se considere expirado y se quite de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a9457-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="a9457-117">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="a9457-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9457-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9457-118">Child Elements</span></span>  
 <span data-ttu-id="a9457-119">None</span><span class="sxs-lookup"><span data-stu-id="a9457-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9457-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a9457-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a9457-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9457-121">Element</span></span>|<span data-ttu-id="a9457-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a9457-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9457-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a9457-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a9457-124">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="a9457-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="a9457-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="a9457-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a9457-126">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a9457-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9457-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9457-127">Remarks</span></span>  
 <span data-ttu-id="a9457-128">Un `<tokenReplayDetection>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento.</span><span class="sxs-lookup"><span data-stu-id="a9457-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="a9457-129">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="a9457-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="a9457-130">El tipo de la memoria caché de reproducción de tokens se [ \<](tokenreplaycache.md) especifica mediante el elemento > de tokenReplayCache.</span><span class="sxs-lookup"><span data-stu-id="a9457-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
