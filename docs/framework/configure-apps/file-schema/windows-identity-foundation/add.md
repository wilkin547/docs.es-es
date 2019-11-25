---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973799"
---
# <a name="add"></a><span data-ttu-id="5bf72-101">\<add></span><span class="sxs-lookup"><span data-stu-id="5bf72-101">\<add></span></span>
<span data-ttu-id="5bf72-102">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5bf72-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="5bf72-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5bf72-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5bf72-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5bf72-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5bf72-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5bf72-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5bf72-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers**](securitytokenhandlers.md) ></span><span class="sxs-lookup"><span data-stu-id="5bf72-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="5bf72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**</span><span class="sxs-lookup"><span data-stu-id="5bf72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf72-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bf72-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bf72-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5bf72-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5bf72-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5bf72-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bf72-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5bf72-111">Attributes</span></span>  
  
|<span data-ttu-id="5bf72-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5bf72-112">Attribute</span></span>|<span data-ttu-id="5bf72-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bf72-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5bf72-114">tipo</span><span class="sxs-lookup"><span data-stu-id="5bf72-114">type</span></span>|<span data-ttu-id="5bf72-115">Nombre del tipo de CLR del controlador de token que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="5bf72-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="5bf72-116">Para obtener más información sobre cómo especificar el atributo `type`, vea [referencias a tipos personalizados](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="5bf72-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bf72-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5bf72-117">Child Elements</span></span>  
  
|<span data-ttu-id="5bf72-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bf72-118">Element</span></span>|<span data-ttu-id="5bf72-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bf72-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bf72-120">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="5bf72-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="5bf72-121">Proporciona la configuración para la clase <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, la clase <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="5bf72-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="5bf72-122">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="5bf72-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="5bf72-123">Proporciona la configuración para la clase <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="5bf72-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="5bf72-124">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="5bf72-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="5bf72-125">Proporciona la configuración para la clase <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="5bf72-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="5bf72-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="5bf72-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="5bf72-127">Proporciona una configuración opcional para la clase <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="5bf72-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bf72-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5bf72-128">Parent Elements</span></span>  
  
|<span data-ttu-id="5bf72-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bf72-129">Element</span></span>|<span data-ttu-id="5bf72-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bf72-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bf72-131">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="5bf72-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="5bf72-132">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5bf72-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bf72-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5bf72-133">Remarks</span></span>  
 <span data-ttu-id="5bf72-134">El elemento `<add>` puede tomar un único elemento secundario que especifica la configuración del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="5bf72-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="5bf72-135">Esto depende de si la clase de controlador a la que se hace referencia a través del atributo `type` del elemento `<add>` proporciona compatibilidad con esta característica.</span><span class="sxs-lookup"><span data-stu-id="5bf72-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="5bf72-136">Las clases de controlador de token que proporcionan esta característica deben exponer un constructor que toma un objeto <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="5bf72-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="5bf72-137">Algunas de las clases de controlador de tokens de seguridad integradas proporcionan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="5bf72-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="5bf72-138">Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>y <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="5bf72-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5bf72-139">La colección de controladores de token solo puede contener un único controlador de cualquier tipo dado.</span><span class="sxs-lookup"><span data-stu-id="5bf72-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="5bf72-140">Esto significa, por ejemplo, que si desea agregar un controlador que se deriva de la clase <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> a la colección, primero debe quitar el <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, que está presente de forma predeterminada, de la colección.</span><span class="sxs-lookup"><span data-stu-id="5bf72-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="5bf72-141">Puede usar el elemento [\<remove >](remove.md) para quitar un solo controlador de la colección o utilizar el elemento [\<Clear >](clear.md) para quitar todos los controladores de la colección.</span><span class="sxs-lookup"><span data-stu-id="5bf72-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="5bf72-142">La configuración especificada en un controlador invalida los valores de configuración equivalentes especificados en la colección de controladores de tokens en el elemento [\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md) y los especificados en el nivel de servicio bajo el elemento [\<identityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="5bf72-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bf72-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bf72-143">Example</span></span>  
 <span data-ttu-id="5bf72-144">El siguiente XML muestra el uso de los elementos `<add>` y `<remove>` para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="5bf72-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="5bf72-145">El XML se toma del ejemplo `ClaimsAwareWebFarm`.</span><span class="sxs-lookup"><span data-stu-id="5bf72-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
