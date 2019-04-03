---
title: <message> de <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 5c2176883dc3107445702724a7caa7ac2f6cb0d3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2019
ms.locfileid: "58890571"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="9ee67-102">\<mensaje > de \<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="9ee67-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="9ee67-103">Define la configuración de seguridad del mensaje SOAP en este enlace `netMsmqBinding`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="9ee67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ee67-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9ee67-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ee67-105">Attributes and Elements</span></span>

<span data-ttu-id="9ee67-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ee67-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ee67-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ee67-107">Attributes</span></span>

|<span data-ttu-id="9ee67-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ee67-108">Attribute</span></span>|<span data-ttu-id="9ee67-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ee67-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="9ee67-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9ee67-110">algorithmSuite</span></span>|<span data-ttu-id="9ee67-111">Establece el cifrado de mensajes y algoritmos de ajuste de clave que se utilizan para lograr la seguridad basada en mensaje para los mensajes enviados sobre transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9ee67-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="9ee67-112">El valor predeterminado es `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-112">The default value is `Aes256`.</span></span> <span data-ttu-id="9ee67-113">Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="9ee67-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="9ee67-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9ee67-114">clientCredentialType</span></span>|<span data-ttu-id="9ee67-115">Especifica el tipo de credencial que se va a utilizar al realizar la autenticación del cliente para los mensajes enviados sobre el transporte de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="9ee67-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="9ee67-116">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9ee67-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9ee67-117">-None: Esto permite al servicio interactuar con clientes anónimos.</span><span class="sxs-lookup"><span data-stu-id="9ee67-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="9ee67-118">Ni el servicio ni el cliente requieren una credencial.</span><span class="sxs-lookup"><span data-stu-id="9ee67-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="9ee67-119">-Windows: Esto permite que los intercambios de SOAP estar bajo el contexto autenticado de una credencial de Windows.</span><span class="sxs-lookup"><span data-stu-id="9ee67-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="9ee67-120">Esto siempre realiza una autenticación basada en Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9ee67-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="9ee67-121">-   UserName: Esto permite al servicio exigir que el cliente se autentique utilizando una credencial UserName.</span><span class="sxs-lookup"><span data-stu-id="9ee67-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="9ee67-122">La credencial en este caso necesita ser especificada utilizando el `clientCredentials` comportamiento **Precaución:**  Windows Communication Foundation (WCF) no admite enviar un resumen de contraseña ni derivar claves mediante contraseña y utilizando tales claves para seguridad de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9ee67-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="9ee67-123">Por lo tanto, WCF impone que el intercambio sea seguro al usar credenciales UserName.</span><span class="sxs-lookup"><span data-stu-id="9ee67-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="9ee67-124">Este modo requiere que el certificado del servicio se especifique en el lado del cliente mediante el comportamiento de `clientCredential` y `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="9ee67-125">-Certificado: Esto permite al servicio exigir que el cliente se autentique utilizando un certificado.</span><span class="sxs-lookup"><span data-stu-id="9ee67-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="9ee67-126">Las credenciales del cliente en este caso tienen que especificarse mediante el comportamiento `clientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="9ee67-127">La credencial del servicio en este caso necesita ser especificada utilizando el comportamiento `clientCredentials` especificando `serviceCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="9ee67-128">-CardSpace: Esto permite al servicio exigir que el cliente se autentique utilizando un CardSpace.</span><span class="sxs-lookup"><span data-stu-id="9ee67-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="9ee67-129">Se debe proporcionar `serviceCertificate` en el comportamiento `clientCredential`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="9ee67-130">El valor predeterminado es `Windows`.</span><span class="sxs-lookup"><span data-stu-id="9ee67-130">The default value is `Windows`.</span></span> <span data-ttu-id="9ee67-131">Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="9ee67-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9ee67-132">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ee67-132">Child Elements</span></span>

<span data-ttu-id="9ee67-133">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9ee67-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9ee67-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ee67-134">Parent Elements</span></span>

|<span data-ttu-id="9ee67-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ee67-135">Element</span></span>|<span data-ttu-id="9ee67-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ee67-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ee67-137">\<security></span><span class="sxs-lookup"><span data-stu-id="9ee67-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="9ee67-138">Define la configuración de seguridad de un enlace.</span><span class="sxs-lookup"><span data-stu-id="9ee67-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9ee67-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ee67-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="9ee67-140">Colas en WCF</span><span class="sxs-lookup"><span data-stu-id="9ee67-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="9ee67-141">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9ee67-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9ee67-142">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9ee67-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9ee67-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="9ee67-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9ee67-144">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="9ee67-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9ee67-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ee67-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
