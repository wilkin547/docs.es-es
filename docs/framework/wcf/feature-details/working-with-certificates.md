---
title: Trabajar con certificados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF]
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
ms.openlocfilehash: e38ead0d378092af086218277fd2e85b4a6396c3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746887"
---
# <a name="working-with-certificates"></a>Trabajar con certificados

Para programar la seguridad de Windows Communication Foundation (WCF), los certificados digitales de X.509 se usan normalmente para autenticar clientes y servidores, cifrar y firmar mensajes digitalmente. En este tema se explican brevemente las características de los certificados digitales X.509 y cómo usarlos en WCF, y se incluyen vínculos a los temas en los que se explican estos conceptos en mayor profundidad o en los que se muestra cómo llevar a cabo tareas comunes mediante WCF y los certificados.

En resumen, un certificado digital forma una parte de una *infraestructura de clave pública* (PKI), que es un sistema de certificados digitales, entidades de certificación y otras autoridades de registro que comprueban y autentican la validez de cada parte implicada en una transacción electrónica a través del uso de criptografía de claves públicas. Una entidad de certificación emite certificados y cada certificado tiene un conjunto de campos que contienen datos, como el *asunto* (la entidad a la que se emite el certificado), las fechas de validez (cuándo es válido el certificado), el emisor (la entidad que emitió el certificado) y una clave pública. En WCF, cada una de estas propiedades se procesa como una <xref:System.IdentityModel.Claims.Claim>, y cada notificación se divide en dos tipos: identidad y derecho. Para obtener más información sobre los certificados X.509, vea [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates) (Certificados X.509 de clave pública). Para obtener más información sobre las notificaciones y la autorización en WCF, vea [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md). Para obtener más información acerca de la implementación de una PKI, consulte [PKI de empresa con Windows Server 2012 R2 Active Directory servicios de servidor de certificados](https://docs.microsoft.com/archive/blogs/yungchou/enterprise-pki-with-windows-server-2012-r2-active-directory-certificate-services-part-1-of-2).

La función principal de un certificado es la de autenticar la identidad del propietario del certificado ante los demás. Un certificado contiene la *clave pública* del propietario, mientras que el propietario conserva la clave privada. La clave pública se puede usar para cifrar los mensajes enviados al propietario del certificado. Solo el propietario tiene acceso a la clave privada, por lo que únicamente él puede descifrar esos mensajes.

Los certificados los debe emitir una entidad de certificación, que suele ser un emisor de certificados de terceros. En un dominio de Windows, se incluye una entidad de certificación que se puede usar para emitir los certificados a los equipos del dominio.

## <a name="viewing-certificates"></a>Visualización de certificados

Para trabajar con certificados, a menudo es necesario verlos y examinar sus propiedades. Esto se hace con facilidad con la herramienta de complemento Microsoft Management Console (MMC). Para más información, consulte [Visualización de certificados con el complemento MMC](how-to-view-certificates-with-the-mmc-snap-in.md).

## <a name="certificate-stores"></a>Almacenes de certificados

Los certificados se encuentran en almacenes. Existen dos ubicaciones de almacenamiento principales que se dividen en subalmacenes. Si es el administrador en un equipo, puede ver ambos almacenes principales utilizando la herramienta de complemento MMC. Los usuarios que no sean administradores solo pueden ver el almacén del usuario actual.

- **El almacén del equipo local**. Contiene los certificados a los que tienen acceso los procesos de la máquina, como ASP.NET. Utilice esta ubicación para almacenar certificados que autentiquen el servidor a los clientes.

- **El almacén del usuario actual**. Las aplicaciones interactivas colocan aquí, por lo general, certificados para el usuario actual del equipo. Si está creando una aplicación cliente, es aquí donde normalmente colocará los certificados que autentiquen un usuario a un servicio.

Estos dos almacenes se dividen en subalmacenes. Entre los más importantes de estos cuando se programa con WCF se incluyen:

- **Entidades de certificación raíz de confianza**. Puede usar los certificados en este almacén para crear una cadena de certificados, que se pueden trazar hacia atrás hasta un certificado de la entidad de certificación en este almacén.

  > [!IMPORTANT]
  > El equipo local confía implícitamente en cualquier certificado ubicado en este almacén, aún cuando el certificado no proceda de una entidad de certificación de otro fabricante de confianza. Por esta razón, no coloque ningún certificado en este almacén a menos que confíe plenamente en el emisor y comprenda las consecuencias.

- **Personal**. Este almacén se utiliza para los certificados asociados a un usuario de un equipo. Normalmente este almacén se usa para los certificados emitidos por uno de los certificados de la entidad de certificación situado en el almacén de las Entidades emisoras de certificados raíz de confianza. O bien, una aplicación puede confiar en un certificado que se encuentre aquí y que sea de emisión propia.

Para obtener más información sobre los almacenes de certificados, vea [Almacenes de certificados](/windows/desktop/secauthn/certificate-stores).

### <a name="selecting-a-store"></a>Selección de un almacén

Seleccionar dónde almacenar un certificado depende de cómo y cuándo se ejecute el cliente o el servicio. Se aplican las siguientes reglas generales:

- Si el servicio WCF se hospeda en un servicio Windows, use el almacén del **equipo local**. Observe que es necesario tener privilegios de administrador para instalar certificados en el almacén de la máquina local.

- Si el servicio o cliente es una aplicación que se ejecuta bajo una cuenta de usuario, use el almacén del **usuario actual**.

### <a name="accessing-stores"></a>Obtención de acceso a almacenes

Los almacenes son protegidos por las listas de control de acceso (ACL), como las carpetas de un equipo. Al crear un servicio hospedado por Internet Information Services (IIS), el proceso ASP.NET se ejecuta en la cuenta ASP.NET. Esa cuenta debe tener acceso al almacén que contiene los certificados que utiliza un servicio. Cada uno de los almacenes principales se encuentra protegido mediante una lista de acceso predeterminada, pero se pueden modificar las listas. Si crea un rol independiente para obtener acceso a un almacén, debe garantizar el permiso de acceso a ese rol. Para obtener información sobre cómo modificar la lista de acceso con la herramienta WinHttpCertConfig.exe, vea [Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo](how-to-create-temporary-certificates-for-use-during-development.md).

## <a name="chain-trust-and-certificate-authorities"></a>Confianza de cadena y entidades de certificación

Los certificados se crean en una jerarquía en la que cada certificado individual se vincula a la CA que emite el certificado. Este vínculo va al certificado de la CA. A continuación, el certificado de la CA se vincula a la CA que emitió el certificado de la CA original. Este proceso se repite hasta que se llegue al certificado de la CA raíz. Se confía intrínsecamente en el certificado de la CA raíz.

Los certificados digitales se usan para autenticar una entidad confiando en esta jerarquía, que también se denomina *cadena de confianza*. Para ver la cadena de cualquier certificado mediante el complemento MMC, haga doble clic en cualquier certificado y, a continuación, haga clic en la pestaña **ruta de acceso del certificado** . Para obtener más información acerca de la importación de cadenas de certificados para una entidad de certificación, consulte [Cómo: especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas](specify-the-certificate-authority-chain-verify-signatures-wcf.md).

> [!NOTE]
> A cualquier emisor se le puede designar una entidad emisora raíz de confianza colocando el certificado del emisor en el almacén de certificados de la entidad emisora raíz de confianza.

### <a name="disabling-chain-trust"></a>Deshabilitación de la confianza de cadena

Al crear un nuevo servicio, puede que esté utilizando un certificado que no ha emitido un certificado raíz de confianza, o puede que el propio certificado emisor no esté en el almacén Entidades de certificación raíz de confianza. Solo con fines de desarrollo, puede deshabilitar temporalmente el mecanismo que comprueba la cadena de confianza de un certificado. Para hacerlo, establezca la propiedad `CertificateValidationMode` en `PeerTrust` o `PeerOrChainTrust`. Ambos modos especifican que el certificado puede autoemitirse (confianza de mismo nivel) o formar parte de una cadena de confianza. Puede establecer la propiedad en cualquiera de las clases siguientes.

|Clase|Propiedad|
|-----------|--------------|
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=nameWithType>|

También puede establecer la propiedad mediante configuración. Los siguientes elementos se utilizan para especificar el modo de validación:

- [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)

- [\<peerAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)

- [\<messageSenderAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)

## <a name="custom-authentication"></a>Autenticación personalizada

La propiedad `CertificateValidationMode` también le permite personalizar cómo se autentican los certificados. De manera predeterminada, el nivel se establece en `ChainTrust`. Para utilizar el valor <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>, también debe establecer el atributo `CustomCertificateValidatorType` en un ensamblado y tipo utilizado para validar el certificado. Para crear un validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta.

Al crear un autenticador personalizado, el método más importante para invalidar es el método <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>. Para obtener un ejemplo de autenticación personalizada, vea el ejemplo [Validador de certificado X.509](../../../../docs/framework/wcf/samples/x-509-certificate-validator.md). Para obtener más información, vea [Credencial personalizada y validación de la credencial](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md).

## <a name="using-the-powershell-new-selfsignedcertificate-cmdlet-to-build-a-certificate-chain"></a>Uso del cmdlet New-SelfSignedCertificate de PowerShell para crear una cadena de certificados

El cmdlet New-SelfSignedCertificate de PowerShell crea certificados X. 509 y pares de clave privada y clave pública. Puede guardar la clave privada en el disco y, a continuación, usarla para emitir y firmar nuevos certificados, simulando así una jerarquía de certificados encadenados. El cmdlet está diseñado para usarse solo como ayuda al desarrollar servicios y nunca se debe usar para crear certificados para la implementación real. Al desarrollar un servicio WCF, use los pasos siguientes para crear una cadena de confianza con el cmdlet New-SelfSignedCertificate.

#### <a name="to-build-a-chain-of-trust-with-the-new-selfsignedcertificate-cmdlet"></a>Para compilar una cadena de confianza con el cmdlet New-SelfSignedCertificate

1. Cree un certificado de entidad de certificación raíz (autofirmado) temporal con el cmdlet New-SelfSignedCertificate. Guarde la clave privada en el disco.

2. Utilice el nuevo certificado para emitir otro certificado que contenga la clave pública.

3. Importe el certificado de la entidad emisora raíz en el almacén Entidades emisoras de certificados raíz de confianza.

4. Para obtener instrucciones paso a paso, vea [Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo](how-to-create-temporary-certificates-for-use-during-development.md).

## <a name="which-certificate-to-use"></a>¿Qué certificado utilizar?

Las preguntas más comunes sobre certificados son qué certificados utilizar y por qué. La respuesta depende de si está programando un cliente o servicio. La siguiente información proporciona una directriz general y no es una respuesta exhaustiva a estas preguntas.

### <a name="service-certificates"></a>Certificados de servicio

Los certificados de servicio tienen la tarea principal de autenticar el servidor a los clientes. Una de las comprobaciones iniciales cuando un cliente autentica un servidor es comparar el valor del campo **Asunto** con el Identificador uniforme de recursos (URI) que se usa para ponerse en contacto con el servicio: el DNS de ambos debe coincidir. Por ejemplo, si el URI del servicio se `http://www.contoso.com/endpoint/`, el campo **asunto** también debe contener el valor `www.contoso.com`.

Observe que el campo puede contener varios valores, cada uno prefijado con una inicialización que indique el valor. Normalmente, la inicialización es "CN" para el nombre común, por ejemplo, `CN = www.contoso.com`. También es posible que el campo **Asunto** esté en blanco, en cuyo caso el campo **Nombre alternativo del firmante** puede contener el valor **Nombre DNS**.

También tenga en cuenta que el valor del campo **Propósitos planteados** del certificado debería incluir un valor adecuado, como "Autenticación del Servidor" o "Autenticación del cliente".

### <a name="client-certificates"></a>Certificados de cliente

Los certificados de cliente no son emitidos, por regla general, por una autoridad de certificación de otro fabricante. En su lugar, el almacén Personal de la ubicación del usuario actual contiene normalmente certificados colocados ahí por una entidad emisora raíz, con un propósito planteado de "Autenticación de cliente." El cliente puede usar este tipo de certificado cuando se requiere autenticación mutua.

## <a name="online-revocation-and-offline-revocation"></a>Revocación en línea y sin conexión

### <a name="certificate-validity"></a>Validez del certificado

Cada certificado es válido solo durante un período determinado de tiempo, llamado *período de validez*. Los campos **Válido desde** y **Válido hasta** de un certificado X.509 definen el período de validez. Durante la autenticación, el certificado se comprueba para determinar si el certificado todavía está dentro del período de validez.

### <a name="certificate-revocation-list"></a>Lista de revocación de certificados

En cualquier momento, durante el período de validez, la entidad de certificación puede revocar un certificado. Esto puede producirse por muchas razones, como que la clave privada del certificado esté en peligro.

Cuando esto sucede, cualquier cadena que descienda del certificado revocado dejará también de ser válida y no se confiará en ella durante los procedimientos de autenticación. Para averiguar qué certificados se revocan, cada emisor publica una *lista de certificados revocados* (CRL) con marca de fecha y hora. La lista se puede comprobar utilizando revocación en línea o sin conexión estableciendo la propiedad `RevocationMode` o `DefaultRevocationMode` de las siguientes clases en uno de los valores de enumeración <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> : <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>, <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>, <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>, y las clases <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>. El valor predeterminado para todas las propiedades es `Online`.

También se puede establecer el modo de configuración con el atributo `revocationMode` de [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (de [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)) y [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (de [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)).

## <a name="the-setcertificate-method"></a>El método SetCertificate

En WCF, a menudo se debe especificar un certificado o conjunto de certificados que un servicio o cliente va a usar para autenticar, cifrar o firmar digitalmente un mensaje. Puede hacer esto mediante programación utilizando el método `SetCertificate` de varias clases que representan certificados X.509. Las siguientes clases utilizan el método `SetCertificate` para especificar un certificado.

|Clase|Método|
|-----------|------------|
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|

El método `SetCertificate` funciona designando una ubicación del almacén y almacén, un tipo de "búsqueda” (parámetro`x509FindType`) que especifica un campo del certificado, y un valor para encontrar en el campo. Por ejemplo, en el código siguiente se crea una instancia de <xref:System.ServiceModel.ServiceHost> y se establece el certificado de servicio que se usa para autenticar el servicio a los clientes con el método `SetCertificate`.

[!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
[!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]

### <a name="multiple-certificates-with-the-same-value"></a>Varios certificados con el mismo valor

Un almacén puede contener varios certificados con el mismo nombre de asunto. Esto significa que si se especifica que `x509FindType` es <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> o <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectDistinguishedName>, y hay más de un certificado con el mismo valor, se inicia una excepción porque no hay manera de distinguir cuál es el certificado necesario. Puede mitigar esto estableciendo el `x509FindType` en <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>. El campo de huella digital contiene un valor único que se puede utilizar para encontrar un certificado concreto en un almacén. Sin embargo, este tiene su propia desventaja: si el certificado se revoca o renueva, el método `SetCertificate` falla porque también se ha ido la huella digital. O, si el certificado ya no es válido, se produce un error de autenticación. Para mitigar esto se ha de establecer el parámetro `x590FindType` en <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByIssuerName> y especificar el nombre del emisor. Si no se requiere ningún emisor determinado, también puede establecer uno de los otros valores de enumeración<xref:System.Security.Cryptography.X509Certificates.X509FindType>, como <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByTimeValid>.

## <a name="certificates-in-configuration"></a>Certificados en configuración

También puede establecer certificados mediante configuración. Si va a crear un servicio, las credenciales, incluidos los certificados, se especifican bajo [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md). Si se está programando un cliente, los certificados se especifican bajo [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).

## <a name="mapping-a-certificate-to-a-user-account"></a>Asignación de un certificado a una cuenta de usuario

Una característica de IIS y de Active Directory es la capacidad de asignar un certificado a una cuenta de usuario de Windows. Para obtener más información sobre la característica, vea [Map certificates to user accounts](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc736706(v=ws.10)) (Asignar certificados a cuentas de usuario).

Para obtener más información sobre el uso de la asignación de Active Directory, vea [Mapping Client Certificates with Directory Service Mapping](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc758484(v=ws.10)) (Asignación de certificados de cliente mediante la asignación del servicio de directorio).

Con esta capacidad habilitada, puede definir la propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A> de la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> en `true`. En la configuración, se puede establecer el atributo `mapClientCertificateToWindowsAccount` del elemento [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) en `true`, como se muestra en el código siguiente.

```xml
<serviceBehaviors>
 <behavior name="MappingBehavior">
  <serviceCredentials>
   <clientCertificate>
    <authentication certificateValidationMode="None" mapClientCertificateToWindowsAccount="true" />
   </clientCertificate>
  </serviceCredentials>
 </behavior>
</serviceBehaviors>
```

Asignar un certificado X.509 al token que representa una cuenta de usuario de Windows está considerado como un aumento de los privilegios, porque, una vez asignado, el token de Windows se puede utilizar para obtener acceso a recursos protegidos. Por consiguiente, la directiva de dominio requiere que el certificado X.509 cumpla con su directiva antes de realizar la asignación. El paquete de seguridad *SChannel* hace cumplir este requisito.

Cuando se usa .NET Framework 3,5 o versiones posteriores, WCF garantiza que el certificado se ajusta a la Directiva de dominio antes de que se asigne a una cuenta de Windows.

En la primera versión de WCF, la asignación se realiza sin consultar la directiva de dominio. Por consiguiente, es posible que las aplicaciones anteriores que solían funcionar al ejecutarse bajo la primera publicación, provoquen un error si se habilita la asignación y el certificado X.509 no cumple la directiva de dominio.

## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Security>
- <xref:System.ServiceModel>
- <xref:System.Security.Cryptography.X509Certificates.X509FindType>
- [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
