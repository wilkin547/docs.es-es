---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 0940248364488bb38a329c5e461d72463c574e74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192050"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="a93e7-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="a93e7-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="a93e7-102">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="a93e7-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="a93e7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a93e7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a93e7-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a93e7-104">\<behaviors></span></span>  
<span data-ttu-id="a93e7-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a93e7-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a93e7-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a93e7-106">\<behavior></span></span>  
<span data-ttu-id="a93e7-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="a93e7-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93e7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a93e7-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a93e7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a93e7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a93e7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a93e7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a93e7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a93e7-111">Attributes</span></span>  
  
|<span data-ttu-id="a93e7-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="a93e7-112">Attribute</span></span>|<span data-ttu-id="a93e7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a93e7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a93e7-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="a93e7-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="a93e7-115">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="a93e7-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a93e7-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a93e7-116">Child Elements</span></span>  
 <span data-ttu-id="a93e7-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a93e7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a93e7-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a93e7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a93e7-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a93e7-119">Element</span></span>|<span data-ttu-id="a93e7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="a93e7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a93e7-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a93e7-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a93e7-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a93e7-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a93e7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a93e7-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
