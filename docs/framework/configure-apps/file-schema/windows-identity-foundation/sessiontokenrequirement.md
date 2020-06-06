---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152546"
---
# \<sessionTokenRequirement>
<span data-ttu-id="eea4e-101">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="eea4e-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="eea4e-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eea4e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eea4e-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eea4e-103">Attributes and Elements</span></span>  
 <span data-ttu-id="eea4e-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eea4e-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eea4e-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="eea4e-105">Attributes</span></span>  
  
|<span data-ttu-id="eea4e-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="eea4e-106">Attribute</span></span>|<span data-ttu-id="eea4e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eea4e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eea4e-108">lifetime</span><span class="sxs-lookup"><span data-stu-id="eea4e-108">lifetime</span></span>|<span data-ttu-id="eea4e-109">Especifica la duración de los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="eea4e-109">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eea4e-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eea4e-110">Child Elements</span></span>  
 <span data-ttu-id="eea4e-111">None</span><span class="sxs-lookup"><span data-stu-id="eea4e-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eea4e-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eea4e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="eea4e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="eea4e-113">Element</span></span>|<span data-ttu-id="eea4e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="eea4e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="eea4e-115">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="eea4e-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="eea4e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eea4e-116">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
