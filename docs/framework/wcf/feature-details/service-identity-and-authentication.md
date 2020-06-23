---
title: Identidad del servicio y autenticación
description: Obtenga información sobre la identidad del punto de conexión de un servicio, un valor generado a partir del WSDL del servicio, que WCF usa para autenticar el servicio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [WCF], specifying the identity of a service
ms.assetid: a4c8f52c-5b30-45c4-a545-63244aba82be
ms.openlocfilehash: ae217b4a2c3432321c7ef2e663922a87b82acbea
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246576"
---
# <a name="service-identity-and-authentication"></a>Identidad del servicio y autenticación
La identidad del *extremo* de un servicio es un valor generado a partir del lenguaje de descripción de servicios web (WSDL) del servicio. Este valor, propagado a cualquier cliente, se utiliza para autenticar el servicio. Después de que el cliente inicie una comunicación con un punto de conexión y el servicio se autentique a sí mismo ante el cliente, el cliente compara el valor de identidad del punto de conexión con el valor real devuelto por el proceso de autenticación del punto de conexión. Si coinciden, se asegura al cliente que se ha puesto en contacto con el punto de conexión de servicio esperado. Esto funciona como una protección contra la *suplantación de identidad (phishing)* al impedir que un cliente se redirija a un punto de conexión hospedado por un servicio malintencionado.  
  
 Para obtener una aplicación de ejemplo que muestra la configuración de identidad, vea [ejemplo de identidad de servicio](../samples/service-identity-sample.md). Para obtener más información sobre los extremos y las direcciones de punto de conexión, vea [Addresses](endpoint-addresses.md).  
  
> [!NOTE]
> Al utilizar NT LanMan (NTLM) para la autenticación, no se comprueba la identidad del servicio porque, bajo NTLM, el cliente no puede autenticar el servidor. Se utiliza NTLM cuando los equipos forman parte de un grupo de trabajo de Windows, o al ejecutar una versión anterior de Windows que no admite la autenticación Kerberos.  
  
 Cuando el cliente inicia un canal seguro para enviar un mensaje a un servicio sobre él, la infraestructura de Windows Communication Foundation (WCF) autentica el servicio y solo envía el mensaje si la identidad del servicio coincide con la identidad especificada en la dirección del extremo que usa el cliente.  
  
 El procesamiento de la identidad consta de las siguientes fases:  
  
- En la fase de diseño, el programador del cliente determina la identidad del servicio desde los metadatos del punto de conexión (se expone a través de WSDL).  
  
- En el tiempo de ejecución, la aplicación de cliente comprueba las notificaciones de las credenciales de seguridad del servicio antes de enviar ningún mensaje al servicio.  
  
 El procesamiento de identidad en el cliente es análogo a la autenticación del cliente en el servicio. Un servicio seguro no ejecuta código hasta que se hayan autenticado las credenciales del cliente. Del mismo modo, el cliente no envía mensajes al servicio hasta que las credenciales del servicio se hayan autenticado en función de lo que se conoce de antemano de los metadatos del servicio.  
  
 La propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A> de la clase <xref:System.ServiceModel.EndpointAddress> representa la identidad del servicio llamada por el cliente. El servicio publica la <xref:System.ServiceModel.EndpointAddress.Identity%2A> en sus metadatos. Cuando el desarrollador del cliente ejecuta la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con el punto de conexión de servicio, la configuración generada contiene el valor de la propiedad del servicio <xref:System.ServiceModel.EndpointAddress.Identity%2A> . La infraestructura de WCF (si se configura con seguridad) comprueba que el servicio posee la identidad especificada.  
  
> [!IMPORTANT]
> Los metadatos contienen la identidad esperada del servicio, por lo que se recomienda que exponga los metadatos del servicio a través de medios seguros, como, por ejemplo, creando un extremo HTTPS para el servicio. Para obtener más información, consulte [Cómo: proteger los extremos de metadatos](how-to-secure-metadata-endpoints.md).  
  
