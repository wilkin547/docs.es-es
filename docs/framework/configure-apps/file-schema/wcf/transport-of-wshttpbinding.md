---
description: 'Más información sobre: <transport> de <wsHttpBinding>'
title: <transport> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 7801148d76aaa9c074eeb7a83c1dd2fa152d871c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749304"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="91cfa-103">\<transport> de \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="91cfa-103">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="91cfa-104">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="91cfa-104">Defines authentication settings for the HTTP transport.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a><span data-ttu-id="91cfa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91cfa-105">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="91cfa-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="91cfa-106">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="91cfa-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="91cfa-107">Attributes and Elements</span></span>

<span data-ttu-id="91cfa-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="91cfa-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="91cfa-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="91cfa-109">Attributes</span></span>

|<span data-ttu-id="91cfa-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="91cfa-110">Attribute</span></span>|<span data-ttu-id="91cfa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="91cfa-111">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="91cfa-112">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="91cfa-112">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="91cfa-113">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="91cfa-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="91cfa-114">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="91cfa-114">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="91cfa-115">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="91cfa-115">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="91cfa-116">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="91cfa-116">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="91cfa-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="91cfa-117">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="91cfa-118">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="91cfa-118">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="91cfa-119">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="91cfa-119">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="91cfa-120">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="91cfa-120">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="91cfa-121">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="91cfa-121">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="91cfa-122">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="91cfa-122">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="91cfa-123">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="91cfa-123">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="91cfa-124">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="91cfa-124">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="91cfa-125">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="91cfa-125">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="91cfa-126">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="91cfa-126">clientCredentialType Attribute</span></span>

|<span data-ttu-id="91cfa-127">Value</span><span class="sxs-lookup"><span data-stu-id="91cfa-127">Value</span></span>|<span data-ttu-id="91cfa-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="91cfa-128">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="91cfa-129">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="91cfa-129">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="91cfa-130">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="91cfa-130">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="91cfa-131">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="91cfa-131">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="91cfa-132">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="91cfa-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="91cfa-133">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="91cfa-133">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="91cfa-134">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="91cfa-134">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="91cfa-135">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="91cfa-135">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="91cfa-136">Value</span><span class="sxs-lookup"><span data-stu-id="91cfa-136">Value</span></span>|<span data-ttu-id="91cfa-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="91cfa-137">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="91cfa-138">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="91cfa-138">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="91cfa-139">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="91cfa-139">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="91cfa-140">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="91cfa-140">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="91cfa-141">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="91cfa-141">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="91cfa-142">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="91cfa-142">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="91cfa-143">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="91cfa-143">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="91cfa-144">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="91cfa-144">Child Elements</span></span>

<span data-ttu-id="91cfa-145">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="91cfa-145">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91cfa-146">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="91cfa-146">Parent Elements</span></span>

|<span data-ttu-id="91cfa-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="91cfa-147">Element</span></span>|<span data-ttu-id="91cfa-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="91cfa-148">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="91cfa-149">Representa las capacidades de seguridad de [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="91cfa-149">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="91cfa-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="91cfa-150">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="91cfa-151">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="91cfa-151">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="91cfa-152">Enlaces</span><span class="sxs-lookup"><span data-stu-id="91cfa-152">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="91cfa-153">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="91cfa-153">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="91cfa-154">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="91cfa-154">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
