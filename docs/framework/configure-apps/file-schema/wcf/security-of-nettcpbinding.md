---
title: <security> de <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: aa01e906ddd2f15007c72bfc2a45122cfb15ba2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736371"
---
# <a name="security-of-nettcpbinding"></a><span data-ttu-id="70f3f-102">\<security> de \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="70f3f-102">\<security> of \<netTcpBinding></span></span>
<span data-ttu-id="70f3f-103">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="70f3f-103">Defines the security settings for a binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="70f3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70f3f-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70f3f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="70f3f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="70f3f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70f3f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70f3f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="70f3f-107">Attributes</span></span>  
  
|<span data-ttu-id="70f3f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="70f3f-108">Attribute</span></span>|<span data-ttu-id="70f3f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="70f3f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70f3f-110">mode</span><span class="sxs-lookup"><span data-stu-id="70f3f-110">mode</span></span>|<span data-ttu-id="70f3f-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="70f3f-111">Optional.</span></span> <span data-ttu-id="70f3f-112">Especifica el tipo de seguridad que se aplica.</span><span class="sxs-lookup"><span data-stu-id="70f3f-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="70f3f-113">Se muestran los valores válidos a continuación.</span><span class="sxs-lookup"><span data-stu-id="70f3f-113">Valid values are shown below.</span></span> <span data-ttu-id="70f3f-114">El valor predeterminado es `Transport`.</span><span class="sxs-lookup"><span data-stu-id="70f3f-114">The default value is `Transport`.</span></span><br /><br /> <span data-ttu-id="70f3f-115">Este atributo es del tipo <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="70f3f-115">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="70f3f-116">Atributo de modo</span><span class="sxs-lookup"><span data-stu-id="70f3f-116">mode Attribute</span></span>  
  
|<span data-ttu-id="70f3f-117">Value</span><span class="sxs-lookup"><span data-stu-id="70f3f-117">Value</span></span>|<span data-ttu-id="70f3f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="70f3f-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70f3f-119">None</span><span class="sxs-lookup"><span data-stu-id="70f3f-119">None</span></span>|<span data-ttu-id="70f3f-120">La seguridad está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="70f3f-120">Security is disabled.</span></span>|  
|<span data-ttu-id="70f3f-121">Transporte</span><span class="sxs-lookup"><span data-stu-id="70f3f-121">Transport</span></span>|<span data-ttu-id="70f3f-122">La seguridad de transporte se proporciona utilizando TLS sobre TCP o SPNego.</span><span class="sxs-lookup"><span data-stu-id="70f3f-122">Transport security is provided using TLS over TCP or SPNego.</span></span> <span data-ttu-id="70f3f-123">El servicio puede necesitar ser configurado con certificados SSL.</span><span class="sxs-lookup"><span data-stu-id="70f3f-123">The service may need to be configured with SSL certificates.</span></span> <span data-ttu-id="70f3f-124">Con este modo es posible controlar el nivel de protección.</span><span class="sxs-lookup"><span data-stu-id="70f3f-124">It is possible to control the protection level with this mode.</span></span>|  
|<span data-ttu-id="70f3f-125">Message</span><span class="sxs-lookup"><span data-stu-id="70f3f-125">Message</span></span>|<span data-ttu-id="70f3f-126">La seguridad se proporciona mediante la seguridad del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="70f3f-126">Security is provided using SOAP message security.</span></span> <span data-ttu-id="70f3f-127">De forma predeterminada, el cuerpo SOAP se cifra y firma.</span><span class="sxs-lookup"><span data-stu-id="70f3f-127">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="70f3f-128">Este modo proporciona una variedad de características, como si las credenciales del servicio están disponibles para el cliente fuera de la banda, el conjunto de algoritmos que se utiliza y qué nivel de protección se aplica al cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="70f3f-128">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body.</span></span> <span data-ttu-id="70f3f-129">Se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="70f3f-129">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="70f3f-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="70f3f-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="70f3f-131">La seguridad de transporte va unida a la seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="70f3f-131">Transport security is coupled with message security.</span></span> <span data-ttu-id="70f3f-132">TLS proporciona la seguridad de transporte sobre TCP o SPNego y asegura la integridad, confidencialidad y autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="70f3f-132">Transport security is provided by TLS over TCP, or SPNego, and ensures integrity, confidentiality, and server authentication.</span></span> <span data-ttu-id="70f3f-133">La seguridad del mensaje SOAP proporciona la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="70f3f-133">SOAP message security provides client authentication.</span></span> <span data-ttu-id="70f3f-134">De manera predeterminada, se realiza la autenticación del cliente una vez por sesión y los resultados de autenticación están almacenados en la memoria caché durante la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="70f3f-134">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70f3f-135">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="70f3f-135">Child Elements</span></span>  
  
