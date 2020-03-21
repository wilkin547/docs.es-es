---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152546"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="88895-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="88895-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="88895-102">Proporciona configuración <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> para la clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="88895-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="88895-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="88895-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="88895-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="88895-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="88895-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="88895-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="88895-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="88895-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="88895-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<añadir>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="88895-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="88895-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span><span class="sxs-lookup"><span data-stu-id="88895-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88895-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88895-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88895-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88895-110">Attributes and Elements</span></span>  
 <span data-ttu-id="88895-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88895-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88895-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="88895-112">Attributes</span></span>  
  
|<span data-ttu-id="88895-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="88895-113">Attribute</span></span>|<span data-ttu-id="88895-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="88895-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88895-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="88895-115">lifetime</span></span>|<span data-ttu-id="88895-116">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="88895-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88895-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88895-117">Child Elements</span></span>  
 <span data-ttu-id="88895-118">None</span><span class="sxs-lookup"><span data-stu-id="88895-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88895-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88895-119">Parent Elements</span></span>  
  
|<span data-ttu-id="88895-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="88895-120">Element</span></span>|<span data-ttu-id="88895-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="88895-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88895-122">\<añadir></span><span class="sxs-lookup"><span data-stu-id="88895-122">\<add></span></span>](add.md)|<span data-ttu-id="88895-123">Agrega el controlador de token de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="88895-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="88895-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88895-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
