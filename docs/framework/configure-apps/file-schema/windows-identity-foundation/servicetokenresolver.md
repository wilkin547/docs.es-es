---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2018
ms.locfileid: "47454294"
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="0817d-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="0817d-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="0817d-103">Registra a la resolución de tokens de servicio que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="0817d-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="0817d-104">La resolución del servicio de token se usa para resolver el token cifrado en los mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="0817d-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="0817d-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="0817d-105">\<system.identityModel></span></span>  
<span data-ttu-id="0817d-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0817d-106">\<identityConfiguration></span></span>  
<span data-ttu-id="0817d-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="0817d-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="0817d-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0817d-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="0817d-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="0817d-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0817d-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0817d-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0817d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0817d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0817d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0817d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0817d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0817d-113">Attributes</span></span>  
  
|<span data-ttu-id="0817d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0817d-114">Attribute</span></span>|<span data-ttu-id="0817d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0817d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0817d-116">type</span><span class="sxs-lookup"><span data-stu-id="0817d-116">type</span></span>|<span data-ttu-id="0817d-117">Especifica el tipo de la resolución de tokens de servicio.</span><span class="sxs-lookup"><span data-stu-id="0817d-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="0817d-118">Ya sea el <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que se deriva el <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="0817d-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="0817d-119">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado].</span><span class="sxs-lookup"><span data-stu-id="0817d-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="0817d-120">Requerido.</span><span class="sxs-lookup"><span data-stu-id="0817d-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0817d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0817d-121">Child Elements</span></span>  
 <span data-ttu-id="0817d-122">Ninguna</span><span class="sxs-lookup"><span data-stu-id="0817d-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0817d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0817d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0817d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0817d-124">Element</span></span>|<span data-ttu-id="0817d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0817d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0817d-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0817d-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="0817d-127">Proporciona la configuración para una colección de seguridad controladores de token.</span><span class="sxs-lookup"><span data-stu-id="0817d-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0817d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0817d-128">Remarks</span></span>  
 <span data-ttu-id="0817d-129">La resolución del servicio de token puede usarse para resolver el token cifrado en los mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="0817d-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="0817d-130">Sirve para recuperar la clave que debe usarse para descifrar tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="0817d-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="0817d-131">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="0817d-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="0817d-132">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="0817d-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="0817d-133">Algunos controladores de tokens permiten especificar la configuración de resolución de tokens del servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="0817d-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="0817d-134">La configuración en los controladores de token individuales invalida los especificados en la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0817d-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0817d-135">Especificar el `<serviceTokenResolver>` como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0817d-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="0817d-136">Configuración de la `<securityTokenHandlerConfiguration>` elemento invalidan aquellas establecidas en el `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="0817d-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0817d-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0817d-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
