---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793814"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="1dd08-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1dd08-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="1dd08-102">Registra a la resolución de tokens de servicio que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="1dd08-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="1dd08-103">La resolución del servicio de token se usa para resolver el token cifrado en los mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="1dd08-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="1dd08-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1dd08-104">\<system.identityModel></span></span>  
<span data-ttu-id="1dd08-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1dd08-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1dd08-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="1dd08-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1dd08-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1dd08-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="1dd08-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1dd08-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dd08-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dd08-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dd08-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1dd08-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1dd08-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1dd08-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dd08-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="1dd08-112">Attributes</span></span>  
  
|<span data-ttu-id="1dd08-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="1dd08-113">Attribute</span></span>|<span data-ttu-id="1dd08-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dd08-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dd08-115">type</span><span class="sxs-lookup"><span data-stu-id="1dd08-115">type</span></span>|<span data-ttu-id="1dd08-116">Especifica el tipo de la resolución de tokens de servicio.</span><span class="sxs-lookup"><span data-stu-id="1dd08-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="1dd08-117">Ya sea el <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que se deriva el <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="1dd08-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="1dd08-118">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado].</span><span class="sxs-lookup"><span data-stu-id="1dd08-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="1dd08-119">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1dd08-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dd08-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1dd08-120">Child Elements</span></span>  
 <span data-ttu-id="1dd08-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="1dd08-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dd08-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1dd08-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1dd08-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dd08-123">Element</span></span>|<span data-ttu-id="1dd08-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dd08-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dd08-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1dd08-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="1dd08-126">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="1dd08-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dd08-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1dd08-127">Remarks</span></span>  
 <span data-ttu-id="1dd08-128">La resolución del servicio de token puede usarse para resolver el token cifrado en los mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="1dd08-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="1dd08-129">Sirve para recuperar la clave que debe usarse para descifrar tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="1dd08-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="1dd08-130">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="1dd08-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="1dd08-131">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="1dd08-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="1dd08-132">Algunos controladores de tokens permiten especificar la configuración de resolución de tokens del servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="1dd08-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="1dd08-133">La configuración en los controladores de token individuales invalida los especificados en la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1dd08-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1dd08-134">Especificar el `<serviceTokenResolver>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="1dd08-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="1dd08-135">Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="1dd08-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dd08-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1dd08-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
