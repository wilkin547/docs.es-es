---
title: <security> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736392"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="02134-102">\<security> de \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="02134-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="02134-103">Representa la configuración de seguridad utilizada con el [\<ws2007HttpBinding>](ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="02134-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="02134-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02134-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02134-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02134-105">Attributes and Elements</span></span>  
 <span data-ttu-id="02134-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02134-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02134-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="02134-107">Attributes</span></span>  
  
|<span data-ttu-id="02134-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="02134-108">Attribute</span></span>|<span data-ttu-id="02134-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="02134-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="02134-110">Opta.</span><span class="sxs-lookup"><span data-stu-id="02134-110">-   Optional.</span></span> <span data-ttu-id="02134-111">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="02134-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="02134-112">De manera predeterminada, es `Message`.</span><span class="sxs-lookup"><span data-stu-id="02134-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="02134-113">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="02134-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="02134-114">Atributo mode</span><span class="sxs-lookup"><span data-stu-id="02134-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="02134-115">Value</span><span class="sxs-lookup"><span data-stu-id="02134-115">Value</span></span>|<span data-ttu-id="02134-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="02134-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="02134-117">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="02134-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="02134-118">La seguridad se proporciona utilizando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="02134-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="02134-119">El servicio se debe configurar con certificados de Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="02134-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="02134-120">El mensaje se protege completamente utilizando HTTPS y el servicio se autentica por el cliente usando el certificado SSL del servicio.</span><span class="sxs-lookup"><span data-stu-id="02134-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="02134-121">La autenticación del cliente se controla a través del `ClientCredentials` atributo del [\<transport>](transport-of-ws2007httpbinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="02134-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="02134-122">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="02134-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="02134-123">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="02134-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="02134-124">Este modo ofrece diversas características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se van a usar y qué nivel de protección se aplica al cuerpo del mensaje a través de <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="02134-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="02134-125">Se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="02134-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="02134-126">En este modo, HTTPS proporciona integridad, confidencialidad y autenticación de servidor y la seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="02134-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="02134-127">De manera predeterminada, se realiza la autenticación del cliente una vez por cada sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="02134-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02134-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02134-128">Child Elements</span></span>  
  
|<span data-ttu-id="02134-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="02134-129">Element</span></span>|<span data-ttu-id="02134-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="02134-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="02134-131">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="02134-131">Defines the transport security settings.</span></span> <span data-ttu-id="02134-132">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="02134-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="02134-133">Esta configuración se aplica sólo cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="02134-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="02134-134">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="02134-134">Defines the security settings for the message.</span></span> <span data-ttu-id="02134-135">Este elemento corresponde al tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="02134-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="02134-136">Esta configuración no se aplica cuando el modo se establece en Transporte.</span><span class="sxs-lookup"><span data-stu-id="02134-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02134-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02134-137">Parent Elements</span></span>  
  
|<span data-ttu-id="02134-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="02134-138">Element</span></span>|<span data-ttu-id="02134-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="02134-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="02134-140">Un enlace seguro para las aplicaciones de transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="02134-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02134-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02134-141">Remarks</span></span>  
 <span data-ttu-id="02134-142">Este elemento está diseñado para la interoperación con servicios que implementan las especificaciones de WS-\*.</span><span class="sxs-lookup"><span data-stu-id="02134-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="02134-143">La seguridad de transporte para este enlace es Capa de sockets seguros (SSL) sobre HTTP o HTTPS.</span><span class="sxs-lookup"><span data-stu-id="02134-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02134-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02134-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="02134-145">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="02134-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="02134-146">Enlaces</span><span class="sxs-lookup"><span data-stu-id="02134-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="02134-147">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="02134-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="02134-148">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="02134-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
