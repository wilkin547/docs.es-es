---
title: Procedimiento para crear un enlace federado dúplex
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 3ecd9e2dbeb30bb255cbf66488b50a9b20219431
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141717"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="cea8a-102">Procedimiento para crear un enlace federado dúplex</span><span class="sxs-lookup"><span data-stu-id="cea8a-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="cea8a-103"><xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="cea8a-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="cea8a-104">Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="cea8a-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="cea8a-105">Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="cea8a-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="cea8a-106">El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="cea8a-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="cea8a-107">También puede crear el enlace en el código.</span><span class="sxs-lookup"><span data-stu-id="cea8a-107">You can also create the binding in code.</span></span> <span data-ttu-id="cea8a-108">Para obtener una descripción de la pila de elementos de enlace que se va a crear, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="cea8a-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="cea8a-109">Para crear un enlace personalizado federado dúplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="cea8a-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="cea8a-110">En el nodo [\<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="cea8a-111">Dentro del elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un elemento [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) con el atributo `name` establecido en `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="cea8a-112">Dentro del elemento de [> de enlace\<](../../configure-apps/file-schema/wcf/bindings.md) , cree un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con el atributo `authenticationMode` establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="cea8a-113">Dentro del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo `authenticationMode` establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="cea8a-114">Después del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento vacío [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="cea8a-115">Después del elemento [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , cree un elemento de [> oneWay\<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) en blanco.</span><span class="sxs-lookup"><span data-stu-id="cea8a-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="cea8a-116">Después del elemento [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) , cree un elemento vacío [\<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="cea8a-117">Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP</span><span class="sxs-lookup"><span data-stu-id="cea8a-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="cea8a-118">En el nodo [\<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="cea8a-119">Dentro del elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un elemento [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) con el atributo `name` establecido en `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="cea8a-120">Dentro del elemento de [> de enlace\<](../../configure-apps/file-schema/wcf/bindings.md) , cree un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con el atributo `authenticationMode` establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="cea8a-121">Dentro del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo `authenticationMode` establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="cea8a-122">Después del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento vacío [\<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="cea8a-123">Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP</span><span class="sxs-lookup"><span data-stu-id="cea8a-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="cea8a-124">En el nodo [\<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="cea8a-125">Dentro del elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un elemento [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) con el atributo `name` establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="cea8a-126">Dentro del elemento de [> de enlace\<](../../configure-apps/file-schema/wcf/bindings.md) , cree un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con el atributo `authenticationMode` establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="cea8a-127">Dentro del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo `authenticationMode` establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="cea8a-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="cea8a-128">Después del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento vacío [\<sección sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="cea8a-129">Después del elemento [\<sección sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , cree un elemento vacío [\<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) .</span><span class="sxs-lookup"><span data-stu-id="cea8a-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="cea8a-130">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="cea8a-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="cea8a-131">Ejemplo con tres enlaces</span><span class="sxs-lookup"><span data-stu-id="cea8a-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="cea8a-132">Inserte el código siguiente en su archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="cea8a-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="cea8a-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cea8a-133">Example</span></span>

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