## <a name="identity-types"></a>Tipos de identidad  
 Un servicio puede proporcionar seis tipos de identidades. Cada tipo de identidad corresponde a un elemento que se puede contener dentro del elemento `<identity>` mediante configuración. El tipo utilizado depende del escenario y de los requisitos de seguridad del servicio. La tabla siguiente describe cada tipo de identidad.  
  
|Tipo de identidad|Descripción|Escenario típico|  
|-------------------|-----------------|----------------------|  
|Sistema de nombres de dominio (DNS)|Utilice este elemento con certificados X.509 o cuentas de Windows. Compara el nombre DNS especificado en la credencial con el valor especificado en este elemento.|Una comprobación de DNS le permite utilizar certificados con DNS o nombres de sujetos. Si un certificado se vuelve a emitir con el mismo DNS o nombre de sujeto, la comprobación de identidad sigue siendo válida. Cuando se vuelve a emitir un certificado, obtiene una nueva clave RSA pero conserva el mismo DNS o nombre de sujeto. Esto significa que los clientes no tienen que actualizar su información de identidad sobre el servicio.|  
|Certificado. El valor predeterminado cuando `ClientCredentialType` se establece en Certificate (certificado).|Este elemento especifica un valor de certificado X.509 codificado en Base64 para compararlo con el cliente.<br /><br /> Utilice también este elemento al usar un CardSpace como credencial para autenticar el servicio.|Este elemento restringe la autenticación a un certificado único basado en su valor de huella digital. Esto habilita autenticación más estricta, puesto que los valores de huella digital son únicos. Esto viene con una advertencia: si el certificado se vuelve a emitir con el mismo nombre de sujeto, tiene también una nueva huella digital. Por consiguiente, los clientes no pueden validar el servicio a menos que se conozca la nueva huella digital. Para obtener más información sobre cómo encontrar la huella digital de un certificado, consulte [Cómo: recuperar la huella digital de un certificado](how-to-retrieve-the-thumbprint-of-a-certificate.md).|  
|Referencia del certificado|Idéntica a la opción Certificado descrita previamente. Sin embargo, este elemento le permite especificar un nombre de certificado y una ubicación de almacenamiento desde la que recuperar el certificado.|Igual que el escenario del Certificado descrito previamente.<br /><br /> La ventaja es que la ubicación del almacén de certificados puede cambiar.|  
|RSA|Este elemento especifica un valor de clave de RSA para comparar con el cliente. Esto es similar a la opción de certificado, pero en lugar de utilizar la huella digital del certificado, se utiliza la clave RSA del certificado.|Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basándose en su clave RSA. Esto permite una autenticación más estricta de una clave RSA específica en el gasto del servicio, que ya no trabaja con clientes existentes si cambia el valor de clave de RSA.|  
|Nombre principal de usuario (UPN). El valor predeterminado cuando `ClientCredentialType` está establecido en Windows y el proceso del servicio no se está ejecutando bajo una de las cuentas del sistema.|Este elemento especifica el UPN bajo el que el servicio se está ejecutando. Vea la sección sobre el protocolo Kerberos y la identidad de [invalidación de la identidad de un servicio para la autenticación](../extending/overriding-the-identity-of-a-service-for-authentication.md).|Esto asegura que el servicio se esté ejecutando bajo una cuenta de usuario de Windows concreta. La cuenta de usuario puede ser el usuario actual con sesión iniciada o el servicio que se ejecuta bajo una cuenta de usuario determinada.<br /><br /> Este valor se beneficia de la seguridad de Windows Kerberos si el servicio se ejecuta bajo una cuenta de dominio dentro de un entorno de Active Directory.|  
|Nombre de entidad de seguridad de servicio (SPN). El valor predeterminado cuando `ClientCredentialType` está establecido en Windows y el proceso del servicio no se está ejecutando bajo una de las cuentas del sistema: LocalService, LocalSystem o NetworkService.|Este elemento especifica el SPN asociado a la cuenta del servicio. Vea la sección sobre el protocolo Kerberos y la identidad de [invalidación de la identidad de un servicio para la autenticación](../extending/overriding-the-identity-of-a-service-for-authentication.md).|Esto asegurar que el SPN y la cuenta de Windows concreta asociada al SPN identifican el servicio.<br /><br /> Puede utilizar la herramienta Setspn.exe para asociar una cuenta de equipo a la cuenta de usuario del servicio.<br /><br /> Este valor se beneficia de la seguridad de de Windows Kerberos si el servicio se está ejecutando bajo una de las cuentas del sistema o bajo una cuenta de dominio que tiene asociado un nombre SPN a ella y el equipo es un miembro de un dominio dentro de un entorno de Active Directory.|  
  
