---
title: '&lt;add&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: cc1907d5f6117307ebadd04641c9eddc48e77cec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt"></a><span data-ttu-id="b9b96-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="b9b96-102">&lt;add&gt;</span></span>
<span data-ttu-id="b9b96-103">Agrega el controlador de token de seguridad especificado a la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="b9b96-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="b9b96-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b9b96-104">\<system.identityModel></span></span>  
<span data-ttu-id="b9b96-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b9b96-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b9b96-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b9b96-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b9b96-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b9b96-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b96-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9b96-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9b96-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b9b96-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b9b96-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b9b96-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9b96-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b9b96-111">Attributes</span></span>  
  
|<span data-ttu-id="b9b96-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b9b96-112">Attribute</span></span>|<span data-ttu-id="b9b96-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9b96-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9b96-114">type</span><span class="sxs-lookup"><span data-stu-id="b9b96-114">type</span></span>|<span data-ttu-id="b9b96-115">El nombre del tipo CLR del controlador de token va a agregar.</span><span class="sxs-lookup"><span data-stu-id="b9b96-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="b9b96-116">Para obtener más información sobre cómo especificar el `type` de atributo, vea [las referencias de tipos personalizado](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="b9b96-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9b96-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b9b96-117">Child Elements</span></span>  
  
|<span data-ttu-id="b9b96-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b9b96-118">Element</span></span>|<span data-ttu-id="b9b96-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9b96-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9b96-120">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b9b96-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="b9b96-121">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> (clase), el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="b9b96-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="b9b96-122">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b9b96-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="b9b96-123">Proporciona la configuración para el <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="b9b96-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="b9b96-124">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b9b96-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="b9b96-125">Proporciona la configuración para el <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="b9b96-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="b9b96-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b9b96-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="b9b96-127">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="b9b96-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b9b96-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b9b96-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b9b96-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="b9b96-129">Element</span></span>|<span data-ttu-id="b9b96-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9b96-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9b96-131">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b9b96-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="b9b96-132">Especifica una colección de controladores de tokens de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b9b96-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9b96-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9b96-133">Remarks</span></span>  
 <span data-ttu-id="b9b96-134">El `<add>` elemento puede tomar un único elemento secundario que especifica la configuración para el controlador de token.</span><span class="sxs-lookup"><span data-stu-id="b9b96-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="b9b96-135">Esto depende de si la clase del controlador al que hace referencia a través de la `type` atributo de la `<add>` elemento proporciona compatibilidad para esta característica.</span><span class="sxs-lookup"><span data-stu-id="b9b96-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="b9b96-136">Las clases de controlador de token que proporcionan esta característica deben exponer un constructor que toma un <xref:System.Xml.XmlElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="b9b96-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="b9b96-137">Algunas de las clases de controlador de token de seguridad integrados proporcionan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b9b96-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="b9b96-138">Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, y <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="b9b96-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9b96-139">La colección de controlador de token solo puede contener un único controlador de un tipo dado.</span><span class="sxs-lookup"><span data-stu-id="b9b96-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="b9b96-140">Esto significa, por ejemplo, que si desea agregar un controlador que se deriva de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase a la colección, primero debe quitar la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, que está presente de forma predeterminada, de la colección.</span><span class="sxs-lookup"><span data-stu-id="b9b96-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="b9b96-141">Puede usar el [ \<quitar >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) elemento para quitar un único controlador de la colección o el uso del [ \<borrar >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) elemento que se va a quitar todos los controladores de la colección.</span><span class="sxs-lookup"><span data-stu-id="b9b96-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="b9b96-142">La configuración especificada en un controlador de invalida la configuración equivalente especificada en la colección de controlador de token en el [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento y a la que se especifica en el nivel de servicio en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="b9b96-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9b96-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9b96-143">Example</span></span>  
 <span data-ttu-id="b9b96-144">El siguiente XML muestra el uso de la `<add>` y `<remove>` elementos para reemplazar el controlador de token de sesión de forma predeterminada con un controlador de token de sesión personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b9b96-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="b9b96-145">El XML procede de la `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b9b96-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
