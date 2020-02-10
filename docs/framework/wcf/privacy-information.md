---
title: Información de privacidad de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: b724ff1ce85442f64980fdc972188705992d5a4f
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094987"
---
# <a name="windows-communication-foundation-privacy-information"></a>Información de privacidad de Windows Communication Foundation
Microsoft se compromete a proteger la privacidad de los usuarios finales. Al compilar una aplicación mediante Windows Communication Foundation (WCF), versión 3,0, la aplicación puede afectar a la privacidad de los usuarios finales. Por ejemplo, su aplicación puede recoger explícitamente información de contacto del usuario o puede solicitar o enviar información a través de Internet a su sitio web. Si incrusta la tecnología de Microsoft en su aplicación, esa tecnología puede tener su propio comportamiento que podría afectar a la privacidad. WCF no envía ninguna información a Microsoft desde su aplicación a menos que usted o el usuario final decida enviarla.  
  
## <a name="wcf-in-brief"></a>WCF en breve  
 WCF es un marco de mensajería distribuida que usa el marco de Microsoft .NET que permite a los desarrolladores crear aplicaciones distribuidas. Los mensajes comunicados entre dos aplicaciones contienen encabezado e información del cuerpo.  
  
 Los encabezados pueden contener enrutamiento de mensajes, información de seguridad, transacciones, y más, en función de los servicios utilizados por la aplicación. Generalmente, se cifran los mensajes de forma predeterminada. Una excepción es cuando se utiliza `BasicHttpBinding`, diseñado para el uso con Servicio Web no seguros, heredados. Como diseñador de aplicaciones, es el responsable del último diseño. Los mensajes del cuerpo de SOAP contienen datos específicos de la aplicación; sin embargo, estos datos, como la información personal definida por la aplicación, se pueden proteger mediante el cifrado de WCF o las características de confidencialidad. Las secciones siguientes describen las características que pueden afectan a la privacidad.  
  
## <a name="messaging"></a>Mensajería  
 Cada mensaje de WCF tiene un encabezado de dirección que especifica el destino del mensaje y dónde debe ir la respuesta.  
  
 El componente de dirección de una dirección de extremo es un Identificador uniforme de recursos (URI) que identifica el extremo. La dirección puede ser una dirección de red o una dirección lógica. La dirección puede incluir nombre del equipo (nombre del host, nombre de dominio completo) y una dirección IP. La dirección del punto de conexión también puede contener un identificador único global (GUID) o una colección de GUID para el direccionamiento temporal utilizado para discernir cada dirección. Cada mensaje contiene un id. de mensaje que es un GUID. Esta característica sigue la regla de referencia WS-Addressing.  
  
 La capa de mensajería de WCF no escribe información personal en el equipo local. Sin embargo, podría propagar información personal en el nivel de la red si un programador del servicio ha creado un servicio que expone dicha información (por ejemplo, utilizando el nombre de una persona en un nombre de extremo o incluso información personal en el Lenguaje de descripción de servicios Web (WSDL) del extremo pero no requiero que los clientes utilicen http para tener acceso al WSDL). Además, si un desarrollador ejecuta la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) en un punto de conexión que expone información personal, la salida de la herramienta podría contener esa información y el archivo de salida se escribe en el disco duro local.  
  
## <a name="hosting"></a>Hospedaje  
 La característica de hospedaje de WCF permite a las aplicaciones iniciarse a petición o habilitar el uso compartido de puertos entre varias aplicaciones. Una aplicación WCF se puede hospedar en Internet Information Services (IIS), de forma similar a ASP.NET.  
  
 Al hospedarse, no se expone ninguna información específica sobre la red y no mantiene los datos en el equipo.  
  
## <a name="message-security"></a>Seguridad de los mensajes  
 La seguridad de WCF proporciona las capacidades de seguridad para las aplicaciones de mensajería. Las funciones de seguridad proporcionadas incluyen autenticación y autorización.  
  
 La autenticación se lleva a cabo pasando las credenciales entre clientes y servicios. La autenticación se puede llevar a cabo a través de la seguridad de nivel de transporte o a través de seguridad del nivel del mensaje SOAP, tal y como se muestra a continuación:  
  
