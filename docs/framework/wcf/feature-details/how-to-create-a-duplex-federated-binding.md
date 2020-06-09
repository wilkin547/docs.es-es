---
title: Procedimiento para crear un enlace federado dúplex
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: e93651ce9fe9dae55c299fcb061da6bdc4b6bc5e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598975"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="49690-102">Procedimiento para crear un enlace federado dúplex</span><span class="sxs-lookup"><span data-stu-id="49690-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="49690-103"><xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="49690-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="49690-104">Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="49690-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="49690-105">Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="49690-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="49690-106">El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="49690-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="49690-107">También puede crear el enlace en el código.</span><span class="sxs-lookup"><span data-stu-id="49690-107">You can also create the binding in code.</span></span> <span data-ttu-id="49690-108">Para obtener una descripción de la pila de elementos de enlace que se va a crear, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="49690-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="49690-109">Para crear un enlace personalizado federado dúplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="49690-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="49690-110">En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="49690-110">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="49690-111">Dentro del [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con el `name` atributo establecido en `FederationDuplexHttpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="49690-111">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="49690-112">Dentro del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, cree un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="49690-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="49690-113">Dentro del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="49690-113">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="49690-114">Después del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="49690-114">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="49690-115">Después del [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento, cree un [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="49690-115">Following the [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="49690-116">Después del [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento, cree un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="49690-116">Following the [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="49690-117">Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP</span><span class="sxs-lookup"><span data-stu-id="49690-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="49690-118">En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="49690-118">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="49690-119">Dentro del [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con el `name` atributo establecido en `FederationDuplexTcpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="49690-119">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="49690-120">Dentro del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, cree un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="49690-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="49690-121">Dentro del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="49690-121">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="49690-122">Después del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="49690-122">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="49690-123">Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP</span><span class="sxs-lookup"><span data-stu-id="49690-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="49690-124">En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="49690-124">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="49690-125">Dentro del [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con el `name` atributo establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .</span><span class="sxs-lookup"><span data-stu-id="49690-125">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="49690-126">Dentro del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, cree un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="49690-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="49690-127">Dentro del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="49690-127">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="49690-128">Después del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="49690-128">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="49690-129">Después del [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, cree un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vacío.</span><span class="sxs-lookup"><span data-stu-id="49690-129">Following the [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="49690-130">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="49690-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="49690-131">Ejemplo con tres enlaces</span><span class="sxs-lookup"><span data-stu-id="49690-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="49690-132">Inserte el código siguiente en su archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="49690-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="49690-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49690-133">Example</span></span>

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
