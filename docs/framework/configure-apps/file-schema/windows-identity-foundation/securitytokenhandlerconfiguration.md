---
description: 'Más información acerca de: <securityTokenHandlerConfiguration>'
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 8c014d971d3e8cc640a3b7042e3a0266d902de7d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698315"
---
# \<securityTokenHandlerConfiguration>

<span data-ttu-id="5b702-102">Proporciona la configuración para la colección de controladores de token.</span><span class="sxs-lookup"><span data-stu-id="5b702-102">Provides configuration for the collection of token handlers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
## <a name="syntax"></a><span data-ttu-id="5b702-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b702-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b702-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b702-104">Attributes and Elements</span></span>  

 <span data-ttu-id="5b702-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b702-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b702-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b702-106">Attributes</span></span>  
  
|<span data-ttu-id="5b702-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b702-107">Attribute</span></span>|<span data-ttu-id="5b702-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b702-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b702-109">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="5b702-109">saveBootstrapContext</span></span>|<span data-ttu-id="5b702-110">Especifica si los tokens de arranque deben incluirse en el token de sesión.</span><span class="sxs-lookup"><span data-stu-id="5b702-110">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="5b702-111">El valor también se puede establecer en una colección de controladores de tokens estableciendo el `saveBootstrapContext` atributo en el [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5b702-111">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="5b702-112">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b702-112">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="5b702-113">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="5b702-113">maximumClockSkew</span></span>|<span data-ttu-id="5b702-114"><xref:System.TimeSpan>Que especifica el sesgo de reloj máximo permitido.</span><span class="sxs-lookup"><span data-stu-id="5b702-114">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="5b702-115">Controla el sesgo de reloj máximo permitido al realizar operaciones dependientes del tiempo, como la validación de la hora de expiración de una sesión de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5b702-115">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="5b702-116">El valor predeterminado es 5 minutos, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="5b702-116">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="5b702-117">Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="5b702-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="5b702-118">El sesgo de reloj máximo también se puede establecer en el nivel de servicio estableciendo el `maximumClockSkew` atributo en el [\<identityConfiguration>](identityconfiguration.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5b702-118">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="5b702-119">Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b702-119">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b702-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b702-120">Child Elements</span></span>  
  
|<span data-ttu-id="5b702-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b702-121">Element</span></span>|<span data-ttu-id="5b702-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b702-122">Description</span></span>|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|<span data-ttu-id="5b702-123">Especifica el conjunto de URI que son identificadores aceptables de este usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="5b702-123">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="5b702-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-124">Optional.</span></span>|  
|[\<caches>](caches.md)|<span data-ttu-id="5b702-125">Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.</span><span class="sxs-lookup"><span data-stu-id="5b702-125">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="5b702-126">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b702-126">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5b702-127">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-127">Optional.</span></span>|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="5b702-128">Controla la configuración que usan los controladores de token para validar certificados.</span><span class="sxs-lookup"><span data-stu-id="5b702-128">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="5b702-129">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b702-129">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5b702-130">Esta configuración se invalida si un controlador concreto se configura con su propio validador.</span><span class="sxs-lookup"><span data-stu-id="5b702-130">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="5b702-131">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-131">Optional.</span></span>|  
|[\<issuerNameRegistry>](issuernameregistry.md)|<span data-ttu-id="5b702-132">Configura el registro de nombres de emisores que usan los controladores de la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5b702-132">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5b702-133">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-133">Optional.</span></span>|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|<span data-ttu-id="5b702-134">Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5b702-134">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5b702-135">La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="5b702-135">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="5b702-136">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-136">Optional.</span></span>|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|<span data-ttu-id="5b702-137">Registra la resolución del token de servicio que usan los controladores en la colección de controladores de tokens.</span><span class="sxs-lookup"><span data-stu-id="5b702-137">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5b702-138">La resolución de tokens de servicio se usa para resolver el token de cifrado en mensajes y tokens entrantes.</span><span class="sxs-lookup"><span data-stu-id="5b702-138">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="5b702-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-139">Optional.</span></span>|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|<span data-ttu-id="5b702-140">Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.</span><span class="sxs-lookup"><span data-stu-id="5b702-140">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="5b702-141">Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b702-141">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="5b702-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="5b702-142">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5b702-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b702-143">Parent Elements</span></span>  
  
|<span data-ttu-id="5b702-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b702-144">Element</span></span>|<span data-ttu-id="5b702-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b702-145">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|<span data-ttu-id="5b702-146">Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5b702-146">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b702-147">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b702-147">Remarks</span></span>  

 <span data-ttu-id="5b702-148">En esta sección se proporcionan los valores de propiedad de un <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> objeto.</span><span class="sxs-lookup"><span data-stu-id="5b702-148">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="5b702-149">Los valores configurados en esta sección reemplazan a los configurados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="5b702-149">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="5b702-150">Algunos de estos valores se pueden reemplazar a su vez por los valores que se especifican cuando se agrega un controlador a la colección de controladores de tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b702-150">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b702-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b702-151">Example</span></span>  
  
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