|<span data-ttu-id="70f3f-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="70f3f-136">Element</span></span>|<span data-ttu-id="70f3f-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="70f3f-137">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|<span data-ttu-id="70f3f-138">Define la configuración de seguridad para el transporte.</span><span class="sxs-lookup"><span data-stu-id="70f3f-138">Defines the security settings for the transport.</span></span> <span data-ttu-id="70f3f-139">Este elemento es del tipo <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="70f3f-139">This element is of type <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement>.</span></span>|  
|[\<message>](message-element-of-nettcpbinding.md)|<span data-ttu-id="70f3f-140">Define la configuración de seguridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="70f3f-140">Defines the security settings for the message.</span></span> <span data-ttu-id="70f3f-141">Este elemento es del tipo <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span><span class="sxs-lookup"><span data-stu-id="70f3f-141">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70f3f-142">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="70f3f-142">Parent Elements</span></span>  
  
|<span data-ttu-id="70f3f-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="70f3f-143">Element</span></span>|<span data-ttu-id="70f3f-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="70f3f-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70f3f-145">binding</span><span class="sxs-lookup"><span data-stu-id="70f3f-145">binding</span></span>|<span data-ttu-id="70f3f-146">Elemento de enlace de [\<netTcpBinding>](nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="70f3f-146">The binding element of the [\<netTcpBinding>](nettcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70f3f-147">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70f3f-147">Remarks</span></span>  
 <span data-ttu-id="70f3f-148">Cada uno de los enlaces estándar proporciona los parámetros para controlar los requisitos de seguridad de la transferencia.</span><span class="sxs-lookup"><span data-stu-id="70f3f-148">Each of the standard bindings provides parameters for controlling the transfer security requirements.</span></span> <span data-ttu-id="70f3f-149">Estos parámetros incluyen normalmente el modo de seguridad que especificó si se usó la seguridad del nivel de mensaje o del nivel de transporte y la elección del tipo de credencial del cliente.</span><span class="sxs-lookup"><span data-stu-id="70f3f-149">These parameters typically include the security mode that specified whether message-level or transport-level security is used and the choice of client credential type.</span></span> <span data-ttu-id="70f3f-150">Basada en la elección de opciones que estos parámetros presentan, se construirá una pila de canal con la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="70f3f-150">Based on the choice of options these parameters present, a channel stack is constructed with appropriate security.</span></span>  
  
 <span data-ttu-id="70f3f-151">Los enlaces proporcionados por el sistema suministrados por Windows Communication Foundation (WCF) son un conjunto diseñado para cumplir algunos de los requisitos de escenario más comunes.</span><span class="sxs-lookup"><span data-stu-id="70f3f-151">The system-provided bindings supplied by Windows Communication Foundation (WCF) are a set designed to meet some of the most common scenario requirements.</span></span> <span data-ttu-id="70f3f-152">Cada uno de estos enlaces permite la especificación de requisitos de seguridad para algunos escenarios concretos.</span><span class="sxs-lookup"><span data-stu-id="70f3f-152">Each of these bindings allows the specification of security requirements for some specific targeted scenarios.</span></span>  
  
 <span data-ttu-id="70f3f-153">Este elemento de configuración proporciona especificaciones de seguridad para `netTcpBinding`.</span><span class="sxs-lookup"><span data-stu-id="70f3f-153">This configuration element provides the security specifications for `netTcpBinding`.</span></span> <span data-ttu-id="70f3f-154">Se trata de un enlace seguro, confiable y optimizado adecuado para la comunicación entre equipos.</span><span class="sxs-lookup"><span data-stu-id="70f3f-154">This is a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="70f3f-155">De forma predeterminada, genera una pila de comunicación en tiempo de ejecución que admite TCP para la entrega del mensaje y Seguridad de Windows para la seguridad y autenticación del mensaje, WS-ReliableMessaging para la confiabilidad, y la codificación binaria del mensaje.</span><span class="sxs-lookup"><span data-stu-id="70f3f-155">By default it generates a runtime communication stack supporting TCP for message delivery and Windows Security for message security and authentication, WS-ReliableMessaging for reliability, and binary message encoding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f3f-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70f3f-156">See also</span></span>

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="70f3f-157">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="70f3f-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="70f3f-158">Enlaces</span><span class="sxs-lookup"><span data-stu-id="70f3f-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="70f3f-159">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="70f3f-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="70f3f-160">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="70f3f-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
