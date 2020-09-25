---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: a86265ba3963ebc8bea880befbcf80345529116d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203857"
---
# \<claimTypeRequired>

<span data-ttu-id="caa3e-101">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="caa3e-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="caa3e-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caa3e-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caa3e-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="caa3e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="caa3e-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="caa3e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caa3e-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="caa3e-105">Attributes</span></span>  

 <span data-ttu-id="caa3e-106">None</span><span class="sxs-lookup"><span data-stu-id="caa3e-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="caa3e-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="caa3e-107">Child Elements</span></span>  
  
|<span data-ttu-id="caa3e-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="caa3e-108">Element</span></span>|<span data-ttu-id="caa3e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="caa3e-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="caa3e-110">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="caa3e-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="caa3e-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="caa3e-111">Parent Elements</span></span>  
  
|<span data-ttu-id="caa3e-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="caa3e-112">Element</span></span>|<span data-ttu-id="caa3e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="caa3e-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="caa3e-114">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="caa3e-114">Specifies service-level identity settings.</span></span>|
