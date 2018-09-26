---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205936"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="04d32-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="04d32-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="04d32-103">Habilita la detección de reproducción de tokens y especifica la hora de expiración de tokens.</span><span class="sxs-lookup"><span data-stu-id="04d32-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="04d32-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="04d32-104">\<system.identityModel></span></span>  
<span data-ttu-id="04d32-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="04d32-105">\<identityConfiguration></span></span>  
<span data-ttu-id="04d32-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="04d32-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04d32-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04d32-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="04d32-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="04d32-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04d32-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04d32-109">Attributes and Elements</span></span>  
 <span data-ttu-id="04d32-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="04d32-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04d32-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="04d32-111">Attributes</span></span>  
  
|<span data-ttu-id="04d32-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="04d32-112">Attribute</span></span>|<span data-ttu-id="04d32-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="04d32-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="04d32-114">enabled</span><span class="sxs-lookup"><span data-stu-id="04d32-114">enabled</span></span>|<span data-ttu-id="04d32-115">Un valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar el token de la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="04d32-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="04d32-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="04d32-116">expirationPeriod</span></span>|<span data-ttu-id="04d32-117">Un <xref:System.TimeSpan> que especifica la cantidad máxima de tiempo antes de que un elemento se considerará caducado y quita de la caché.</span><span class="sxs-lookup"><span data-stu-id="04d32-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="04d32-118">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="04d32-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="04d32-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04d32-119">Child Elements</span></span>  
 <span data-ttu-id="04d32-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="04d32-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="04d32-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04d32-121">Parent Elements</span></span>  
  
|<span data-ttu-id="04d32-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="04d32-122">Element</span></span>|<span data-ttu-id="04d32-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="04d32-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04d32-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="04d32-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="04d32-125">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="04d32-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="04d32-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="04d32-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="04d32-127">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="04d32-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04d32-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04d32-128">Remarks</span></span>  
 <span data-ttu-id="04d32-129">Un `<tokenReplayDetection>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="04d32-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="04d32-130">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="04d32-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="04d32-131">El tipo de la caché de reproducción de tokens especificado por el [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="04d32-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
