---
title: <transport> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732740"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="25e12-102">\<transport> de \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="25e12-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="25e12-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="25e12-103">Defines authentication settings for the HTTP transport.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a><span data-ttu-id="25e12-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25e12-104">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="25e12-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="25e12-105">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="25e12-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="25e12-106">Attributes and Elements</span></span>

<span data-ttu-id="25e12-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="25e12-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="25e12-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="25e12-108">Attributes</span></span>

|<span data-ttu-id="25e12-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="25e12-109">Attribute</span></span>|<span data-ttu-id="25e12-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="25e12-110">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="25e12-111">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="25e12-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="25e12-112">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="25e12-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="25e12-113">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="25e12-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="25e12-114">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="25e12-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="25e12-115">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="25e12-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="25e12-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="25e12-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="25e12-117">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="25e12-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="25e12-118">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="25e12-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="25e12-119">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="25e12-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="25e12-120">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="25e12-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="25e12-121">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="25e12-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="25e12-122">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="25e12-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="25e12-123">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="25e12-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="25e12-124">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="25e12-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="25e12-125">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="25e12-125">clientCredentialType Attribute</span></span>

|<span data-ttu-id="25e12-126">Value</span><span class="sxs-lookup"><span data-stu-id="25e12-126">Value</span></span>|<span data-ttu-id="25e12-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="25e12-127">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="25e12-128">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="25e12-128">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="25e12-129">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="25e12-129">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="25e12-130">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="25e12-130">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="25e12-131">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="25e12-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="25e12-132">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="25e12-132">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="25e12-133">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="25e12-133">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="25e12-134">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="25e12-134">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="25e12-135">Value</span><span class="sxs-lookup"><span data-stu-id="25e12-135">Value</span></span>|<span data-ttu-id="25e12-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="25e12-136">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="25e12-137">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="25e12-137">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="25e12-138">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="25e12-138">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="25e12-139">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="25e12-139">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="25e12-140">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="25e12-140">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="25e12-141">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="25e12-141">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="25e12-142">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="25e12-142">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="25e12-143">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="25e12-143">Child Elements</span></span>

<span data-ttu-id="25e12-144">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="25e12-144">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="25e12-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="25e12-145">Parent Elements</span></span>

|<span data-ttu-id="25e12-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="25e12-146">Element</span></span>|<span data-ttu-id="25e12-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="25e12-147">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="25e12-148">Representa las capacidades de seguridad de [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="25e12-148">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="25e12-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25e12-149">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="25e12-150">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="25e12-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="25e12-151">Enlaces</span><span class="sxs-lookup"><span data-stu-id="25e12-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="25e12-152">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="25e12-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="25e12-153">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="25e12-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