- En seguridad del mensaje SOAP, la autenticación se realiza a través de las credenciales como el nombre de usuario/contraseñas, certificados X.509, vales de Kerberos y tokens de SAML, los cuales podrían contener datos personales, en función del emisor.  
  
- En el uso de seguridad de transporte, la autenticación se realiza a través de los mecanismos de autenticación de transporte tradicionales como los esquemas de autenticación de HTTP (Básica, implícita, Negociada, Autorización de Windows Integrada, NTLM, Ninguna, y Anónima) y autenticación de formularios.  
  
 La autenticación puede producir una sesión segura establecida entre los extremos en comunicación. Un GUID, cuya duración es igual a la sesión de seguridad, identifica la sesión. La tabla siguiente muestra lo que se guarda y dónde.  
  
|data|Storage|  
|----------|-------------|  
|Las credenciales de presentación, como el nombre de usuario, certificados X.509, tokens de Kerberos, y referencias a las credenciales.|Mecanismos de administración de credencial de Windows estándar como el almacén de certificados de Windows.|  
|Información de pertenencia del usuario, como nombres de usuario y contraseñas.|Proveedores de pertenencia a ASP.NET.|  
|Información de identidad sobre el servicio utilizado para autenticar el servicio a los clientes.|La dirección del punto de conexión del servicio.|  
|Información del agente de llamada.|Registros de auditoría.|  
  
## <a name="auditing"></a>Auditoría  
 La auditoría registra si se ha completado o se ha producido un error en la autenticación y eventos de autorización. Los registros de la auditoría contienen los datos siguientes: servicio URI, acción URI y la identificación del agente de llamada.  
  
 La auditoría también registra cuando el administrador modifica la configuración de registro de mensajes (activándolo o desactivándolo), porque el registro de mensajes puede registrar los datos específicos de la aplicación en encabezados y cuerpos. En Windows XP, se registra un registro en el registro de eventos de la aplicación. En Windows Vista y Windows Server 2003, se registra un registro en el registro de eventos de seguridad.  
  
## <a name="transactions"></a>Transacciones  
 La característica de transacciones proporciona servicios transaccionales a una aplicación WCF.  
  
 Los encabezados de las transacciones utilizados en la propagación de la transacción pueden contener los id. de transacción o id. de inscripción, que son GUID.  
  
 La característica de las transacciones utiliza el Administrador de transacciones (un componente de Windows) de Microsoft DTC (Coordinador de transacciones distribuidas) para administrar el estado de la transacción. De forma predeterminada, se cifran las comunicaciones entre Administradores de las Transacciones. Los administradores de transacciones pueden registrar referencias de punto de conexión, id. de transacción e id. de inscripción como parte de su estado duradero. La duración del archivo de registro del Administrador de la Transacción determina la duración de este estado. El servicio de MSDTC posee y mantiene este registro.  
  
 La característica Transacciones implementa los estándares WS-Coordination y WS-Atomic Transaction.  
  
## <a name="reliable-sessions"></a>Sesiones de confianza  
 Las sesiones confiables en WCF proporcionan la transferencia de mensajes cuando se producen errores de transporte o intermedios. Incluso proporcionan una transferencia de mensajes,, exactamente una vez, cuando el transporte subyacente desconecta (por ejemplo, una conexión TCP en una red inalámbrica) o pierde un mensaje (un proxy HTTP al colocar un mensaje de salida o entrante). Las sesiones de confianza también recuperan el mensaje reordenando (como puede pasar en el caso de enrutamiento de varias rutas de acceso), conservando el orden en el que se enviaron los mensajes.  
  
 Las sesiones de confianza se implementan utilizando el protocolo WS-ReliableMessaging (WS-RM). Agregan los encabezados WS-RM que contienen información de la sesión, la cual se utiliza para identificar todos los mensajes asociados a una sesión de confianza determinada. Cada sesión de WS-RM tiene un identificador, que es un GUID.  
  
 No se conserva información personal en el equipo del usuario final.  
  
