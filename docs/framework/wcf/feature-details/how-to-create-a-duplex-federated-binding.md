---
title: Filtrar para crear un enlace federado dúplex
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346241"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="ecb93-102">Filtrar para crear un enlace federado dúplex</span><span class="sxs-lookup"><span data-stu-id="ecb93-102">How to: Create a Duplex Federated Binding</span></span>
<xref:System.ServiceModel.WSFederationHttpBinding> <span data-ttu-id="ecb93-103">solo es compatible con los contratos de intercambio de mensajes de datagrama y solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="ecb93-103">only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="ecb93-104">Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ecb93-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="ecb93-105">Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="ecb93-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="ecb93-106">El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ecb93-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="ecb93-107">También puede crear el enlace en el código.</span><span class="sxs-lookup"><span data-stu-id="ecb93-107">You can also create the binding in code.</span></span> <span data-ttu-id="ecb93-108">Para obtener una descripción de la pila de elementos de enlace para crear, ver [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="ecb93-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="ecb93-109">Para crear un enlace personalizado federado dúplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="ecb93-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1. <span data-ttu-id="ecb93-110">En el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2. <span data-ttu-id="ecb93-111">Dentro de la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento con el `name` atributo establecido en `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="ecb93-112">Dentro de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento, cree un [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="ecb93-113">Dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="ecb93-114">Siguiendo el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear vacío [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6. <span data-ttu-id="ecb93-115">Siguiendo el [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento, crear vacío [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7. <span data-ttu-id="ecb93-116">Siguiendo el [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, crear vacío [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="ecb93-117">Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP</span><span class="sxs-lookup"><span data-stu-id="ecb93-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1. <span data-ttu-id="ecb93-118">En el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="ecb93-119">Dentro de la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento con el `name` atributo establecido en `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="ecb93-120">Dentro de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento, cree un [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="ecb93-121">Dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="ecb93-122">Siguiendo el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear vacío [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="ecb93-123">Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP</span><span class="sxs-lookup"><span data-stu-id="ecb93-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1. <span data-ttu-id="ecb93-124">En el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="ecb93-125">Dentro de la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento con el `name` atributo establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3. <span data-ttu-id="ecb93-126">Dentro de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento, cree un [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="ecb93-127">Dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="ecb93-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="ecb93-128">Siguiendo el [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear vacío [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6. <span data-ttu-id="ecb93-129">Siguiendo el [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, crear vacío [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ecb93-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="ecb93-130">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="ecb93-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="ecb93-131">Ejemplo con tres enlaces</span><span class="sxs-lookup"><span data-stu-id="ecb93-131">Sample with 3 Bindings</span></span>  
  
1. <span data-ttu-id="ecb93-132">Inserte el código siguiente en su archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ecb93-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecb93-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecb93-133">Example</span></span>  
  
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
