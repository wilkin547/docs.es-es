---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251769"
---
# \<tokenReplayDetection>
<span data-ttu-id="9413c-101">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="9413c-101">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="9413c-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9413c-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="9413c-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="9413c-103">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9413c-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9413c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="9413c-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9413c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9413c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="9413c-106">Attributes</span></span>  
  
|<span data-ttu-id="9413c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="9413c-107">Attribute</span></span>|<span data-ttu-id="9413c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9413c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9413c-109">enabled</span><span class="sxs-lookup"><span data-stu-id="9413c-109">enabled</span></span>|<span data-ttu-id="9413c-110">Valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="9413c-110">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="9413c-111">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="9413c-111">expirationPeriod</span></span>|<span data-ttu-id="9413c-112"><xref:System.TimeSpan>Que especifica la cantidad máxima de tiempo antes de que un elemento se considere expirado y se quite de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="9413c-112">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="9413c-113">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9413c-113">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9413c-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9413c-114">Child Elements</span></span>  
 <span data-ttu-id="9413c-115">None</span><span class="sxs-lookup"><span data-stu-id="9413c-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9413c-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9413c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9413c-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9413c-117">Element</span></span>|<span data-ttu-id="9413c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9413c-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="9413c-119">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="9413c-119">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9413c-120">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9413c-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9413c-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9413c-121">Remarks</span></span>  
 <span data-ttu-id="9413c-122">Un `<tokenReplayDetection>` elemento se puede especificar en el nivel de servicio bajo el `<identityConfiguration>` elemento o en el nivel de colección de controladores de tokens de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="9413c-122">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="9413c-123">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="9413c-123">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="9413c-124">El elemento especifica el tipo de la memoria caché de reproducción de tokens [\<tokenReplayCache>](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="9413c-124">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
