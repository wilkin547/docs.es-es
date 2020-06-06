---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152585"
---
# \<serviceTokenResolver>
<span data-ttu-id="c254a-101">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="c254a-101">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c254a-102">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="c254a-102">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="c254a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c254a-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c254a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c254a-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c254a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c254a-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c254a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="c254a-106">Attributes</span></span>  
  
|<span data-ttu-id="c254a-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="c254a-107">Attribute</span></span>|<span data-ttu-id="c254a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c254a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c254a-109">type</span><span class="sxs-lookup"><span data-stu-id="c254a-109">type</span></span>|<span data-ttu-id="c254a-110">Especifica el tipo de la resolución del token de servicio.</span><span class="sxs-lookup"><span data-stu-id="c254a-110">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="c254a-111"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>Tipo o tipo que se deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="c254a-111">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="c254a-112">Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado].</span><span class="sxs-lookup"><span data-stu-id="c254a-112">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="c254a-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="c254a-113">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c254a-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c254a-114">Child Elements</span></span>  
 <span data-ttu-id="c254a-115">None</span><span class="sxs-lookup"><span data-stu-id="c254a-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c254a-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c254a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c254a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c254a-117">Element</span></span>|<span data-ttu-id="c254a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c254a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="c254a-119">Proporciona la configuración para una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c254a-119">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c254a-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c254a-120">Remarks</span></span>  
 <span data-ttu-id="c254a-121">La resolución de tokens de servicio se puede usar para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="c254a-121">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="c254a-122">Se usa para recuperar la clave que se debe usar para descifrar los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="c254a-122">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="c254a-123">Debe especificar el `type` atributo.</span><span class="sxs-lookup"><span data-stu-id="c254a-123">You must specify the `type` attribute.</span></span> <span data-ttu-id="c254a-124">El tipo especificado puede ser <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Selectors.SecurityTokenResolver> clase.</span><span class="sxs-lookup"><span data-stu-id="c254a-124">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="c254a-125">Algunos controladores de token permiten especificar la configuración de la resolución de tokens de servicio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c254a-125">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="c254a-126">La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c254a-126">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c254a-127">Especificar el `<serviceTokenResolver>` elemento como elemento secundario del [\<identityConfiguration>](identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="c254a-127">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="c254a-128">La configuración del `<securityTokenHandlerConfiguration>` elemento invalida la del `<identityConfiguration>` elemento.</span><span class="sxs-lookup"><span data-stu-id="c254a-128">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c254a-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c254a-129">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
