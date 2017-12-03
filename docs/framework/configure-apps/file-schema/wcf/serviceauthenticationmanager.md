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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 077878ae1746008532c3bee6b12913f98afc343f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="53331-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="53331-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="53331-103">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="53331-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="53331-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="53331-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="53331-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="53331-105">\<behaviors></span></span>  
<span data-ttu-id="53331-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="53331-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="53331-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="53331-107">\<behavior></span></span>  
<span data-ttu-id="53331-108">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="53331-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53331-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53331-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53331-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53331-110">Attributes and Elements</span></span>  
 <span data-ttu-id="53331-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53331-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53331-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="53331-112">Attributes</span></span>  
  
|<span data-ttu-id="53331-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="53331-113">Attribute</span></span>|<span data-ttu-id="53331-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="53331-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53331-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="53331-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="53331-116">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="53331-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53331-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53331-117">Child Elements</span></span>  
 <span data-ttu-id="53331-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="53331-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53331-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53331-119">Parent Elements</span></span>  
  
|<span data-ttu-id="53331-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="53331-120">Element</span></span>|<span data-ttu-id="53331-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="53331-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53331-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="53331-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="53331-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="53331-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53331-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="53331-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