## <a name="queued-channels"></a>Canals en la cola  
 Las colas almacenan mensajes de una aplicación emisora en nombre de una aplicación receptora y, a continuación, reenvían estos mensajes a la aplicación receptora. Ayudan a garantizar la transferencia de mensajes desde aplicaciones de envío a aplicaciones de recepción cuando, por ejemplo, la aplicación receptora es transitoria. WCF proporciona compatibilidad para la puesta en cola mediante Microsoft Message Queuing (MSMQ) como transporte.  
  
 La característica de los canales en cola no agrega encabezados a un mensaje. En su lugar, crea un mensaje de Message Queuing con propiedades de mensaje de Message Queuing adecuadas establecidas e invoca los métodos Message Queuing para colocar el mensaje en la cola de Message Queuing. Message Queuing es un componente opcional distribuido con Windows.  
  
 La característica de canales en cola no conserva ninguna información en el equipo del usuario final, ya que utiliza Message Queue Server como infraestructura de cola.  
  
## <a name="com-integration"></a>Integración de COM+  
 Esta característica ajusta la funcionalidad existente de COM y COM+ para crear servicios que sean compatibles con los servicios WCF. Esta característica no utiliza encabezados específicos y no conserva los datos en el equipo del usuario final.  
  
## <a name="com-service-moniker"></a>Moniker de servicio COM  
 Esto proporciona un contenedor no administrado a un cliente de WCF estándar. Esta característica no tiene encabezados específicos en la conexión ni conserva datos en el equipo.  
  
## <a name="peer-channel"></a>Canal del mismo nivel  
 Un canal del mismo nivel permite el desarrollo de aplicaciones multiparte con WCF. La mensajería multipartidaria se produce en el contexto de una malla. Un nombre al cual se pueden unir los nodos identifica las mallas. Cada nodo del canal del mismo nivel crea un agente de escucha de TCP en un puerto especificado por el usuario y establece las conexiones con otros nodos en la malla para garantizar la resiliencia. Para conectar a otros nodos en la malla, los nodos también intercambian algunos datos, incluso la dirección del agente de escucha y las direcciones IP del equipo, con otros nodos de la malla. Los mensajes enviados en la malla pueden contener información de seguridad que pertenece al remitente para evitar que se suplante y se manipule el mensaje.  
  
 No se almacena información personal en el equipo del usuario final.  
  
## <a name="it-professional-experience"></a>Experiencia profesional de TI  
  
### <a name="tracing"></a>Seguimiento  
 La característica de diagnóstico de la infraestructura de WCF registra los mensajes que pasan a través de las capas del modelo de transporte y servicio, así como las actividades y eventos asociados a estos mensajes. Esta característica está desactivada de forma predeterminada. Se habilita mediante el archivo de configuración de la aplicación y el comportamiento del seguimiento se puede modificar con el proveedor de WMI de WCF en tiempo de ejecución. Cuando se habilita, la infraestructura de la traza emite una traza de diagnóstico que contiene mensajes, actividades y eventos de procesamiento a los agentes de escucha configurados. Las opciones de configuración del agente de escucha del administrador determinan el formato y ubicación del resultado, pero es normalmente un archivo con formato XML. El administrador es responsable de establecer la lista de control de acceso (ACL) en los archivos de seguimiento. En particular, cuando está hospedado por el Sistema de Activación de Windows (WAS), el administrador debería asegurarse de que los archivos no provienen del directorio raíz virtual público si no se desea.  
  
 Hay dos tipos de traza: registro de mensajes y traza de diagnóstico de modelo de servicio, descritos en la sección siguiente. Cada tipo se configura a través de su propio origen de traza: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> y <xref:System.ServiceModel>. Estos orígenes de traza de registro capturan locales a la aplicación.  
  
### <a name="message-logging"></a>Registro de mensajes  
 El origen de traza del registro de mensajes (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) permite a un administrador registrar los mensajes que fluyen a través del sistema. A través de la configuración, el usuario puede decidir si quiere registrar mensajes completos o solamente encabezados de mensaje, registrar en el transporte y/o niveles de modelo de servicio y si quiere incluir mensajes incorrectos. Además, el usuario puede configurar el filtro para restringir qué mensajes están registrados.  
  
 De forma predeterminada, el registro de mensajes está deshabilitado. El administrador del equipo local puede evitar que el administrador del nivel de la aplicación active el registro de mensajes.  
  
