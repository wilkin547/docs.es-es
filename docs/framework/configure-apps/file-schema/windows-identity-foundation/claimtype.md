---
description: 'Más información acerca de: <claimType>'
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 55fd32edc7fb810742c3cf678b434675aebba00e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664228"
---
# \<claimType>

<span data-ttu-id="ced18-102">Especifica una única demanda opcional o necesaria para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="ced18-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="ced18-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ced18-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ced18-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ced18-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ced18-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ced18-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ced18-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ced18-106">Attributes</span></span>  
  
|<span data-ttu-id="ced18-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ced18-107">Attribute</span></span>|<span data-ttu-id="ced18-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ced18-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ced18-109">type</span><span class="sxs-lookup"><span data-stu-id="ced18-109">type</span></span>|<span data-ttu-id="ced18-110">Tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="ced18-110">The claim type.</span></span> <span data-ttu-id="ced18-111">Normalmente es un URI.</span><span class="sxs-lookup"><span data-stu-id="ced18-111">Typically a URI.</span></span> <span data-ttu-id="ced18-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="ced18-112">Required.</span></span>|  
|<span data-ttu-id="ced18-113">opcional</span><span class="sxs-lookup"><span data-stu-id="ced18-113">optional</span></span>|<span data-ttu-id="ced18-114">Valor booleano que especifica si el tipo de demanda es opcional.</span><span class="sxs-lookup"><span data-stu-id="ced18-114">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="ced18-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="ced18-115">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ced18-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ced18-116">Child Elements</span></span>  

 <span data-ttu-id="ced18-117">None</span><span class="sxs-lookup"><span data-stu-id="ced18-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ced18-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ced18-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ced18-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ced18-119">Element</span></span>|<span data-ttu-id="ced18-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ced18-120">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="ced18-121">Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada.</span><span class="sxs-lookup"><span data-stu-id="ced18-121">Specifies the set of required claims for incoming security tokens.</span></span>|
