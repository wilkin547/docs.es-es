---
title: Procedimiento para establecer el modo de seguridad
description: 'Obtenga información sobre cómo establecer los tres modos de seguridad de WCF comunes en la mayoría de los enlaces predefinidos: Transport, Message y TransportWithMessageCredential.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 2f834e1930b7676592f6cbc29a577424d75ebc01
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244548"
---
# <a name="how-to-set-the-security-mode"></a>Procedimiento para establecer el modo de seguridad

La seguridad de Windows Communication Foundation (WCF) tiene tres modos de seguridad comunes que se encuentran en la mayoría de los enlaces predefinidos: transporte, mensaje y "transporte con credenciales de mensaje". Dos modos adicionales son específicos para dos enlaces: el modo “solo credencial de transporte” encontrado en el <xref:System.ServiceModel.BasicHttpBinding>y el modo “Ambos” encontrado en el <xref:System.ServiceModel.NetMsmqBinding>. Sin embargo, este tema se concentra en los tres modos de seguridad comunes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>y <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.

Tenga en cuenta que no todos los enlaces predefinidos admiten todos estos modos. Este tema establece el modo con las clases <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.NetTcpBinding> y muestra cómo establecer el modo mediante programación y configuración.

Para obtener más información, vea seguridad de WCF, vea [información general sobre seguridad](./feature-details/security-overview.md), [proteger servicios](securing-services.md)y [proteger servicios y clientes](./feature-details/securing-services-and-clients.md). Para obtener más información sobre el modo de transporte y el mensaje, vea [seguridad de transporte](./feature-details/transport-security.md) y [seguridad de mensajes](./feature-details/message-security-in-wcf.md).

## <a name="to-set-the-security-mode-in-code"></a>Para establecer el modo de seguridad en código

1. Cree una instancia de la clase del enlace que está utilizando. Para obtener una lista de enlaces predefinidos, vea [enlaces proporcionados por el sistema](system-provided-bindings.md). En el siguiente ejemplo se crea una instancia de la clase <xref:System.ServiceModel.WSHttpBinding>.

2. Establezca la propiedad `Mode` del objeto devuelto por la propiedad `Security`.

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     De manera alternativa, establezca el modo en mensaje, como se muestra en el código siguiente.

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     O establezca el modo en transporte con credenciales de mensaje, como se muestra en el código siguiente.

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. También puede establecer el modo en el constructor del enlace, como se muestra en el código siguiente.

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a>Establecimiento de la propiedad la propiedad ClientCredentialType 

El establecimiento del modo en uno de los tres valores determina cómo establece la propiedad `ClientCredentialType`. Por ejemplo, el uso de la clase <xref:System.ServiceModel.WSHttpBinding>, estableciendo el modo en `Transport` implica que debe establecer la propiedad <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> de la clase <xref:System.ServiceModel.HttpTransportSecurity> en un valor adecuado.

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a>Para establecer la propiedad ClientCredentialType para el modo de transporte

1. Cree una instancia del enlace.

2. Establezca la propiedad `Mode` en `Transport`.

3. Establezca la propiedad `ClientCredential` en un valor apropiado. El siguiente código establece la propiedad en `Windows`:

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a>Para establecer la propiedad ClientCredentialType para el modo de mensaje

1. Cree una instancia del enlace.

2. Establezca la propiedad `Mode` en `Message`.

3. Establezca la propiedad `ClientCredential` en un valor apropiado. El siguiente código establece la propiedad en `Certificate`:

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a>Para establecer el Modo y la propiedad ClientCredentialType en configuración

1. Agregue un elemento de enlace adecuado al [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) elemento del archivo de configuración. En el siguiente ejemplo se agrega un [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elemento.

2. Agregue un `<binding>` elemento y establezca su `name` atributo en un valor adecuado.

3. Agregue un `<security>` elemento y establezca el `mode` atributo en `Message` , `Transport` o `TransportWithMessageCredential` .

4. Si se establece el modo en `Transport`, agregue un elemento `<transport>` en un valor apropiado.

     El siguiente ejemplo establece el modo en “`Transport"`, y, a continuación, establece el atributo `clientCredentialType` del `<transport>`.

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     De manera alternativa, establezca el `security mode` en "`Message"`, seguido por un elemento `<"message">`. Este ejemplo establece el `clientCredentialType` en "`Certificate"`.

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     Utilizar el valor <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> es un caso especial y se explica más adelante.

### <a name="using-transportwithmessagecredential"></a>Uso de TransportWithMessageCredential

Al establecer el modo de seguridad en `TransportWithMessageCredential`, el transporte determina el mecanismo real que proporciona la seguridad de nivel de transporte. Por ejemplo, el protocolo HTTP utiliza Secure Sockets Layer (SSL) sobre HTTP (HTTPS). Por consiguiente, se omite el establecimiento de la propiedad `ClientCredentialType` de cualquier objeto de seguridad de transporte (como <xref:System.ServiceModel.HttpTransportSecurity>).  En otras palabras, solo puede establecer el `ClientCredentialType` del objeto de seguridad del mensaje (para el enlace `WSHttpBinding`, el objeto <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).

Para obtener más información, consulte [Cómo: usar la seguridad de transporte y las credenciales de mensaje](./feature-details/how-to-use-transport-security-and-message-credentials.md).

## <a name="see-also"></a>Vea también

- [Procedimiento para configurar un puerto con un certificado SSL](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [Procedimiento para usar seguridad de transporte y credenciales de mensajes](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [Seguridad de transporte](./feature-details/transport-security.md)
- [Seguridad de los mensajes](./feature-details/message-security-in-wcf.md)
- [Información general sobre seguridad](./feature-details/security-overview.md)
- [Enlaces proporcionados por el sistema](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
