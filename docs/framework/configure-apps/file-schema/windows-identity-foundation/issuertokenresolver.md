---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 946ae8601e1e4563becd0b346b6c792724405a45
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165044"
---
# \<issuerTokenResolver>

<span data-ttu-id="e5be1-101">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="e5be1-101">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e5be1-102">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e5be1-102">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="e5be1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5be1-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5be1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e5be1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e5be1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e5be1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5be1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="e5be1-106">Attributes</span></span>  
  
|<span data-ttu-id="e5be1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="e5be1-107">Attribute</span></span>|<span data-ttu-id="e5be1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5be1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5be1-109">type</span><span class="sxs-lookup"><span data-stu-id="e5be1-109">type</span></span>|<span data-ttu-id="e5be1-110">Especifica el tipo de solucionador de tokens del emisor.</span><span class="sxs-lookup"><span data-stu-id="e5be1-110">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e5be1-111">Debe ser la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase o un tipo que deriva de la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="e5be1-111">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e5be1-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e5be1-112">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5be1-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e5be1-113">Child Elements</span></span>  

 <span data-ttu-id="e5be1-114">None</span><span class="sxs-lookup"><span data-stu-id="e5be1-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5be1-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e5be1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e5be1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="e5be1-116">Element</span></span>|<span data-ttu-id="e5be1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5be1-117">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e5be1-118">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e5be1-118">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5be1-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5be1-119">Remarks</span></span>  

 <span data-ttu-id="e5be1-120">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="e5be1-120">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e5be1-121">Se utiliza para recuperar el material criptográfico que se usa para comprobar la firma.</span><span class="sxs-lookup"><span data-stu-id="e5be1-121">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e5be1-122">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="e5be1-122">You must specify the `type` attribute.</span></span> <span data-ttu-id="e5be1-123">El tipo especificado puede ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="e5be1-123">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e5be1-124">Algunos controladores de token permiten especificar la configuración de la resolución de tokens del emisor en la configuración.</span><span class="sxs-lookup"><span data-stu-id="e5be1-124">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e5be1-125">La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e5be1-125">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5be1-126">Especificar el `<issuerTokenResolver>` elemento como elemento secundario del [\<identityConfiguration>](identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="e5be1-126">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e5be1-127">La configuración del `<securityTokenHandlerConfiguration>` elemento invalida la del `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e5be1-127">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5be1-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5be1-128">Example</span></span>  

 <span data-ttu-id="e5be1-129">El siguiente XML muestra la configuración de un solucionador de tokens de emisor que se basa en una clase personalizada que deriva de <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .</span><span class="sxs-lookup"><span data-stu-id="e5be1-129">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e5be1-130">La resolución de tokens mantiene un diccionario de pares de clave de audiencia que se inicializa a partir de un elemento de configuración personalizado ( `<AddAudienceKeyPair>` ) definido para la clase.</span><span class="sxs-lookup"><span data-stu-id="e5be1-130">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e5be1-131">La clase invalida el <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> método para procesar este elemento.</span><span class="sxs-lookup"><span data-stu-id="e5be1-131">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e5be1-132">La invalidación se muestra en el ejemplo siguiente: sin embargo, los métodos a los que llama no se muestran por motivos de brevedad.</span><span class="sxs-lookup"><span data-stu-id="e5be1-132">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e5be1-133">Para obtener el ejemplo completo, vea el `CustomToken` ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e5be1-133">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e5be1-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5be1-134">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5be1-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5be1-135">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
