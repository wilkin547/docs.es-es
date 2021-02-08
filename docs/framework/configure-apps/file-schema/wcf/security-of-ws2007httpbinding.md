---
description: 'Más información sobre: <security> de <ws2007HttpBinding>'
title: <security> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: ef8b82d34b318db79db061b9c01b147e619d39c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786816"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="a1e8e-103">\<security> de \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="a1e8e-103">\<security> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="a1e8e-104">Representa la configuración de seguridad utilizada con el [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-104">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="a1e8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1e8e-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1e8e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a1e8e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a1e8e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1e8e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a1e8e-108">Attributes</span></span>  
  
|<span data-ttu-id="a1e8e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a1e8e-109">Attribute</span></span>|<span data-ttu-id="a1e8e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e8e-110">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="a1e8e-111">Opta.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-111">-   Optional.</span></span> <span data-ttu-id="a1e8e-112">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a1e8e-113">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-113">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="a1e8e-114">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a1e8e-115">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="a1e8e-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="a1e8e-116">Value</span><span class="sxs-lookup"><span data-stu-id="a1e8e-116">Value</span></span>|<span data-ttu-id="a1e8e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e8e-117">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="a1e8e-118">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-118">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="a1e8e-119">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-119">Security is provided using HTTPS.</span></span> <span data-ttu-id="a1e8e-120">El servicio se debe configurar con certificados de Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="a1e8e-120">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="a1e8e-121">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-121">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="a1e8e-122">La autenticación del cliente se controla a través del `ClientCredentials` atributo del [\<transport>](transport-of-ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-122">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="a1e8e-123">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-123">Security is provided using SOAP message security.</span></span> <span data-ttu-id="a1e8e-124">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-124">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="a1e8e-125">Este modo ofrece diversas características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se van a usar y qué nivel de protección se aplica al cuerpo del mensaje a través de <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-125">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="a1e8e-126">Se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-126">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="a1e8e-127">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-127">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="a1e8e-128">De manera predeterminada, se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-128">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1e8e-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a1e8e-129">Child Elements</span></span>  
  
|<span data-ttu-id="a1e8e-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1e8e-130">Element</span></span>|<span data-ttu-id="a1e8e-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e8e-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="a1e8e-132">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-132">Defines the transport security settings.</span></span> <span data-ttu-id="a1e8e-133">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="a1e8e-134">Esta configuración se aplica sólo cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-134">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="a1e8e-135">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-135">Defines the security settings for the message.</span></span> <span data-ttu-id="a1e8e-136">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-136">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="a1e8e-137">Esta configuración no se aplica cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-137">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1e8e-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a1e8e-138">Parent Elements</span></span>  
  
|<span data-ttu-id="a1e8e-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="a1e8e-139">Element</span></span>|<span data-ttu-id="a1e8e-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e8e-140">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="a1e8e-141">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-141">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1e8e-142">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a1e8e-142">Remarks</span></span>  

 <span data-ttu-id="a1e8e-143">Este elemento está diseñado para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-143">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="a1e8e-144">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a1e8e-144">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e8e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1e8e-145">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="a1e8e-146">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a1e8e-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a1e8e-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a1e8e-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a1e8e-148">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a1e8e-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a1e8e-149">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a1e8e-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
