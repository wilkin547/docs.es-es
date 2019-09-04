---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251886"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="af90b-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="af90b-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="af90b-102">Proporciona la configuración para la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="af90b-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="af90b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af90b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af90b-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="af90b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="af90b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="af90b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="af90b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="af90b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="af90b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> securityTokenHandlerConfiguration**</span><span class="sxs-lookup"><span data-stu-id="af90b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af90b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af90b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af90b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af90b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af90b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af90b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af90b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="af90b-111">Attributes</span></span>  
  
|<span data-ttu-id="af90b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="af90b-112">Attribute</span></span>|<span data-ttu-id="af90b-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="af90b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af90b-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="af90b-114">saveBootstrapContext</span></span>|<span data-ttu-id="af90b-115">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="af90b-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="af90b-116">El valor también se puede establecer en una colección de controladores de tokens `saveBootstrapContext` estableciendo el atributo en el [ \<elemento > de identityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="af90b-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="af90b-117">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="af90b-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="af90b-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="af90b-118">maximumClockSkew</span></span>|<span data-ttu-id="af90b-119"><xref:System.TimeSpan> Que especifica el sesgo de reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="af90b-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="af90b-120">Controla el sesgo de reloj máximo permitido al realizar operaciones dependientes del tiempo, como la validación de la hora de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="af90b-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="af90b-121">El valor predeterminado es 5 minutos, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="af90b-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="af90b-122">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="af90b-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="af90b-123">El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo `maximumClockSkew` el atributo en el [ \<elemento > de identityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="af90b-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="af90b-124">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="af90b-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af90b-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af90b-125">Child Elements</span></span>  
  
|<span data-ttu-id="af90b-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="af90b-126">Element</span></span>|<span data-ttu-id="af90b-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="af90b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af90b-128">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="af90b-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="af90b-129">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="af90b-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="af90b-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-130">Optional.</span></span>|  
|[<span data-ttu-id="af90b-131">\<caches></span><span class="sxs-lookup"><span data-stu-id="af90b-131">\<caches></span></span>](caches.md)|<span data-ttu-id="af90b-132">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="af90b-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="af90b-133">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af90b-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="af90b-134">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-134">Optional.</span></span>|  
|[<span data-ttu-id="af90b-135">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="af90b-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="af90b-136">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="af90b-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="af90b-137">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af90b-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="af90b-138">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="af90b-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="af90b-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-139">Optional.</span></span>|  
|[<span data-ttu-id="af90b-140">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="af90b-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="af90b-141">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="af90b-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="af90b-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-142">Optional.</span></span>|  
|[<span data-ttu-id="af90b-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="af90b-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="af90b-144">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="af90b-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="af90b-145">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="af90b-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="af90b-146">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-146">Optional.</span></span>|  
|[<span data-ttu-id="af90b-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="af90b-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="af90b-148">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="af90b-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="af90b-149">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="af90b-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="af90b-150">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-150">Optional.</span></span>|  
|[<span data-ttu-id="af90b-151">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="af90b-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="af90b-152">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="af90b-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="af90b-153">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af90b-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="af90b-154">Opcional.</span><span class="sxs-lookup"><span data-stu-id="af90b-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af90b-155">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af90b-155">Parent Elements</span></span>  
  
|<span data-ttu-id="af90b-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="af90b-156">Element</span></span>|<span data-ttu-id="af90b-157">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="af90b-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af90b-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="af90b-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="af90b-159">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="af90b-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af90b-160">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af90b-160">Remarks</span></span>  
 <span data-ttu-id="af90b-161">En esta sección se proporcionan los valores <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> de propiedad de un objeto.</span><span class="sxs-lookup"><span data-stu-id="af90b-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="af90b-162">Los valores configurados en esta sección reemplazan a los configurados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="af90b-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="af90b-163">Algunos de estos valores se pueden reemplazar a su vez por los valores que se especifican cuando se agrega un controlador a la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af90b-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af90b-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af90b-164">Example</span></span>  
  
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
