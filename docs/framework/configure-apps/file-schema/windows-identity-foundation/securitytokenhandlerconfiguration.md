---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262892"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="6b517-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b517-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="6b517-102">Proporciona la configuración de la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="6b517-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="6b517-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6b517-103">\<system.identityModel></span></span>  
<span data-ttu-id="6b517-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b517-104">\<identityConfiguration></span></span>  
<span data-ttu-id="6b517-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6b517-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6b517-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b517-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b517-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b517-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b517-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b517-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b517-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b517-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b517-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b517-110">Attributes</span></span>  
  
|<span data-ttu-id="6b517-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6b517-111">Attribute</span></span>|<span data-ttu-id="6b517-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b517-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b517-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="6b517-113">saveBootstrapContext</span></span>|<span data-ttu-id="6b517-114">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="6b517-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="6b517-115">El valor también se puede establecer en una colección de controladores de token estableciendo el `saveBootstrapContext` atributo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6b517-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6b517-116">Un valor establecido en la colección de controladores de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6b517-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="6b517-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="6b517-117">maximumClockSkew</span></span>|<span data-ttu-id="6b517-118">Un <xref:System.TimeSpan> que especifica el sesgo del reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="6b517-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="6b517-119">Controla el sesgo de reloj permitido máximo al realizar operaciones sensibles a la hora, como la validación de la hora de expiración de una inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="6b517-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="6b517-120">El valor predeterminado es 5 minutos, "00: 05:00".</span><span class="sxs-lookup"><span data-stu-id="6b517-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="6b517-121">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6b517-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="6b517-122">El sesgo de reloj máximo también se puede establecer el nivel de servicio estableciendo el `maximumClockSkew` atributo el [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="6b517-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6b517-123">Un valor establecido en la colección de controladores de token reemplaza al valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6b517-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b517-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b517-124">Child Elements</span></span>  
  
|<span data-ttu-id="6b517-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b517-125">Element</span></span>|<span data-ttu-id="6b517-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b517-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b517-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="6b517-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="6b517-128">Especifica el conjunto de URI que son identificadores aceptables de este usuario autenticado.</span><span class="sxs-lookup"><span data-stu-id="6b517-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="6b517-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-129">Optional.</span></span>|  
|[<span data-ttu-id="6b517-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="6b517-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="6b517-131">Registra las memorias caché utilizadas para la detección de reproducción de tokens y los tokens de sesión.</span><span class="sxs-lookup"><span data-stu-id="6b517-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="6b517-132">Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b517-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6b517-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-133">Optional.</span></span>|  
|[<span data-ttu-id="6b517-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="6b517-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="6b517-135">Controla la configuración que los controladores de token que se usan para validar los certificados.</span><span class="sxs-lookup"><span data-stu-id="6b517-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6b517-136">Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b517-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6b517-137">Esta configuración se invalida si un controlador específico se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="6b517-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="6b517-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-138">Optional.</span></span>|  
|[<span data-ttu-id="6b517-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="6b517-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="6b517-140">Configura el registro de nombre del emisor que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="6b517-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6b517-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-141">Optional.</span></span>|  
|[<span data-ttu-id="6b517-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6b517-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="6b517-143">Registra a la resolución del token del emisor que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="6b517-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6b517-144">La resolución del emisor del token se utiliza para resolver el token de firma en mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="6b517-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="6b517-145">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-145">Optional.</span></span>|  
|[<span data-ttu-id="6b517-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6b517-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="6b517-147">Registra a la resolución de tokens de servicio que se usa los controladores en la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="6b517-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6b517-148">La resolución del servicio de token se usa para resolver el token cifrado en los mensajes y los tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="6b517-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="6b517-149">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-149">Optional.</span></span>|  
|[<span data-ttu-id="6b517-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="6b517-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="6b517-151">Habilita la detección de reproducción de tokens y especifica la hora de expiración de tokens.</span><span class="sxs-lookup"><span data-stu-id="6b517-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="6b517-152">Puede especificarse en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b517-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6b517-153">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6b517-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b517-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b517-154">Parent Elements</span></span>  
  
|<span data-ttu-id="6b517-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b517-155">Element</span></span>|<span data-ttu-id="6b517-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b517-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b517-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6b517-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="6b517-158">Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6b517-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b517-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b517-159">Remarks</span></span>  
 <span data-ttu-id="6b517-160">Esta sección proporcionan valores de propiedad para un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.</span><span class="sxs-lookup"><span data-stu-id="6b517-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="6b517-161">Configurada en esta sección invalidará los configurados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="6b517-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="6b517-162">Algunos de estos valores pueden invalidarse a su vez, los valores que se especifican cuando se agrega un controlador a la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6b517-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b517-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b517-163">Example</span></span>  
  
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