#### <a name="encrypted-and-decrypted-message-logging"></a>Registro de mensajes cifrado y descifrado  
 Los mensajes se registran, cifran o descifran, tal y como se ha descrito en los términos siguientes.  
  
 Registro de transporte  
 Registra los mensajes recibidos y enviados en el nivel de transporte. Estos mensajes contienen todos los encabezados y se pueden cifrar antes de ser enviados en la conexión y al recibirse.  
  
 Si se cifran los mensajes antes de ser enviados en la conexión y cuando se reciben, están registrados y cifrados también. Una excepción es cuando se utiliza un protocolo de seguridad (https): están registrados y descifrado antes de ser enviados y después de ser recibidos, incluso si se cifran en la conexión.  
  
 Registro del servicio  
 Registra mensajes recibidos o enviados en el nivel de modelo del servicio, después de que se haya producido el procesamiento del encabezado del canal procesar, justo antes y después de escribir el código de usuario.  
  
 Se descifran los mensajes registrados en este nivel incluso si se protegieron y cifraron en la conexión.  
  
 Registro de mensajes incorrectos  
 Registra mensajes que la infraestructura de WCF no puede comprender ni procesar.  
  
 Los mensajes están registrados tal cual, es decir, cifrados o no  
  
 Cuando los mensajes se registran en un formato descifrado o sin cifrar, de forma predeterminada, WCF quita las claves de seguridad y potencialmente información personal de los mensajes antes de registrarlos. Las secciones siguientes describen qué información se quita, y cuándo. El administrador del equipo e implementador de la aplicación deben tomar ciertas medidas de configuración para cambiar el comportamiento predeterminado con el fin de registrar las claves y potencialmente datos personales.  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a>Información quitada de los encabezados del mensaje al registrar mensajes descifrados/no cifrados  
 Cuando los mensajes están registrados en forma de descifrados/no cifrados, las claves de seguridad y potencialmente los datos personales se quitan de forma predeterminada de los encabezados del mensaje y los cuerpos del mensaje antes de registrarse. En la lista siguiente se muestra lo que WCF considera claves y potencialmente información personal.  
  
 Claves que se quitan:  
  
 \- para xmlns: elemento WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" y xmlns: elemento WST = "http://schemas.xmlsoap.org/ws/2005/02/trust"  
  
 wst:BinarySecret  
  
 wst:Entropy  
  
 \- para xmlns: wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" y xmlns: wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Password  
  
 wsse:Nonce  
  
 Datos personales posibles que se quitan:  
  
 \- para xmlns: wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" y xmlns: wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Username  
  
 wsse:BinarySecurityToken  
  
 \- para xmlns: SAML = "urn: oasis: names: TC: SAML: 1.0: Assertion", se quitan los elementos en negrita (a continuación):  
  
 Aserción de \<  
  
 MajorVersion="1"  
  
 MinorVersion="1"  
  
 AssertionId =" [ID]"  
  
 Issuer="[string]"  
  
 IssueInstant="[dateTime]"  
  
 >  
  
 \<condiciones NotBefore = "[dateTime]" NotOnOrAfter = "[dateTime]" >  
  
 \<AudienceRestrictionCondition >  
  
 \<audiencia > [URI]\</Audience > +  
  
 \</AudienceRestrictionCondition > *  
  
 \<DoNotCacheCondition/> *  
  
 <\!--tipo base abstracto  
  
 \<condición/> *  
  
 -->  
  
 \<>/Conditions?  
  
 \<consejos >  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > *  
  
 \<aserción > [Assertion]\</Assertion > *  
  
 [any]*  
  
 \<>/Advice?  
  
 <\!: tipos base abstractos  
  
 \<instrucción/> *  
  
 \<SubjectStatement >  
  
 \<asunto >  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation >  
  
 \<ConfirmationMethod > [anyURI]\</ConfirmationMethod > +  
  
 \<SubjectConfirmationData > [any]\</SubjectConfirmationData >?  
  
 \<DS: KeyInfo >...\</DS: KeyInfo >?  
  
 \<>/SubjectConfirmation?  
  
 \</Subject >  
  
 \</SubjectStatement > *  
  
 -->  
  
 \<AuthenticationStatement  
  
 AuthenticationMethod =" [uri]"  
  
 AuthenticationInstant="[dateTime]"  
  
 >  
  
 [Subject]  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 < AuthorityBinding  
  
 AuthorityKind =" [QName]"  
  
 Location="[uri]"  
  
 Enlace =" [uri]"  
  
 />*  
  
 \</AuthenticationStatement > *  
  
 \<AttributeStatement >  
  
 [Subject]  
  
 \<atributo)  
  
 AttributeName="[string]"  
  
 AttributeNamespace =" [uri]"  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</Attribute > +  
  
 \</AttributeStatement > *  
  
 \<AuthorizationDecisionStatement  
  
 Resource =" [uri]"  
  
 Decision = "[permitir&#124;denegar&#124;indeterminados]"  
  
 >  
  
 [Subject]  
  
 \<Action namespace = "[URI]" > [cadena]\</Action > +  
  
 \<Evidence >  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > +  
  
 \<aserción > [Assertion]\</Assertion > +  
  
 \<>/Evidence?  
  
 \</AuthorizationDecisionStatement > *  
  
 \</Assertion >  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a>Información quitada de los cuerpos del mensaje al registrar mensajes descifrados/no cifrados  
 Como se ha descrito anteriormente, WCF quita las claves y la información personal potencialmente conocida de los encabezados de mensaje para los mensajes descifrados/no cifrados registrados. Además, WCF quita las claves y los datos personales potencialmente conocidos de los cuerpos de mensaje de los elementos de cuerpo y las acciones de la lista siguiente, que describen los mensajes de seguridad implicados en el intercambio de claves.  
  
 Para los siguientes espacios de nombres:  
  
 xmlns: elemento WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" y xmlns: elemento WST = "http://schemas.xmlsoap.org/ws/2005/02/trust" (por ejemplo, si no hay ninguna acción disponible)  
  
 La información se quita de estos elementos del cuerpo, lo cual implica intercambio de claves:  
  
 wst:RequestSecurityToken  
  
 wst:RequestSecurityTokenResponse  
  
 wst:RequestSecurityTokenResponseCollection  
  
 La información también se quita en cada una de las acciones siguientes:  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a>No se quita información de los encabezados y datos del cuerpo específicos de la aplicación  
 WCF no realiza un seguimiento de la información personal en encabezados específicos de la aplicación (por ejemplo, cadenas de consulta) o datos del cuerpo (por ejemplo, el número de la tarjeta de crédito).  
  
 Cuando el registro de mensajes está activado, los datos personales en encabezados específicos de la aplicación e información del cuerpo pueden estar visibles en los registros. De nuevo, el implementador de la aplicación es el responsable de establecer las ACL en los archivos de registro y configuración. También pueden desactivar el registro si no quieren que esta información esté visible, o bien filtrar esta información de los archivos de registro una vez que se ha registrado.  
  
