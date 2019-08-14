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
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedimiento para crear un enlace federado dúplex

<xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta. Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado. Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP. El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.

También puede crear el enlace en el código. Para obtener una descripción de la pila de elementos de enlace que [se va a crear, consulte How to: Cree un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Para crear un enlace personalizado federado dúplex con HTTP

1. En el [ \<nodo enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. Dentro del [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un [ \<elemento Binding >](../../../../docs/framework/misc/binding.md) con el `name` atributo establecido en `FederationDuplexHttpMessageSecurityBinding`.

3. Dentro del elemento de [ \<> de enlace](../../../../docs/framework/misc/binding.md) , cree un `authenticationMode` `SecureConversation` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad con el atributo establecido en.

4. Dentro del [ \<elemento > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un `authenticationMode` `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento de > secureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo establecido en o.

5. Después del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad, cree un elemento de [ \<> compositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) vacío.

6. Después del [ \<elemento > compositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , cree un elemento [ \<> oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) vacío.

7. Después del elemento de [ \<> oneWay](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) , cree un elemento de [ \<> httpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) vacío.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP

1. En el [ \<nodo enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. Dentro del [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un [ \<elemento Binding >](../../../../docs/framework/misc/binding.md) con el `name` atributo establecido en `FederationDuplexTcpMessageSecurityBinding`.

3. Dentro del elemento de [ \<> de enlace](../../../../docs/framework/misc/binding.md) , cree un `authenticationMode` `SecureConversation` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad con el atributo establecido en.

4. Dentro del [ \<elemento > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un `authenticationMode` `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento de > secureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo establecido en o.

5. Después del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad, cree un elemento de [ \<> tcpTransport](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vacío.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP

1. En el [ \<nodo enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. Dentro del [ \<elemento customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un [ \<elemento Binding >](../../../../docs/framework/misc/binding.md) con el `name` atributo establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.

3. Dentro del elemento de [ \<> de enlace](../../../../docs/framework/misc/binding.md) , cree un `authenticationMode` `SecureConversation` [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad con el atributo establecido en.

4. Dentro del [ \<elemento > de seguridad](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un `authenticationMode` `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` [ \<elemento de > secureConversationBootstrap](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo establecido en o.

5. Después del [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) elemento de > de seguridad, cree un elemento de [ \<> sección sslstreamsecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) vacío.

6. Después del [ \<elemento > sección sslstreamsecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , cree un elemento [ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) vacío.

## <a name="code-sample"></a>Ejemplo de código

### <a name="sample-with-3-bindings"></a>Ejemplo con tres enlaces

1. Inserte el código siguiente en su archivo de configuración.

## <a name="example"></a>Ejemplo

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
