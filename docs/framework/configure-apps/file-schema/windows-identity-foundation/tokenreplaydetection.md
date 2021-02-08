---
description: 'Más información acerca de: <tokenReplayDetection>'
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a8a6b754a3282afe4f2932296b06b84c09fb6f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786543"
---
# \<tokenReplayDetection>

<span data-ttu-id="e7403-102">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="e7403-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
## <a name="syntax"></a><span data-ttu-id="e7403-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7403-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="e7403-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="e7403-104">Type</span></span>  

 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7403-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7403-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e7403-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7403-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7403-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7403-107">Attributes</span></span>  
  
|<span data-ttu-id="e7403-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e7403-108">Attribute</span></span>|<span data-ttu-id="e7403-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7403-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7403-110">enabled</span><span class="sxs-lookup"><span data-stu-id="e7403-110">enabled</span></span>|<span data-ttu-id="e7403-111">Valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="e7403-111">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="e7403-112">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="e7403-112">expirationPeriod</span></span>|<span data-ttu-id="e7403-113"><xref:System.TimeSpan>Que especifica la cantidad máxima de tiempo antes de que un elemento se considere expirado y se quite de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e7403-113">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="e7403-114">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7403-114">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7403-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7403-115">Child Elements</span></span>  

 <span data-ttu-id="e7403-116">None</span><span class="sxs-lookup"><span data-stu-id="e7403-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7403-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7403-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e7403-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7403-118">Element</span></span>|<span data-ttu-id="e7403-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7403-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="e7403-120">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="e7403-120">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e7403-121">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e7403-121">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7403-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7403-122">Remarks</span></span>  

 <span data-ttu-id="e7403-123">Un `<tokenReplayDetection>` elemento se puede especificar en el nivel de servicio bajo el `<identityConfiguration>` elemento o en el nivel de colección de controladores de tokens de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e7403-123">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="e7403-124">La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="e7403-124">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="e7403-125">El elemento especifica el tipo de la memoria caché de reproducción de tokens [\<tokenReplayCache>](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="e7403-125">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