### <a name="service-model-tracing"></a>Traza de modelo de servicio  
 El origen de la traza de modelo de servicio (<xref:System.ServiceModel>) habilita la traza de las actividades y el segumiento de eventos relacionados con el procesamiento de mensajes. Esta característica utiliza la funcionalidad de diagnóstico del marco .NET de <xref:System.Diagnostics>. Como con la propiedad <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>, el usuario puede configurar la ubicación y su ACL mediante los archivos de configuración de la aplicación del marco .NET. Como con el registro de mensajes, la ubicación del archivo se configura siempre cuando el administrador habilita la traza; de este modo, el administrador controla el ACL.  
  
 Las trazas contienen los encabezados del mensaje cuando un mensaje está en ámbito. Se aplican las mismas reglas para ocultar los posibles datos personales en encabezados del mensaje de la sección anterior: los datos personales previamente identificados se quitan de forma predeterminada de los encabezados en trazas. El administrador del equipo y el implementador de la aplicación deben modificar la configuración para registrar potencialmente datos personales. Sin embargo, los datos personales contenidos en encabezados específicos de la aplicación están registrados en trazas. El implementador de la aplicación es el responsable de establecer las ACL en los archivos de seguimiento y configuración. También pueden desactivar el seguimiento para ocultar esta información o filtrar esta información de los archivos de seguimiento después de registrarla.  
  
 Como parte de la traza de ServiceModel, los id. únicos (llamados id. de actividad y normalmente un GUID) vinculan actividades diferentes juntas como un mensaje fluye a través de diferentes partes de la infraestructura.  
  
