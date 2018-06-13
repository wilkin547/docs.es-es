---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755232"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="38ccc-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="38ccc-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="38ccc-103">Habilita la detección de reproducción de tokens y especifica la hora de expiración de símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="38ccc-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="38ccc-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="38ccc-104">\<system.identityModel></span></span>  
<span data-ttu-id="38ccc-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="38ccc-105">\<identityConfiguration></span></span>  
<span data-ttu-id="38ccc-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="38ccc-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ccc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38ccc-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="38ccc-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="38ccc-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38ccc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38ccc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="38ccc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38ccc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38ccc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="38ccc-111">Attributes</span></span>  
  
|<span data-ttu-id="38ccc-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="38ccc-112">Attribute</span></span>|<span data-ttu-id="38ccc-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ccc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38ccc-114">enabled</span><span class="sxs-lookup"><span data-stu-id="38ccc-114">enabled</span></span>|<span data-ttu-id="38ccc-115">Un valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar el token de la detección de reproducción.</span><span class="sxs-lookup"><span data-stu-id="38ccc-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="38ccc-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="38ccc-116">expirationPeriod</span></span>|<span data-ttu-id="38ccc-117">Un <xref:System.TimeSpan> que especifica la cantidad máxima de tiempo antes de que un elemento se considera caducado y eliminado de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="38ccc-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="38ccc-118">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, consulte [valores de intervalo de tiempo](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="38ccc-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38ccc-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38ccc-119">Child Elements</span></span>  
 <span data-ttu-id="38ccc-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="38ccc-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38ccc-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38ccc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="38ccc-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="38ccc-122">Element</span></span>|<span data-ttu-id="38ccc-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ccc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38ccc-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="38ccc-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="38ccc-125">Especifica los valores de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="38ccc-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="38ccc-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="38ccc-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="38ccc-127">Proporciona la configuración para una colección de seguridad controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="38ccc-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38ccc-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38ccc-128">Remarks</span></span>  
 <span data-ttu-id="38ccc-129">A `<tokenReplayDetection>` elemento puede especificarse en el nivel de servicio en la `<identityConfiguration>` elemento o en el nivel de colección de controlador de token de seguridad en el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="38ccc-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="38ccc-130">La configuración en una colección de controlador de token invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="38ccc-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="38ccc-131">El tipo de la memoria caché de la respuesta de token es especificado por el [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="38ccc-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
