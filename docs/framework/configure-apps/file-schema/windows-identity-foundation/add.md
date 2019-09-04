---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 932e8452542ace66824fba1262694c220ce88676
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252186"
---
# <a name="add"></a><span data-ttu-id="da508-101">\<add></span><span class="sxs-lookup"><span data-stu-id="da508-101">\<add></span></span>
<span data-ttu-id="da508-102">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="da508-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="da508-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da508-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da508-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="da508-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="da508-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="da508-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="da508-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="da508-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="da508-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="da508-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da508-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da508-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da508-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="da508-109">Attributes and Elements</span></span>  
 <span data-ttu-id="da508-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="da508-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da508-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="da508-111">Attributes</span></span>  
  
|<span data-ttu-id="da508-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="da508-112">Attribute</span></span>|<span data-ttu-id="da508-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da508-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da508-114">type</span><span class="sxs-lookup"><span data-stu-id="da508-114">type</span></span>|<span data-ttu-id="da508-115">Nombre del tipo de CLR del controlador de token que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="da508-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="da508-116">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="da508-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da508-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="da508-117">Child Elements</span></span>  
  
|<span data-ttu-id="da508-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="da508-118">Element</span></span>|<span data-ttu-id="da508-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da508-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da508-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="da508-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="da508-121">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="da508-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="da508-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="da508-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="da508-123">Proporciona la configuración para <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="da508-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="da508-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="da508-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="da508-125">Proporciona la configuración para <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="da508-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="da508-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="da508-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="da508-127">Proporciona una configuración opcional para <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> la clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="da508-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da508-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="da508-128">Parent Elements</span></span>  
  
|<span data-ttu-id="da508-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="da508-129">Element</span></span>|<span data-ttu-id="da508-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="da508-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da508-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="da508-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="da508-132">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="da508-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da508-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da508-133">Remarks</span></span>  
 <span data-ttu-id="da508-134">El `<add>` elemento puede tomar un único elemento secundario que especifica la configuración del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="da508-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="da508-135">Esto depende de si la clase `type` `<add>` de controlador a la que se hace referencia mediante el atributo del elemento proporciona compatibilidad para esta característica.</span><span class="sxs-lookup"><span data-stu-id="da508-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="da508-136">Las clases de controlador de token que proporcionan esta característica deben exponer un constructor <xref:System.Xml.XmlElement> que toma un objeto.</span><span class="sxs-lookup"><span data-stu-id="da508-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="da508-137">Algunas de las clases de controlador de tokens de seguridad integradas proporcionan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="da508-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="da508-138">Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>,, ,<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>y .<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="da508-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="da508-139">La colección de controladores de token solo puede contener un único controlador de cualquier tipo dado.</span><span class="sxs-lookup"><span data-stu-id="da508-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="da508-140">Esto significa, por ejemplo, que si desea agregar un controlador que se deriva de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase a la colección, primero debe <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>quitar, que está presente de forma predeterminada, de la colección.</span><span class="sxs-lookup"><span data-stu-id="da508-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="da508-141">Puede usar el [ \<elemento Remove >](remove.md) para quitar un único controlador de la colección o utilizar el [ \<elemento Clear >](clear.md) para quitar todos los controladores de la colección.</span><span class="sxs-lookup"><span data-stu-id="da508-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="da508-142">La configuración especificada en un controlador invalida los valores equivalentes especificados en la colección de controladores de tokens en el [ \<elemento > securityTokenHandlerConfiguration](securitytokenhandlerconfiguration.md) y los especificados en el nivel de servicio en el [ \< elemento > identityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="da508-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da508-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da508-143">Example</span></span>  
 <span data-ttu-id="da508-144">El siguiente XML muestra el uso de los `<add>` elementos `<remove>` y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="da508-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="da508-145">El XML se toma `ClaimsAwareWebFarm` del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="da508-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