#### <a name="custom-trace-listeners"></a>Agentes de escucha de traza personalizados  
 Para el registro y la traza de mensajes, se puede configurar un agente de escucha de traza personalizado que puede enviar rastros y mensajes en la conexión (por ejemplo, a una base de datos remota). El implementador de la aplicación es el responsable de configurar agentes de escucha personalizados o habilitar los usuarios para ello. También son responsables de cualquier información personal expuesta en la ubicación remota y de aplicar correctamente las ACL a esta ubicación.  
  
### <a name="other-features-for-it-professionals"></a>Otras características para profesionales de TI  
 WCF tiene un proveedor de WMI que expone la información de configuración de la infraestructura de WCF a través de WMI (incluido con Windows). De forma predeterminada, la interfaz WMI está disponible para los administradores.  
  
 La configuración de WCF usa el mecanismo de configuración de .NET Framework. Los archivos de configuración están almacenados en el equipo. El desarrollador de aplicaciones y el administrador crean los archivos de configuración y ACL para cada uno de los requisitos de la aplicación. Un archivo de configuración puede contener las direcciones del punto de conexión y vínculos a los certificados en el almacén de certificados. Los certificados se pueden usar para proporcionar los datos de la aplicación con el fin de configurar varias propiedades de las características utilizadas por la aplicación.  
  
 WCF también usa la funcionalidad de volcado de .NET Framework proceso mediante una llamada al método <xref:System.Environment.FailFast%2A>.  
  
### <a name="it-pro-tools"></a>IT Pro Tools  
 WCF también proporciona las siguientes herramientas profesionales de ti, que se distribuyen en el Windows SDK.  
  
#### <a name="svctraceviewerexe"></a>SvcTraceViewer.exe  
 El visor muestra los archivos de seguimiento de WCF. El visor muestra la información cualquier contenida en los seguimientos.  
  
#### <a name="svcconfigeditorexe"></a>SvcConfigEditor.exe  
 El editor permite al usuario crear y modificar archivos de configuración de WCF. El editor muestra la información cualquier contenida en los archivos de configuración. La misma tarea se puede lograr con un editor de texto.  
  
#### <a name="servicemodel_reg"></a>ServiceModel_Reg  
 Esta herramienta permite al usuario administrar las instalaciones de ServiceModel en un equipo. La herramienta muestra los mensajes de estado en una ventana de la consola cuando se ejecuta y, en el proceso, puede mostrar información sobre la configuración de la instalación de WCF.  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a>WSATConfig.exe y WSATUI.dll  
 Estas herramientas permiten a los profesionales de ti configurar la compatibilidad de red de WS-AtomicTransaction interoperable en WCF. Las herramientas muestran y permiten al usuario cambiar los valores de la configuración más utilizada de WS-AtomicTransaction almacenada en el registro.  
  
## <a name="cross-cutting-features"></a>Características del corte del cruce  
 Las características siguientes son transversales. Es decir, se pueden crear con cualquiera de las características anteriores.  
  
### <a name="service-framework"></a>Marco de servicios  
 Los encabezados pueden contener un id. de instancia, que es un GUID que asocia un mensaje a una instancia de una clase CLR.  
  
 El Lenguaje de descripción de servicios Web (WSDL) contiene una definición del puerto. Cada puerto tiene una dirección del extremo y un enlace que representa los servicios utilizados por la aplicación. Exponer WSDL se puede desactivar utilizando la configuración. No se retiene información en el equipo.  
  
## <a name="see-also"></a>Consulte también

- [Windows Communication Foundation](index.md)
- [Seguridad](./feature-details/security.md)
