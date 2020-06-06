---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152572"
---
# \<securityTokenHandlerConfiguration>
<span data-ttu-id="fc998-101">Proporciona la configuración para la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="fc998-101">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="fc998-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc998-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc998-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc998-103">Attributes and Elements</span></span>  
 <span data-ttu-id="fc998-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc998-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc998-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc998-105">Attributes</span></span>  
  
|<span data-ttu-id="fc998-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc998-106">Attribute</span></span>|<span data-ttu-id="fc998-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc998-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc998-108">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="fc998-108">saveBootstrapContext</span></span>|<span data-ttu-id="fc998-109">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="fc998-109">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="fc998-110">El valor también se puede establecer en una colección de controladores de tokens estableciendo el `saveBootstrapContext` atributo en el [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="fc998-110">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="fc998-111">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="fc998-111">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="fc998-112">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="fc998-112">maximumClockSkew</span></span>|<span data-ttu-id="fc998-113"><xref:System.TimeSpan>Que especifica el sesgo de reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="fc998-113">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="fc998-114">Controla el sesgo de reloj máximo permitido al realizar operaciones dependientes del tiempo, como la validación de la hora de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="fc998-114">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="fc998-115">El valor predeterminado es 5 minutos, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="fc998-115">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="fc998-116">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="fc998-116">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="fc998-117">El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo el `maximumClockSkew` atributo en el [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="fc998-117">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="fc998-118">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="fc998-118">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc998-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc998-119">Child Elements</span></span>  
  
|<span data-ttu-id="fc998-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc998-120">Element</span></span>|<span data-ttu-id="fc998-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc998-121">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="fc998-122">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="fc998-122">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="fc998-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-123">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="fc998-124">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="fc998-124">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="fc998-125">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc998-125">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="fc998-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-126">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="fc998-127">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="fc998-127">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="fc998-128">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc998-128">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="fc998-129">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="fc998-129">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="fc998-130">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-130">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="fc998-131">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="fc998-131">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="fc998-132">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-132">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="fc998-133">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="fc998-133">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="fc998-134">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="fc998-134">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="fc998-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-135">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="fc998-136">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="fc998-136">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="fc998-137">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="fc998-137">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="fc998-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-138">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="fc998-139">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="fc998-139">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="fc998-140">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc998-140">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="fc998-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fc998-141">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc998-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc998-142">Parent Elements</span></span>  
  
|<span data-ttu-id="fc998-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc998-143">Element</span></span>|<span data-ttu-id="fc998-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc998-144">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="fc998-145">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fc998-145">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc998-146">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc998-146">Remarks</span></span>  
 <span data-ttu-id="fc998-147">En esta sección se proporcionan los valores de propiedad de un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.</span><span class="sxs-lookup"><span data-stu-id="fc998-147">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="fc998-148">Los valores configurados en esta sección reemplazan a los configurados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="fc998-148">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="fc998-149">Algunos de estos valores se pueden reemplazar a su vez por los valores que se especifican cuando se agrega un controlador a la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="fc998-149">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc998-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc998-150">Example</span></span>  
  
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
