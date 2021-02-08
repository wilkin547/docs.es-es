---
description: 'Más información sobre: <transport> de <webHttpBinding>'
title: <transport> de <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: a845786f4e60a44dcb157201235d28d49ab8d40b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773451"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="3d339-103">\<transport> de \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3d339-103">\<transport> of \<webHttpBinding></span></span>

<span data-ttu-id="3d339-104">Define los valores de seguridad a nivel de transporte para un punto de conexión de servicio configurado para recibir solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="3d339-104">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="3d339-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d339-105">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="3d339-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="3d339-106">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d339-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d339-107">Attributes and Elements</span></span>  

 <span data-ttu-id="3d339-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3d339-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d339-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d339-109">Attributes</span></span>  
  
|<span data-ttu-id="3d339-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d339-110">Attribute</span></span>|<span data-ttu-id="3d339-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d339-111">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="3d339-112">Especifica la credencial utilizada para autenticar el cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="3d339-112">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="3d339-113">Este atributo es del tipo <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3d339-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="3d339-114">Especifica la credencial usada para autenticar al cliente en un proxy del dominio.</span><span class="sxs-lookup"><span data-stu-id="3d339-114">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="3d339-115">Este atributo es del tipo <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3d339-115">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="3d339-116">Una cadena que especifica el dominio de autenticación para autenticación implícita o básica.</span><span class="sxs-lookup"><span data-stu-id="3d339-116">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="3d339-117">El valor predeterminado es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="3d339-117">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="3d339-118">Un dominio de autenticación especifica por lo menos el nombre del host que realiza la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3d339-118">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="3d339-119">También puede especificar una colección de usuarios que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="3d339-119">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="3d339-120">Un usuario puede consultar el dominio de autenticación para determinar cuál de los posibles nombres de usuario y contraseñas se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="3d339-120">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="3d339-121">Esta enumeración especifica cuándo se debe aplicar <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="3d339-121">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="3d339-122">1. Never: la Directiva nunca se aplica (la protección ampliada está deshabilitada).</span><span class="sxs-lookup"><span data-stu-id="3d339-122">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="3d339-123">2. WhenSupported: la Directiva solo se aplica si el cliente admite la protección ampliada.</span><span class="sxs-lookup"><span data-stu-id="3d339-123">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="3d339-124">3. Always: siempre se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="3d339-124">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="3d339-125">Los clientes que no admitan la protección extendida no podrán autenticarse.</span><span class="sxs-lookup"><span data-stu-id="3d339-125">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3d339-126">Atributo clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3d339-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3d339-127">Value</span><span class="sxs-lookup"><span data-stu-id="3d339-127">Value</span></span>|<span data-ttu-id="3d339-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d339-128">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="3d339-129">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="3d339-129">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="3d339-130">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="3d339-130">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="3d339-131">Utiliza los certificados X.509 para autenticar al cliente.</span><span class="sxs-lookup"><span data-stu-id="3d339-131">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="3d339-132">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="3d339-132">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="3d339-133">Utiliza la autenticación NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="3d339-133">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="3d339-134">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="3d339-134">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="3d339-135">Atributo proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="3d339-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3d339-136">Value</span><span class="sxs-lookup"><span data-stu-id="3d339-136">Value</span></span>|<span data-ttu-id="3d339-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d339-137">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="3d339-138">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="3d339-138">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="3d339-139">Usa la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="3d339-139">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="3d339-140">Usa la autenticación implícita.</span><span class="sxs-lookup"><span data-stu-id="3d339-140">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="3d339-141">Utiliza NTLM como reserva con un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="3d339-141">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="3d339-142">Utiliza la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="3d339-142">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d339-143">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d339-143">Child Elements</span></span>  

 <span data-ttu-id="3d339-144">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3d339-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d339-145">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d339-145">Parent Elements</span></span>  
  
|<span data-ttu-id="3d339-146">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d339-146">Element</span></span>|<span data-ttu-id="3d339-147">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d339-147">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="3d339-148">Representa las funciones de seguridad del [\<wsHttpBinding>](wshttpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="3d339-148">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d339-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d339-149">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="3d339-150">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3d339-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3d339-151">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3d339-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3d339-152">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="3d339-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3d339-153">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="3d339-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="3d339-154">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="3d339-154">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
