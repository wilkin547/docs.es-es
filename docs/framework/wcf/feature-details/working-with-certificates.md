---
title: "Trabajar con certificados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "certificados [WCF]"
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Trabajar con certificados
Para programar la seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], los certificados digitales de X.509 se utilizan normalmente para autenticar clientes y servidores, cifrar y firmar mensajes digitalmente.En este tema se explican brevemente las características de los certificados digitales de X.509 y cómo utilizarlos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e incluye vínculos a los temas que explican estos conceptos en mayor profundidad o que muestran cómo llevar a cabo tareas comunes mediante [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y los certificados.  
  
 En resumen, un certificado digital forma una parte de una *infraestructura de clave pública* \(PKI\), que es un sistema de certificados digitales, entidades de certificación y otras autoridades de registro que comprueban y autentican la validez de cada parte implicada en una transacción electrónica a través del uso de criptografía de claves públicas.Una entidad de certificación emite certificados y cada certificado tiene un conjunto de campos que contienen datos, como el *asunto* \(la entidad a la que se emite el certificado\), las fechas de validez \(cuándo es válido el certificado\), el emisor \(la entidad que emitió el certificado\) y una clave pública.En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], cada una de estas propiedades se procesa como clase <xref:System.IdentityModel.Claims.Claim> y cada notificación se divide en dos tipos: identidad y derecho.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los certificados X.509, vea [Certificados de clave pública X.509](http://go.microsoft.com/fwlink/?LinkId=209952)[!INCLUDE[crabout](../../../../includes/crabout-md.md)] las notificaciones y Autorización en WCF, vea [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo implementar una PKI, vea [Windows Server 2008 R2: servicios de servidor de certificados](http://go.microsoft.com/fwlink/?LinkId=209949).  
  
 Una función principal del certificado es la de autenticar la identidad del propietario del certificado ante los demás.Un certificado también contiene la *clave pública* del propietario, mientras que el propietario conserva la clave privada.La clave pública se puede usar para cifrar los mensajes enviados al propietario del certificado.Solo el propietario tiene acceso a la clave privada, por lo que únicamente él puede descifrar esos mensajes.  
  
 Los certificados los debe emitir una entidad de certificación, que suele ser un emisor de certificados de terceros.En un dominio de Windows, se incluye una entidad de certificación que se puede usar para emitir certificados a los equipos del dominio.  
  
## Visualización de certificados  
 Para trabajar con certificados, a menudo es necesario verlos y examinar sus propiedades.Esto se hace con facilidad con la herramienta de complemento Microsoft Management Console \(MMC\).[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## Almacenes de certificados  
 Los certificados se encuentran en almacenes.Existen dos ubicaciones de almacenamiento principales que se dividen en subalmacenes.Si es el administrador en un equipo, puede ver ambos almacenes principales utilizando la herramienta de complemento MMC.Los usuarios que no sean administradores solo pueden ver el almacén del usuario actual.  
  
-   **El almacén del equipo local**.Este contiene los certificados a los que los procesos del equipo obtiene acceso, como [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].Utilice esta ubicación para almacenar certificados que autentiquen el servidor a los clientes.  
  
-   **El almacén del usuario actual**.Las aplicaciones interactivas colocan aquí, por lo general, certificados para el usuario actual del equipo.Si está creando una aplicación cliente, es aquí donde normalmente colocará los certificados que autentiquen un usuario a un servicio.  
  
 Estos dos almacenes se dividen en subalmacenes.Entre los más importantes de éstos al programar con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se incluyen:  
  
-   **Entidades de certificación raíz de confianza**.Puede usar los certificados de este almacén para crear una cadena de certificados, de los que se puede hacer un seguimiento hasta un certificado de la entidad de certificación en este almacén.  
  
    > [!IMPORTANT]
    >  El equipo local confía implícitamente en cualquier certificado ubicado en este almacén, incluso cuando el certificado no proceda de una entidad de certificación de otro fabricante de confianza.Por esta razón, no coloque ningún certificado en este almacén a menos que confíe plenamente en el emisor y comprenda las consecuencias.  
  
-   **Personal**.Este almacén se utiliza para los certificados asociados a un usuario de un equipo.Normalmente este almacén se usa para los certificados emitidos por uno de los certificados de la entidad de certificación situado en el almacén Entidades emisoras de certificados raíz de confianza.O bien, una aplicación puede confiar en un certificado que se encuentre aquí y que sea de emisión propia.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] almacenes de certificados, vea [Almacenes de certificados](http://go.microsoft.com/fwlink/?LinkId=88912).  
  
### Selección de un almacén  
 Seleccionar dónde almacenar un certificado depende de cómo y cuándo se ejecute el cliente o el servicio.Se aplican las siguientes reglas generales:  
  
-   Si el servicio WCF se hospeda en un servicio Windows use el almacén de la **máquina local**.Observe que es necesario tener privilegios de administrador para instalar certificados en el almacén de la máquina local.  
  
-   Si el servicio o cliente es una aplicación que se ejecuta bajo una cuenta de usuario, utilice el almacén del **usuario actual**.  
  
### Obtención de acceso a almacenes  
 Los almacenes son protegidos por las listas de control de acceso \(ACL\), como las carpetas de un equipo.Al crear un servicio alojado por Internet Information Services \(IIS\), el proceso [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se ejecuta bajo la cuenta [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].Esa cuenta debe tener acceso al almacén que contiene los certificados que utiliza un servicio.Cada uno de los almacenes principales se encuentra protegido mediante una lista de acceso predeterminada, pero se pueden modificar las listas.Si crea un rol independiente para obtener acceso a un almacén, debe garantizar el permiso de acceso a ese rol.Para obtener información sobre cómo modificar la lista de acceso mediante la herramienta WinHttpCertConfig.exe, vea [Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo usar certificados de cliente con IIS, vea [Cómo llamar a un servicio web usando un certificado de cliente para la autenticación en una aplicación web ASP.NET](http://go.microsoft.com/fwlink/?LinkId=88914).  
  
## Confianza de cadena y entidades de certificación  
 Los certificados se crean en una jerarquía en la que cada certificado individual se vincula a la CA que emite el certificado.Este vínculo va al certificado de la CA.Después, el certificado de la CA se vincula a la CA que emitió el certificado original de la CA.Este proceso se repite hasta que se llegue al certificado de la CA raíz.Se confía intrínsecamente en el certificado de la CA raíz.  
  
 Los certificados digitales se utilizan para autenticar una entidad confiando en esta jerarquía, que también se denomina *cadena de confianza*.Puede ver la cadena de cualquier certificado utilizando el complemento MMC haciendo doble clic en cualquier certificado y, a continuación, haciendo clic en la pestaña **Ruta de certificado**.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo importar cadenas de certificados para una entidad de certificación, vea [Cómo: Especificar la cadena de certificados de la entidad de certificación utilizada para comprobar las firmas](../../../../docs/framework/wcf/feature-details/specify-the-certificate-authority-chain-verify-signatures-wcf.md).  
  
> [!NOTE]
>  A cualquier emisor se le puede designar una entidad emisora raíz de confianza colocando el certificado del emisor en el almacén de certificados de la entidad emisora raíz de confianza.  
  
### Deshabilitación de la confianza de cadena  
 Al crear un nuevo servicio, puede que esté utilizando un certificado que no ha emitido un certificado raíz de confianza, o puede que el propio certificado emisor no esté en el almacén Entidades de certificación raíz de confianza.Solo con fines de desarrollo, puede deshabilitar temporalmente el mecanismo que comprueba la cadena de confianza de un certificado.Para hacerlo, establezca la propiedad `CertificateValidationMode` en `PeerTrust` o `PeerOrChainTrust`.Ambos modos especifican que el certificado puede autoemitirse \(confianza de mismo nivel\) o formar parte de una cadena de confianza.Puede establecer la propiedad en cualquiera de las clases siguientes.  
  
|Clase|Propiedad|  
|-----------|---------------|  
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=fullName>|  
  
 También puede establecer la propiedad mediante configuración.Los siguientes elementos se utilizan para especificar el modo de validación:  
  
-   [\<autenticación\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)  
  
-   [\<peerAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)  
  
-   [\<messageSenderAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)  
  
## Autenticación personalizada  
 La propiedad `CertificateValidationMode` también le permite personalizar cómo se autentican los certificados.De manera predeterminada, el nivel se establece en `ChainTrust`.Para utilizar el valor <xref:System.ServiceModel.Security.X509CertificateValidationMode>, también debe establecer el atributo `CustomCertificateValidatorType` en un ensamblado y tipo utilizado para validar el certificado.Para crear un validador personalizado, debe heredar a partir de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator> abstracta.  
  
 Al crear un autenticador personalizado, el método más importante para invalidar es el método <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>.Para obtener un ejemplo de autenticación personalizada, vea el ejemplo [Validador de certificado X.509](../../../../docs/framework/wcf/samples/x-509-certificate-validator.md).[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Credencial personalizada y validación de la credencial](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md).  
  
## Uso de Makecert.exe para generar una cadena de certificados  
 La herramienta de creación de certificados \(Makecert.exe\) crea certificados X.509 y pares de claves privadas y públicas.Puede guardar la clave privada en el disco y, a continuación, usarla para emitir y firmar nuevos certificados, simulando así una jerarquía de certificados encadenados.La herramienta está diseñada para usarla únicamente como una ayuda al desarrollar servicios y nunca se debería utilizar para crear los certificados para la implementación real.Al desarrollar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], utilice los siguientes pasos para generar una cadena de confianza con Makecert.exe.  
  
#### Para generar una cadena de confianza con Makecert.exe  
  
1.  Cree un certificado temporal de la entidad emisora raíz \(autofirmado\) mediante la herramienta MakeCert.exe.Guarde la clave privada en el disco.  
  
2.  Utilice el nuevo certificado para emitir otro certificado que contenga la clave pública.  
  
3.  Importe el certificado de la entidad emisora raíz en el almacén Entidades emisoras de certificados raíz de confianza.  
  
4.  Si desea obtener instrucciones paso a paso, vea [Cómo: Crear certificados temporales que puedan utilizarse durante las operaciones de desarrollo](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).  
  
## ¿Qué certificado utilizar?  
 Las preguntas más comunes sobre certificados son qué certificados utilizar y por qué.La respuesta depende de si está programando un cliente o servicio.La siguiente información proporciona una directriz general y no es una respuesta exhaustiva a estas preguntas.  
  
### Certificados de servicio  
 Los certificados de servicio tienen la tarea principal de autenticar el servidor a los clientes.Una de las comprobaciones iniciales cuando un cliente autentica un servidor es comparar el valor del campo **Asunto** con el Identificador uniforme de recursos \(URI\) utilizado para ponerse en contacto con el servicio: el DNS de ambos debe coincidir.Por ejemplo, si el URI del servicio es "http:\/\/www.contoso.com\/endpoint\/", el campo **Asunto** también debe contener el valor "www.contoso.com".  
  
 Observe que el campo puede contener varios valores, cada uno prefijado con una inicialización que indique el valor.Muy comúnmente, la inicialización es "CN" para designar un nombre común, por ejemplo, "CN \= www.contoso.com".También es posible que el campo **Asunto** esté en blanco, en cuyo caso el campo **Nombre alternativo de sujeto** puede contener el valor **Nombre DNS**.  
  
 También tenga en cuenta el valor del campo **Propósitos planteados** del certificado debería incluir un valor adecuado, como "Autenticación del Servidor" o "Autenticación del cliente."  
  
### Certificados de cliente  
 Los certificados de cliente no son emitidos, por regla general, por una entidad de certificación de otro fabricante.En su lugar, el almacén Personal de la ubicación del usuario actual contiene normalmente certificados colocados ahí por una entidad emisora raíz, con un propósito planteado de "Autenticación de cliente."El cliente puede utilizar un certificado de este tipo cuando se requiera una autenticación mutua.  
  
## Revocación en línea y sin conexión  
  
### Validez del certificado  
 Cada certificado es válido solo durante un período determinado de tiempo, llamado el *período de validez*.Los campos **Válido desde** y **Válido hasta** de un certificado X.509 definen el período de validez.Durante la autenticación, el certificado se comprueba para determinar si el certificado todavía está dentro del período de validez.  
  
### Lista de revocación de certificados  
 En cualquier momento durante el período de validez, la entidad de certificación puede revocar un certificado.Esto puede producirse por muchas razones, como que la clave privada del certificado esté en peligro.  
  
 Cuando esto sucede, cualquier cadena que descienda del certificado revocado dejará también de ser válida y no se confiará en ella durante los procedimientos de autenticación.Para averiguar qué certificados se revocan, cada emisor publica una *lista de certificados revocados* \(CRL\) con marca de fecha y hora.La lista se puede comprobar utilizando revocación en línea o sin conexión estableciendo la propiedad `RevocationMode` o `DefaultRevocationMode` de las siguientes clases en uno de los valores de enumeración <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> : <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>, <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>, <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>, y las clases <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>.El valor predeterminado para todas las propiedades es `Online`.  
  
 También puede establecer el modo en la configuración mediante el atributo `revocationMode` del[\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)[\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)[\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)[\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)\) y el  \(de la \).  
  
## El método SetCertificate  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], debe especificar a menudo un certificado o conjunto de certificados que un servicio o cliente han de utilizar para autenticar, cifrar o firmar digitalmente un mensaje.Puede hacer esto mediante programación utilizando el método `SetCertificate` de varias clases que representan certificados X.509.Las siguientes clases utilizan el método `SetCertificate` para especificar un certificado.  
  
|Clase|Método|  
|-----------|------------|  
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|  
  
 El método `SetCertificate` funciona designando una ubicación del almacén y un almacén, un tipo de "búsqueda” \(parámetro`x509FindType`\) que especifica un campo del certificado y un valor que se debe encontrar en el campo.Por ejemplo, el siguiente código crea una instancia <xref:System.ServiceModel.ServiceHost> y establece el certificado de servicio utilizado para autenticar el servicio a clientes con el método `SetCertificate`  
  
 [!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
 [!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]  
  
### Varios certificados con el mismo valor  
 Un almacén puede contener varios certificados con el mismo nombre de asunto.Esto significa que si especifica que `x509FindType` es <xref:System.Security.Cryptography.X509Certificates.X509FindType> o <xref:System.Security.Cryptography.X509Certificates.X509FindType>, y hay más de un certificado con el mismo valor, se genera una excepción porque `no` `hay` manera de distinguir cuál es el certificado necesario.Puede mitigar esto estableciendo el `x509FindType` en <xref:System.Security.Cryptography.X509Certificates.X509FindType>.El campo de huella digital contiene un valor único que se puede utilizar para encontrar un certificado concreto en un almacén.Sin embargo, este tiene su propia desventaja: si el certificado se revoca o renueva, el método `SetCertificate` falla porque también se ha ido la huella digital.O, si el certificado ya no es válido, se produce un error de autenticación.Para mitigar esto se ha de establecer el parámetro `x590FindType` en <xref:System.Security.Cryptography.X509Certificates.X509FindType> y especificar el nombre del emisor.Si no se requiere ningún emisor determinado, también puede establecer uno de los otros valores de enumeración<xref:System.Security.Cryptography.X509Certificates.X509FindType>, como <xref:System.Security.Cryptography.X509Certificates.X509FindType>.  
  
## Certificados en configuración  
 También puede establecer certificados mediante configuración.Si está creando un servicio, las credenciales, incluidos los certificados, se especifican bajo la sección [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md).Si está programando un cliente, los certificados se especifican bajo [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).  
  
## Asignación de un certificado a una cuenta de usuario  
 Una característica de IIS y de Active Directory es la capacidad de asignar un certificado a una cuenta de usuario de Windows.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] la característica, vea [Asignar certificados a cuentas de usuario](http://go.microsoft.com/fwlink/?LinkId=88917).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] uso de la asignación de Active Directory, vea [Asignación de certificados de cliente mediante la asignación del servicio de directorio](http://go.microsoft.com/fwlink/?LinkId=88918).  
  
 Con esta capacidad habilitada, puede definir la propiedad <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A> de la clase <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> en `true`.En configuración, puede establecer el atributo `mapClientCertificateToWindowsAccount` del elemento [\<autenticación\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)`true en` , tal y como se muestra en el código siguiente.  
  
```  
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
  
 Asignar un certificado X.509 al token que representa una cuenta de usuario de Windows está considerado como un aumento de los privilegios, porque, una vez asignado, el token de Windows se puede utilizar para obtener acceso a recursos protegidos.Por consiguiente, la directiva de dominio requiere que el certificado X.509 cumpla con su directiva antes de realizar la asignación.El paquete de seguridad *SChannel*  hace cumplir este requisito.  
  
 Si se utiliza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o una versión posterior, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que el certificado es conforme con la directiva de dominio antes de asignarlo a una cuenta de Windows.  
  
 En la primera publicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], la asignación se realiza sin consultar la directiva de dominio.Por consiguiente, es posible que las aplicaciones anteriores que solían funcionar al ejecutarse bajo la primera publicación, provoquen un error si se habilita la asignación y el certificado X.509 no cumple la directiva de dominio.  
  
## Vea también  
 <xref:System.ServiceModel.Channels>   
 <xref:System.ServiceModel.Security>   
 <xref:System.ServiceModel>   
 <xref:System.Security.Cryptography.X509Certificates.X509FindType>   
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)