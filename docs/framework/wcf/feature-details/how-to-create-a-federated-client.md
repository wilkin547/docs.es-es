---
title: Procedimiento para crear un cliente federado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 56ece47e-98bf-4346-b92b-fda1fc3b4d9c
ms.openlocfilehash: 47e59452edfff74daf17d94a058ce8b12af7867c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593547"
---
# <a name="how-to-create-a-federated-client"></a>Procedimiento para crear un cliente federado
En Windows Communication Foundation (WCF), la creación de un cliente para un *servicio federado* consta de tres pasos principales:  
  
1. Configure un [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) o un enlace personalizado similar. Para obtener más información sobre cómo crear un enlace adecuado, vea [Cómo: crear un WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md). Como alternativa, ejecute la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con el punto de conexión de metadatos del servicio federado para generar un archivo de configuración para comunicarse con el servicio federado y uno o varios servicios de token de seguridad.  
  
2. Establezca las propiedades de la <xref:System.ServiceModel.Security.IssuedTokenClientCredential> que controla varios aspectos de la interacción de un cliente con un servicio de tokens de seguridad.  
  
3. Establezca las propiedades de la <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>, que permite que los certificados necesarios para comunicarse de manera segura con extremos determinados, como servicios de tokens de seguridad.  
  
> [!NOTE]
> Se podría iniciar una <xref:System.Security.Cryptography.CryptographicException> cuando un cliente utiliza credenciales suplantadas, el enlace <xref:System.ServiceModel.WSFederationHttpBinding> o un token emitido personalizado, y claves asimétricas. Las claves asimétricas se utilizan con el enlace <xref:System.ServiceModel.WSFederationHttpBinding> y tokens emitidos personalizados cuando las propiedades <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A> y <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A>, respectivamente, están establecidas en <xref:System.IdentityModel.Tokens.SecurityKeyType.AsymmetricKey>. Se inicia <xref:System.Security.Cryptography.CryptographicException> cuando el cliente intenta enviar un mensaje y no existe un perfil de usuario para la identidad que el cliente está suplantando. Para mitigar este problema, inicie sesión en el equipo cliente o llame a `LoadUserProfile` antes de enviar el mensaje.  
  
 Este tema proporciona información detallada sobre estos procedimientos. Para obtener más información sobre cómo crear un enlace adecuado, vea [Cómo: crear un WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md). Para obtener más información sobre cómo funciona un servicio federado, vea [Federación](federation.md).  
  
### <a name="to-generate-and-examine-the-configuration-for-a-federated-service"></a>Generar y examinar la configuración para un servicio federado  
  
1. Ejecute la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con la dirección URL de metadatos del servicio como un parámetro de línea de comandos.  
  
2. Abra el archivo de configuración generado en un editor adecuado.  
  
3. Examine los atributos y el contenido de los [\<issuer>](../../configure-apps/file-schema/wcf/issuer.md) elementos y generados [\<issuerMetadata>](../../configure-apps/file-schema/wcf/issuermetadata.md) . Se encuentran dentro de los [\<security>](../../configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) elementos de los [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) elementos de enlaces personalizados o. Asegúrese de que las direcciones contienen los nombres de dominio esperados u otra información de dirección. Es importante comprobar esta información porque el cliente se autentica en estas direcciones y podría revelar información como pares de nombre de usuario y contraseña. Si la dirección no es la dirección esperada, podría revelarse información en un destinatario incorrecto.  
  
4. Examine los [\<issuedTokenParameters>](../../configure-apps/file-schema/wcf/issuedtokenparameters.md) elementos adicionales incluidos en el elemento> de comentario <`alternativeIssuedTokenParameters` . Al utilizar la herramienta Svcutil.exe para generar la configuración de un servicio federado, si el servicio federado o cualquier servicio de tokens de seguridad intermedio no especifican una dirección de emisor, sino que especifican una dirección de metadatos para un servicio de tokens de seguridad que expone varios puntos de conexión, el archivo de configuración resultante hace referencia al primer punto de conexión. Los puntos de conexión adicionales se encuentran en el archivo de configuración como comentario <`alternativeIssuedTokenParameters`> elementos.  
  
     Determine si una de estas <`issuedTokenParameters`> es preferible a la que ya está presente en la configuración. Por ejemplo, el cliente podría preferir autenticarse en un servicio de token de seguridad mediante un token de Windows CardSpace en lugar de un par de nombre de usuario/contraseña.  
  
    > [!NOTE]
    > Un servicio de tokens de seguridad intermedio puede dirigir el cliente a un servicio de tokens de seguridad incorrecto si se deben atravesar varios servicios de tokens de seguridad antes de comunicarse con el servicio. Por lo tanto, asegúrese de que el extremo del servicio de token de seguridad en [\<issuedTokenParameters>](../../configure-apps/file-schema/wcf/issuedtokenparameters.md) es el servicio de token de seguridad esperado y no un servicio de token de seguridad desconocido.  
  
