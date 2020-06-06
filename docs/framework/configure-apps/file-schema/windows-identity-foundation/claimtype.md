---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252071"
---
# \<claimType>
<span data-ttu-id="cd5e9-101">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="cd5e9-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd5e9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd5e9-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cd5e9-103">Attributes and Elements</span></span>  
 <span data-ttu-id="cd5e9-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd5e9-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd5e9-105">Attributes</span></span>  
  
|<span data-ttu-id="cd5e9-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="cd5e9-106">Attribute</span></span>|<span data-ttu-id="cd5e9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd5e9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd5e9-108">type</span><span class="sxs-lookup"><span data-stu-id="cd5e9-108">type</span></span>|<span data-ttu-id="cd5e9-109">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-109">The claim type.</span></span> <span data-ttu-id="cd5e9-110">Normalmente es un URI.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-110">Typically a URI.</span></span> <span data-ttu-id="cd5e9-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-111">Required.</span></span>|  
|<span data-ttu-id="cd5e9-112">opcional</span><span class="sxs-lookup"><span data-stu-id="cd5e9-112">optional</span></span>|<span data-ttu-id="cd5e9-113">Valor booleano que especifica si el tipo de demanda es opcional.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="cd5e9-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd5e9-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cd5e9-115">Child Elements</span></span>  
 <span data-ttu-id="cd5e9-116">None</span><span class="sxs-lookup"><span data-stu-id="cd5e9-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd5e9-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cd5e9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cd5e9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd5e9-118">Element</span></span>|<span data-ttu-id="cd5e9-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd5e9-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="cd5e9-120">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="cd5e9-120">Specifies the set of required claims for incoming security tokens.</span></span>|
