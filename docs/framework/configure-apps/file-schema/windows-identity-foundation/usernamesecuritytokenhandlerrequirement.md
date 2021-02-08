---
description: 'Más información acerca de: <userNameSecurityTokenHandlerRequirement>'
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: c2bca086d06738699517fe140173f321a3233a4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786504"
---
# \<userNameSecurityTokenHandlerRequirement>

<span data-ttu-id="4b81b-102">Proporciona la configuración para la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="4b81b-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="4b81b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b81b-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b81b-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4b81b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="4b81b-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4b81b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b81b-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="4b81b-106">Attributes</span></span>  
  
|<span data-ttu-id="4b81b-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="4b81b-107">Attribute</span></span>|<span data-ttu-id="4b81b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b81b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b81b-109">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="4b81b-109">membershipProviderName</span></span>|<span data-ttu-id="4b81b-110">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4b81b-110">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b81b-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4b81b-111">Child Elements</span></span>  

 <span data-ttu-id="4b81b-112">None</span><span class="sxs-lookup"><span data-stu-id="4b81b-112">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b81b-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4b81b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="4b81b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b81b-114">Element</span></span>|<span data-ttu-id="4b81b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b81b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="4b81b-116">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="4b81b-116">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b81b-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b81b-117">Remarks</span></span>  

 <span data-ttu-id="4b81b-118">El `<userNameSecurityTokenHandlerRequirement>` elemento establece la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="4b81b-118">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b81b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b81b-119">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
