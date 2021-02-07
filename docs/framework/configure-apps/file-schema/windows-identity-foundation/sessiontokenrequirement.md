---
description: 'Más información acerca de: <sessionTokenRequirement>'
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 8f2868df4939dc0dc7c779eb9ca5a35a6b996fc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698276"
---
# \<sessionTokenRequirement>

<span data-ttu-id="ccab9-102">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ccab9-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="ccab9-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccab9-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccab9-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ccab9-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ccab9-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ccab9-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccab9-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ccab9-106">Attributes</span></span>  
  
|<span data-ttu-id="ccab9-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="ccab9-107">Attribute</span></span>|<span data-ttu-id="ccab9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccab9-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ccab9-109">lifetime</span><span class="sxs-lookup"><span data-stu-id="ccab9-109">lifetime</span></span>|<span data-ttu-id="ccab9-110">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="ccab9-110">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccab9-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ccab9-111">Child Elements</span></span>  

 <span data-ttu-id="ccab9-112">None</span><span class="sxs-lookup"><span data-stu-id="ccab9-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccab9-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ccab9-113">Parent Elements</span></span>  
  
|<span data-ttu-id="ccab9-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccab9-114">Element</span></span>|<span data-ttu-id="ccab9-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccab9-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="ccab9-116">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="ccab9-116">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ccab9-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccab9-117">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
