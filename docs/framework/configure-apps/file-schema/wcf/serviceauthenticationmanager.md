---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399708"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="9c238-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="9c238-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="9c238-102">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c238-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="9c238-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9c238-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9c238-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9c238-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9c238-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9c238-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9c238-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9c238-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="9c238-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9c238-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="9c238-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceAuthenticationManager**</span><span class="sxs-lookup"><span data-stu-id="9c238-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c238-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c238-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c238-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c238-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9c238-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c238-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c238-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c238-112">Attributes</span></span>  
  
|<span data-ttu-id="9c238-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9c238-113">Attribute</span></span>|<span data-ttu-id="9c238-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9c238-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c238-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="9c238-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="9c238-116">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="9c238-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c238-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c238-117">Child Elements</span></span>  
 <span data-ttu-id="9c238-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9c238-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c238-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c238-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9c238-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c238-120">Element</span></span>|<span data-ttu-id="9c238-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9c238-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c238-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9c238-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9c238-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9c238-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c238-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c238-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
