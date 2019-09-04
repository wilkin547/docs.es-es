---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251827"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="36d6b-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="36d6b-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="36d6b-102">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="36d6b-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="36d6b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36d6b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36d6b-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="36d6b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="36d6b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="36d6b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="36d6b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="36d6b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="36d6b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="36d6b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="36d6b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sessionTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="36d6b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d6b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36d6b-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36d6b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="36d6b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36d6b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="36d6b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36d6b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="36d6b-112">Attributes</span></span>  
  
|<span data-ttu-id="36d6b-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="36d6b-113">Attribute</span></span>|<span data-ttu-id="36d6b-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="36d6b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36d6b-115">duración</span><span class="sxs-lookup"><span data-stu-id="36d6b-115">lifetime</span></span>|<span data-ttu-id="36d6b-116">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="36d6b-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36d6b-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="36d6b-117">Child Elements</span></span>  
 <span data-ttu-id="36d6b-118">None</span><span class="sxs-lookup"><span data-stu-id="36d6b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36d6b-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="36d6b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="36d6b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="36d6b-120">Element</span></span>|<span data-ttu-id="36d6b-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="36d6b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d6b-122">\<add></span><span class="sxs-lookup"><span data-stu-id="36d6b-122">\<add></span></span>](add.md)|<span data-ttu-id="36d6b-123">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="36d6b-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="36d6b-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36d6b-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
