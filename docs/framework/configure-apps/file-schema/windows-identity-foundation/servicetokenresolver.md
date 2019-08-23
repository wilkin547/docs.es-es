---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923103"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="b935d-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b935d-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="b935d-102">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="b935d-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b935d-103">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="b935d-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b935d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b935d-104">\<system.identityModel></span></span>  
<span data-ttu-id="b935d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b935d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b935d-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b935d-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b935d-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b935d-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b935d-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b935d-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b935d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b935d-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b935d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b935d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b935d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b935d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b935d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b935d-112">Attributes</span></span>  
  
|<span data-ttu-id="b935d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b935d-113">Attribute</span></span>|<span data-ttu-id="b935d-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b935d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b935d-115">type</span><span class="sxs-lookup"><span data-stu-id="b935d-115">type</span></span>|<span data-ttu-id="b935d-116">Especifica el tipo de la resolución del token de servicio.</span><span class="sxs-lookup"><span data-stu-id="b935d-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="b935d-117">Tipo o tipo que se deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b935d-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="b935d-118">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="b935d-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="b935d-119">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b935d-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b935d-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b935d-120">Child Elements</span></span>  
 <span data-ttu-id="b935d-121">None</span><span class="sxs-lookup"><span data-stu-id="b935d-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b935d-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b935d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b935d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b935d-123">Element</span></span>|<span data-ttu-id="b935d-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b935d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b935d-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b935d-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="b935d-126">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b935d-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b935d-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b935d-127">Remarks</span></span>  
 <span data-ttu-id="b935d-128">La resolución de tokens de servicio se puede usar para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="b935d-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="b935d-129">Se usa para recuperar la clave que se debe usar para descifrar los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="b935d-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="b935d-130">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="b935d-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="b935d-131">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="b935d-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b935d-132">Algunos controladores de token permiten especificar la configuración de la resolución de tokens de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="b935d-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="b935d-133">La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b935d-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b935d-134">Especificar el `<serviceTokenResolver>` elemento como elemento secundario [ \<](identityconfiguration.md) del elemento de > identityConfiguration está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="b935d-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b935d-135">La `<securityTokenHandlerConfiguration>` configuración del elemento invalida la `<identityConfiguration>` del elemento.</span><span class="sxs-lookup"><span data-stu-id="b935d-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b935d-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b935d-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
