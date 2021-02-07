---
description: 'Más información acerca de: <claimTypeRequired>'
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: ba95c56af431a6dd81323751a42ce47160544cc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664176"
---
# \<claimTypeRequired>

<span data-ttu-id="03a02-102">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="03a02-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="03a02-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03a02-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03a02-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03a02-104">Attributes and Elements</span></span>  

 <span data-ttu-id="03a02-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03a02-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03a02-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="03a02-106">Attributes</span></span>  

 <span data-ttu-id="03a02-107">None</span><span class="sxs-lookup"><span data-stu-id="03a02-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03a02-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03a02-108">Child Elements</span></span>  
  
|<span data-ttu-id="03a02-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="03a02-109">Element</span></span>|<span data-ttu-id="03a02-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="03a02-110">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="03a02-111">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="03a02-111">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03a02-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03a02-112">Parent Elements</span></span>  
  
|<span data-ttu-id="03a02-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="03a02-113">Element</span></span>|<span data-ttu-id="03a02-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="03a02-114">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="03a02-115">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="03a02-115">Specifies service-level identity settings.</span></span>|
