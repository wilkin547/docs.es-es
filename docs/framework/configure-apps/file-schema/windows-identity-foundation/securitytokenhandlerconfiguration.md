---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152572"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="c69d0-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c69d0-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="c69d0-102">Proporciona configuración para la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="c69d0-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="c69d0-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c69d0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c69d0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c69d0-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c69d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c69d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c69d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="c69d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="c69d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="c69d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c69d0-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c69d0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c69d0-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c69d0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c69d0-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c69d0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c69d0-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c69d0-111">Attributes</span></span>  
  
|<span data-ttu-id="c69d0-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="c69d0-112">Attribute</span></span>|<span data-ttu-id="c69d0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c69d0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c69d0-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="c69d0-114">saveBootstrapContext</span></span>|<span data-ttu-id="c69d0-115">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="c69d0-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="c69d0-116">El valor también se puede establecer en `saveBootstrapContext` una colección de controladores de tokens estableciendo el atributo en el [ \<elemento identityConfiguration>.](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c69d0-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="c69d0-117">Un valor establecido en la colección de controladores de tokens reemplaza el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c69d0-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="c69d0-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="c69d0-118">maximumClockSkew</span></span>|<span data-ttu-id="c69d0-119">A <xref:System.TimeSpan> que especifica el sesgo de reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="c69d0-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="c69d0-120">Controla el sesgo máximo permitido del reloj al realizar operaciones sensibles al tiempo, como validar la hora de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c69d0-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="c69d0-121">El valor predeterminado es 5 minutos, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="c69d0-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="c69d0-122">Para obtener más información <xref:System.TimeSpan> sobre cómo especificar valores, consulte Valores de intervalo de [tiempo](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="c69d0-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="c69d0-123">El sesgo de reloj máximo también se `maximumClockSkew` puede establecer en el nivel de servicio estableciendo el atributo en el [ \<elemento identityConfiguration>.](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c69d0-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="c69d0-124">Un valor establecido en la colección de controladores de tokens reemplaza el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c69d0-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c69d0-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c69d0-125">Child Elements</span></span>  
  
|<span data-ttu-id="c69d0-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="c69d0-126">Element</span></span>|<span data-ttu-id="c69d0-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="c69d0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c69d0-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="c69d0-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="c69d0-129">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="c69d0-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="c69d0-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-130">Optional.</span></span>|  
|[<span data-ttu-id="c69d0-131">\<almacena en caché></span><span class="sxs-lookup"><span data-stu-id="c69d0-131">\<caches></span></span>](caches.md)|<span data-ttu-id="c69d0-132">Registra las memorias caché utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="c69d0-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="c69d0-133">Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c69d0-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c69d0-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-134">Optional.</span></span>|  
|[<span data-ttu-id="c69d0-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="c69d0-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="c69d0-136">Controla la configuración que usan los controladores de tokens para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="c69d0-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="c69d0-137">Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c69d0-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c69d0-138">Esta configuración se invalida si un controlador específico está configurado con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="c69d0-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="c69d0-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-139">Optional.</span></span>|  
|[<span data-ttu-id="c69d0-140">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="c69d0-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="c69d0-141">Configura el registro de nombres de emisor que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="c69d0-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c69d0-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-142">Optional.</span></span>|  
|[<span data-ttu-id="c69d0-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="c69d0-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="c69d0-144">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="c69d0-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c69d0-145">El solucionador de tokens de emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c69d0-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="c69d0-146">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-146">Optional.</span></span>|  
|[<span data-ttu-id="c69d0-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="c69d0-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="c69d0-148">Registra el solucionador de tokens de servicio que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="c69d0-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c69d0-149">El solucionador de tokens de servicio se usa para resolver el token de cifrado en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="c69d0-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="c69d0-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-150">Optional.</span></span>|  
|[<span data-ttu-id="c69d0-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="c69d0-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="c69d0-152">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="c69d0-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="c69d0-153">Se puede especificar en el nivel de servicio o en una colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c69d0-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c69d0-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c69d0-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c69d0-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c69d0-155">Parent Elements</span></span>  
  
|<span data-ttu-id="c69d0-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="c69d0-156">Element</span></span>|<span data-ttu-id="c69d0-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="c69d0-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c69d0-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="c69d0-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="c69d0-159">Especifica una colección de controladores de token de seguridad que están registrados con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c69d0-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c69d0-160">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c69d0-160">Remarks</span></span>  
 <span data-ttu-id="c69d0-161">Esta sección proporciona valores <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> de propiedad para un objeto.</span><span class="sxs-lookup"><span data-stu-id="c69d0-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="c69d0-162">Las configuraciones configuradas en esta sección reemplazan las configuradas en el servicio.</span><span class="sxs-lookup"><span data-stu-id="c69d0-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="c69d0-163">Algunas de estas opciones se pueden invalidar, a su vez, por la configuración que se especifica cuando se agrega un controlador a la colección de controladores de token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c69d0-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c69d0-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c69d0-164">Example</span></span>  
  
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
