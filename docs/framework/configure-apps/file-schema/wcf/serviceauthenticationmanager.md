---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 65488c34931f6d7c424ece58a4855e746ea455bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936421"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="c1dbc-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="c1dbc-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="c1dbc-102">Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, un mensaje o un autor en el nivel del servicio.</span><span class="sxs-lookup"><span data-stu-id="c1dbc-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="c1dbc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1dbc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1dbc-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="c1dbc-104">\<behaviors></span></span>  
<span data-ttu-id="c1dbc-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c1dbc-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c1dbc-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c1dbc-106">\<behavior></span></span>  
<span data-ttu-id="c1dbc-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="c1dbc-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1dbc-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1dbc-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1dbc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1dbc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c1dbc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1dbc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1dbc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1dbc-111">Attributes</span></span>  
  
|<span data-ttu-id="c1dbc-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c1dbc-112">Attribute</span></span>|<span data-ttu-id="c1dbc-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1dbc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1dbc-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="c1dbc-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="c1dbc-115">Cadena que especifica el tipo de la directiva de autenticación para el comportamiento actual.</span><span class="sxs-lookup"><span data-stu-id="c1dbc-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1dbc-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1dbc-116">Child Elements</span></span>  
 <span data-ttu-id="c1dbc-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1dbc-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1dbc-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1dbc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c1dbc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1dbc-119">Element</span></span>|<span data-ttu-id="c1dbc-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c1dbc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1dbc-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="c1dbc-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="c1dbc-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="c1dbc-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1dbc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1dbc-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
