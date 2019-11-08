---
title: <transport> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732740"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="dfb7b-102">\<> de transporte de \<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="dfb7b-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="dfb7b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dfb7b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dfb7b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dfb7b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dfb7b-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="dfb7b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding**](wshttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="dfb7b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="dfb7b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-wshttpbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="dfb7b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**transporte** ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="dfb7b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfb7b-111">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="dfb7b-112">Type</span><span class="sxs-lookup"><span data-stu-id="dfb7b-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="dfb7b-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dfb7b-113">Attributes and Elements</span></span>

<span data-ttu-id="dfb7b-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="dfb7b-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="dfb7b-115">Attributes</span></span>

|<span data-ttu-id="dfb7b-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="dfb7b-116">Attribute</span></span>|<span data-ttu-id="dfb7b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfb7b-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="dfb7b-118">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="dfb7b-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="dfb7b-120">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="dfb7b-121">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="dfb7b-122">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="dfb7b-123">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="dfb7b-124">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="dfb7b-125">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="dfb7b-126">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="dfb7b-127">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="dfb7b-128">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="dfb7b-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="dfb7b-129">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="dfb7b-130">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="dfb7b-131">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="dfb7b-132">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="dfb7b-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="dfb7b-133">Valor</span><span class="sxs-lookup"><span data-stu-id="dfb7b-133">Value</span></span>|<span data-ttu-id="dfb7b-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfb7b-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="dfb7b-135">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="dfb7b-136">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="dfb7b-137">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="dfb7b-138">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="dfb7b-139">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="dfb7b-140">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="dfb7b-141">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="dfb7b-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="dfb7b-142">Valor</span><span class="sxs-lookup"><span data-stu-id="dfb7b-142">Value</span></span>|<span data-ttu-id="dfb7b-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfb7b-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="dfb7b-144">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="dfb7b-145">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="dfb7b-146">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="dfb7b-147">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="dfb7b-148">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="dfb7b-149">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="dfb7b-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dfb7b-150">Child Elements</span></span>

<span data-ttu-id="dfb7b-151">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dfb7b-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dfb7b-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dfb7b-152">Parent Elements</span></span>

|<span data-ttu-id="dfb7b-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="dfb7b-153">Element</span></span>|<span data-ttu-id="dfb7b-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="dfb7b-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dfb7b-155">\<La ></span><span class="sxs-lookup"><span data-stu-id="dfb7b-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="dfb7b-156">Representa las capacidades de seguridad de la [\<wsHttpBinding >](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dfb7b-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="dfb7b-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfb7b-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="dfb7b-158">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="dfb7b-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dfb7b-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="dfb7b-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dfb7b-160">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="dfb7b-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dfb7b-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="dfb7b-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dfb7b-162">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="dfb7b-162">\<binding></span></span>](bindings.md)
