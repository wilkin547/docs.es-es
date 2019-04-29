---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790499"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="27958-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="27958-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="27958-102">Habilita la detección de reproducción de tokens y especifica la hora de expiración de tokens.</span><span class="sxs-lookup"><span data-stu-id="27958-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="27958-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="27958-103">\<system.identityModel></span></span>  
<span data-ttu-id="27958-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="27958-104">\<identityConfiguration></span></span>  
<span data-ttu-id="27958-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="27958-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27958-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27958-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="27958-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="27958-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27958-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="27958-108">Attributes and Elements</span></span>  
 <span data-ttu-id="27958-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="27958-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27958-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="27958-110">Attributes</span></span>  
  
|<span data-ttu-id="27958-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="27958-111">Attribute</span></span>|<span data-ttu-id="27958-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="27958-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27958-113">enabled</span><span class="sxs-lookup"><span data-stu-id="27958-113">enabled</span></span>|<span data-ttu-id="27958-114">Un valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar el token de la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="27958-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="27958-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="27958-115">expirationPeriod</span></span>|<span data-ttu-id="27958-116">Un <xref:System.TimeSpan> que especifica la cantidad máxima de tiempo antes de que un elemento se considerará caducado y quita de la caché.</span><span class="sxs-lookup"><span data-stu-id="27958-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="27958-117">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="27958-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27958-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="27958-118">Child Elements</span></span>  
 <span data-ttu-id="27958-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="27958-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27958-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="27958-120">Parent Elements</span></span>  
  
|<span data-ttu-id="27958-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="27958-121">Element</span></span>|<span data-ttu-id="27958-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="27958-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27958-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="27958-123">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="27958-124">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="27958-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="27958-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="27958-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="27958-126">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="27958-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27958-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27958-127">Remarks</span></span>  
 <span data-ttu-id="27958-128">Un `<tokenReplayDetection>` elemento puede especificarse en el nivel de servicio bajo la `<identityConfiguration>` elemento o en el nivel de colección de controladores de token de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="27958-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="27958-129">La configuración en una colección de controladores de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="27958-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="27958-130">El tipo de la caché de reproducción de tokens especificado por el [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="27958-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
