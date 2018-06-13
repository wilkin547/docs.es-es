---
title: Procedimiento para crear un enlace federado dúplex
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: d736d0119f3e938d81a15d57bb6d97ca2a1990fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495731"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="86a2c-102">Procedimiento para crear un enlace federado dúplex</span><span class="sxs-lookup"><span data-stu-id="86a2c-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="86a2c-103"><xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta.</span><span class="sxs-lookup"><span data-stu-id="86a2c-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="86a2c-104">Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="86a2c-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="86a2c-105">Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP.</span><span class="sxs-lookup"><span data-stu-id="86a2c-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="86a2c-106">El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="86a2c-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="86a2c-107">También puede crear el enlace en el código.</span><span class="sxs-lookup"><span data-stu-id="86a2c-107">You can also create the binding in code.</span></span> <span data-ttu-id="86a2c-108">Para obtener una descripción de la pila de elementos de enlace para crear, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="86a2c-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="86a2c-109">Para crear un enlace personalizado federado dúplex con HTTP</span><span class="sxs-lookup"><span data-stu-id="86a2c-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1.  <span data-ttu-id="86a2c-110">En el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2.  <span data-ttu-id="86a2c-111">Dentro de la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, crear una [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento con la `name` atributo establecido en `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="86a2c-112">Dentro de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento, crear una [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` atributo establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="86a2c-113">Dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear una [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con la `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="86a2c-114">Después de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear vacío [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6.  <span data-ttu-id="86a2c-115">Después de la [ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) elemento, crear vacío [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7.  <span data-ttu-id="86a2c-116">Después de la [ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) elemento, crear vacío [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="86a2c-117">Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP</span><span class="sxs-lookup"><span data-stu-id="86a2c-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1.  <span data-ttu-id="86a2c-118">En el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="86a2c-119">Dentro de la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, crear una [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento con la `name` atributo establecido en `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="86a2c-120">Dentro de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento, crear una [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` atributo establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="86a2c-121">Dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear una [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con la `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="86a2c-122">Después de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear vacío [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="86a2c-123">Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP</span><span class="sxs-lookup"><span data-stu-id="86a2c-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1.  <span data-ttu-id="86a2c-124">En el [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="86a2c-125">Dentro de la [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) elemento, crear una [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento con la `name` atributo establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3.  <span data-ttu-id="86a2c-126">Dentro de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento, crear una [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con la `authenticationMode` atributo establecido en `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="86a2c-127">Dentro de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear una [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con la `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="86a2c-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="86a2c-128">Después de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, crear vacío [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6.  <span data-ttu-id="86a2c-129">Después de la [ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, crear vacío [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="86a2c-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="86a2c-130">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="86a2c-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="86a2c-131">Ejemplo con tres enlaces</span><span class="sxs-lookup"><span data-stu-id="86a2c-131">Sample with 3 Bindings</span></span>  
  
1.  <span data-ttu-id="86a2c-132">Inserte el código siguiente en su archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="86a2c-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86a2c-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86a2c-133">Example</span></span>  
  
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
