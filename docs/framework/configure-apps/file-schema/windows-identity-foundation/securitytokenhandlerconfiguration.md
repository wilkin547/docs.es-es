---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ac7284fa418c1540582c40bd744e913ba31aa881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="93db7-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="93db7-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="93db7-103">Proporciona la configuración de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="93db7-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="93db7-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="93db7-104">\<system.identityModel></span></span>  
<span data-ttu-id="93db7-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="93db7-105">\<identityConfiguration></span></span>  
<span data-ttu-id="93db7-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="93db7-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="93db7-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="93db7-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93db7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93db7-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93db7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="93db7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="93db7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="93db7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93db7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="93db7-111">Attributes</span></span>  
  
|<span data-ttu-id="93db7-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="93db7-112">Attribute</span></span>|<span data-ttu-id="93db7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="93db7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93db7-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="93db7-114">saveBootstrapContext</span></span>|<span data-ttu-id="93db7-115">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="93db7-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="93db7-116">El valor también puede establecerse en una colección de controlador de token estableciendo la `saveBootstrapContext` del atributo en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="93db7-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="93db7-117">Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="93db7-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="93db7-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="93db7-118">maximumClockSkew</span></span>|<span data-ttu-id="93db7-119">Un <xref:System.TimeSpan> que define el sesgo de reloj permitido máximo.</span><span class="sxs-lookup"><span data-stu-id="93db7-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="93db7-120">Controla el sesgo de reloj permitido máximo al realizar operaciones de sujetos a limitación temporal, como la validación de la fecha de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="93db7-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="93db7-121">El valor predeterminado es 5 minutos, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="93db7-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="93db7-122">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, consulte [valores de intervalo de tiempo](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="93db7-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="93db7-123">El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo el `maximumClockSkew` del atributo en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="93db7-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="93db7-124">Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="93db7-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93db7-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="93db7-125">Child Elements</span></span>  
  
|<span data-ttu-id="93db7-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="93db7-126">Element</span></span>|<span data-ttu-id="93db7-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="93db7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93db7-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="93db7-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="93db7-129">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="93db7-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="93db7-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-130">Optional.</span></span>|  
|[<span data-ttu-id="93db7-131">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="93db7-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="93db7-132">Registra las memorias caché que se utiliza para la detección de reproducción de tokens y símbolos de sesión.</span><span class="sxs-lookup"><span data-stu-id="93db7-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="93db7-133">Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="93db7-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="93db7-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-134">Optional.</span></span>|  
|[<span data-ttu-id="93db7-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="93db7-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="93db7-136">Controla la configuración que usan los controladores de tokens para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="93db7-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="93db7-137">Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="93db7-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="93db7-138">Estos valores se sustituyen si se configura un controlador específico con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="93db7-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="93db7-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-139">Optional.</span></span>|  
|[<span data-ttu-id="93db7-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="93db7-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="93db7-141">Configura el registro de nombre de emisor que se usa por los controladores de la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="93db7-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="93db7-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-142">Optional.</span></span>|  
|[<span data-ttu-id="93db7-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="93db7-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="93db7-144">Registra a la resolución del token de emisor que se usa por los controladores de la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="93db7-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="93db7-145">La resolución del token de emisor se utiliza para resolver el token de firma en mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="93db7-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="93db7-146">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-146">Optional.</span></span>|  
|[<span data-ttu-id="93db7-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="93db7-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="93db7-148">Registra a la resolución del token de servicio que usa controladores en la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="93db7-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="93db7-149">La resolución del token de servicio se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="93db7-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="93db7-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-150">Optional.</span></span>|  
|[<span data-ttu-id="93db7-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="93db7-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="93db7-152">Habilita la detección de reproducción de tokens y especifica la hora de expiración de símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="93db7-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="93db7-153">Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="93db7-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="93db7-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="93db7-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="93db7-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="93db7-155">Parent Elements</span></span>  
  
|<span data-ttu-id="93db7-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="93db7-156">Element</span></span>|<span data-ttu-id="93db7-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="93db7-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93db7-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="93db7-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="93db7-159">Especifica una colección de controladores de tokens de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="93db7-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93db7-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93db7-160">Remarks</span></span>  
 <span data-ttu-id="93db7-161">Esta sección proporcionan valores de propiedad para un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.</span><span class="sxs-lookup"><span data-stu-id="93db7-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="93db7-162">Configuración realizada en esta sección reemplaza a las que configura en el servicio.</span><span class="sxs-lookup"><span data-stu-id="93db7-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="93db7-163">Algunas de estas opciones a su vez, pueden reemplazarse por los valores que se especifican cuando se agrega un controlador a la colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="93db7-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93db7-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93db7-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
