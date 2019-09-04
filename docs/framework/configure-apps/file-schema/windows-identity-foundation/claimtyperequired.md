---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252058"
---
# <a name="claimtyperequired"></a><span data-ttu-id="a4db7-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="a4db7-101">\<claimTypeRequired></span></span>
<span data-ttu-id="a4db7-102">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="a4db7-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="a4db7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a4db7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a4db7-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a4db7-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a4db7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a4db7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a4db7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> claimTypeRequired**</span><span class="sxs-lookup"><span data-stu-id="a4db7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4db7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4db7-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4db7-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a4db7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a4db7-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a4db7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4db7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a4db7-110">Attributes</span></span>  
 <span data-ttu-id="a4db7-111">None</span><span class="sxs-lookup"><span data-stu-id="a4db7-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a4db7-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a4db7-112">Child Elements</span></span>  
  
|<span data-ttu-id="a4db7-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4db7-113">Element</span></span>|<span data-ttu-id="a4db7-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a4db7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4db7-115">\<claimType></span><span class="sxs-lookup"><span data-stu-id="a4db7-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="a4db7-116">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="a4db7-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a4db7-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a4db7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a4db7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a4db7-118">Element</span></span>|<span data-ttu-id="a4db7-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a4db7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a4db7-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a4db7-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a4db7-121">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="a4db7-121">Specifies service-level identity settings.</span></span>|
