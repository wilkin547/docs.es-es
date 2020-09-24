---
title: <transport> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: b9efc732832a8862373b14f657796a59fb52c1a1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162119"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="01316-102">\<transport> de \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="01316-102">\<transport> of \<webHttpBinding></span></span>

<span data-ttu-id="01316-103">Define los valores de seguridad a nivel de transporte para un punto de conexión de servicio configurado para recibir solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="01316-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="01316-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01316-104">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="01316-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="01316-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01316-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="01316-106">Attributes and Elements</span></span>  

 <span data-ttu-id="01316-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="01316-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01316-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="01316-108">Attributes</span></span>  
  
|<span data-ttu-id="01316-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="01316-109">Attribute</span></span>|<span data-ttu-id="01316-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="01316-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="01316-111">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="01316-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="01316-112">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="01316-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="01316-113">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="01316-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="01316-114">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="01316-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="01316-115">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="01316-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="01316-116">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="01316-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="01316-117">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="01316-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="01316-118">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="01316-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="01316-119">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="01316-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="01316-120">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="01316-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="01316-121">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="01316-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="01316-122">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="01316-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="01316-123">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="01316-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="01316-124">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="01316-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="01316-125">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="01316-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="01316-126">Value</span><span class="sxs-lookup"><span data-stu-id="01316-126">Value</span></span>|<span data-ttu-id="01316-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="01316-127">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="01316-128">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="01316-128">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="01316-129">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="01316-129">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="01316-130">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="01316-130">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="01316-131">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="01316-131">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="01316-132">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="01316-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="01316-133">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="01316-133">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="01316-134">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="01316-134">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="01316-135">Value</span><span class="sxs-lookup"><span data-stu-id="01316-135">Value</span></span>|<span data-ttu-id="01316-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="01316-136">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="01316-137">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="01316-137">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="01316-138">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="01316-138">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="01316-139">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="01316-139">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="01316-140">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="01316-140">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="01316-141">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="01316-141">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01316-142">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="01316-142">Child Elements</span></span>  

 <span data-ttu-id="01316-143">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="01316-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01316-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="01316-144">Parent Elements</span></span>  
  
|<span data-ttu-id="01316-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="01316-145">Element</span></span>|<span data-ttu-id="01316-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="01316-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="01316-147">Representa las funciones de seguridad del [\<wsHttpBinding>](wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="01316-147">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01316-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01316-148">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="01316-149">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="01316-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="01316-150">Enlaces</span><span class="sxs-lookup"><span data-stu-id="01316-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="01316-151">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="01316-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="01316-152">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="01316-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="01316-153">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="01316-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
