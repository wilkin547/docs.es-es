---
description: 'Más información sobre: <message> de <netMsmqBinding>'
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 0e8cf641ef8ba5361318f7b658d5d60beef6ce56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749589"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="7ea9f-103">\<message> de \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="7ea9f-103">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="7ea9f-104">Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-104">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  

## <a name="syntax"></a><span data-ttu-id="7ea9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ea9f-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7ea9f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ea9f-106">Attributes and Elements</span></span>

<span data-ttu-id="7ea9f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7ea9f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ea9f-108">Attributes</span></span>

|<span data-ttu-id="7ea9f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ea9f-109">Attribute</span></span>|<span data-ttu-id="7ea9f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ea9f-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="7ea9f-111">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="7ea9f-111">algorithmSuite</span></span>|<span data-ttu-id="7ea9f-112">Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-112">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="7ea9f-113">El valor predeterminado es `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-113">The default value is `Aes256`.</span></span> <span data-ttu-id="7ea9f-114">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="7ea9f-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="7ea9f-115">clientCredentialType</span></span>|<span data-ttu-id="7ea9f-116">Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-116">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="7ea9f-117">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7ea9f-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7ea9f-118">-None: Esto permite al servicio interactuar con clientes anónimos.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-118">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="7ea9f-119">Ni el servicio ni el cliente requieren una credencial.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-119">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="7ea9f-120">-Windows: permite que los intercambios de SOAP estén en el contexto autenticado de una credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-120">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="7ea9f-121">Esto siempre realiza una autenticación basada en Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-121">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="7ea9f-122">-UserName: permite al servicio exigir que el cliente se autentique con una credencial de nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-122">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="7ea9f-123">La credencial en este caso debe especificarse con el `clientCredentials` comportamiento **precaución:**  Windows Communication Foundation (WCF) no admite el envío de un resumen de contraseña ni la derivación de claves mediante contraseña y el uso de tales claves para la seguridad de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-123">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="7ea9f-124">Por lo tanto, WCF impone que el intercambio esté protegido cuando se usen las credenciales UserName.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-124">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="7ea9f-125">Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-125">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="7ea9f-126">-Certificate: permite que el servicio requiera que el cliente se autentique mediante un certificado.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-126">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="7ea9f-127">Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-127">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="7ea9f-128">La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-128">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="7ea9f-129">-CardSpace: permite que el servicio requiera que el cliente se autentique mediante un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-129">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="7ea9f-130">Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-130">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="7ea9f-131">El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-131">The default value is `Windows`.</span></span> <span data-ttu-id="7ea9f-132">Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-132">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7ea9f-133">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ea9f-133">Child Elements</span></span>

<span data-ttu-id="7ea9f-134">None</span><span class="sxs-lookup"><span data-stu-id="7ea9f-134">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7ea9f-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ea9f-135">Parent Elements</span></span>

|<span data-ttu-id="7ea9f-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ea9f-136">Element</span></span>|<span data-ttu-id="7ea9f-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ea9f-137">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="7ea9f-138">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="7ea9f-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="7ea9f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ea9f-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="7ea9f-140">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="7ea9f-140">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="7ea9f-141">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7ea9f-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7ea9f-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7ea9f-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7ea9f-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="7ea9f-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7ea9f-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="7ea9f-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
