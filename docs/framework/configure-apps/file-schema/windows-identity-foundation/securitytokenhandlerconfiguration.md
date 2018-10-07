---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838486"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="937b6-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="937b6-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="937b6-103">Proporciona la configuración de la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="937b6-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="937b6-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="937b6-104">\<system.identityModel></span></span>  
<span data-ttu-id="937b6-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="937b6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="937b6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="937b6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="937b6-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="937b6-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="937b6-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="937b6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="937b6-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="937b6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="937b6-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="937b6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="937b6-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="937b6-111">Attributes</span></span>  
  
|<span data-ttu-id="937b6-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="937b6-112">Attribute</span></span>|<span data-ttu-id="937b6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="937b6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="937b6-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="937b6-114">saveBootstrapContext</span></span>|<span data-ttu-id="937b6-115">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="937b6-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="937b6-116">El valor también se puede establecer en una colección de controladores de token estableciendo el `saveBootstrapContext` atributo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="937b6-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="937b6-117">Un valor establecido en la colección de controladores de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="937b6-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="937b6-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="937b6-118">maximumClockSkew</span></span>|<span data-ttu-id="937b6-119">Un <xref:System.TimeSpan> que especifica el sesgo del reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="937b6-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="937b6-120">Controla el sesgo de reloj permitido máximo al realizar operaciones sensibles a la hora, como la validación de la hora de expiración de una inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="937b6-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="937b6-121">El valor predeterminado es 5 minutos, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="937b6-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="937b6-122">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="937b6-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="937b6-123">El sesgo de reloj máximo también se puede establecer el nivel de servicio estableciendo el `maximumClockSkew` atributo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="937b6-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="937b6-124">Un valor establecido en la colección de controladores de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="937b6-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="937b6-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="937b6-125">Child Elements</span></span>  
  
|<span data-ttu-id="937b6-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="937b6-126">Element</span></span>|<span data-ttu-id="937b6-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="937b6-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="937b6-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="937b6-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="937b6-129">Especifica el conjunto de URI que son identificadores aceptables de este usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="937b6-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="937b6-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-130">Optional.</span></span>|  
|[<span data-ttu-id="937b6-131">\<las memorias caché ></span><span class="sxs-lookup"><span data-stu-id="937b6-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="937b6-132">Registra las memorias caché utilizadas para la detección de reproducción de tokens y los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="937b6-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="937b6-133">Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="937b6-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="937b6-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-134">Optional.</span></span>|  
|[<span data-ttu-id="937b6-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="937b6-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="937b6-136">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="937b6-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="937b6-137">Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="937b6-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="937b6-138">Esta configuración se invalida si un controlador específico se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="937b6-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="937b6-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-139">Optional.</span></span>|  
|[<span data-ttu-id="937b6-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="937b6-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="937b6-141">Configura el registro de nombre del emisor que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="937b6-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="937b6-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-142">Optional.</span></span>|  
|[<span data-ttu-id="937b6-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="937b6-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="937b6-144">Registra a la resolución del token del emisor que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="937b6-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="937b6-145">La resolución del emisor del token se utiliza para resolver el token de firma en mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="937b6-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="937b6-146">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-146">Optional.</span></span>|  
|[<span data-ttu-id="937b6-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="937b6-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="937b6-148">Registra a la resolución de tokens de servicio que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="937b6-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="937b6-149">La resolución del servicio de token se usa para resolver el token cifrado en los mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="937b6-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="937b6-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-150">Optional.</span></span>|  
|[<span data-ttu-id="937b6-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="937b6-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="937b6-152">Habilita la detección de reproducción de tokens y especifica la hora de expiración de tokens.</span><span class="sxs-lookup"><span data-stu-id="937b6-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="937b6-153">Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="937b6-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="937b6-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="937b6-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="937b6-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="937b6-155">Parent Elements</span></span>  
  
|<span data-ttu-id="937b6-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="937b6-156">Element</span></span>|<span data-ttu-id="937b6-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="937b6-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="937b6-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="937b6-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="937b6-159">Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="937b6-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="937b6-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="937b6-160">Remarks</span></span>  
 <span data-ttu-id="937b6-161">Esta sección proporcionan valores de propiedad para un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.</span><span class="sxs-lookup"><span data-stu-id="937b6-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="937b6-162">Configurada en esta sección invalidará los configurados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="937b6-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="937b6-163">Algunos de estos valores pueden invalidarse a su vez, los valores que se especifican cuando se agrega un controlador a la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="937b6-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="937b6-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="937b6-164">Example</span></span>  
  
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
