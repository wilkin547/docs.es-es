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
# <a name="how-to-create-a-duplex-federated-binding"></a>Procedimiento para crear un enlace federado dúplex

<xref:System.ServiceModel.WSFederationHttpBinding> solo admite los contratos de intercambio de mensajes de datagrama y solicitud/respuesta. Para utilizar el contrato de intercambio de mensajes dúplex, debe crear un enlace personalizado. Los procedimientos siguientes muestran cómo conseguirlo mediante configuración, utilizando la seguridad de modo de mensaje para los transportes TCP y HTTP, y la seguridad de modo mixto para el transporte TCP. El ejemplo de código donde se muestran los tres enlaces se encuentra al final de este tema.

También puede crear el enlace en el código. Para obtener una descripción de la pila de elementos de enlace que se va a crear, vea [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>Para crear un enlace personalizado federado dúplex con HTTP

1. En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.

2. Dentro del [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con el `name` atributo establecido en `FederationDuplexHttpMessageSecurityBinding` .

3. Dentro del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, cree un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation` .

4. Dentro del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .

5. Después del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento vacío.

6. Después del [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) elemento, cree un [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento vacío.

7. Después del [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) elemento, cree un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) elemento vacío.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>Para crear un enlace personalizado federado dúplex con el modo de seguridad de mensajes TCP

1. En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.

2. Dentro del [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con el `name` atributo establecido en `FederationDuplexTcpMessageSecurityBinding` .

3. Dentro del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, cree un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation` .

4. Dentro del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .

5. Después del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vacío.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>Para crear un enlace personalizado federado dúplex con el modo de seguridad mixto TCP

1. En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) nodo del archivo de configuración, cree un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento.

2. Dentro del [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) elemento, cree un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento con el `name` atributo establecido en `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .

3. Dentro del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento, cree un [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento con el `authenticationMode` atributo establecido en `SecureConversation` .

4. Dentro del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento con el `authenticationMode` atributo establecido en `IssuedTokenForCertificate` o `IssuedTokenForSslNegotiated` .

5. Después del [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) elemento, cree un [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento vacío.

6. Después del [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) elemento, cree un [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) elemento vacío.

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
