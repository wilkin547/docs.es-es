---
title: <transport> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 95cfa076f62f767af431ff5a0bcc2ca31b824e30
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399245"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="fe96f-102">\<> de transporte \<de WSHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fe96f-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="fe96f-103">Define la configuración de autenticación del transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="fe96f-103">Defines authentication settings for the HTTP transport.</span></span>

<span data-ttu-id="fe96f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fe96f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fe96f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fe96f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fe96f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fe96f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fe96f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsHttpBinding >** ](wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fe96f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)</span></span>\
<span data-ttu-id="fe96f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="fe96f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fe96f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fe96f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)</span></span>\
<span data-ttu-id="fe96f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de transporte**</span><span class="sxs-lookup"><span data-stu-id="fe96f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="fe96f-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe96f-111">Syntax</span></span>

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

## <a name="type"></a><span data-ttu-id="fe96f-112">Type</span><span class="sxs-lookup"><span data-stu-id="fe96f-112">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="fe96f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fe96f-113">Attributes and Elements</span></span>

<span data-ttu-id="fe96f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fe96f-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fe96f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="fe96f-115">Attributes</span></span>

|<span data-ttu-id="fe96f-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="fe96f-116">Attribute</span></span>|<span data-ttu-id="fe96f-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fe96f-117">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="fe96f-118">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="fe96f-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="fe96f-119">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fe96f-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="fe96f-120">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="fe96f-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="fe96f-121">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fe96f-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="fe96f-122">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="fe96f-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="fe96f-123">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="fe96f-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="fe96f-124">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="fe96f-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="fe96f-125">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="fe96f-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="fe96f-126">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="fe96f-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="fe96f-127">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="fe96f-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="fe96f-128">1.  Never: la directiva nunca se aplica (la protección extendida está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="fe96f-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="fe96f-129">2.  WhenSupported: la directiva solamente se aplica si el cliente admite la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="fe96f-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="fe96f-130">3.  Always: la directiva siempre se aplica.</span><span class="sxs-lookup"><span data-stu-id="fe96f-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="fe96f-131">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="fe96f-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="fe96f-132">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="fe96f-132">clientCredentialType Attribute</span></span>

|<span data-ttu-id="fe96f-133">Valor</span><span class="sxs-lookup"><span data-stu-id="fe96f-133">Value</span></span>|<span data-ttu-id="fe96f-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fe96f-134">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="fe96f-135">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fe96f-135">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="fe96f-136">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="fe96f-136">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="fe96f-137">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="fe96f-137">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="fe96f-138">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="fe96f-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="fe96f-139">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="fe96f-139">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="fe96f-140">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="fe96f-140">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="fe96f-141">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="fe96f-141">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="fe96f-142">Value</span><span class="sxs-lookup"><span data-stu-id="fe96f-142">Value</span></span>|<span data-ttu-id="fe96f-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fe96f-143">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="fe96f-144">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="fe96f-144">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="fe96f-145">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="fe96f-145">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="fe96f-146">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="fe96f-146">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="fe96f-147">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="fe96f-147">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="fe96f-148">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="fe96f-148">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="fe96f-149">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="fe96f-149">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fe96f-150">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fe96f-150">Child Elements</span></span>

<span data-ttu-id="fe96f-151">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fe96f-151">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fe96f-152">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fe96f-152">Parent Elements</span></span>

|<span data-ttu-id="fe96f-153">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe96f-153">Element</span></span>|<span data-ttu-id="fe96f-154">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fe96f-154">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fe96f-155">\<security></span><span class="sxs-lookup"><span data-stu-id="fe96f-155">\<security></span></span>](security-of-wshttpbinding.md)|<span data-ttu-id="fe96f-156">Representa las funciones de seguridad del [ \<> wsHttpBinding](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="fe96f-156">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="fe96f-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe96f-157">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="fe96f-158">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fe96f-158">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fe96f-159">Enlaces</span><span class="sxs-lookup"><span data-stu-id="fe96f-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fe96f-160">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="fe96f-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fe96f-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="fe96f-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fe96f-162">\<binding></span><span class="sxs-lookup"><span data-stu-id="fe96f-162">\<binding></span></span>](../../../misc/binding.md)
