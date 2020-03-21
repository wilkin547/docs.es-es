---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152676"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="152a1-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="152a1-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="152a1-102">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="152a1-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="152a1-103">El solucionador de tokens de emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="152a1-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="152a1-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="152a1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="152a1-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="152a1-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="152a1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="152a1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="152a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="152a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="152a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="152a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="152a1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="152a1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="152a1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="152a1-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="152a1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="152a1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="152a1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="152a1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="152a1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="152a1-113">Attributes</span></span>  
  
|<span data-ttu-id="152a1-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="152a1-114">Attribute</span></span>|<span data-ttu-id="152a1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="152a1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="152a1-116">type</span><span class="sxs-lookup"><span data-stu-id="152a1-116">type</span></span>|<span data-ttu-id="152a1-117">Especifica el tipo del solucionador de tokens de emisor.</span><span class="sxs-lookup"><span data-stu-id="152a1-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="152a1-118">Debe ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> la clase o un tipo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> que deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="152a1-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="152a1-119">Necesario.</span><span class="sxs-lookup"><span data-stu-id="152a1-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="152a1-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="152a1-120">Child Elements</span></span>  
 <span data-ttu-id="152a1-121">None</span><span class="sxs-lookup"><span data-stu-id="152a1-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="152a1-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="152a1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="152a1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="152a1-123">Element</span></span>|<span data-ttu-id="152a1-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="152a1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="152a1-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="152a1-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="152a1-126">Proporciona configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="152a1-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="152a1-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="152a1-127">Remarks</span></span>  
 <span data-ttu-id="152a1-128">El solucionador de tokens de emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="152a1-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="152a1-129">Se utiliza para recuperar el material criptográfico que se utiliza para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="152a1-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="152a1-130">Debe especificar `type` el atributo.</span><span class="sxs-lookup"><span data-stu-id="152a1-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="152a1-131">El tipo especificado puede <xref:System.IdentityModel.Tokens.IssuerTokenResolver> ser un tipo personalizado <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o uno que deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="152a1-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="152a1-132">Algunos controladores de tokens le permiten especificar la configuración del solucionador de tokens de emisor en la configuración.</span><span class="sxs-lookup"><span data-stu-id="152a1-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="152a1-133">La configuración de los controladores de tokens individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="152a1-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="152a1-134">Especificar el `<issuerTokenResolver>` elemento como un elemento secundario del elemento [ \<de>identityConfiguration](identityconfiguration.md) ha quedado en desuso, pero sigue siendo compatible con la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="152a1-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="152a1-135">La configuración `<securityTokenHandlerConfiguration>` del elemento `<identityConfiguration>` los reemplaza en el elemento.</span><span class="sxs-lookup"><span data-stu-id="152a1-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="152a1-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="152a1-136">Example</span></span>  
 <span data-ttu-id="152a1-137">El siguiente XML muestra la configuración de un solucionador de <xref:System.IdentityModel.Tokens.IssuerTokenResolver>tokens de emisor que se basa en una clase personalizada que deriva de .</span><span class="sxs-lookup"><span data-stu-id="152a1-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="152a1-138">El solucionador de tokens mantiene un diccionario de pares de clave`<AddAudienceKeyPair>`de audiencia que se inicializa a partir de un elemento de configuración personalizado ( ) definido para la clase.</span><span class="sxs-lookup"><span data-stu-id="152a1-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="152a1-139">La clase reemplaza <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> el método para procesar este elemento.</span><span class="sxs-lookup"><span data-stu-id="152a1-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="152a1-140">La invalidación se muestra en el ejemplo siguiente; sin embargo, los métodos a los que llama no se muestran por brevedad.</span><span class="sxs-lookup"><span data-stu-id="152a1-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="152a1-141">Para ver el ejemplo `CustomToken` completo, consulte el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="152a1-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="152a1-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="152a1-142">Example</span></span>
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="152a1-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="152a1-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
