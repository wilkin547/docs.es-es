---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251846"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="de4ea-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="de4ea-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="de4ea-102">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="de4ea-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="de4ea-103">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="de4ea-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="de4ea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de4ea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de4ea-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="de4ea-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="de4ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="de4ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="de4ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="de4ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="de4ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="de4ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="de4ea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> serviceTokenResolver**</span><span class="sxs-lookup"><span data-stu-id="de4ea-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de4ea-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de4ea-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de4ea-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="de4ea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="de4ea-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="de4ea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de4ea-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="de4ea-113">Attributes</span></span>  
  
|<span data-ttu-id="de4ea-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="de4ea-114">Attribute</span></span>|<span data-ttu-id="de4ea-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="de4ea-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de4ea-116">type</span><span class="sxs-lookup"><span data-stu-id="de4ea-116">type</span></span>|<span data-ttu-id="de4ea-117">Especifica el tipo de la resolución del token de servicio.</span><span class="sxs-lookup"><span data-stu-id="de4ea-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="de4ea-118">Tipo o tipo que se deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="de4ea-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="de4ea-119">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="de4ea-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="de4ea-120">Necesario.</span><span class="sxs-lookup"><span data-stu-id="de4ea-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de4ea-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="de4ea-121">Child Elements</span></span>  
 <span data-ttu-id="de4ea-122">None</span><span class="sxs-lookup"><span data-stu-id="de4ea-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de4ea-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de4ea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="de4ea-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="de4ea-124">Element</span></span>|<span data-ttu-id="de4ea-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="de4ea-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de4ea-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="de4ea-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="de4ea-127">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="de4ea-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de4ea-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de4ea-128">Remarks</span></span>  
 <span data-ttu-id="de4ea-129">La resolución de tokens de servicio se puede usar para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="de4ea-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="de4ea-130">Se usa para recuperar la clave que se debe usar para descifrar los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="de4ea-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="de4ea-131">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="de4ea-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="de4ea-132">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="de4ea-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="de4ea-133">Algunos controladores de token permiten especificar la configuración de la resolución de tokens de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="de4ea-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="de4ea-134">La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="de4ea-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de4ea-135">Especificar el `<serviceTokenResolver>` elemento como elemento secundario [ \<](identityconfiguration.md) del elemento de > identityConfiguration está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="de4ea-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="de4ea-136">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="de4ea-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de4ea-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de4ea-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 