---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: eefd18c206b7f013c3a423df424c795583c0dde8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075257"
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="b90c5-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="b90c5-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="b90c5-103">Registra a la resolución del token del emisor que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="b90c5-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b90c5-104">La resolución del emisor del token se utiliza para resolver el token de firma en mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="b90c5-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b90c5-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b90c5-105">\<system.identityModel></span></span>  
<span data-ttu-id="b90c5-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b90c5-106">\<identityConfiguration></span></span>  
<span data-ttu-id="b90c5-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b90c5-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b90c5-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b90c5-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b90c5-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b90c5-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b90c5-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b90c5-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b90c5-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b90c5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b90c5-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b90c5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b90c5-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b90c5-113">Attributes</span></span>  
  
|<span data-ttu-id="b90c5-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b90c5-114">Attribute</span></span>|<span data-ttu-id="b90c5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b90c5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b90c5-116">type</span><span class="sxs-lookup"><span data-stu-id="b90c5-116">type</span></span>|<span data-ttu-id="b90c5-117">Especifica el tipo de la resolución del token del emisor.</span><span class="sxs-lookup"><span data-stu-id="b90c5-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b90c5-118">Debe ser el <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase o un tipo que deriva la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="b90c5-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b90c5-119">Requerido.</span><span class="sxs-lookup"><span data-stu-id="b90c5-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b90c5-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b90c5-120">Child Elements</span></span>  
 <span data-ttu-id="b90c5-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b90c5-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b90c5-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b90c5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b90c5-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b90c5-123">Element</span></span>|<span data-ttu-id="b90c5-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b90c5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b90c5-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b90c5-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b90c5-126">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="b90c5-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b90c5-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b90c5-127">Remarks</span></span>  
 <span data-ttu-id="b90c5-128">La resolución del emisor del token se utiliza para resolver el token de firma en mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="b90c5-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b90c5-129">Sirve para recuperar el material criptográfico que se utiliza para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="b90c5-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b90c5-130">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="b90c5-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="b90c5-131">El tipo especificado puede ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizado que deriva la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="b90c5-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b90c5-132">Algunos controladores de tokens permiten especificar la configuración de resolución de tokens del emisor en la configuración.</span><span class="sxs-lookup"><span data-stu-id="b90c5-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b90c5-133">La configuración en los controladores de token individuales invalida los especificados en la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b90c5-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b90c5-134">Especificar el `<issuerTokenResolver>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b90c5-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b90c5-135">Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="b90c5-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b90c5-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b90c5-136">Example</span></span>  
 <span data-ttu-id="b90c5-137">El siguiente XML muestra la configuración para una resolución del token del emisor que se basa en una clase personalizada que deriva de <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="b90c5-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b90c5-138">La resolución del token mantiene un diccionario de pares de clave de audiencia que se inicializa a partir de un elemento de configuración personalizado (`<AddAudienceKeyPair>`) definidas para la clase.</span><span class="sxs-lookup"><span data-stu-id="b90c5-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b90c5-139">La clase invalida el <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> método para procesar este elemento.</span><span class="sxs-lookup"><span data-stu-id="b90c5-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b90c5-140">La invalidación se muestra en el ejemplo siguiente; Sin embargo, no se muestran los métodos que llama por motivos de brevedad.</span><span class="sxs-lookup"><span data-stu-id="b90c5-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b90c5-141">Para obtener un ejemplo completo, vea el `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b90c5-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b90c5-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b90c5-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b90c5-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b90c5-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
