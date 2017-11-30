---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="5c8c0-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="5c8c0-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="5c8c0-103">Registra a la resolución del token de servicio que usa controladores en la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5c8c0-104">La resolución del token de servicio se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="5c8c0-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="5c8c0-105">\<system.identityModel></span></span>  
<span data-ttu-id="5c8c0-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5c8c0-106">\<identityConfiguration></span></span>  
<span data-ttu-id="5c8c0-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="5c8c0-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="5c8c0-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5c8c0-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="5c8c0-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="5c8c0-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c8c0-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c8c0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c8c0-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c8c0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5c8c0-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c8c0-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c8c0-113">Attributes</span></span>  
  
|<span data-ttu-id="5c8c0-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c8c0-114">Attribute</span></span>|<span data-ttu-id="5c8c0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c8c0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c8c0-116">type</span><span class="sxs-lookup"><span data-stu-id="5c8c0-116">type</span></span>|<span data-ttu-id="5c8c0-117">Especifica el tipo de la resolución del token de servicio.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="5c8c0-118">Ya sea la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="5c8c0-119">Para obtener más información sobre cómo especificar el `type` atributo, consulte la sección [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="5c8c0-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="5c8c0-120">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c8c0-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c8c0-121">Child Elements</span></span>  
 <span data-ttu-id="5c8c0-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5c8c0-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c8c0-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c8c0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5c8c0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c8c0-124">Element</span></span>|<span data-ttu-id="5c8c0-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c8c0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c8c0-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5c8c0-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="5c8c0-127">Proporciona la configuración para una colección de seguridad controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c8c0-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c8c0-128">Remarks</span></span>  
 <span data-ttu-id="5c8c0-129">La resolución del token de servicio puede utilizarse para resolver el token de cifrado de mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="5c8c0-130">Se utiliza para recuperar la clave que se debe usar para descifrar tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="5c8c0-131">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="5c8c0-132">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="5c8c0-133">Algunos controladores de tokens permiten especificar la configuración de la resolución del token de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="5c8c0-134">La configuración en los controladores de tokens individuales invalida los especificados en la colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c8c0-135">Especificar el `<serviceTokenResolver>` elemento como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="5c8c0-136">Configuración de la `<securityTokenHandlerConfiguration>` elemento reemplazan a las que en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="5c8c0-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c8c0-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c8c0-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
