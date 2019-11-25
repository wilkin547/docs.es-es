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
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedimiento para crear un enlace federado dúplex

<xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta. Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado. Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP. El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.

También puede crear el enlace en el código. Para obtener una descripción de la pila de elementos de enlace que se va a crear, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Para crear un enlace personalizado federado dúplex con HTTP

1. En el nodo [\<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. Dentro del elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un elemento [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) con el atributo `name` establecido en `FederationDuplexHttpMessageSecurityBinding`.

3. Dentro del elemento de [> de enlace\<](../../configure-apps/file-schema/wcf/bindings.md) , cree un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con el atributo `authenticationMode` establecido en `SecureConversation`.

4. Dentro del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo `authenticationMode` establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.

5. Después del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento vacío [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) .

6. Después del elemento [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) , cree un elemento de [> oneWay\<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) en blanco.

7. Después del elemento [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) , cree un elemento vacío [\<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) .

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP

1. En el nodo [\<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. Dentro del elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un elemento [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) con el atributo `name` establecido en `FederationDuplexTcpMessageSecurityBinding`.

3. Dentro del elemento de [> de enlace\<](../../configure-apps/file-schema/wcf/bindings.md) , cree un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con el atributo `authenticationMode` establecido en `SecureConversation`.

4. Dentro del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo `authenticationMode` establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.

5. Después del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento vacío [\<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) .

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP

1. En el nodo [\<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) del archivo de configuración, cree un elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) .

2. Dentro del elemento [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , cree un elemento [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) con el atributo `name` establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.

3. Dentro del elemento de [> de enlace\<](../../configure-apps/file-schema/wcf/bindings.md) , cree un elemento [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) con el atributo `authenticationMode` establecido en `SecureConversation`.

4. Dentro del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) con el atributo `authenticationMode` establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated`.

5. Después del elemento [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) , cree un elemento vacío [\<sección sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) .

6. Después del elemento [\<sección sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) , cree un elemento vacío [\<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) .

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
