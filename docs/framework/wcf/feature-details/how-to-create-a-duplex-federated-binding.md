---
title: Procedimiento para crear un enlace federado dúplex
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972053"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="f941e-102">Procedimiento para crear un enlace federado dúplex</span><span class="sxs-lookup"><span data-stu-id="f941e-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="f941e-103"><xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="f941e-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="f941e-104">Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f941e-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="f941e-105">Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="f941e-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="f941e-106">El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f941e-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="f941e-107">También puede crear el enlace en el código.</span><span class="sxs-lookup"><span data-stu-id="f941e-107">You can also create the binding in code.</span></span> <span data-ttu-id="f941e-108">Para obtener una descripción de la pila de elementos de enlace que [se va a crear, consulte How to: Cree un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="f941e-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="f941e-109">Para crear un enlace personalizado federado dúplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="f941e-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="f941e-110">En el [ \<nodo enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f941e-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="f941e-111">Dentro del [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un [ \<elemento Binding >](../../../../docs/framework/misc/binding.md) con el `name` atributo establecido en `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="f941e-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="f941e-112">Dentro del elemento de [ \<> de enlace](../../../../docs/framework/misc/binding.md) , cree un `authenticationMode` `SecureConversation` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad con el atributo establecido en.</span><span class="sxs-lookup"><span data-stu-id="f941e-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="f941e-113">Dentro del [ \<elemento > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un `authenticationMode` `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento de > secureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo establecido en o.</span><span class="sxs-lookup"><span data-stu-id="f941e-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="f941e-114">Después del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad, cree un elemento de [ \<> compositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vacío.</span><span class="sxs-lookup"><span data-stu-id="f941e-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="f941e-115">Después del [ \<elemento > compositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , cree un elemento [ \<> oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vacío.</span><span class="sxs-lookup"><span data-stu-id="f941e-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="f941e-116">Después del elemento de [ \<> oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) , cree un elemento de [ \<> httpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vacío.</span><span class="sxs-lookup"><span data-stu-id="f941e-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="f941e-117">Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP</span><span class="sxs-lookup"><span data-stu-id="f941e-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="f941e-118">En el [ \<nodo enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f941e-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="f941e-119">Dentro del [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un [ \<elemento Binding >](../../../../docs/framework/misc/binding.md) con el `name` atributo establecido en `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="f941e-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="f941e-120">Dentro del elemento de [ \<> de enlace](../../../../docs/framework/misc/binding.md) , cree un `authenticationMode` `SecureConversation` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad con el atributo establecido en.</span><span class="sxs-lookup"><span data-stu-id="f941e-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="f941e-121">Dentro del [ \<elemento > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un `authenticationMode` `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento de > secureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo establecido en o.</span><span class="sxs-lookup"><span data-stu-id="f941e-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="f941e-122">Después del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad, cree un elemento de [ \<> tcpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vacío.</span><span class="sxs-lookup"><span data-stu-id="f941e-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="f941e-123">Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP</span><span class="sxs-lookup"><span data-stu-id="f941e-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="f941e-124">En el [ \<nodo enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f941e-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="f941e-125">Dentro del [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un [ \<elemento Binding >](../../../../docs/framework/misc/binding.md) con el `name` atributo establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="f941e-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="f941e-126">Dentro del elemento de [ \<> de enlace](../../../../docs/framework/misc/binding.md) , cree un `authenticationMode` `SecureConversation` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad con el atributo establecido en.</span><span class="sxs-lookup"><span data-stu-id="f941e-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="f941e-127">Dentro del [ \<elemento > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un `authenticationMode` `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento de > secureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo establecido en o.</span><span class="sxs-lookup"><span data-stu-id="f941e-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="f941e-128">Después del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad, cree un elemento de [ \<> sección sslstreamsecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vacío.</span><span class="sxs-lookup"><span data-stu-id="f941e-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="f941e-129">Después del [ \<elemento > sección sslstreamsecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , cree un elemento [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vacío.</span><span class="sxs-lookup"><span data-stu-id="f941e-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f941e-130">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="f941e-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="f941e-131">Ejemplo con tres enlaces</span><span class="sxs-lookup"><span data-stu-id="f941e-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="f941e-132">Inserte el código siguiente en su archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f941e-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="f941e-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f941e-133">Example</span></span>

```xml
<bindings>
   <customBinding>
      <binding name="FederationDuplexHttpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <compositeDuplex />
          <oneWay />
          <httpTransport />
       </binding>
<!-- duplex over https is not supported -->
       <binding name="FederationDuplexTcpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <tcpTransport />
       </binding>
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />
          </security>
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->
          <sslStreamSecurity />
          <tcpTransport />
       </binding>
    </customBinding>
</bindings>
```