## <a name="specifying-identity-at-the-service"></a>Especificación de la identidad en el servicio  
 Normalmente, no tiene que establecer la identidad en un servicio porque la selección de un tipo de credencial de cliente dicta el tipo de identidad expuesto en los metadatos del servicio. Para obtener más información sobre cómo invalidar o especificar la identidad del servicio, consulte [invalidación de la identidad de un servicio para la autenticación](../extending/overriding-the-identity-of-a-service-for-authentication.md).  
  
## <a name="using-the-identity-element-in-configuration"></a>Usar el \<identity> elemento en la configuración  
 Si cambia el tipo de credencial de cliente en el enlace mostrado anteriormente a `Certificate,`, entonces el WSDL generado contiene un certificado X.509 serializado con Base64 para el valor de identidad en el código siguiente. Éste es el valor predeterminado para todos los tipos de credencial de cliente excepto Windows.  

 Puede cambiar el valor de la identidad de servicio predeterminada o cambiar el tipo de la identidad mediante el `<identity>` elemento de la configuración o estableciendo la identidad en el código. El código de configuración siguiente establece una identidad del sistema de nombres de dominio (DNS) con el valor `contoso.com`.  

## <a name="setting-identity-programmatically"></a>Establecimiento mediante programación de la identidad  
 El servicio no tiene que especificar explícitamente una identidad, ya que WCF la determina automáticamente. Sin embargo, WCF le permite especificar una identidad en un punto de conexión, si es necesario. El código siguiente agrega un nuevo punto de conexión de servicio con una identidad de DNS concreta.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="specifying-identity-at-the-client"></a>Especificación de la identidad en el cliente  
 En tiempo de diseño, un desarrollador de cliente suele usar la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para generar la configuración de cliente. El archivo de configuración generado (pensado para que lo utilice el cliente) contiene la identidad del servidor. Por ejemplo, el código siguiente se genera a partir de un servicio que especifica una identidad de DNS, tal y como se muestra en el ejemplo anterior. Observe que el valor de identidad de extremo del cliente coincide con el del servicio. En este caso, cuando el cliente recibe las credenciales de Windows (Kerberos) para el servicio, espera que el valor sea `contoso.com`.  

 Si, en lugar de Windows, el servicio especifica un certificado como el tipo de credencial de cliente, se espera que la propiedad DNS del certificado sea el valor `contoso.com`. (O si la propiedad DNS es `null`, el nombre de sujeto del certificado debe ser `contoso.com`.)  
  
#### <a name="using-a-specific-value-for-identity"></a>Uso de un valor específico de identidad  
 El siguiente archivo de configuración del cliente muestra cómo se espera que la identidad del servicio sea un valor concreto. En el ejemplo siguiente, el cliente puede comunicarse con dos puntos de conexión. El primero se identifica con una huella digital del certificado y el segundo con una clave RSA certificada. Es decir, un certificado que contiene solo un par de clave pública/clave privada, pero que no es emitido por una autoridad de confianza.  

