---
description: 'Más información acerca de: <securityTokenHandlers>'
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 14937f6763644f9b7f43c0f7be71ea2352b21402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782031"
---
# \<securityTokenHandlers>

<span data-ttu-id="9bf62-102">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9bf62-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a><span data-ttu-id="9bf62-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9bf62-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bf62-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9bf62-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9bf62-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9bf62-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bf62-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="9bf62-106">Attributes</span></span>  
  
|<span data-ttu-id="9bf62-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="9bf62-107">Attribute</span></span>|<span data-ttu-id="9bf62-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bf62-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9bf62-109">name</span><span class="sxs-lookup"><span data-stu-id="9bf62-109">name</span></span>|<span data-ttu-id="9bf62-110">Especifica el nombre de una colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="9bf62-110">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="9bf62-111">Los únicos valores que reconoce el marco son "ActAs" y "Onbehalfof".</span><span class="sxs-lookup"><span data-stu-id="9bf62-111">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="9bf62-112">Si se especifican colecciones de controladores de token con cualquiera de estos nombres, la colección se usará al procesar los tokens ActAs o Onbehalfof, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9bf62-112">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9bf62-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9bf62-113">Child Elements</span></span>  
  
|<span data-ttu-id="9bf62-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bf62-114">Element</span></span>|<span data-ttu-id="9bf62-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bf62-115">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="9bf62-116">Agrega un controlador de tokens de seguridad a la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="9bf62-116">Adds a security token handler to the token handler collection.</span></span>|  
|[\<clear>](clear.md)|<span data-ttu-id="9bf62-117">Borra todos los controladores de token de seguridad de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="9bf62-117">Clears all security token handlers from the token handler collection.</span></span>|  
|[\<remove>](remove.md)|<span data-ttu-id="9bf62-118">Quita un controlador de tokens de seguridad de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="9bf62-118">Removes a security token handler from the token handler collection.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9bf62-119">Proporciona la configuración para la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="9bf62-119">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bf62-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9bf62-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9bf62-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9bf62-121">Element</span></span>|<span data-ttu-id="9bf62-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bf62-122">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="9bf62-123">Especifica la configuración de identidad de nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="9bf62-123">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bf62-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9bf62-124">Remarks</span></span>  

 <span data-ttu-id="9bf62-125">Puede especificar una o varias colecciones con nombre de controladores de token de seguridad en una configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="9bf62-125">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="9bf62-126">Puede especificar un nombre para una colección mediante el `name` atributo.</span><span class="sxs-lookup"><span data-stu-id="9bf62-126">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="9bf62-127">Los únicos nombres que controla el marco de trabajo son "ActAs" y "Onbehalfof".</span><span class="sxs-lookup"><span data-stu-id="9bf62-127">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="9bf62-128">Si existen controladores en estas colecciones, un servicio de token de seguridad (STS) los usa en lugar de los controladores predeterminados al procesar `ActAs` los `OnBehalfOf` tokens y.</span><span class="sxs-lookup"><span data-stu-id="9bf62-128">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="9bf62-129">De forma predeterminada, la colección se rellena con los siguientes tipos de controlador: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> y <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="9bf62-129">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="9bf62-130">Puede modificar la colección mediante los `<add>` `<remove>` elementos, y `<clear>` .</span><span class="sxs-lookup"><span data-stu-id="9bf62-130">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="9bf62-131">Debe asegurarse de que solo existe en la colección un único controlador de un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="9bf62-131">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="9bf62-132">Por ejemplo, si se deriva un controlador de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase, el controlador o <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> se puede configurar en una colección única, pero no en ambos.</span><span class="sxs-lookup"><span data-stu-id="9bf62-132">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="9bf62-133">Use el `<securityTokenHandlerConfiguration>` elemento para especificar los valores de configuración de los controladores de la colección.</span><span class="sxs-lookup"><span data-stu-id="9bf62-133">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="9bf62-134">Los valores especificados a través de este elemento reemplazan a los especificados en el servicio a través del [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="9bf62-134">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="9bf62-135">Algunos controladores (incluidos algunos de los tipos de controlador integrados) pueden admitir la configuración adicional a través de un elemento secundario del `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="9bf62-135">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="9bf62-136">La configuración especificada en un controlador invalida la configuración equivalente especificada en la colección o el servicio.</span><span class="sxs-lookup"><span data-stu-id="9bf62-136">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
