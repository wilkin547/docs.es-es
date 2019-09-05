---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252071"
---
# <a name="claimtype"></a><span data-ttu-id="69af1-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="69af1-101">\<claimType></span></span>
<span data-ttu-id="69af1-102">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="69af1-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
<span data-ttu-id="69af1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69af1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69af1-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="69af1-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="69af1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="69af1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="69af1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> claimTypeRequired**](claimtyperequired.md)</span><span class="sxs-lookup"><span data-stu-id="69af1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)</span></span>\  
<span data-ttu-id="69af1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimType**</span><span class="sxs-lookup"><span data-stu-id="69af1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69af1-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69af1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69af1-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69af1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="69af1-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69af1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69af1-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="69af1-111">Attributes</span></span>  
  
|<span data-ttu-id="69af1-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="69af1-112">Attribute</span></span>|<span data-ttu-id="69af1-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="69af1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69af1-114">type</span><span class="sxs-lookup"><span data-stu-id="69af1-114">type</span></span>|<span data-ttu-id="69af1-115">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="69af1-115">The claim type.</span></span> <span data-ttu-id="69af1-116">Normalmente es un URI.</span><span class="sxs-lookup"><span data-stu-id="69af1-116">Typically a URI.</span></span> <span data-ttu-id="69af1-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="69af1-117">Required.</span></span>|  
|<span data-ttu-id="69af1-118">opcional</span><span class="sxs-lookup"><span data-stu-id="69af1-118">optional</span></span>|<span data-ttu-id="69af1-119">Valor booleano que especifica si el tipo de demanda es opcional.</span><span class="sxs-lookup"><span data-stu-id="69af1-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="69af1-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="69af1-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69af1-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69af1-121">Child Elements</span></span>  
 <span data-ttu-id="69af1-122">None</span><span class="sxs-lookup"><span data-stu-id="69af1-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69af1-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69af1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="69af1-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="69af1-124">Element</span></span>|<span data-ttu-id="69af1-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="69af1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69af1-126">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="69af1-126">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="69af1-127">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="69af1-127">Specifies the set of required claims for incoming security tokens.</span></span>|
