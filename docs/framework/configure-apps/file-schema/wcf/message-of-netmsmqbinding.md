---
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 09d9d4a5d1967afaf9a6ed5756c309e78fee0923
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400253"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="35c55-102">\<> de mensajes \<de netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="35c55-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="35c55-103">Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="35c55-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="35c55-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35c55-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35c55-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="35c55-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="35c55-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="35c55-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="35c55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="35c55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="35c55-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="35c55-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="35c55-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguridad**](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="35c55-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="35c55-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de mensajes**</span><span class="sxs-lookup"><span data-stu-id="35c55-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="35c55-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35c55-111">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="35c55-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35c55-112">Attributes and Elements</span></span>

<span data-ttu-id="35c55-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="35c55-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="35c55-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="35c55-114">Attributes</span></span>

|<span data-ttu-id="35c55-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="35c55-115">Attribute</span></span>|<span data-ttu-id="35c55-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="35c55-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="35c55-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="35c55-117">algorithmSuite</span></span>|<span data-ttu-id="35c55-118">Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="35c55-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="35c55-119">El valor predeterminado es `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="35c55-119">The default value is `Aes256`.</span></span> <span data-ttu-id="35c55-120">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="35c55-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="35c55-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="35c55-121">clientCredentialType</span></span>|<span data-ttu-id="35c55-122">Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="35c55-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="35c55-123">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="35c55-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="35c55-124">Ninguna Esto permite al servicio interactuar con clientes anónimos.</span><span class="sxs-lookup"><span data-stu-id="35c55-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="35c55-125">Ni el servicio ni el cliente requieren una credencial.</span><span class="sxs-lookup"><span data-stu-id="35c55-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="35c55-126">Windows Esto permite a los intercambios de SOAP estar bajo el contexto autenticado de una credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="35c55-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="35c55-127">Esto siempre realiza una autenticación basada en Kerberos.</span><span class="sxs-lookup"><span data-stu-id="35c55-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="35c55-128">Nombre Esto permite que el servicio requiera que el cliente se autentique con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="35c55-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="35c55-129">En este caso, la credencial debe especificarse con el `clientCredentials` comportamiento **PRECAUCIÓN:**  Windows Communication Foundation (WCF) no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseña y el uso de tales claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="35c55-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="35c55-130">Por lo tanto, WCF exige que el intercambio esté protegido al utilizar las credenciales de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="35c55-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="35c55-131">Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="35c55-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="35c55-132">Certificado Esto permite que el servicio requiera que el cliente se autentique mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="35c55-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="35c55-133">Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="35c55-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="35c55-134">La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="35c55-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="35c55-135">CardSpace Esto permite que el servicio requiera que el cliente se autentique mediante un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="35c55-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="35c55-136">Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="35c55-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="35c55-137">El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="35c55-137">The default value is `Windows`.</span></span> <span data-ttu-id="35c55-138">Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="35c55-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="35c55-139">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35c55-139">Child Elements</span></span>

<span data-ttu-id="35c55-140">None</span><span class="sxs-lookup"><span data-stu-id="35c55-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="35c55-141">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35c55-141">Parent Elements</span></span>

|<span data-ttu-id="35c55-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="35c55-142">Element</span></span>|<span data-ttu-id="35c55-143">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="35c55-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="35c55-144">\<security></span><span class="sxs-lookup"><span data-stu-id="35c55-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="35c55-145">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="35c55-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="35c55-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="35c55-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="35c55-147">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="35c55-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="35c55-148">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="35c55-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="35c55-149">Enlaces</span><span class="sxs-lookup"><span data-stu-id="35c55-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="35c55-150">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="35c55-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="35c55-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="35c55-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="35c55-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="35c55-152">\<binding></span></span>](../../../misc/binding.md)
