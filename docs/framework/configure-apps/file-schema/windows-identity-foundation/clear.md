---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252044"
---
# <a name="clear"></a><span data-ttu-id="d2189-101">\<clear></span><span class="sxs-lookup"><span data-stu-id="d2189-101">\<clear></span></span>
<span data-ttu-id="d2189-102">Borra todos los controladores de token de seguridad de la colección de controladores de tokens actual.</span><span class="sxs-lookup"><span data-stu-id="d2189-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="d2189-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2189-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2189-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2189-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d2189-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d2189-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d2189-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d2189-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d2189-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<borrar >**</span><span class="sxs-lookup"><span data-stu-id="d2189-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2189-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2189-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2189-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d2189-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d2189-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d2189-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2189-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d2189-111">Attributes</span></span>  
 <span data-ttu-id="d2189-112">None</span><span class="sxs-lookup"><span data-stu-id="d2189-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d2189-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d2189-113">Child Elements</span></span>  
 <span data-ttu-id="d2189-114">None</span><span class="sxs-lookup"><span data-stu-id="d2189-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d2189-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d2189-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d2189-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="d2189-116">Element</span></span>|<span data-ttu-id="d2189-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d2189-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2189-118">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d2189-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="d2189-119">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d2189-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
