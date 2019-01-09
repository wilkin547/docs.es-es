---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 3456ffa952372b014d579b5c420f7c44222fdad5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145359"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="48f32-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="48f32-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="48f32-103">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="48f32-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="48f32-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="48f32-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="48f32-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="48f32-105">\<behaviors></span></span>  
<span data-ttu-id="48f32-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="48f32-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="48f32-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="48f32-107">\<behavior></span></span>  
<span data-ttu-id="48f32-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="48f32-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f32-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48f32-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48f32-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48f32-110">Attributes and Elements</span></span>  
 <span data-ttu-id="48f32-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="48f32-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48f32-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="48f32-112">Attributes</span></span>  
  
|<span data-ttu-id="48f32-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="48f32-113">Attribute</span></span>|<span data-ttu-id="48f32-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="48f32-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48f32-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="48f32-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="48f32-116">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="48f32-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48f32-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48f32-117">Child Elements</span></span>  
 <span data-ttu-id="48f32-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="48f32-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48f32-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48f32-119">Parent Elements</span></span>  
  
|<span data-ttu-id="48f32-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="48f32-120">Element</span></span>|<span data-ttu-id="48f32-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="48f32-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48f32-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="48f32-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="48f32-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="48f32-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48f32-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="48f32-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
