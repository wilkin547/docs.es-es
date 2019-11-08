---
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736757"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="d10c5-102">\<> de mensajes de \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="d10c5-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="d10c5-103">Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="d10c5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d10c5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d10c5-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d10c5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d10c5-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="d10c5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d10c5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding**](netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="d10c5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="d10c5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="d10c5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d10c5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**seguridad**](security-of-netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="d10c5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="d10c5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**mensaje** ></span><span class="sxs-lookup"><span data-stu-id="d10c5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d10c5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d10c5-111">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d10c5-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d10c5-112">Attributes and Elements</span></span>

<span data-ttu-id="d10c5-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d10c5-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d10c5-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d10c5-114">Attributes</span></span>

|<span data-ttu-id="d10c5-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="d10c5-115">Attribute</span></span>|<span data-ttu-id="d10c5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="d10c5-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d10c5-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d10c5-117">algorithmSuite</span></span>|<span data-ttu-id="d10c5-118">Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d10c5-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="d10c5-119">El valor predeterminado es `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-119">The default value is `Aes256`.</span></span> <span data-ttu-id="d10c5-120">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="d10c5-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="d10c5-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="d10c5-121">clientCredentialType</span></span>|<span data-ttu-id="d10c5-122">Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="d10c5-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="d10c5-123">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d10c5-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d10c5-124">-None: Esto permite al servicio interactuar con clientes anónimos.</span><span class="sxs-lookup"><span data-stu-id="d10c5-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="d10c5-125">Ni el servicio ni el cliente requieren una credencial.</span><span class="sxs-lookup"><span data-stu-id="d10c5-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="d10c5-126">-Windows: permite que los intercambios de SOAP estén en el contexto autenticado de una credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="d10c5-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="d10c5-127">Esto siempre realiza una autenticación basada en Kerberos.</span><span class="sxs-lookup"><span data-stu-id="d10c5-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="d10c5-128">-UserName: permite al servicio exigir que el cliente se autentique con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="d10c5-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="d10c5-129">La credencial en este caso debe especificarse con el comportamiento `clientCredentials` **PRECAUCIÓN:** Windows Communication Foundation (WCF) no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseña y el uso de dichas claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d10c5-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="d10c5-130">Por lo tanto, WCF exige que el intercambio esté protegido al utilizar las credenciales de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="d10c5-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="d10c5-131">Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="d10c5-132">-Certificate: permite que el servicio requiera que el cliente se autentique mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="d10c5-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="d10c5-133">Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="d10c5-134">La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="d10c5-135">-CardSpace: permite que el servicio requiera que el cliente se autentique mediante un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="d10c5-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="d10c5-136">Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="d10c5-137">El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="d10c5-137">The default value is `Windows`.</span></span> <span data-ttu-id="d10c5-138">Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d10c5-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d10c5-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d10c5-139">Child Elements</span></span>

<span data-ttu-id="d10c5-140">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d10c5-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d10c5-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d10c5-141">Parent Elements</span></span>

|<span data-ttu-id="d10c5-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="d10c5-142">Element</span></span>|<span data-ttu-id="d10c5-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="d10c5-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d10c5-144">\<La ></span><span class="sxs-lookup"><span data-stu-id="d10c5-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="d10c5-145">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="d10c5-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d10c5-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d10c5-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="d10c5-147">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="d10c5-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="d10c5-148">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d10c5-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d10c5-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="d10c5-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d10c5-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="d10c5-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d10c5-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="d10c5-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d10c5-152">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="d10c5-152">\<binding></span></span>](bindings.md)
