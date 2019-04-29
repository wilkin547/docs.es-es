---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 34643d10ef1ed2e87152e5013634e62859e0594e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791773"
---
# <a name="add"></a><span data-ttu-id="209de-101">\<add></span><span class="sxs-lookup"><span data-stu-id="209de-101">\<add></span></span>
<span data-ttu-id="209de-102">Agrega el controlador de token de seguridad especificado a la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="209de-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="209de-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="209de-103">\<system.identityModel></span></span>  
<span data-ttu-id="209de-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="209de-104">\<identityConfiguration></span></span>  
<span data-ttu-id="209de-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="209de-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="209de-106">\<add></span><span class="sxs-lookup"><span data-stu-id="209de-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="209de-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="209de-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="209de-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="209de-108">Attributes and Elements</span></span>  
 <span data-ttu-id="209de-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="209de-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="209de-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="209de-110">Attributes</span></span>  
  
|<span data-ttu-id="209de-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="209de-111">Attribute</span></span>|<span data-ttu-id="209de-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="209de-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="209de-113">type</span><span class="sxs-lookup"><span data-stu-id="209de-113">type</span></span>|<span data-ttu-id="209de-114">El nombre del tipo CLR del controlador de token que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="209de-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="209de-115">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="209de-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="209de-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="209de-116">Child Elements</span></span>  
  
|<span data-ttu-id="209de-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="209de-117">Element</span></span>|<span data-ttu-id="209de-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="209de-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="209de-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="209de-119">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="209de-120">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="209de-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="209de-121">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="209de-121">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="209de-122">Proporciona la configuración de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="209de-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="209de-123">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="209de-123">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="209de-124">Proporciona la configuración de la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="209de-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="209de-125">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="209de-125">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="209de-126">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="209de-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="209de-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="209de-127">Parent Elements</span></span>  
  
|<span data-ttu-id="209de-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="209de-128">Element</span></span>|<span data-ttu-id="209de-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="209de-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="209de-130">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="209de-130">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="209de-131">Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="209de-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="209de-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="209de-132">Remarks</span></span>  
 <span data-ttu-id="209de-133">El `<add>` elemento puede tomar un único elemento secundario que especifica la configuración para el controlador de token.</span><span class="sxs-lookup"><span data-stu-id="209de-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="209de-134">Esto depende de si hace referencia la clase de controlador a través de la `type` atributo de la `<add>` elemento proporciona compatibilidad para esta característica.</span><span class="sxs-lookup"><span data-stu-id="209de-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="209de-135">Clases de controlador de token que proporcionan esta característica deben exponer un constructor que toma un <xref:System.Xml.XmlElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="209de-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="209de-136">Algunas de las clases de controlador de token de seguridad integradas proporcionan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="209de-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="209de-137">Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, y <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="209de-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="209de-138">La colección de controladores de token solo puede contener un único controlador de un tipo dado.</span><span class="sxs-lookup"><span data-stu-id="209de-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="209de-139">Esto significa, por ejemplo, que si desea agregar un controlador que se deriva el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase a la colección, primero debe quitar el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, que está presente de forma predeterminada, de la colección.</span><span class="sxs-lookup"><span data-stu-id="209de-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="209de-140">Puede usar el [ \<quitar >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) elemento para quitar un único controlador de la colección o el uso del [ \<borrar >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) elemento que se va a quitar todos los controladores de la colección.</span><span class="sxs-lookup"><span data-stu-id="209de-140">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="209de-141">Configuración especificada en un controlador invalida la configuración equivalente especificada en la colección de controladores de token en el [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento y los especificados en el nivel de servicio bajo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="209de-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="209de-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="209de-142">Example</span></span>  
 <span data-ttu-id="209de-143">El siguiente XML muestra el uso de la `<add>` y `<remove>` elementos que se va a reemplazar el controlador de token de sesión de forma predeterminada con un controlador de token de sesión personalizada.</span><span class="sxs-lookup"><span data-stu-id="209de-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="209de-144">El XML procede de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="209de-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
