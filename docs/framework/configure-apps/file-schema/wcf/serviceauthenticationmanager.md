---
title: '&lt;serviceAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2385b96460e0a3d53efb62054fb7da334ddd2d49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="3123d-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="3123d-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="3123d-103">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="3123d-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="3123d-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3123d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3123d-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="3123d-105">\<behaviors></span></span>  
<span data-ttu-id="3123d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="3123d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="3123d-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3123d-107">\<behavior></span></span>  
<span data-ttu-id="3123d-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="3123d-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3123d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3123d-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3123d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3123d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3123d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3123d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3123d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3123d-112">Attributes</span></span>  
  
|<span data-ttu-id="3123d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3123d-113">Attribute</span></span>|<span data-ttu-id="3123d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3123d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3123d-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="3123d-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="3123d-116">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="3123d-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3123d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3123d-117">Child Elements</span></span>  
 <span data-ttu-id="3123d-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3123d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3123d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3123d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3123d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3123d-120">Element</span></span>|<span data-ttu-id="3123d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3123d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3123d-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3123d-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3123d-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3123d-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3123d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3123d-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
