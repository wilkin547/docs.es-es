---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 0aefaa808dfc32085a208420fcd582b1671acc64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942455"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="3841c-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3841c-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="3841c-102">Proporciona la configuración para la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="3841c-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="3841c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3841c-103">\<system.identityModel></span></span>  
<span data-ttu-id="3841c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3841c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3841c-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3841c-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3841c-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3841c-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3841c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3841c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3841c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3841c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3841c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3841c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3841c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3841c-110">Attributes</span></span>  
  
|<span data-ttu-id="3841c-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="3841c-111">Attribute</span></span>|<span data-ttu-id="3841c-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3841c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3841c-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="3841c-113">saveBootstrapContext</span></span>|<span data-ttu-id="3841c-114">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="3841c-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="3841c-115">El valor también se puede establecer en una colección de controladores de tokens `saveBootstrapContext` estableciendo el atributo en el [ \<elemento > de identityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="3841c-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="3841c-116">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="3841c-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="3841c-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="3841c-117">maximumClockSkew</span></span>|<span data-ttu-id="3841c-118"><xref:System.TimeSpan> Que especifica el sesgo de reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="3841c-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="3841c-119">Controla el sesgo de reloj máximo permitido al realizar operaciones dependientes del tiempo, como la validación de la hora de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="3841c-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="3841c-120">El valor predeterminado es 5 minutos, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="3841c-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="3841c-121">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="3841c-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="3841c-122">El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo `maximumClockSkew` el atributo en el [ \<elemento > de identityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="3841c-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="3841c-123">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="3841c-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3841c-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3841c-124">Child Elements</span></span>  
  
|<span data-ttu-id="3841c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3841c-125">Element</span></span>|<span data-ttu-id="3841c-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3841c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3841c-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="3841c-127">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="3841c-128">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="3841c-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="3841c-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-129">Optional.</span></span>|  
|[<span data-ttu-id="3841c-130">\<caches></span><span class="sxs-lookup"><span data-stu-id="3841c-130">\<caches></span></span>](caches.md)|<span data-ttu-id="3841c-131">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="3841c-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="3841c-132">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3841c-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="3841c-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-133">Optional.</span></span>|  
|[<span data-ttu-id="3841c-134">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="3841c-134">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="3841c-135">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="3841c-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="3841c-136">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3841c-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="3841c-137">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="3841c-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="3841c-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-138">Optional.</span></span>|  
|[<span data-ttu-id="3841c-139">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="3841c-139">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="3841c-140">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3841c-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="3841c-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-141">Optional.</span></span>|  
|[<span data-ttu-id="3841c-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="3841c-142">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="3841c-143">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3841c-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="3841c-144">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="3841c-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="3841c-145">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-145">Optional.</span></span>|  
|[<span data-ttu-id="3841c-146">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="3841c-146">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="3841c-147">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="3841c-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="3841c-148">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="3841c-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="3841c-149">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-149">Optional.</span></span>|  
|[<span data-ttu-id="3841c-150">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="3841c-150">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="3841c-151">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="3841c-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="3841c-152">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3841c-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="3841c-153">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3841c-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3841c-154">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3841c-154">Parent Elements</span></span>  
  
|<span data-ttu-id="3841c-155">Elemento</span><span class="sxs-lookup"><span data-stu-id="3841c-155">Element</span></span>|<span data-ttu-id="3841c-156">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3841c-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3841c-157">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3841c-157">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="3841c-158">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3841c-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3841c-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3841c-159">Remarks</span></span>  
 <span data-ttu-id="3841c-160">En esta sección se proporcionan los valores <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> de propiedad de un objeto.</span><span class="sxs-lookup"><span data-stu-id="3841c-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="3841c-161">Los valores configurados en esta sección reemplazan a los configurados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="3841c-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="3841c-162">Algunos de estos valores se pueden reemplazar a su vez por los valores que se especifican cuando se agrega un controlador a la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3841c-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3841c-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3841c-163">Example</span></span>  
  
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
