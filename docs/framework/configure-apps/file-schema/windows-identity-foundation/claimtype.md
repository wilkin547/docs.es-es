---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942882"
---
# <a name="claimtype"></a><span data-ttu-id="47081-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="47081-101">\<claimType></span></span>
<span data-ttu-id="47081-102">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="47081-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="47081-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="47081-103">\<system.identityModel></span></span>  
<span data-ttu-id="47081-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="47081-104">\<identityConfiguration></span></span>  
<span data-ttu-id="47081-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="47081-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="47081-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="47081-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47081-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47081-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47081-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="47081-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47081-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="47081-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47081-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="47081-110">Attributes</span></span>  
  
|<span data-ttu-id="47081-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="47081-111">Attribute</span></span>|<span data-ttu-id="47081-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="47081-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47081-113">type</span><span class="sxs-lookup"><span data-stu-id="47081-113">type</span></span>|<span data-ttu-id="47081-114">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="47081-114">The claim type.</span></span> <span data-ttu-id="47081-115">Normalmente es un URI.</span><span class="sxs-lookup"><span data-stu-id="47081-115">Typically a URI.</span></span> <span data-ttu-id="47081-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="47081-116">Required.</span></span>|  
|<span data-ttu-id="47081-117">opcional</span><span class="sxs-lookup"><span data-stu-id="47081-117">optional</span></span>|<span data-ttu-id="47081-118">Valor booleano que especifica si el tipo de demanda es opcional.</span><span class="sxs-lookup"><span data-stu-id="47081-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="47081-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="47081-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47081-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="47081-120">Child Elements</span></span>  
 <span data-ttu-id="47081-121">None</span><span class="sxs-lookup"><span data-stu-id="47081-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47081-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="47081-122">Parent Elements</span></span>  
  
|<span data-ttu-id="47081-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="47081-123">Element</span></span>|<span data-ttu-id="47081-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="47081-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47081-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="47081-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="47081-126">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="47081-126">Specifies the set of required claims for incoming security tokens.</span></span>|
