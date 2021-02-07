---
description: 'Más información acerca de: <serviceTokenResolver>'
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: ab24c92eee43324365adb3bb3a64c8a765017a53
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698302"
---
# \<serviceTokenResolver>

<span data-ttu-id="75469-102">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="75469-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="75469-103">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="75469-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="75469-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75469-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75469-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75469-105">Attributes and Elements</span></span>  

 <span data-ttu-id="75469-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75469-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75469-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="75469-107">Attributes</span></span>  
  
|<span data-ttu-id="75469-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="75469-108">Attribute</span></span>|<span data-ttu-id="75469-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="75469-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75469-110">type</span><span class="sxs-lookup"><span data-stu-id="75469-110">type</span></span>|<span data-ttu-id="75469-111">Especifica el tipo de la resolución del token de servicio.</span><span class="sxs-lookup"><span data-stu-id="75469-111">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="75469-112"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>Tipo o tipo que se deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="75469-112">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="75469-113">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="75469-113">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="75469-114">Necesario.</span><span class="sxs-lookup"><span data-stu-id="75469-114">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75469-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75469-115">Child Elements</span></span>  

 <span data-ttu-id="75469-116">None</span><span class="sxs-lookup"><span data-stu-id="75469-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75469-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75469-117">Parent Elements</span></span>  
  
|<span data-ttu-id="75469-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="75469-118">Element</span></span>|<span data-ttu-id="75469-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="75469-119">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="75469-120">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75469-120">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75469-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75469-121">Remarks</span></span>  

 <span data-ttu-id="75469-122">La resolución de tokens de servicio se puede usar para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="75469-122">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="75469-123">Se usa para recuperar la clave que se debe usar para descifrar los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="75469-123">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="75469-124">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="75469-124">You must specify the `type` attribute.</span></span> <span data-ttu-id="75469-125">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="75469-125">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="75469-126">Algunos controladores de token permiten especificar la configuración de la resolución de tokens de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="75469-126">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="75469-127">La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="75469-127">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75469-128">Especificar el `<serviceTokenResolver>` elemento como elemento secundario del [\<identityConfiguration>](identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="75469-128">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="75469-129">La configuración del `<securityTokenHandlerConfiguration>` elemento invalida la del `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="75469-129">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75469-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75469-130">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
