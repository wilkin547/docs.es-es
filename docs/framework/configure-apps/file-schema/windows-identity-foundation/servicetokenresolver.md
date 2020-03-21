---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152585"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="cc86e-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="cc86e-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="cc86e-102">Registra el solucionador de tokens de servicio que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="cc86e-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="cc86e-103">El solucionador de tokens de servicio se usa para resolver el token de cifrado en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="cc86e-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="cc86e-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cc86e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cc86e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cc86e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cc86e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cc86e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cc86e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="cc86e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="cc86e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cc86e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="cc86e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="cc86e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc86e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc86e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc86e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cc86e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cc86e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cc86e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc86e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc86e-113">Attributes</span></span>  
  
|<span data-ttu-id="cc86e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="cc86e-114">Attribute</span></span>|<span data-ttu-id="cc86e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc86e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc86e-116">type</span><span class="sxs-lookup"><span data-stu-id="cc86e-116">type</span></span>|<span data-ttu-id="cc86e-117">Especifica el tipo del solucionador de tokens de servicio.</span><span class="sxs-lookup"><span data-stu-id="cc86e-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="cc86e-118">El <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que <xref:System.IdentityModel.Selectors.SecurityTokenResolver> deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="cc86e-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="cc86e-119">Para obtener más información `type` acerca de cómo especificar el atributo, vea [Referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="cc86e-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="cc86e-120">Necesario.</span><span class="sxs-lookup"><span data-stu-id="cc86e-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc86e-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc86e-121">Child Elements</span></span>  
 <span data-ttu-id="cc86e-122">None</span><span class="sxs-lookup"><span data-stu-id="cc86e-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc86e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cc86e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cc86e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc86e-124">Element</span></span>|<span data-ttu-id="cc86e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc86e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc86e-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cc86e-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="cc86e-127">Proporciona configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cc86e-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc86e-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cc86e-128">Remarks</span></span>  
 <span data-ttu-id="cc86e-129">El solucionador de tokens de servicio se puede usar para resolver el token de cifrado en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="cc86e-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="cc86e-130">Se utiliza para recuperar la clave que se debe usar para descifrar los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="cc86e-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="cc86e-131">Debe especificar `type` el atributo.</span><span class="sxs-lookup"><span data-stu-id="cc86e-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="cc86e-132">El tipo especificado puede <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ser un tipo personalizado <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o uno que deriva de la clase.</span><span class="sxs-lookup"><span data-stu-id="cc86e-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="cc86e-133">Algunos controladores de tokens le permiten especificar la configuración del solucionador de tokens de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="cc86e-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="cc86e-134">La configuración de los controladores de tokens individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cc86e-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc86e-135">Especificar el `<serviceTokenResolver>` elemento como un elemento secundario del elemento [ \<de>identityConfiguration](identityconfiguration.md) ha quedado en desuso, pero sigue siendo compatible con la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cc86e-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="cc86e-136">La configuración `<securityTokenHandlerConfiguration>` del elemento `<identityConfiguration>` los reemplaza en el elemento.</span><span class="sxs-lookup"><span data-stu-id="cc86e-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc86e-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc86e-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
