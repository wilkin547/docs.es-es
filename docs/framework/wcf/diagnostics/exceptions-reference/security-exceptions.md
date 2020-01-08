---
title: Excepciones de seguridad
ms.date: 03/30/2017
ms.assetid: 76d5e5cd-e4f4-404f-9a5a-ec3522494ad8
ms.openlocfilehash: e96c317862867b9e461eb2d13dce6ede5b30cf13
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348242"
---
# <a name="security-exceptions"></a>Excepciones de seguridad

En este tema se enumeran todas las excepciones de seguridad.

## <a name="exception-list"></a>Lista de excepciones

|Código de recurso|Cadena de recurso|
|-------------------|---------------------|
|AnonymousLogonsAreNotAllowed|El servicio no le permite iniciar sesión de manera anónima.|
|AtLeastOneContractOperationRequestRequiresProtectionLevelNotSupportedByBinding|Se debe proteger el mensaje de solicitud. Una operación del contrato especificado requiere esto. El enlace especificado debe proporcionar la protección.|
|AtLeastOneContractOperationResponseRequiresProtectionLevelNotSupportedByBinding|Se debe proteger el mensaje de respuesta. Una operación del contrato especificado requiere esto. El enlace especificado debe proporcionar la protección.|
|AtMostOnePrimarySignatureInReceiveSecurityHeader|Solo se permite una firma primaria en un encabezado de seguridad.|
|BadContextTokenFaultReason|El token de contexto de seguridad expiró o no es válido. No se procesó el mensaje.|
|BadEncryptionState|EncryptedData o EncryptedKey no es un estado válido para esta operación.|
|BasicHttpMessageSecurityRequiresCertificate|El enlace BasicHttp requiere que BasicHttpBinding.Security.Message.ClientCredentialType sea equivalente al tipo de credencial de BasicHttpMessageCredentialType.Certificate para mensajes seguros. Seleccione la seguridad Transport o TransportWithMessageCredential para las credenciales UserName.|
|BasicTokenCannotBeWrittenWithoutEncryption|El token básico no se puede escribir sin cifrado.|
|BindingDoesNotSupportProtectionForRst|El enlace especificado para el contrato especificado se configura con SecureConversation, pero el modo de autenticación no puede proporcionar la confidencialidad e integridad basada en solicitud/respuesta requeridas para la negociación.|
|BindingDoesNotSupportWindowsIdenityForImpersonation|La operación del contrato especificado requiere la identidad de Windows para la suplantación automática. Una identidad de Windows que representa al llamador no es proporcionada por el enlace específico para el contrato específico.|
|CachedNegotiationStateQuotaReached|El servicio no puede almacenar en caché el estado de la negociación cuando se ha alcanzado la capacidad especificada. Reintente la solicitud.|
|CacheQuotaReached|No se puede agregar el elemento. Se especifica el tamaño de caché máximo.|
|CannotDetermineSPNBasedOnAddress|El cliente no puede determinar el nombre de la entidad de seguridad del servicio basándose en la identidad en la dirección de destino especificada con el propósito de SspiNegotiation/Kerberos. La identidad de la dirección de destino debe ser una identidad UPN (como acmedomain\\\alice) o una identidad SPN (como host/bobs-Machine).|
|CannotFindCert|No se puede encontrar el certificado X.509 mediante el criterio de búsqueda concreto: StoreName, StoreLocation, FindType, FindValue.|
|CannotFindCertForTarget|No se puede encontrar el certificado X.509 mediante el criterio de búsqueda concreto: StoreName, StoreLocation, FindType, FindValue para el destino especificado.|
|CannotFindCorrelationStateForApplyingSecurity|No se puede encontrar el estado de correlación para aplicar la seguridad para responder en el respondedor.|
|CannotFindNegotiationState|No se puede encontrar el estado de negociación para el contexto especificado.|
|CannotFindSecuritySession|No se puede encontrar la sesión de seguridad con el id. especificado.|
|CannotImportProtectionLevelForContract|La directiva para importar un proceso no puede importar un enlace para el contrato especificado. Los requisitos de protección para el enlace no son compatibles con un enlace ya importado para el contrato. Debe reconfigurar el enlace.|
|CannotImportSupportingTokensForOperationWithoutRequestAction|Error en la importación de la directiva de seguridad. La directiva de seguridad contiene los requisitos de tokens auxiliares en el ámbito de la operación. La descripción del contrato no especifica la acción para el mensaje de solicitud asociado a esta operación.|
|CannotIssueRstTokenType|No puede emitir el token o especificar el tipo.|
|CannotObtainIssuedTokenKeySize|No puede determinar el tamaño de clave del token emitido.|
|CannotPerformImpersonationOnUsernameToken|No se puede realizar la suplantación mediante el token del cliente. El enlace especificado para el contrato especificado utiliza el token de seguridad de nombre de usuario para la autenticación de cliente con un proveedor de pertenencia registrado. Use otro tipo de token de seguridad para el cliente.|
|CannotPerformS4UImpersonationOnPlatform|El enlace especificado para el contrato especificado solo admite la suplantación en Windows Server 2003 y una versión más reciente de Windows. Utilice autenticación de SspiNegotiated y un enlace con Secure Conversation con la cancelación habilitada.|
|CannotReadKeyIdentifier|No se puede leer el KeyIdentifier del elemento especificado con el espacio de nombres especificado.|
|CannotReadToken|No se puede leer el token del elemento especificado con el espacio de nombres especificado para BinarySecretSecurityToken, con un ValueType especificado. Si se espera que este elemento sea válido, asegúrese de que la seguridad se configura para utilizar los tokens con el nombre, espacio de nombres y tipo de valor especificados.|
|CertificateUnsupportedForHttpTransportCredentialOnly|La autenticación de cliente basada en certificado no se admite en modo de seguridad de TransportCredentialOnly. Seleccione el modo de seguridad Transport.|
|ClaimTypeCannotBeEmpty|El claimType no puede ser una cadena vacía.|
|ClientCertificateNotProvided|No se ha proporcionado el certificado para el cliente. El certificado se puede establecer en ClientCredentials o ServiceCredentials.|
|ClientCredentialTypeMustBeSpecifiedForMixedMode|ClientCredentialType.None no es válido para el modo de seguridad de TransportWithMessageCredential. Especifique un tipo de credencial o utilice un modo de seguridad diferente.|
|ConfigurationSchemaInsuffientForSecurityBindingElementInstance|El esquema de configuración no es suficiente para describir la configuración no estándar del siguiente elemento de enlace de seguridad:|
|DerivedKeyTokenGenerationAndLengthTooHigh|La generación y longitud especificada de la clave derivada producen un desplazamiento de derivación de claves mayor que el desplazamiento máximo permitido.|
|DnsIdentityCheckFailedForIncomingMessage|Error en la comprobación de identidad para el mensaje entrante. Se especificó la identidad del sistema de nombres de dominio (DNS) esperada del punto de conexión remoto. El extremo remoto proporcionó la demanda especificada del sistema de nombres de dominio (DNS). Si éste es un punto de conexión remoto legítimo, puede corregir el problema especificando la identidad del sistema de nombres de dominio como la propiedad de identidad de EndpointAddress al crear el proxy del canal.|
|DnsIdentityCheckFailedForOutgoingMessage|Error en la comprobación de identidad para el mensaje que estaba saliendo. El punto de conexión remoto debe haber tenido la identidad de sistema de nombres de dominio especificada. El extremo remoto proporcionó la demanda del sistema de nombres de dominio (DNS). Si éste es un punto de conexión remoto legítimo, puede corregir el problema especificando de manera explícita la identidad DNS como la propiedad Identity de EndpointAddress al crear el proxy del canal.|
|DuplicateIdInMessageToBeVerified|El ID. especificado se produjo dos veces en el mensaje que se proporciona para la comprobación.|
|EmptyBase64Attribute|Un valor vacío se encontró para el espacio de nombres y nombre de atributo de base64 necesario.|
|ExportOfBindingWithAsymmetricAndTransportSecurityNotSupported|Error en la exportación de la directiva de seguridad. El enlace contiene un elemento AsymmetricSecurityBindingElement y otro de enlace de transporte seguro. No se admite la exportación de directivas para este tipo de enlaces.|
|ExportOfBindingWithSymmetricAndTransportSecurityNotSupported|Error en la exportación de la directiva de seguridad. El enlace contiene un elemento SymmetricSecurityBindingElement y otro de enlace de transporte seguro. No se admite la exportación de directivas para este tipo de enlaces.|
|ExportOfBindingWithTransportSecurityBindingElementAndNoTransportSecurityNotSupported|Error en la exportación de la directiva de seguridad. El enlace contiene un TransportSecurityBindingElement pero ningún elemento de enlace de transporte que implemente ITransportTokenAssertionProvider. No se admite la exportación de directivas para este tipo de enlaces. Asegúrese de que el elemento de enlace de transporte en el enlace implementa la interfaz ITransportTokenAssertionProvider.|
|FoundMultipleCerts|Se encontraron varios certificados X.509 mediante el criterio de búsqueda especificado: StoreName, StoreLocation, FindType, FindValue. Proporcione un valor de búsqueda más concreto.|
|FoundMultipleCertsForTarget|Se encontraron múltiples certificados X.509 mediante el criterio de búsqueda especificado: StoreName, StoreLocation, FindType, FindValue para el destino especificado. Proporcione un valor de búsqueda más concreto.|
|HeaderDecryptionNotSupportedInWsSecurityJan2004|SecurityVersion.WSSecurityJan2004 no admite el descifrado de encabezados. Utilice SecurityVersion.WsSecurityXXX2005 y superiores o utilice seguridad de transporte para cifrar el mensaje completo.|
|IdentityCheckFailedForIncomingMessage|Error en la comprobación de identidad para el mensaje entrante. La identidad esperada se especifica para el punto de conexión de destino.|
|IdentityCheckFailedForOutgoingMessage|Error en la comprobación de identidad para el mensaje saliente. La identidad esperada se especifica para el punto de conexión de destino.|
|IncorrectSpnOrUpnSpecified|Error de autenticación de la interfaz del proveedor de compatibilidad para seguridad (SSPI). Es posible que el servidor no se esté ejecutando en una cuenta con la identidad especificada. Si el servidor se está ejecutando en una cuenta de servicio (servicio de red, por ejemplo), especifique el ServicePrincipalName de la cuenta como la identidad en la EndpointAddress para el servidor. Si el servidor se está ejecutando en una cuenta de usuario, especifique el UserPrincipalName de la cuenta como la identidad en la EndpointAddress para el servidor.|
|InvalidAttributeInSignedHeader|El encabezado firmado especificado contiene el atributo especificado. Se especifica el atributo esperado.|
|InvalidCloseResponseAction|Se recibió una respuesta de cierre de sesión de seguridad con la acción no válida especificada.|
|InvalidQName|El QName no es válido.|
|InvalidRenewResponseAction|Se recibió una respuesta de renovación de sesión de seguridad con la acción no válida especificada.|
|InvalidSspiNegotiation|Error en la negociación de la Interfaz del proveedor de compatibilidad para seguridad (SSPI).|
|IssuerBindingNotPresentInTokenRequirement|El administrador de tokens de seguridad requiere que se especifique el elemento de enlace de seguridad de arranque en el requisito de token que describe la conversación segura. El requisito de token se especifica de la siguiente manera.|
|KeyLengthMustBeMultipleOfEight|La longitud de la clave especificada no es un múltiplo de 8 para claves simétricas.|
|LsaAuthorityNotContacted|Error de SSL interno (consulte el código de estado de Win32 para obtener detalles). Compruebe el certificado de servidor para determinar si es capaz de intercambiar claves.|
|MaximumPolicyRedirectionsExceeded|Se ha alcanzado el límite de captura de directivas recursivas. Compruebe si hay un bucle en la cadena de servicios de federación.|
|MessagePartSpecificationMustBeImmutable|La especificación de parte del mensaje se debe hacer constante antes de que se establezca.|
|MissingCustomCertificateValidator|X509CertificateValidationMode.Custom requiere CustomCertificateValidator. Especifique la propiedad CustomCertificateValidator.|
|MissingCustomUserNamePasswordValidator|UserNamePasswordValidationMode.Custom requiere CustomUserNamePasswordValidator. Especifique la propiedad CustomUserNamePasswordValidator.|
|MissingMembershipProvider|UserNamePasswordValidationMode.MembershipProvider requiere MembershipProvider. Especifique la propiedad MembershipProvider.|
|NoBinaryNegoToSend|No se envió ninguna negociación binaria a la otra parte.|
|NoEncryptionPartsSpecified|No se especificó ninguna parte de mensaje de cifrado con la acción especificada.|
|NoKeyInfoInEncryptedItemToFindDecryptingToken|No se encontró el valor KeyInfo en el elemento cifrado para encontrar el token de descifrado.|
|NonceLengthTooShort|El valor de seguridad (nonce) especificado es demasiado corto. La longitud mínima requerida es 4 bytes.|
|NoOutgoingEndpointAddressAvailableForDoingIdentityCheck|Ninguna EndpointAddress de salida está disponible para comprobar la identidad en un mensaje que se va a enviar.|
|NoOutgoingEndpointAddressAvailableForDoingIdentityCheckOnReply|Ninguna EndpointAddress de salida está disponible para comprobar la identidad en una respuesta recibida.|
|NoPartsOfMessageMatchedPartsToSign|No se creó ninguna firma porque ninguna parte del mensaje coincidió con la especificación de la parte del mensaje proporcionada.|
|NoPrincipalSpecifiedInAuthorizationContext|No se especifica ninguna entidad de seguridad personalizada en el contexto de autorización.|
|NoSignatureAvailableInSecurityHeaderToDoReplayDetection|No hay ninguna firma disponible en el encabezado de seguridad para proporcionar el valor de seguridad (nonce) para la detección de reproducción.|
|NoSignaturePartsSpecified|No se especificó ninguna parte de mensaje de firma con la acción especificada.|
|NoSigningTokenAvailableToDoIncomingIdentityCheck|No hay disponible ningún token de firma para realizar una comprobación de identidad de entrada.|
|NoTimestampAvailableInSecurityHeaderToDoReplayDetection|No hay disponible ninguna marca de tiempo en el encabezado de seguridad para realizar la detección de la repetición.|
|NoTransportTokenAssertionProvided|Error en el experto de directivas de seguridad. La aserción del token de transporte proporcionado del tipo especificado no creó una aserción de token de transporte para incluir la aserción de directiva de seguridad de sp:TransportBinding.|
|OnlyOneOfEncryptedKeyOrSymmetricBindingCanBeSelected|El protocolo de seguridad simétrico se puede configurar con un proveedor y un autenticador de tokens simétrico o con un proveedor de tokens asimétrico. No se puede configurar con ambos.|
|OperationCannotBeDoneOnReceiverSideSecurityHeaders|Esta operación no se puede realizar en los encabezados de seguridad del receptor.|
|OperationDoesNotAllowImpersonation|La operación del servicio especificada que pertenece al contrato con el nombre y el espacio de nombres especificado no permite la suplantación.|
|PolicyRequiresConfidentialityWithoutIntegrity|La directiva de seguridad de mensajes para la acción especificada requiere confidencialidad sin integridad. No se admite la confidencialidad sin integridad.|
|PrimarySignatureIsRequiredToBeEncrypted|Se debe cifrar la firma primaria.|
|PropertySettingErrorOnProtocolFactory|La propiedad necesaria en el generador de protocolos de seguridad especificado no se ha establecido o no tiene un valor válido.|
|ProtocolFactoryCouldNotCreateProtocol|El generador de protocolos no puede crear un protocolo.|
|PublicKeyNotRSA|La clave pública no es una clave RSA.|
|RequiredMessagePartNotEncrypted|No se cifró la parte del mensaje necesaria especificada.|
|RequiredMessagePartNotEncryptedNs|No se cifró la parte del mensaje necesaria especificada.|
|RequiredMessagePartNotSigned|No se firmó la parte del mensaje necesaria especificada.|
|RequiredMessagePartNotSignedNs|No se firmó la parte del mensaje necesaria especificada.|
|RequiredSecurityHeaderElementNotSigned|El elemento de encabezado de seguridad especificado con el ID. especificado debe estar firmado.|
|RequiredSecurityTokenNotEncrypted|Se debe cifrar el token de seguridad especificado con el modo de datos adjuntos especificado.|
|RequiredSecurityTokenNotSigned|Se debe firmar el token de seguridad especificado con el modo de datos adjuntos especificado.|
|RequiredSignatureMissing|La firma debe estar en el encabezado de seguridad.|
|RequireNonCookieMode|El enlace especificado con el espacio de nombres especificado se configura para emitir tokens de contexto de seguridad de cookies. Los servicios de integración de COM+ no admiten tokens de seguridad de contexto de cookies.|
|RevertingPrivilegeFailed|Error en la operación de reversión con la excepción especificada.|
|RSTRAuthenticatorIncorrect|El CombinedHash de RequestSecurityTokenResponse es incorrecto.|
|SecureConversationCancelNotAllowedFaultReason|El enlace no permite una cancelación de conversación segura.|
|SecureConversationDriverVersionDoesNotSupportSession|La versión SecureConversation configurada no admite sesiones. Utilice WSSecureConversationFeb2005 o superior.|
|SecureConversationRequiredByReliableSession|No se puede establecer una sesión fiable sin una conversación segura. Habilite la conversación segura.|
|SecurityAuditFailToLoadDll|No se pudo cargar la biblioteca de vínculos dinámicos especificada (dll).|
|SecurityAuditNotSupportedOnChannelFactory|SecurityAuditBehavior no se admite en el generador de canales.|
|SecurityAuditPlatformNotSupported|La plataforma actual no admite la escritura de mensajes de auditoría en el registro de seguridad. Debe escribir los mensajes de auditoría en el registro de aplicaciones.|
|SecurityBindingElementCannotBeExpressedInConfig|Una directiva de seguridad se importó para el punto de conexión. La directiva de seguridad contiene requisitos que no se pueden representar en una configuración de Windows Communication Foundation. Busque un comentario acerca de los parámetros SecurityBindingElement que se requieren en el archivo de configuración generado. Cree el elemento de enlace correcto con código. La configuración de enlace que se encuentra en el archivo de configuración no es segura.|
|SecurityBindingSupportsOneWayOnly|El SecurityBinding para el enlace especificado para el contrato especificado solo admite la operación OneWay.|
|SecurityContextDoesNotAllowImpersonation|No se puede iniciar la suplantación porque el SecurityContext para la función UltimateReceiver del mensaje de solicitud con la acción especificada no está asignado a una identidad de Windows.|
|SecurityListenerClosing|El agente de escucha no acepta nuevas conversaciones seguras porque se está cerrando.|
|SecurityListenerClosingFaultReason|El servidor no acepta actualmente nuevas conversaciones seguras porque se está cerrando. Vuelva a intentarlo más tarde.|
|SecurityProtocolFactoryShouldBeSetBeforeThisOperation|Se debe establecer el generador de protocolos de seguridad antes de que se realice esta operación.|
|SecuritySessionAbortedFaultReason|Se finalizó la sesión de seguridad. Esto puede deberse a que no se recibieron mensajes en la sesión durante mucho tiempo.|
|SecuritySessionKeyIsStale|Se debe renovar la clave de sesión antes de que pueda proteger los mensajes de la aplicación.|
|SecuritySessionLimitReached|No se puede crear una sesión de seguridad. Vuelva a intentarlo más tarde.|
|SecuritySessionNotPending|No hay pendiente ninguna sesión de seguridad con el ID. especificado.|
|SecurityTokenParametersHasIncompatibleInclusionMode|El enlace especificado se configura con un parámetro de token de seguridad que tiene el modo de inclusión de token de seguridad incompatible especificado. Especifique un modo de inclusión de token  de seguridad alternativo.|
|SecurityVersionDoesNotSupportEncryptedKeyBinding|El enlace especificado para el contrato especificado se ha configurado con una versión de seguridad incompatible que no admite las referencias no adjuntas a EncryptedKeys. Utilice el valor especificado o uno superior como la versión de seguridad del enlace.|
|SecurityVersionDoesNotSupportSignatureConfirmation|La SecurityVersion especificada no admite la confirmación de la firma. Utilice una SecurityVersion posterior.|
|SecurityVersionDoesNotSupportThumbprintX509KeyIdentifierClause|El enlace especificado para el contrato especificado se configura con una versión de seguridad que no admite las referencias externas a los tokens de X.509 utilizando el valor de huella digital del certificado. Utilice el valor especificado o uno superior como la versión de seguridad del enlace.|
|SenderSideSupportingTokensMustSpecifySecurityTokenParameters|Los parámetros de token de seguridad deben especificarse con tokens auxiliares para cada mensaje.|
|ServerCertificateNotProvided|El destinatario no proporcionó su certificado. El protocolo TLS requiere este certificado. Ambas partes deben tener acceso a sus certificados.|
|SignatureConfirmationNotSupported|La SecurityVersion configurada no admite la confirmación de la firma. Utilice WSSecurityXXX2005 o superior.|
|SignatureConfirmationRequiresRequestReply|El generador de protocolos debe admitir seguridad Solicitud/Respuesta para proporcionar la confirmación de firmas.|
|SignatureNotExpected|No se espera una firma para este mensaje.|
|SigningTokenHasNoKeys|El token de la firma especificada no tiene claves. El token de seguridad se utiliza en un contexto que requiere que realice operaciones criptográficas, pero el token no contiene ninguna clave criptográfica. O el tipo de token no admite operaciones criptográficas o la instancia determinada del token no contiene claves criptográficas. Compruebe su configuración para asegurarse que los tipos de token deshabilitados criptográficamente (como, por ejemplo, UserNameSecurityToken) no se especifican en un contexto que requiera operaciones criptográficas (como, por ejemplo, un token auxiliar de aprobación).|
|SpnegoImpersonationLevelCannotBeSetToNone|La Interfaz del proveedor de compatibilidad de seguridad no admite el nivel de suplantación 'None' (Ninguno). Especifique la Identificación, Suplantación o el Nivel de delegación.|
|SslClientCertMustHavePrivateKey|El certificado especificado debe tener una clave privada. El proceso debe tener los derechos de acceso para la clave privada.|
|SslServerCertMustDoKeyExchange|El certificado especificado debe tener una clave privada que sea capaz de realizar intercambio de claves. El proceso debe tener los derechos de acceso para la clave privada.|
|StandardsManagerCannotWriteObject|El serializador de tokens no puede serializar el objeto especificado.  Si se trata de un tipo personalizado, debe proporcionar un serializador personalizado.|
|TimeStampHasCreationAheadOfExpiry|La marca de tiempo de seguridad no es válida porque su hora de creación es mayor o igual que su hora de expiración.|
|TimeStampHasCreationTimeInFuture|La marca de tiempo de seguridad no es válida porque su hora de creación está en el futuro. Se especifica la hora actual y el sesgo de reloj permitido.|
|TimeStampHasExpiryTimeInPast|La marca de tiempo de seguridad está obsoleta porque su hora de expiración está en el pasado. Se especifica la hora actual y el sesgo de reloj permitido.|
|TimeStampWasCreatedTooLongAgo|La marca de tiempo de seguridad está obsoleta porque su hora de creación está muy atrás en el pasado. Se especifican la hora actual, la duración máxima de marca de tiempo y el sesgo de reloj permitido.|
|TokenProviderCannotGetTokensForTarget|El proveedor de tokens no puede obtener tokens para el destino especificado.|
|TooManyIssuedSecurityTokenParameters|Una sección de la cadena de seguridad federada contiene varios IssuedSecurityTokenParameters. El sistema InfoCard solo admite un elemento IssuedSecurityTokenParameters para cada fase.|
|TransportDoesNotProtectMessage|El enlace especificado para el contrato especificado se configura con un modo de autenticación que requiere confidencialidad e integridad de nivel de transporte. Sin embargo, el transporte no puede proporcionar integridad y confidencialidad.|
|TrustApr2004DoesNotSupportCertainIssuedTokens|WSTrustApr2004 no permite emitir certificados X.509 o EncryptedKeys. Utilice WsTrustFeb2005 o posterior.|
|TrustDriverVersionDoesNotSupportSession|La versión configurada Trust no admite sesiones. Utilice WSTrustFeb2005 o posterior.|
|UnableToCreateICryptoFromTokenForSignatureVerification|No se puede crear una interfaz ICrypto a partir del token especificado para la comprobación de firmas.|
|UnableToCreateSymmetricAlgorithmFromToken|No se puede crear el algoritmo simétrico especificado a partir del token.|
|UnableToDeriveKeyFromKeyInfoClause|La cláusula KeyInfo especificada se resolvió en el token especificado, que no contiene ninguna clave simétrica que pueda usarse para la derivación.|
|UnableToFindTokenAuthenticator|No puede encontrar un autenticador de tokens para el tipo de token especificado. Los tokens de ese tipo no se pueden aceptar de acuerdo con la configuración de seguridad actual.|
|UnableToLoadCertificateIdentity|No se puede cargar la identidad del certificado X.509 especificada en la configuración.|
|UnexpectedEmptyElementExpectingClaim|El elemento especificado del espacio de nombres especificado está vacío y no especifica una demanda de identidad válida.|
|UnknownEncodingInBinarySecurityToken|La codificación desconocida tuvo lugar mientras se leía el token de seguridad binario.|
|UnsecuredMessageFaultReceived|Se recibió un error de protección nula o incorrecta desde la otra parte. Vea la FaultException interna para obtener el código de error y detalles.|
|UnsupportedPasswordType|El token del nombre de usuario especificado tiene un tipo de contraseña no permitido.|
|UnsupportedSecureConversationBootstrapProtectionRequirements|No se puede importar la directiva de seguridad. No se admiten los requisitos de protección para el enlace de arranque de conversación segura. Los requisitos de protección para el arranque de conversación segura deben requerir que la solicitud y la respuesta se firmen y cifren.|
|UnsupportedSecurityPolicyAssertion|Se detectó una aserción de la directiva de seguridad no compatible durante la importación de la directiva de seguridad especificada.|
