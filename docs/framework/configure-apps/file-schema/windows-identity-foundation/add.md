---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73973799"
---
# \<add>
<span data-ttu-id="9bfe4-101">Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-101">Adds the specified security token handler to the token handler collection.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="9bfe4-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bfe4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bfe4-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9bfe4-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9bfe4-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bfe4-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="9bfe4-105">Attributes</span></span>  
  
|<span data-ttu-id="9bfe4-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="9bfe4-106">Attribute</span></span>|<span data-ttu-id="9bfe4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bfe4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9bfe4-108">type</span><span class="sxs-lookup"><span data-stu-id="9bfe4-108">type</span></span>|<span data-ttu-id="9bfe4-109">Nombre del tipo de CLR del controlador de token que se va a agregar.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-109">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="9bfe4-110">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="9bfe4-110">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bfe4-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9bfe4-111">Child Elements</span></span>  
  
|<span data-ttu-id="9bfe4-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bfe4-112">Element</span></span>|<span data-ttu-id="9bfe4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bfe4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="9bfe4-114">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-114">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|<span data-ttu-id="9bfe4-115">Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="9bfe4-116">Proporciona la configuración para la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-116">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="9bfe4-117">Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-117">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bfe4-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9bfe4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9bfe4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bfe4-119">Element</span></span>|<span data-ttu-id="9bfe4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bfe4-120">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="9bfe4-121">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-121">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bfe4-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9bfe4-122">Remarks</span></span>  
 <span data-ttu-id="9bfe4-123">El `<add>` elemento puede tomar un único elemento secundario que especifica la configuración del controlador de token.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-123">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="9bfe4-124">Esto depende de si la clase de controlador a la que se hace referencia mediante el `type` atributo del `<add>` elemento proporciona compatibilidad para esta característica.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-124">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="9bfe4-125">Las clases de controlador de token que proporcionan esta característica deben exponer un constructor que toma un <xref:System.Xml.XmlElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-125">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="9bfe4-126">Algunas de las clases de controlador de tokens de seguridad integradas proporcionan esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-126">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="9bfe4-127">Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> y <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="9bfe4-127">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9bfe4-128">La colección de controladores de token solo puede contener un único controlador de cualquier tipo dado.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-128">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="9bfe4-129">Esto significa, por ejemplo, que si desea agregar un controlador que se deriva de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase a la colección, primero debe quitar <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , que está presente de forma predeterminada, de la colección.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-129">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="9bfe4-130">Puede usar el [\<remove>](remove.md) elemento para quitar un solo controlador de la colección o utilizar el [\<clear>](clear.md) elemento para quitar todos los controladores de la colección.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-130">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="9bfe4-131">La configuración especificada en un controlador invalida los valores equivalentes especificados en la colección de controladores de tokens en el [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento y los especificados en el nivel de servicio bajo el [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-131">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9bfe4-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9bfe4-132">Example</span></span>  
 <span data-ttu-id="9bfe4-133">El siguiente XML muestra el uso de los `<add>` `<remove>` elementos y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-133">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="9bfe4-134">El XML se toma del `ClaimsAwareWebFarm` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9bfe4-134">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
