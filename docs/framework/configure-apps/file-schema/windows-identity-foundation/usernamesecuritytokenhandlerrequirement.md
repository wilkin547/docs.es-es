---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251746"
---
# \<userNameSecurityTokenHandlerRequirement>
<span data-ttu-id="71874-101">Proporciona la configuración para la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="71874-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="71874-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71874-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71874-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="71874-103">Attributes and Elements</span></span>  
 <span data-ttu-id="71874-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="71874-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71874-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="71874-105">Attributes</span></span>  
  
|<span data-ttu-id="71874-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="71874-106">Attribute</span></span>|<span data-ttu-id="71874-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="71874-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71874-108">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="71874-108">membershipProviderName</span></span>|<span data-ttu-id="71874-109">Especifica el <xref:System.Web.Security.MembershipProvider> que debe usar el controlador de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="71874-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71874-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="71874-110">Child Elements</span></span>  
 <span data-ttu-id="71874-111">None</span><span class="sxs-lookup"><span data-stu-id="71874-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71874-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="71874-112">Parent Elements</span></span>  
  
|<span data-ttu-id="71874-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="71874-113">Element</span></span>|<span data-ttu-id="71874-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="71874-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="71874-115">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="71874-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71874-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71874-116">Remarks</span></span>  
 <span data-ttu-id="71874-117">El `<userNameSecurityTokenHandlerRequirement>` elemento establece la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> propiedad cuando <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> se inicializa un objeto a partir de la configuración.</span><span class="sxs-lookup"><span data-stu-id="71874-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71874-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="71874-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