### <a name="to-configure-an-issuedtokenclientcredential-in-code"></a>Configuración de una IssuedTokenClientCredential mediante código  
  
1. Obtenga acceso a la <xref:System.ServiceModel.Security.IssuedTokenClientCredential> mediante la propiedad <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> de la clase <xref:System.ServiceModel.Description.ClientCredentials> (devuelta por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> de la clase <xref:System.ServiceModel.ClientBase%601>, o a través de la clase <xref:System.ServiceModel.ChannelFactory>), tal y como se muestra en el siguiente código de muestra.  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
2. Si no se requiere el almacenamiento en caché de tokens, establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A> en `false`. La propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A> controla si esos tokens de un servicio de tokens de seguridad están almacenados en memoria caché. Si esta propiedad está establecida en `false`, el cliente solicita un nuevo token del servicio de tokens de de seguridad cada vez que se tenga que volver a autenticar en el servicio federado, sin tener en cuenta si un token anterior aún es válido. Si esta propiedad está establecida en `true`, el cliente reutiliza un token existente cada vez que se debe volver a autenticar en el servicio federado (siempre que el token no se haya caducado). De manera predeterminada, es `true`.  
  
3. Si se requiere un límite horario en tokens almacenados en memoria caché, establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.MaxIssuedTokenCachingTime%2A> en un valor <xref:System.TimeSpan>. La propiedad especifica cuánto tiempo puede estar un token almacenado en memoria caché. Después de que el intervalo de tiempo especificado haya transcurrido, el token se quita de la caché del cliente. De forma predeterminada, los tokens se almacenan en memoria caché indefinidamente. El siguiente ejemplo establece el intervalo de tiempo en 10 minutos.  
  
     [!code-csharp[c_CreateSTS#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#15)]
     [!code-vb[c_CreateSTS#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#15)]  
  
4. Opcional. Establezca el <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> en un porcentaje. El valor predeterminado es 60 (por ciento). La propiedad especifica un porcentaje del período de validez del token. Por ejemplo, si el token emitido es válido durante 10 horas y <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> se establece en 80, el token se renovará después de ocho horas. El siguiente ejemplo establece el valor en 80 por ciento.  
  
     [!code-csharp[c_CreateSTS#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#16)]
     [!code-vb[c_CreateSTS#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#16)]  
  
     El intervalo de renovación determinado por el período de validez del token y el valor `IssuedTokenRenewalThresholdPercentage` es invalidado por el valor `MaxIssuedTokenCachingTime` en casos donde el tiempo de almacenamiento en caché es menor que el tiempo límite de renovación. Por ejemplo, si el producto de `IssuedTokenRenewalThresholdPercentage` y la duración del token es de ocho horas, y el valor de `MaxIssuedTokenCachingTime` es de 10 minutos, el cliente se pone en contacto con el servicio de tokens de seguridad de un token actualizado cada 10 minutos.  
  
5. Si es necesario un modo de entropía de clave distinto de <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy> en un enlace que no usa seguridad de mensaje o seguridad de transporte con credenciales de mensajes (por ejemplo, el enlace no tiene <xref:System.ServiceModel.Channels.SecurityBindingElement>), establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> en un valor apropiado. El modo de *entropía* determina si las claves simétricas se pueden controlar mediante la <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> propiedad. Este valor predeterminado es <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy>, donde el cliente y el emisor de tokens proporcionan datos que se combinan para generar la clave real. Otros valores son <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ClientEntropy> y <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ServerEntropy>, que quieren decir que el cliente o el servidor, respectivamente, especifican la clave al completo. El siguiente ejemplo establece la propiedad para utilizar solo los datos del servidor para la clave.  
  
     [!code-csharp[c_CreateSTS#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#17)]
     [!code-vb[c_CreateSTS#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#17)]  
  
    > [!NOTE]
    > Si se encuentra presente un <xref:System.ServiceModel.Channels.SecurityBindingElement> en un servicio de tokens de seguridad o enlace de servicio, el <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> establecido en <xref:System.ServiceModel.Security.IssuedTokenClientCredential> es invalidado por la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.KeyEntropyMode%2A> del `SecurityBindingElement`.  
  
6. Configure los comportamientos de punto de conexión específicos del emisor agregándolos a la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-issuedtokenclientcredential-in-configuration"></a>Configuración de la IssuedTokenClientCredential mediante configuración  
  
1. Cree un [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) elemento como elemento secundario del [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) elemento en un comportamiento del extremo.  
  
2. Si no se requiere el almacenamiento en caché de tokens, establezca el `cacheIssuedTokens` atributo (del `issuedToken` elemento <>) en `false` .  
  
3. Si se requiere un límite de tiempo en los tokens almacenados en caché, establezca el `maxIssuedTokenCachingTime` atributo del `issuedToken` elemento <> en un valor adecuado. Por ejemplo:  
    `<issuedToken maxIssuedTokenCachingTime='00:10:00' />`  
  
4. Si se prefiere un valor distinto del predeterminado, establezca el `issuedTokenRenewalThresholdPercentage` atributo del `issuedToken` elemento <> en un valor adecuado, por ejemplo:  
  
    ```xml  
    <issuedToken issuedTokenRenewalThresholdPercentage = "80" />  
    ```  
  
5. Si un modo de entropía de clave distinto de `CombinedEntropy` está en un enlace que no utiliza seguridad de mensaje o seguridad de transporte con credenciales de mensaje (por ejemplo, el enlace no tiene un `SecurityBindingElement`), establezca el atributo `defaultKeyEntropyMode` del elemento `<issuedToken>``ServerEntropy`, según se requiera.  
  
    ```xml  
    <issuedToken defaultKeyEntropyMode = "ServerEntropy" />  
    ```  
  
6. Opcional. Configure cualquier comportamiento de punto de conexión personalizado específico del emisor creando un <`issuerChannelBehaviors` elemento> como elemento secundario del `issuedToken` elemento <>. Para cada comportamiento, cree un `add` elemento <> como elemento secundario del elemento <`issuerChannelBehaviors`>. Especifique la dirección del emisor del comportamiento estableciendo el `issuerAddress` atributo en el `add` elemento <>. Especifique el comportamiento estableciendo el `behaviorConfiguration` atributo en el `add` elemento <>.  
  
    ```xml  
    <issuerChannelBehaviors>  
    <add issuerAddress="http://fabrikam.org/sts" behaviorConfiguration="FabrikamSTS" />  
    </issuerChannelBehaviors>  
    ```  
  
### <a name="to-configure-an-x509certificaterecipientclientcredential-in-code"></a>Configuración de una X509CertificateRecipientClientCredential mediante código  
  
1. Obtenga acceso a la <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> a través de la propiedad <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A> de la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> de la clase <xref:System.ServiceModel.ClientBase%601> o la propiedad <xref:System.ServiceModel.ChannelFactory>.  
  
     [!code-csharp[c_CreateSTS#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#18)]
     [!code-vb[c_CreateSTS#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#18)]  
  
2. Si una instancia de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> está disponible para el certificado de un punto de conexión determinado, utilice el método <xref:System.Collections.Generic.ICollection%601.Add%2A> de la colección devuelto por la propiedad <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>.  
  
     [!code-csharp[c_CreateSTS#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#19)]
     [!code-vb[c_CreateSTS#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#19)]  
  
3. Si una instancia <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> no está disponible, utilice el método <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential> como se muestra en el ejemplo siguiente.  
  
     [!code-csharp[c_CreateSTS#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#20)]
     [!code-vb[c_CreateSTS#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#20)]  
  
### <a name="to-configure-an-x509certificaterecipientclientcredential-in-configuration"></a>Configuración de una X509CertificateRecipientClientCredential mediante configuración  
  
1. Cree un [\<scopedCertificates>](../../configure-apps/file-schema/wcf/scopedcertificates-element.md) elemento como elemento secundario del [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) elemento que es en sí mismo un elemento secundario del [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) elemento en un comportamiento del extremo.  
  
2. Cree un elemento `<add>` como elemento secundario del elemento `<scopedCertificates>`. Especifique valores para los atributos `storeLocation`, `storeName`, `x509FindType`y `findValue` para hacer referencia al certificado adecuado. Establezca el atributo `targetUri` en un valor que proporcione la dirección del extremo para la que se ha de utilizar el certificado, tal y como se muestra en el siguiente ejemplo.  
  
    ```xml  
    <scopedCertificates>  
     <add targetUri="http://fabrikam.com/sts"
          storeLocation="CurrentUser"  
          storeName="TrustedPeople"  
          x509FindType="FindBySubjectName"  
          findValue="FabrikamSTS" />  
    </scopedCertificates>  
    ```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código configura una instancia de la clase <xref:System.ServiceModel.Security.IssuedTokenClientCredential> mediante código.  
  
 [!code-csharp[c_FederatedClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedclient/cs/source.cs#2)]
 [!code-vb[c_FederatedClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedclient/vb/source.vb#2)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para evitar la posible divulgación de la información, los clientes que están ejecutando la herramienta Svcutil.exe para procesar los metadatos desde puntos de conexión federados deberían asegurarse de que las direcciones del servicio de tokens de seguridad resultantes son las esperadas. Esto es especialmente importante cuando un servicio de tokens de seguridad expone varios puntos de conexión, porque la herramienta Svcutil.exe genera el archivo de configuración resultante para utilizar el primero de esos puntos de conexión, que no puede ser el que el cliente debería estar utilizando.  
  
## <a name="localissuer-required"></a>LocalIssuer requerido  
 Si se espera que los clientes utilicen siempre un emisor local, tenga en cuenta lo siguiente: la salida predeterminada de Svcutil.exe hace que no se utilice el emisor local si el servicio de tokens de seguridad de segundo a último en la cadena especifica una dirección de emisor o una dirección de metadatos de emisor.  
  
 Para obtener más información sobre cómo establecer las <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> propiedades, y <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> de la <xref:System.ServiceModel.Security.IssuedTokenClientCredential> clase, consulte [How to: Configure a local issuer](how-to-configure-a-local-issuer.md).  
  
## <a name="scoped-certificates"></a>Certificados con ámbito  
 Si los certificados del servicio se deben especificar para comunicarse con cualquiera de los servicios de tokens de seguridad, normalmente debido a que no se utiliza la negociación de certificados, se pueden especificar mediante la propiedad <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A> de la clase <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>. El método <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetDefaultCertificate%2A> toma un <xref:System.Uri> y un <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> como parámetros. Se utiliza el certificado especificado al comunicarse con puntos de conexión en el URI especificado. De manera alternativa, puede utilizar el método <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A> para agregar un certificado a la colección devuelta por la propiedad <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>.  
  
> [!NOTE]
> La idea del cliente con respecto a los certificados que tienen su ámbito restringido a un URI determinado solo se aplica en aplicaciones que están realizando llamadas salientes a servicios que exponen los extremos en esos URI. No se aplica a los certificados que se usan para firmar los tokens emitidos, como los configurados en el servidor en la colección devuelta por la <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> clase de la <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> clase. Para obtener más información, consulte [Cómo: configurar credenciales en un servicio de Federación](how-to-configure-credentials-on-a-federation-service.md).  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de federación](../samples/federation-sample.md)
- [Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Procedimiento para crear un WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)
- [Procedimiento para configurar las credenciales en un servicio de federación](how-to-configure-credentials-on-a-federation-service.md)
- [Procedimiento para configurar un emisor local](how-to-configure-a-local-issuer.md)
- [Consideraciones de seguridad con metadatos](security-considerations-with-metadata.md)
- [Procedimiento para proteger puntos de conexión de metadatos](how-to-secure-metadata-endpoints.md)
