---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 168bdc4fbf640b201ebc61462d04727c23f838f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758430"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="6417e-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="6417e-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="6417e-103">Proporciona la configuración de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="6417e-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="6417e-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="6417e-104">\<system.identityModel></span></span>  
<span data-ttu-id="6417e-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6417e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6417e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6417e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6417e-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6417e-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6417e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6417e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6417e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6417e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6417e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6417e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6417e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="6417e-111">Attributes</span></span>  
  
|<span data-ttu-id="6417e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="6417e-112">Attribute</span></span>|<span data-ttu-id="6417e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6417e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6417e-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="6417e-114">saveBootstrapContext</span></span>|<span data-ttu-id="6417e-115">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="6417e-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="6417e-116">El valor también puede establecerse en una colección de controlador de token estableciendo la `saveBootstrapContext` del atributo en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6417e-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6417e-117">Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6417e-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="6417e-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="6417e-118">maximumClockSkew</span></span>|<span data-ttu-id="6417e-119">Un <xref:System.TimeSpan> que define el sesgo de reloj permitido máximo.</span><span class="sxs-lookup"><span data-stu-id="6417e-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="6417e-120">Controla el sesgo de reloj permitido máximo al realizar operaciones de sujetos a limitación temporal, como la validación de la fecha de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6417e-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="6417e-121">El valor predeterminado es 5 minutos, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="6417e-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="6417e-122">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, consulte [valores de intervalo de tiempo](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6417e-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="6417e-123">El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo el `maximumClockSkew` del atributo en el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6417e-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6417e-124">Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6417e-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6417e-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6417e-125">Child Elements</span></span>  
  
|<span data-ttu-id="6417e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6417e-126">Element</span></span>|<span data-ttu-id="6417e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6417e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6417e-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="6417e-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="6417e-129">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="6417e-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="6417e-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-130">Optional.</span></span>|  
|[<span data-ttu-id="6417e-131">\<almacena en memoria caché ></span><span class="sxs-lookup"><span data-stu-id="6417e-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="6417e-132">Registra las memorias caché que se utiliza para la detección de reproducción de tokens y símbolos de sesión.</span><span class="sxs-lookup"><span data-stu-id="6417e-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="6417e-133">Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6417e-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6417e-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-134">Optional.</span></span>|  
|[<span data-ttu-id="6417e-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="6417e-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="6417e-136">Controla la configuración que usan los controladores de tokens para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="6417e-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6417e-137">Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6417e-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6417e-138">Estos valores se sustituyen si se configura un controlador específico con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="6417e-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="6417e-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-139">Optional.</span></span>|  
|[<span data-ttu-id="6417e-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="6417e-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="6417e-141">Configura el registro de nombre de emisor que se usa por los controladores de la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="6417e-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6417e-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-142">Optional.</span></span>|  
|[<span data-ttu-id="6417e-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="6417e-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="6417e-144">Registra a la resolución del token de emisor que se usa por los controladores de la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="6417e-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6417e-145">La resolución del token de emisor se utiliza para resolver el token de firma en mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="6417e-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="6417e-146">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-146">Optional.</span></span>|  
|[<span data-ttu-id="6417e-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="6417e-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="6417e-148">Registra a la resolución del token de servicio que usa controladores en la colección de controlador de token.</span><span class="sxs-lookup"><span data-stu-id="6417e-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6417e-149">La resolución del token de servicio se utiliza para resolver el token de cifrado de mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="6417e-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="6417e-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-150">Optional.</span></span>|  
|[<span data-ttu-id="6417e-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="6417e-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="6417e-152">Habilita la detección de reproducción de tokens y especifica la hora de expiración de símbolos (tokens).</span><span class="sxs-lookup"><span data-stu-id="6417e-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="6417e-153">Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6417e-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6417e-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6417e-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6417e-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6417e-155">Parent Elements</span></span>  
  
|<span data-ttu-id="6417e-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="6417e-156">Element</span></span>|<span data-ttu-id="6417e-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="6417e-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6417e-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6417e-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="6417e-159">Especifica una colección de controladores de tokens de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6417e-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6417e-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6417e-160">Remarks</span></span>  
 <span data-ttu-id="6417e-161">Esta sección proporcionan valores de propiedad para un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.</span><span class="sxs-lookup"><span data-stu-id="6417e-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="6417e-162">Configuración realizada en esta sección reemplaza a las que configura en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6417e-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="6417e-163">Algunas de estas opciones a su vez, pueden reemplazarse por los valores que se especifican cuando se agrega un controlador a la colección de controlador de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6417e-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6417e-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6417e-164">Example</span></span>  
  
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
