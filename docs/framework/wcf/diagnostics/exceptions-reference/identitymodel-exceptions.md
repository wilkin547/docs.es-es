---
title: Excepciones de IdentityModel
ms.date: 03/30/2017
ms.assetid: 4ef34497-8ff5-4621-b773-7731cc721231
ms.openlocfilehash: 08d81f4eb35d0f4bda3997d6ab4dfd0ec10407e1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275042"
---
# <a name="identitymodel-exceptions"></a>Excepciones de IdentityModel

En este tema se enumeran todas las excepciones generadas por IdentityModel.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena actual|  
|-------------------|--------------------|  
|ValueMustBeOf2Types|El valor de este argumento debe ser de uno de estos dos tipos.|  
|SAMLSubjectNameIdentifierRequiresNameValue|El 'Nombre' especificado para un SamlNameIdentifier no puede ser nulo ni de longitud 0.|  
|TraceCodeIssuanceTokenProviderEndSecurityNegotiation|El IssuanceTokenProvider ha completado una negociación de seguridad.|  
|TraceCodeSecurityNewServerSessionKeyIssued|El servidor emitió una nueva clave de sesión de seguridad.|  
|SAMLAttributeMissingNameAttributeOnRead|El 'Nombre' para el SamlAttribute que se está leyendo falta o es de longitud 0.|  
|UnknownICryptoType|No se admite la implementación de ICrypto.|  
|TraceCodeSecurityTokenProviderClosed|Se cerró el proveedor de tokens de seguridad.|  
|SAMLUnableToLoadAdvice|No se pudo cargar el \<saml:advice> elemento.|  
|SAMLAuthenticationStatementMissingAuthenticationMethodOnRead|El atributo 'AuthenticationMethod' que se lee para una SamlAuthenticationStatement falta o es de longitud 0.|  
|UnsupportedTransformAlgorithm|Algoritmo de canonización o transformación no compatible.|  
|SAMLAudienceRestrictionShouldHaveOneAudience|Una SamlAudienceRestrictionCondition debe contener por lo menos una Audiencia (URI).|  
|SAMLEvidenceShouldHaveOneAssertion|SamlEvidence debe hacer referencia al menos a una SamlAssertion por id. o referencia.|  
|SAMLAudienceRestrictionInvalidAudienceValueOnRead|A la SamlAudienceRestrictionCondition que se está leyendo le falta un valor en el elemento 'Audience'.|  
|X509ChainBuildFail|No se pudo crear la cadena de certificado X.509 concreta. El certificado que se utilizó tiene una cadena de confianza que no se puede comprobar. Reemplace el certificado o cambie el certificateValidationMode.|  
|XDCannotFindValueInDictionaryString|El id. de valor concreto no se encuentra en la cadena del diccionario.|  
|TraceCodeImportSecurityChannelBindingEntry|Inicio de ImportChannelBinding de seguridad.|  
|PrivateKeyExchangeNotSupported|La clave privada no admite la KeySpec de intercambio.|  
|TokenProviderUnableToGetToken|El proveedor de tokens concreto no pudo proporcionar un token de seguridad.|  
|SAMLEntityCannotBeNullOrEmpty|La entidad SamlAssertion concreta no puede ser nula ni vacía.|  
|SAMLAssertionRequireOneStatement|Una SamlAssertion requiere al menos una instrucción. Asegúrese de que ha agregado por lo menos una SamlStatement a la SamlAssertion que está creando.|  
|AESInvalidInputBlockSize|El tamaño de entrada debe ser un múltiplo de bytes concretos.|  
|AESCryptAcquireContextFailed|No se adquirió el contexto del CSP.|  
|SAMLAssertionRequireOneStatementOnRead|La SamlAssertion que se está leyendo no contenía ninguna SamlStatement. Una SamlAssertion debe contener por lo menos una SamlStatement.|  
|TraceCodeSecuritySessionClosedFaultReceived|La sesión de seguridad de cliente recibió un error de sesión cerrada del servidor.|  
|TraceCodeIssuanceTokenProviderRedirectApplied|IssuanceTokenProvider aplicó un encabezado de redirección.|  
|TraceCodeSecuritySessionClosedFaultSendFailure|No se pudo enviar un error de sesión de seguridad cerrada al cliente.|  
|ValueMustBeZero|El valor de este argumento debe ser 0.|  
|SAMLUnableToResolveSignatureKey|No puede resolver el SecurityKeyIdentifier encontrado en la firma de SamlAssertion. La firma de SamlAssertion no se puede validar para el Emisor concreto.|  
|X509IsNotInTrustedStore|El certificado X.509 concreto no está en el almacén de personas de confianza.|  
|SAMLElementNotRecognized|No se admite el elemento concreto.|  
|SAMLAuthorizationDecisionStatementMissingResourceAttributeOnRead|El atributo 'Resource' para la SamlAuthorizationDecisionStatement que se está leyendo falta o es de longitud 0.|  
|SamlTokenMissingSignature|No se firma la SamlAssertion. Las SamlAssertions se pueden firmar estableciendo las SigningCredentials.|  
|ExpectedElementMissing|El elemento esperado con el espacio de nombres concreto falta.|  
|NoKeyIdentifierClauseFound|Ninguna cláusula del tipo específico se encontró en SecurityKeyIdentifier.|  
|MissingPrivateKey|La clave privada no se encuentra presente en el certificado X.509.|  
|UnexpectedEOFFromReader|EOF inesperado desde el lector XML.|  
|UnsupportedKeyDerivationAlgorithm|No se admite el algoritmo de derivación de clave concreta.|  
|TokenDoesNotSupportKeyIdentifierClauseCreation|El token concreto no admite la creación de cláusula del identificador de clave concreta.|  
|LastMessageNumberExceeded|Se ha detectado una infracción del protocolo de número de secuencia.|  
|SymmetricKeyLengthTooShort|La longitud de la clave simétrica especificada también es corta.|  
|SAMLAuthorityBindingMissingAuthorityKindOnRead|Se descubrió que el SamlAuthorityBinding que se está leyendo contenía un 'AuthorityKind' que faltaba o era de longitud 0.  Esto no está permitido.|  
|XmlTokenBufferIsEmpty|XmlTokenBuffer está vacío.|  
|InvalidXmlQualifiedName|Se esperaba un nombre completo Xml, pero se encontró un nombre no válido.|  
|SAMLAuthorityKindMissingName|El XmlQualifiedName que representa el 'AuthorityKind' en el SamlAuthorityBinding no puede ser nulo o de longitud 0.|  
|AESCryptEncryptFailed|No se cifraron los datos específicos.|  
|AuthorizationContextCreated|Se crea el contexto de autorización con el id. concreto.|  
|SamlSerializerUnableToReadSecurityKeyIdentifier|El SamlSerializer no contiene un SecurityTokenSerializer capaz de leer el SecurityKeyIdentifier. Si está utilizando un SecurityKeyIdentifier personalizado, debe proporcionar un SecurityTokenSerializer personalizado.|  
|TraceCodeIssuanceTokenProviderServiceTokenCacheFull|IssuanceTokenProvider redujo la caché de token de servicio.|  
|TraceCodeSecurityTokenProviderOpened|Se abrió el proveedor de tokens de seguridad.|  
|PublicKeyNotRSA|La clave pública no es una clave RSA.|  
|InvalidReaderState|El estado concreto no es válido para el lector de entrada proporcionado.|  
|UnableToResolveReferenceUriForSignature|No puede resolver el URI concreto en la firma para calcular el resumen.|  
|EmptyBase64Attribute|Un valor vacío se encontró para el espacio de nombres y nombre de atributo de base64 necesario.|  
|SAMLSubjectRequiresConfirmationMethodWhenConfirmationDataOrKeyInfoIsSpecified|La SAML SubjectConfirmation requiere un método Confirmation cuando se especifican los datos de confirmación o KeyInfo.|  
|SAMLAudienceRestrictionShouldHaveOneAudienceOnRead|La SamlAudienceRestrictionCondition que se está leyendo debe contener por lo menos un valor 'Audience'. No se encontró ninguno.|  
|TokenProviderUnableToRenewToken|El proveedor de tokens concreto no pudo renovar el token de seguridad.|  
|AESIVLengthNotSupported|Los bits IV concretos no se admiten. Solo se admiten 128 bits IV.|  
|SAMLAuthorityBindingMissingAuthorityKind|Un SamlAuthorityBinding debe contener un 'AuthorityKind' que no sea nulo.|  
|TraceCodeSecuritySessionDemuxFailure|El mensaje entrante no forma parte de una sesión de seguridad existente.|  
|TokenRenewalNotSupported|El proveedor de tokens concreto no admite la renovación de tokens.|  
|AtLeastOneReferenceRequired|Se requiere al menos una referencia en una firma.|  
|SAMLSignatureAlreadyRead|La firma ya se lee en la aserción del SAML.|  
|AlgorithmAndPrivateKeyMisMatch|El algoritmo especificado y la clave privada no coinciden.|  
|EmptyTransformChainNotSupported|No se admite la cadena de la transformación vacía.|  
|SspiWrapperEncryptDecryptAssert1|SSPIWrapper:: EncryptDecryptHelper&#124; ' offset ' está fuera del intervalo.|  
|SspiWrapperEncryptDecryptAssert2|SSPIWrapper:: EncryptDecryptHelper&#124; ' size ' está fuera del intervalo. El administrador de tokens de seguridad de SecurityTokenManagerCannotCreateAuthenticatorForRequirement=El administrador de tokens de seguridad no puede crear un autenticador para el requisito concreto.|  
|UnableToCreateKeyedHashAlgorithm|No se puede crear KeyedHashAlgorithm a partir del valor concreto para el algoritmo de firma concreto.|  
|SAMLUnableToLoadAssertion|\<saml:assertion>No se pudo cargar el elemento.|  
|X509FindValueMismatchMulti|El X509FindType concreto requiere que el tipo del argumento findValue sea uno de los 2 valores. El argumento findValue es de otro tipo.|  
|TraceCodeSecurityIdentityDeterminationSuccess|Se determinó la identidad para una EndpointAddress.|  
|UndefinedUseOfPrefixAtElement|El prefijo concreto que se usa en el elemento no tiene ningún espacio de nombres definido.|  
|TraceCodeSecuritySessionResponderOperationFailure|Error de la operación de la sesión de seguridad en el servidor.|  
|CannotFindCert|No se puede buscar el certificado X.509 mediante el criterio de búsqueda concreto: StoreName, StoreLocation, FindType, FindValue.|  
|X509InvalidUsageTime|La hora concreta de uso del certificado X.509 no es válida. El tiempo de uso no se encuentra entre el tiempo NotBefore y NotAfter requerido.|  
|TraceCodeSecurityIdentityDeterminationFailure|No se puede determinar la identidad para una EndpointAddress.|  
|AsyncObjectAlreadyEnded|Ya se ha llamado al método End en este objeto de resultado asincrónico.|  
|ExternalDictionaryDoesNotContainAllRequiredStrings|El diccionario externo no contiene las definiciones de todas las cadenas necesarias. La cadena concreta no está disponible en el diccionario remoto.|  
|TraceCodeSecuritySessionKeyRenewalFaultReceived|La sesión de seguridad de cliente recibió un error renovación de clave del servidor.|  
|SAMLActionNameRequired|La cadena que representa la SamlAction no puede ser nula o de longitud 0.|  
|SignatureVerificationFailed|Error en la comprobación de la firma.|  
|TraceCodeSecurityContextTokenCacheFull|La caché del SecurityContextSecurityToken está completa.|  
|SAMLAssertionMissingMajorVersionAttributeOnRead|La MajorVersion para la SamlAssertion que se está leyendo falta o es de longitud 0.|  
|SamlAttributeClaimRightShouldBePossessProperty|Este constructor SamlAttribute requiere que el derecho de la demanda tenga el valor System.IdentityModel.Claims.Rights.PossessProperty.|  
|AuthorizationPolicyEvaluated|Se evalúa la directiva con el id. concreto.|  
|SAMLUnableToLoadCondtions<!-- the misspelling here is deliberate. -->|\<saml:conditions>No se pudo cargar el elemento.|  
|AESKeyLengthNotSupported|La clave de bits concreta no se admite. Solo se admiten claves de 128, 192 y 256 bits.|  
|UserNameCannotBeEmpty|El nombre de usuario no puede estar vacío.|  
|AlgorithmAndPublicKeyMisMatch|El algoritmo especificado y la clave pública no coinciden.|  
|SAMLUnableToLoadCondtion<!-- the misspelling here is deliberate. -->|\<saml:conditions>No se pudo cargar el elemento.|  
|SamlAssertionMissingSigningCredentials|Las SigningCredentials no se han establecido en la SamlAssertion. Se deben firmar las SamlAssertions, establezca un SigningCredentials válido en la SamlAssertion para continuar.|  
|SspiPayloadNotEncrypted|Los datos binarios no se cifraron con el contexto de seguridad de SSPI.|  
|SAMLAuthorizationDecisionShouldHaveOneActionOnRead|La SamlAuthorizationDecisionStatement que se lee no contiene ninguna SamlAction.|  
|TraceCodeSecurityBindingSecureOutgoingMessageFailure|El protocolo de seguridad no puede proteger el mensaje saliente.|  
|UndefinedUseOfPrefixAtAttribute|El prefijo concreto usado en el atributo concreto no tiene ningún espacio de nombres definido.|  
|NoInputIsSetForCanonicalization|Ninguna entrada está establecida para escribir la salida canonizada.|  
|TraceCodeSecurityPendingServerSessionAdded|Se agrega una sesión de seguridad pendiente al servidor.|  
|AsyncCallbackException|Una AsyncCallback produjo una excepción.|  
|PrivateKeyNotRSA|La clave privada no es una clave RSA.|  
|TraceCodeSecurityClientSessionKeyRenewed|La sesión de seguridad de cliente renovó la clave de sesión.|  
|SAMLAuthorizationDecisionStatementMissingDecisionAttributeOnRead|La 'Decisión' para la SamlAuthorizationDecisionStatement que se lee falta o es de longitud 0.|  
|SAMLAttributeNameAttributeRequired|El ‘Nombre’ especificado para un SamlAttribute no puede ser nulo ni de longitud 0.|  
|SamlSerializerRequiresExternalSerializers|El SamlSerializer requiere que un SecurityTokenSerializer serialice el SecurityKeyIdentifier presente en el token.|  
|UnableToResolveKeyReference|La resolución del token no puede resolver la referencia clave de seguridad concreta.|  
|UnsupportedKeyWrapAlgorithm|No se admite el algoritmo de ajuste de clave concreto.|  
|SAMLAssertionMissingIssuerAttributeOnRead|El ‘Emisor” de la SamlAssertion que se está leyendo falta o es de longitud 0.|  
|TraceCodeIssuanceTokenProviderUsingCachedToken|IssuanceTokenProvider utilizó el token de servicio almacenado en memoria caché.|  
|AESCryptGetKeyParamFailed|No se pudo obtener el parámetro de clave concreto.|  
|InvalidNamespaceForEmptyPrefix|El espacio de nombres no es válido para el prefijo vacío.|  
|AESCipherModeNotSupported|No se admite el modo de cifrado específico. Solo se admite CBC.|  
|ArgumentCannotBeEmptyString|El argumento debe ser una cadena no vacía.|  
|SAMLAssertionMissingMinorVersionAttributeOnRead|La MinorVersion para la SamlAssertion que se está leyendo falta o es de longitud 0.|  
|SpecifiedStringNotAvailableInDictionary|La cadena especificada no es una entrada en el diccionario actual.|  
|KerberosApReqInvalidOrOutOfMemory|El AP-REQ no es válido o el sistema no tiene suficiente memoria.|  
|FailLogonUser|Error con el LogonUser para el usuario especificado. Asegúrese de que el usuario tiene una cuenta de Windows válida.|  
|ValueMustBeNonNegative|El valor de este argumento no debe ser negativo.|  
|X509ValidationFail|Error en la validación del certificado X.509 especificado.|  
|TraceCodeSecuritySessionRequestorOperationSuccess|La operación de la sesión de seguridad se completó correctamente en el cliente.|  
|SAMLActionNameRequiredOnRead|La cadena que se lee para la SamlAction falta o es de longitud 0.|  
|KerberosMultilegsNotSupported|La identidad se especifica como UPN. La autenticación de un servicio que se ejecuta bajo una cuenta de usuario requiere multi-bifurcaciones de Kerberos, lo cual no se admite.|  
|SAMLAssertionIdRequired|El 'assertionId' para una SamlAssertion no puede ser nulo ni vacío.|  
|InvalidOperationForWriterState|La operación especificada no es válida en el estado de XmlWriter especificado.|  
|CannotValidateSecurityTokenType|El autenticador de tokens de seguridad especificado no puede validar un token del tipo especificado.|  
|X509FindValueMismatch|El X509FindType especificado requiere que el tipo del argumento findValue sea el valor especificado. El argumento findValue es de otro tipo.|  
|TraceCodeSecurityClientSessionCloseSent|La sesión de seguridad de cliente envió un mensaje de cierre.|  
|SuiteDoesNotAcceptAlgorithm|El algoritmo especificado no se acepta para la operación especificada por el conjunto de algoritmos especificado|  
|TraceCodeSecuritySessionRequestorOperationFailure|Se produjo un error en la operación de sesión de seguridad de cliente.|  
|SAMLUnableToLoadStatement|No se pudo cargar una SamlStatement.|  
|InnerReaderMustBeAtElement|El lector interno debe estar en el elemento.|  
|UnableToCreateTokenReference|No puede crear una referencia del token de seguridad.|  
|TraceCodeSecurityBindingIncomingMessageVerified|El protocolo de seguridad comprobó el mensaje entrante.|  
|ObjectIsReadOnly|El objeto es de solo lectura.|  
|TraceCodeSecurityClientSessionPreviousKeyDiscarded|La sesión de seguridad de cliente descartó la clave de sesión anterior.|  
|SAMLTokenTimeInvalid|El SamlToken no tiene una hora válida. El tiempo actual está fuera de la hora de Inicio y Expiración del token.|  
|TraceCodeSecurityIdentityVerificationSuccess|La comprobación de identidad se realizó correctamente.|  
|SigningTokenHasNoKeys|El token de la firma especificada no tiene claves.|  
|TraceCodeSecurityIdentityVerificationFailure|Error en la comprobación de identidad.|  
|AESCryptImportKeyFailed|Error al importar material de la clave.|  
|FailInitializeSecurityContext|Error en InitializeSecurityContent. Asegúrese de que el nombre de entidad de seguridad de servicio es correcto.|  
|TraceCodeStreamSecurityUpgradeAccepted|Se aceptó la actualización de seguridad de secuencia correctamente.|  
|SAMLAuthorityBindingRequiresLocation|El atributo ‘Location’ que se especifica en el SamlAuthorityBinding no puede ser nulo ni de longitud 0.|  
|PublicKeyNotDSA|La clave pública no es una clave DSA.|  
|ImpersonationLevelNotSupported|Los modos de autenticación que usan Kerberos no admiten el nivel de suplantación especificado. Especifique una identificación o nivel de suplantación válidos.|  
|RequiredTargetNotSigned|El elemento con el id. especificado ha de estar firmado, pero no lo estaba.|  
|SAMLAuthenticationStatementMissingAuthenticationInstanceOnRead|El atributo 'AuthenticationInstant' que se lee para una SamlAuthenticationStatement falta o es de longitud 0.|  
|SAMLEvidenceShouldHaveOneAssertionOnRead|La SamlEvidence que se lee no contenía una referencia a una SamlAssertion ni una SamlAssertion integrada.|  
|LengthOfArrayToConvertMustGreaterThanZero|La longitud de la matriz para convertir en un entero debe ser mayor de 0.|  
|InvalidAsyncResult|AsyncResult no válido.|  
|TraceCodeIssuanceTokenProviderRemovedCachedToken|IssuanceTokenProvider quitó el token de servicio caducado.|  
|IncorrectUserNameFormat|El formato del nombre de usuario no es válido. El formato del nombre de usuario debe tener el formato "nombre de usuario" o "dominio \\ \username.".|  
|TraceCodeExportSecurityChannelBindingEntry|Inicio de ExportChannelBinding de seguridad.|  
|UnsupportedInputTypeForTransform|El tipo de entrada especificado no se admite para la transformación.|  
|CannotFindDocumentRoot|No puede encontrar la raíz del documento.|  
|XmlBufferQuotaExceeded|El tamaño necesario para almacenar en búfer el contenido XML superó la cuota del búfer.|  
|TraceCodeSecuritySessionClosedResponseSendFailure|Se produjo un error al enviar un error de respuesta de cierre de sesión de seguridad al cliente.|  
|UnableToResolveReferenceInSamlSignature|No se pudo resolver la referencia especificada en la firma del SAML con AssertionID.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethod|Un SamlSubject requiere que se especifique un 'NameIdentifier' o 'ConfirmationMethod'. Faltaban ambos.|  
|SAMLAttributeMissingNamespaceAttributeOnRead|El ‘Espacio de nombres’ para el SamlAttribute que se está leyendo falta o es de longitud 0.|  
|SAMLSubjectConfirmationClauseMissingConfirmationMethodOnRead|Un 'ConfirmationMethod' no se puede encontrar en la SamlSubjectConfirmation que se lee.|  
|SecurityTokenRequirementHasInvalidTypeForProperty|El requisito del token tiene un tipo inesperado para la propiedad especificada. El tipo de propiedad esperado es de otro valor.|  
|TraceCodeNegotiationTokenProviderAttached|Se adjuntó NegotiationTokenProvider.|  
|TraceCodeSpnegoClientNegotiationCompleted|SpnegoTokenProvider completó la negociación de SSPI.|  
|SAMLUnableToLoadUnknownElement|El SamlSerializer seleccionado no puede deserializar este elemento. Registre un SamlSerializer personalizado para deserializar elementos personalizados.|  
|CreateSequenceRefused|El destino de RM ha rechazado la solicitud de la secuencia de creación.|  
|TraceCodeSecuritySessionRedirectApplied|Se redirigió la sesión de seguridad de cliente.|  
|SecurityTokenRequirementDoesNotContainProperty|El requisito del token no contiene la propiedad especificada.|  
|SAMLAttributeValueCannotBeNull|Se encontró que uno de los attributeValues situado en el SamlAttribute era un valor nulo. Asegúrese de que las listas no son nulas al crear el SamlAttribute.|  
|ValueMustBeGreaterThanZero|El valor de este argumento debe ser mayor de 0.|  
|TraceCodeNegotiationAuthenticatorAttached|Se adjuntó el NegotiationTokenAuthenticator.|  
|ValueMustBePositive||  
|SAMLAuthorizationDecisionShouldHaveOneAction|Una SamlAuthorizationDecisionStatement debe tener al menos una SamlAction.|  
|TraceCodeSecurityTokenAuthenticatorClosed|Se cerró el autenticador de seguridad de tokens.|  
|TraceCodeSecurityAuditWrittenSuccess|El registro de auditoría de seguridad se escribe correctamente.|  
|PrivateKeyNotDSA|La clave privada no es una clave DSA.|  
|MessageNumberRollover|Se ha superado el número de secuencias máximo para esta secuencia.|  
|AESPaddingModeNotSupported|No se admite el modo de relleno especificado. Solo se admite PKCS7 e ISO10126.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethodOnRead|Los elementos requeridos 'NameIdentifier' y 'ConfirmationMethod' no se encuentran para el SamlSubject que se está leyendo.|  
|TraceCodeSecurityAuditWrittenFailure|Se produjo un error al escribir en el registro de auditoría de seguridad.|  
|UnsupportedCryptoAlgorithm|El algoritmo de la clave criptográfica especificado no se admite en este contexto.|  
|SigningTokenHasNoKeysSupportingTheAlgorithmSuite|El token firmado no tiene ninguna clave que admita el conjunto de algoritmos especificado.|  
|SAMLNameIdentifierMissingIdentifierValueOnRead|Falta la cadena 'Identifier' del SamlNameIdentifier que se está leyendo.|  
|SAMLSubjectStatementRequiresSubject|La declaración de sujeto del SAML requiere que se especifique un sujeto SAML.|  
|TraceCodeSslClientCertMissing|El cliente de SSL remoto no proporcionó un certificado necesario.|  
|SAMLTokenVersionNotSupported|No se admiten la versión principal especificada y no se admite la versión secundaria.|  
|TraceCodeConfigurationIsReadOnly|La configuración es de solo lectura.|  
|TraceCodeSecuritySessionRenewFaultSendFailure|Se produjo un error al enviar un error de renovación en la clave de sesión de seguridad al cliente.|  
|TraceCodeSecurityInactiveSessionFaulted|Error de una sesión de seguridad inactiva por el servidor.|  
|SAMLUnableToLoadAttribute|No se cargó un SamlAttribute.|  
|Psha1KeyLengthInvalid|La longitud de la clave PSHA1 especificada no es válida.|  
|KeyIdentifierCannotCreateKey|Este SecurityKeyIdentifier no tiene ninguna cláusula que pueda crear una clave.|  
|X509IsInUntrustedStore|El certificado X.509 especificado está en un almacén de certificados que no es de confianza.|  
|UnexpectedXmlChildNode|El nodo secundario XML especificado de tipo especificado es inesperado para el elemento especificado.|  
|TokenDoesNotMeetKeySizeRequirements|El token especificado no cumple los requisitos de tamaño de la clave para el conjunto de algoritmos especificado.|  
|TraceCodeSecuritySessionRequestorStartOperation|Una operación de sesión de seguridad se inició en el cliente.|  
|InvalidHexString|Formato de cadena hexadecimal no válido.|  
|SamlAttributeClaimResourceShouldBeAString|Este constructor SamlAttribute requiere que el recurso de la demanda sea del tipo 'cadena.'|  
|SamlSigningTokenNotFound|Se firma la SamlAssertion pero no se puede encontrar el token que firmó la SamlAssertion. Asegurarse que la SecurityTokenResolver contiene el token que firmó la SamlAssertion.|  
|TraceCodeSecuritySpnToSidMappingFailure|El ServicePrincipalName no pudo asignarse a un SecurityIdentifier.|  
|UnableToCreateSignatureFormatterFromAsymmetricCrypto|No se pudo crear un formateador de firmas para el algoritmo especificado a partir de la clave criptográfica asimétrica especificada.|  
|TraceCodeSecurityServerSessionClosedFaultSent|La sesión de seguridad de servidor envió un error de cierre de sesión al cliente.|  
|UnableToFindPrefix|No se pudo encontrar el prefijo para el prefijo visiblemente utilizado especificado en el elemento especificado.|  
|TraceCodeSecurityTokenAuthenticatorOpened|Se abrió el autenticador de tokens de seguridad.|  
|RequiredAttributeMissing|El atributo especificado se requiere en el elemento especificado.|  
|LocalIdCannotBeEmpty|El localId no puede estar vacío. Especifique un ‘localId’ válido.|  
|ValueMustBeInRange|El valor de este argumento debe estar dentro del rango especificado.|  
|TraceCodeIssuanceTokenProviderBeginSecurityNegotiation|IssuanceTokenProvider inició una nueva negociación de seguridad.|  
|InvalidNtMapping|El certificado X.509 especificado no puede asignarse a una cuenta de Windows. Se requiere el nombre alternativo de sujeto de UPN.|  
|AESCryptSetKeyParamFailed|No se estableció el parámetro de clave especificado.|  
|TraceCodeSecuritySessionClosedResponseReceived|La sesión de seguridad de cliente recibió una respuesta cerrada del servidor.|  
|UnableToCreateSignatureDeformatterFromAsymmetricCrypto|No se pudo crear un desformateador de firmas para el algoritmo especificado a partir de la clave criptográfica asimétrica especificada.|  
|TraceCodeIdentityModelAsyncCallbackThrewException|Una devolución de llamada asincrónica produjo una excepción.|  
|LengthMustBeGreaterThanZero|La longitud de este argumento debe ser mayor de 0.|  
|FoundMultipleCerts|Se encontraron varios certificados X.509 mediante el criterio de búsqueda especificado: StoreName, StoreLocation, FindType, FindValue. Proporcione un valor de búsqueda más concreto.|  
|AtLeastOneTransformRequired|El elemento Transforms debe contener por lo menos una transformación.|  
|SAMLTokenNotSerialized|La SamlAssertion no se pudo serializar a XML. Vea la excepción interna para obtener detalles.|  
|TraceCodeSecurityBindingOutgoingMessageSecured|El protocolo de seguridad protegió el mensaje saliente.|  
|KeyIdentifierClauseDoesNotSupportKeyCreation|La SecurityKeyIdentifierClause no admite la creación de claves.|  
|UnableToResolveTokenReference|La resolución del token no puede resolver la referencia del token especificada.|  
|UnsupportedEncryptionAlgorithm|No se admite el algoritmo de cifrado especificado.|  
|SamlSerializerUnableToWriteSecurityKeyIdentifier|El SamlSerializer no contiene un SecurityTokenSerializer capaz de serializar el SecurityKeyIdentifier determinado. Si está utilizando un SecurityKeyIdentifier personalizado, debe proporcionar un SecurityTokenSerializer personalizado.|  
|SAMLAttributeShouldHaveOneValue|No se encontraron valores de atributos. Un atributo SamlAttribute debe tener por lo menos un valor de atributo.|  
|TraceCodeSecurityBindingVerifyIncomingMessageFailure|El protocolo de seguridad no puede comprobar el mensaje entrante.|  
|SamlSigningTokenMissing|La SamlAssertion pasada al SamlSecurityTokenAuthenticator no contiene un token de firma.|  
|NoPrivateKeyAvailable|No está disponible ninguna clave privada.|  
|ValueMustBeOne|El valor de este argumento debe ser 1.|  
|TraceCodeSecurityPendingServerSessionRemoved|El servidor activó una sesión de seguridad pendiente.|  
|TraceCodeImportSecurityChannelBindingExit|Seguridad ImportChannelBinding acabada.|  
|X509CertStoreLocationNotValid|La StoreLocation debe ser LocalMachine o CurrentUser.|  
|SettingdMayBeModifiedOnlyWhenTheWriterIsInStartState|Se pueden modificar los valores del sistema de escritura solo cuando el sistema de escritura está en el estado Inicio.|  
|ArgumentInvalidCertificate|El certificado no es válido.|  
|DigestVerificationFailedForReference|Error en la comprobación del resumen para la Referencia especificada.|  
|SAMLAuthorityBindingRequiresBinding|El atributo ‘Binding’ especificado en el SamlAuthorityBinding no puede ser nulo ni de longitud 0.|  
|AESInsufficientOutputBuffer|El búfer de salida debe ser mayor que los bytes especificados.|  
|SAMLAuthorityBindingMissingBindingOnRead|El atributo 'Binding' para el SamlAuthorityBinding que se está leyendo falta o es de longitud 0.|  
|SAMLAuthorityBindingInvalidAuthorityKind|El SamlAuthorityBinding que se está leyendo no tiene un AuthorityKind válido. El formato del AuthorityKind debe ser un QName.|  
|ProvidedNetworkCredentialsForKerberosHasInvalidUserName|Las NetworkCredentials proporcionadas para el token de Kerberos no tiene un Nombre de usuario válido.|  
|SSPIPackageNotSupported|No se admite el paquete de SSPI especificado.|  
|TokenCancellationNotSupported|El proveedor de tokens especificado no admite la cancelación de tokens.|  
|UnboundPrefixInQName|Un prefijo no enlazado se utiliza en el nombre completo especificado.|  
|SAMLAuthorizationDecisionResourceRequired|El 'recurso' especificado a la SamlAuthorizationDecisionStatement no puede ser nulo ni de longitud 0.|  
|TraceCodeSecurityNegotiationProcessingFailure|Error al procesar la negociación de seguridad del servicio.|  
|SAMLAssertionIssuerRequired|El 'Emisor' especificado  para una SamlAssertion no puede ser nulo ni vacío.|  
|UnableToCreateHashAlgorithmFromAsymmetricCrypto|No se puede crear un HashAlgorithm para el algoritmo especificado a partir de la clave criptográfica asimétrica especificada.|  
|SamlUnableToExtractSubjectKey|El SecurityKeyIdentifier que se encontró en el SamlSubject no se puede resolver en un SecurityToken. La SecurityTokenResolver debe contener un SecurityToken como en el que el SecurityKeyIdentifier se resuelve.|  
|ChildNodeTypeMissing|El elemento XML especificado no tiene ningún elemento secundario del tipo especificado.|  
|TraceCodeSecurityPendingServerSessionClosed|El servidor cerró la sesión de seguridad pendiente.|  
|TraceCodeSecuritySessionCloseResponseSent|La sesión de seguridad del servidor envió una respuesta de cierre al cliente.|  
|TraceCodeSecurityIdentityHostNameNormalizationFailure|No se puede normalizar la parte HostName de una dirección de extremo.|  
|FailAcceptSecurityContext|Error en el AcceptSecurityContext.|  
|EmptyXmlElementError|El elemento especificado no puede estar vacío.|  
|PrefixNotDefinedForNamespace|Un prefijo para el espacio de nombres especificado no se define en este contexto y no se puede declarar.|  
|SAMLAuthorizationDecisionHasMoreThanOneEvidence|Se encontró que la SamlAuthorizationDecisionStatement que se está leyendo contiene más de una Prueba. Esto no está permitido.|  
|SamlTokenAuthenticatorCanOnlyProcessSamlTokens|El SamlSecurityTokenAuthenticator solo puede procesar SamlSecurityTokens. Se recibió el SecurityTokenType especificado.|  
|SAMLAttributeStatementMissingAttributeOnRead|El SamlAttributeStatement que se está leyendo no contiene elementos 'SamlAttribute'. Esto no está permitido.|  
|CouldNotFindNamespaceForPrefix|No se puede buscar el espacio de nombres para el prefijo especificado.|  
|TraceCodeExportSecurityChannelBindingExit|Seguridad ExportChannelBinding acabada.|  
|AESCryptDecryptFailed|No se pudo descifrar los datos especificados.|  
|SAMLAttributeNamespaceAttributeRequired|El ‘Espacio de nombres’ especificado para un SamlAttribute no puede ser nulo ni de longitud 0.|  
|TraceCodeSpnegoServiceNegotiationCompleted|SpnegoTokenAuthenticator completó la negociación de SSPI.|  
|TraceCodeSecurityServerSessionRenewalFaultSent|La sesión de seguridad de servidor envió un error de renovación de clave al cliente.|  
|AlgorithmMismatchForTransform|Tuvo lugar una desigualdad en el algoritmo para la transformación.|  
|UserNameAuthenticationFailed|Error en la autenticación de un nombre de usuario/contraseña mediante el mecanismo especificado. No se autentica el usuario.|  
|SamlInvalidSigningToken|La SamlAssertion se ha firmado con un token que no se validó según el protocolo. Si está utilizando certificados X.509, examine su semántica de validación.|  
|TraceCodeSecurityServerSessionKeyUpdated|El servidor actualizó la clave de sesión de seguridad.|  
|TraceCodeSecurityServerSessionCloseReceived|La sesión de seguridad del servidor recibió un mensaje de cierre desde el cliente.|  
|SAMLAuthenticationStatementMissingSubject|La SamlAuthenticationStatement no dispone de la SamlSubjectStatement necesaria.|  
|UnexpectedEndOfFile|Final de archivo inesperado.|  
|UnsupportedAlgorithmForCryptoOperation|El algoritmo especificado no se admite para la operación especificada.|  
|XmlLangAttributeMissing|Falta el atributo xml:lang necesario.|  
|TraceCodeSecurityImpersonationSuccess|Se realizó con éxito la suplantación de seguridad en el servidor.|  
|SAMLAuthorityBindingMissingLocationOnRead|El atributo 'Location' para el SamlAuthorityBinding que se está leyendo falta o es de longitud 0.|  
|SAMLAttributeStatementMissingSubjectOnRead|Falta el elemento 'SamlSubject' para la SamlAttributeStatement.|  
|SAMLAuthorizationDecisionStatementMissingSubjectOnRead|Falta el elemento 'SamlSubject' para la SamlAuthorizationDecisionStatement que se está leyendo.|  
|SAMLBadSchema|Al leer una SamlAssertion, se encontró que este elemento especificado no cumple con el esquema.|  
|SAMLAssertionIDIsInvalid|La 'assertionId' especificada para una SamlAssertion debe comenzar con una letra o '_'.|  
|TraceCodeSecurityActiveServerSessionRemoved|El servidor quitó una sesión de seguridad activa.|  
|UnableToCreateKeyedHashAlgorithmFromSymmetricCrypto|No se puede crear un keyedHashAlgorithm para el algoritmo especificado a partir de la clave criptográfica simétrica especificada.|  
|SAMLAuthenticationStatementMissingAuthenticationMethod|El 'AuthenticationMethod' especificado para una SamlAuthenticationStatement no puede ser nulo ni de longitud 0.|  
|TraceCodeSecurityImpersonationFailure|Error en la suplantación de seguridad en el servidor.|  
|Valor predeterminado|(Es el valor predeterminado).|  
|UnsupportedNodeTypeInReader|No se admite el tipo de nodo especificado con el nombre especificado.|
