---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 8775e3044e58886cfa53a9fd9fc8b4b8ed2105b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251950"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="33150-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="33150-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="33150-102">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="33150-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="33150-103">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="33150-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="33150-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33150-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33150-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="33150-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="33150-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="33150-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="33150-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="33150-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="33150-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="33150-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="33150-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> issuerTokenResolver**</span><span class="sxs-lookup"><span data-stu-id="33150-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33150-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33150-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33150-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33150-111">Attributes and Elements</span></span>  
 <span data-ttu-id="33150-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33150-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33150-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="33150-113">Attributes</span></span>  
  
|<span data-ttu-id="33150-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="33150-114">Attribute</span></span>|<span data-ttu-id="33150-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33150-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33150-116">type</span><span class="sxs-lookup"><span data-stu-id="33150-116">type</span></span>|<span data-ttu-id="33150-117">Especifica el tipo de solucionador de tokens del emisor.</span><span class="sxs-lookup"><span data-stu-id="33150-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="33150-118">Debe ser la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase o un tipo que deriva de la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="33150-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="33150-119">Necesario.</span><span class="sxs-lookup"><span data-stu-id="33150-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33150-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33150-120">Child Elements</span></span>  
 <span data-ttu-id="33150-121">None</span><span class="sxs-lookup"><span data-stu-id="33150-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33150-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33150-122">Parent Elements</span></span>  
  
|<span data-ttu-id="33150-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="33150-123">Element</span></span>|<span data-ttu-id="33150-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33150-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33150-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="33150-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="33150-126">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="33150-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33150-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33150-127">Remarks</span></span>  
 <span data-ttu-id="33150-128">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="33150-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="33150-129">Se utiliza para recuperar el material criptográfico que se usa para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="33150-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="33150-130">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="33150-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="33150-131">El tipo especificado puede ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="33150-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="33150-132">Algunos controladores de token permiten especificar la configuración de la resolución de tokens del emisor en la configuración.</span><span class="sxs-lookup"><span data-stu-id="33150-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="33150-133">La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="33150-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33150-134">Especificar el `<issuerTokenResolver>` elemento como elemento secundario [ \<](identityconfiguration.md) del elemento de > identityConfiguration está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="33150-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="33150-135">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="33150-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33150-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33150-136">Example</span></span>  
 <span data-ttu-id="33150-137">El siguiente XML muestra la configuración de un solucionador de tokens de emisor que se basa en una clase personalizada que deriva <xref:System.IdentityModel.Tokens.IssuerTokenResolver>de.</span><span class="sxs-lookup"><span data-stu-id="33150-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="33150-138">La resolución de tokens mantiene un diccionario de pares de clave de audiencia que se inicializa a partir de un elemento de`<AddAudienceKeyPair>`configuración personalizado () definido para la clase.</span><span class="sxs-lookup"><span data-stu-id="33150-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="33150-139">La clase invalida el <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> método para procesar este elemento.</span><span class="sxs-lookup"><span data-stu-id="33150-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="33150-140">La invalidación se muestra en el ejemplo siguiente: sin embargo, los métodos a los que llama no se muestran por motivos de brevedad.</span><span class="sxs-lookup"><span data-stu-id="33150-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="33150-141">Para obtener el ejemplo completo, vea `CustomToken` el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33150-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="33150-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33150-142">Example</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="33150-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="33150-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
