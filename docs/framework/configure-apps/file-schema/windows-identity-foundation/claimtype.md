---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 1b5427210142c70c31c5f736c9b5e281dca53f33
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150874"
---
# \<claimType>

<span data-ttu-id="be198-101">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="be198-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="be198-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be198-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="be198-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="be198-103">Attributes and Elements</span></span>  

 <span data-ttu-id="be198-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="be198-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="be198-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="be198-105">Attributes</span></span>  
  
|<span data-ttu-id="be198-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="be198-106">Attribute</span></span>|<span data-ttu-id="be198-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="be198-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="be198-108">type</span><span class="sxs-lookup"><span data-stu-id="be198-108">type</span></span>|<span data-ttu-id="be198-109">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="be198-109">The claim type.</span></span> <span data-ttu-id="be198-110">Normalmente es un URI.</span><span class="sxs-lookup"><span data-stu-id="be198-110">Typically a URI.</span></span> <span data-ttu-id="be198-111">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="be198-111">Required.</span></span>|  
|<span data-ttu-id="be198-112">opcional</span><span class="sxs-lookup"><span data-stu-id="be198-112">optional</span></span>|<span data-ttu-id="be198-113">Valor booleano que especifica si el tipo de demanda es opcional.</span><span class="sxs-lookup"><span data-stu-id="be198-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="be198-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="be198-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="be198-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="be198-115">Child Elements</span></span>  

 <span data-ttu-id="be198-116">None</span><span class="sxs-lookup"><span data-stu-id="be198-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="be198-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="be198-117">Parent Elements</span></span>  
  
|<span data-ttu-id="be198-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="be198-118">Element</span></span>|<span data-ttu-id="be198-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="be198-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="be198-120">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="be198-120">Specifies the set of required claims for incoming security tokens.</span></span>|