## <a name="identity-checking-at-run-time"></a>Comprobación de identidad en tiempo de ejecución  
 En la fase de diseño, un programador de cliente determina la identidad del servidor mediante sus metadatos. En tiempo de ejecución, la comprobación de identidad se realiza antes de llamar a ningún punto de conexión del servicio.  
  
 El valor de identidad está ligado al tipo de autenticación especificado mediante metadatos; en otras palabras, el tipo de credenciales utilizadas para el servicio.  
  
 Si el canal se configura para autenticar mediante capa de sockets seguros (SSL) del nivel de transporte o mensaje con certificados X.509 para la autenticación, los siguientes valores de identidad son válidos:  
  
- DNS. WCF garantiza que el certificado proporcionado durante el protocolo de enlace SSL contiene un atributo DNS o `CommonName` (CN) igual al valor especificado en la identidad DNS en el cliente. Observe que estas comprobaciones se hacen además de determinar la validez del certificado de servidor. De forma predeterminada, WCF valida que el certificado de servidor está emitido por una entidad de certificación raíz de confianza.  
  
- Certificado. Durante el protocolo de enlace SSL, WCF garantiza que el punto de conexión remoto proporciona el valor de certificado exacto especificado en la identidad.  
  
- Referencia del certificado. Igual que el certificado.  
  
- RSA. Durante el protocolo de enlace SSL, WCF garantiza que el punto de conexión remoto proporciona la clave RSA exacta especificada en la identidad.  
  
 Si el servicio autentica utilizando SSL de nivel de transporte o mensaje con una credencial de Windows para la autenticación y negocia la credencial, son válidos los siguientes valores de identidad:  
  
- DNS. La negociación pasa el SPN del servicio para que se pueda comprobar el nombre DNS. SPN está en forma de `host/<dns name>`.  
  
- SPN. Se devuelve un SPN de servicio explícito, por ejemplo, `host/myservice`.  
  
- UPN. UPN de la cuenta de servicio. El UPN tiene el formato `username` @ `domain` . Por ejemplo, cuando el servicio se ejecuta en una cuenta de usuario, puede ser `username@contoso.com`.  
  
 Especificar la identidad mediante programación es opcional (utilizando la propiedad <xref:System.ServiceModel.EndpointAddress.Identity%2A>). Si no se especifica ninguna identidad, y el tipo de credencial de cliente es Windows, el valor predeterminado es SPN con el valor establecido en la parte del nombre del host de la dirección del punto de conexión de servicio prefijada con el literal "host/". Si no se especifica ninguna identidad y el tipo de credencial de cliente es un certificado, el valor predeterminado es `Certificate`. Esto se aplica a la seguridad de nivel de mensaje y transporte.  
  
## <a name="identity-and-custom-bindings"></a>Identidad y enlaces personalizados  
 Dado que la identidad de un servicio depende del tipo de enlace utilizado, asegúrese de que se expone una identidad adecuada al crear un enlace personalizado. Por ejemplo, en el siguiente ejemplo de código, la identidad expuesta no es compatible con el tipo de seguridad, porque la identidad del enlace de arranque de conversación segura no coincide con la identidad del enlace en el extremo. El enlace de conversación segura establece la identidad DNS, mientras que <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> establece la identidad UPN o SPN.  
  
 [!code-csharp[C_Identity#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#8)]
 [!code-vb[C_Identity#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#8)]  
  
 Para obtener más información sobre cómo apilar elementos de enlace correctamente para un enlace personalizado, vea [crear enlaces definidos por el usuario](../extending/creating-user-defined-bindings.md). Para obtener más información sobre cómo crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement> , consulte [Cómo: crear un SecurityBindingElement para un modo de autenticación especificado](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
- [Procedimiento para crear un comprobador de identidad de cliente personalizado](../extending/how-to-create-a-custom-client-identity-verifier.md)
- [Selección de tipos de credenciales](selecting-a-credential-type.md)
- [Trabajar con certificados](working-with-certificates.md)
- [Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Creación de enlaces definidos por el usuario](../extending/creating-user-defined-bindings.md)
- [Procedimiento para recuperar la huella digital de un certificado](how-to-retrieve-the-thumbprint-of-a-certificate.md)
