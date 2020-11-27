---
title: Marco de servicios
ms.date: 03/30/2017
ms.assetid: 75f60b87-f80e-4377-ba7c-8e6becaa2b28
ms.openlocfilehash: 1fb39f2106e027cc5d4125cfb0bc89f3e5983cec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96285725"
---
# <a name="service-framework"></a>Marco de servicios

En este tema se enumeran las excepciones generadas por Service Framework Data.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|ABindingInstanceHasAlreadyBeenAssociatedTo1|Una instancia de enlace ya se ha asociado para que escuche al identificador uniforme de recursos especificado. Si dos extremos desean compartir el mismo indicador de recurso ListenUniform, también deben compartir la misma instancia de objeto de enlace. Los dos puntos de conexión en conflicto se especificaron en llamadas AddServiceEndpoint (), en un archivo de configuración, o una combinación de AddServiceEndpoint () y configuración.|  
|AChannelServiceEndpointIsNull0|Un canal o punto de conexión de servicio es nulo.|  
|AChannelServiceEndpointSContractSNameIsNull0|Un nombre del contrato de punto de conexión de servicio/canal es nulo o vacío.|  
|AChannelServiceEndpointSContractSNamespace0|Un espacio de nombres de contrato de extremo de servicio/canal es nulo.|  
|BaseAddressCannotHaveFragment|Una dirección base no puede contener un fragmento de identificador uniforme de recursos.|  
|BaseAddressCannotHaveQuery|Una dirección base no puede contener una cadena de solicitud de identificador uniforme de recursos.|  
|BaseAddressCannotHaveUserInfo|Una dirección base no puede contener una sección de información del usuario de identificador uniforme de recursos.|  
|BaseAddressDuplicateScheme|Esta colección ya contiene una dirección con el esquema especificado. Solo se permite una dirección para cada esquema de esta colección.|  
|BaseAddressMustBeAbsolute|Solo un identificador uniforme de recursos absoluto se puede utilizar como una dirección base.|  
|BindingDoesnTSupportAnyChannelTypes1|El enlace especificado no permite crear ningún tipo de canal. Los elementos de enlace en un enlace personalizado se apilan incorrectamente o en el orden equivocado. En la parte inferior de la pila se requiere un transporte. El orden recomendado para los elementos de enlace es: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, Transport.|  
|BindingDoesnTSupportDuplexButContractRequires1|El contrato requiere Dúplex. El enlace especificado no lo admite o no está configurado correctamente para admitirlo.|  
|BindingDoesnTSupportOneWayButContractRequires1|El contrato requiere Unidireccional. El enlace especificado no lo admite o no está configurado correctamente para admitirlo.|  
|BindingDoesnTSupportRequestReplyButContract1|El contrato requiere Solicitud/Respuesta. El enlace especificado no lo admite o no está configurado correctamente para admitirlo.|  
|BindingDoesnTSupportSessionButContractRequires1|El contrato requiere Sesión.  El enlace especificado no lo admite o no está configurado correctamente para admitirlo.|  
|BindingDoesnTSupportOneWayButContractRequires1|El contrato requiere Bidireccional (solicitud-respuesta o dúplex). El enlace especificado no lo admite o no está configurado correctamente para admitirlo.|  
|BindingRequirementsAttributeDisallowsQueuedDelivery1|DeliveryRequirementsAttribute no permite QueuedDelivery. El enlace para el extremo con el contrato especificado lo admite.|  
|BindingRequirementsAttributeRequiresQueuedDelivery1|DeliveryRequirementsAttribute requiere QueuedDelivery. El enlace para el punto de conexión con el contrato especificado no lo admite o no está configurado correctamente para admitirlo.|  
|channelDoesNotHaveADuplexSession0|El canal actual no permite cerrar la sesión de salida. Este canal no implementa ISessionChannel \<IDuplexSession> .|  
|ClientRuntimeRequiresFormatter0|El ClientOperation especificado requiere un formateador, porque SerializeRequest y DeserializeReply no son ambos falsos.|  
|CommunicationObjectAborted1|El objeto de comunicación especificado no se puede utilizar para la comunicación porque se ha detenido.|  
|CommunicationObjectAbortedStack2|El objeto de comunicación especificado no se puede usar para la comunicación porque se ha detenido: {1}|  
|CommunicationObjectBaseClassMethodNotCalled|El objeto de comunicación especificado ha invalidado la función virtual {1} , pero no llama a la versión definida en la clase base.|  
|ContractIsNotSelfConsistentItHasOneOrMore2|El contrato especificado tiene una o más operaciones IsTerminating o non-IsInitiating. No tiene la propiedad SessionMode establecida como SessionMode.Required. Los atributos IsInitiating e IsTerminating solo se pueden utilizar en el contexto de una sesión.|  
|CouldnTCreateChannelForChannelType2|Se solicitó el tipo de canal especificado, pero el enlace especificado no lo admite o no está configurado correctamente para admitirlo.|  
|DispatchRuntimeRequiresFormatter0|El DispatchOperation especificado requiere un formateador, porque DeserializeRequest y SerializeReply no son ambos falsos.|  
|EndMethodsCannotBeDecoratedWithOperationContractAttribute|El método End no se puede utilizar con OperationContractAttribute al utilizar el patrón de diseño de IAsyncResult. Solo el método Begin correspondiente se puede utilizar con OperationContractAttribute. Ese atributo se aplica al par de métodos Begin-End.|  
|EndpointListenerRequirementsCannotBeMetBy3|IChannelListener no puede cumplir los requisitos de ChannelDispatcher para el enlace especificado porque el contrato requiere la compatibilidad con uno de estos tipos de canales especificados. Pero el enlace solo admite estos tipos de canales especificados.|  
|EndpointsMustHaveAValidBinding0|Los puntos de conexión deben tener un enlace válido.|  
|InvalidOrUnrecognizedAction|No se puede procesar el mensaje porque la acción especificada no es válida ni reconocida.|  
|MultipleMebesInParameters|Se encontró más de un MessageEncodingBindingElement en BindingParameters del BindingContext. CustomBinding no puede tener varios MessageEncodingBindingElements. Solo deje uno de estos elementos y elimine el resto.|  
|MultipleStreamUpgradeProvidersInParameters|Se encontró más de un IStreamUpgradeProviderElement en los BindingParameters del BindingContext. CustomBinding no puede tener más de un IStreamUpgradeProviderElements. Solo deje uno de estos elementos y elimine el resto.|  
|NoChannelBuilderAvailable|El enlace no se puede utilizar para crear un generador de canales o un escuchador de canales porque no tiene un TransportBindingElement. Cada enlace debe tener al menos un elemento de enlace que derive de TransportBindingElement.|  
|NotAllBindingElementsBuilt|No se utilizaron algunos de los elementos de enlace de este enlace al compilar el generador y el escuchador de canales. Los elementos de enlace no están ordenados correctamente. El orden recomendado para los elementos de enlace es: TransactionFlow, ReliableSession, Security, CompositeDuplex, OneWay, StreamSecurity, MessageEncoding, Transport.  Tenga en cuenta que TransportBindingElement debe ser el último. Los elementos de enlace especificados no se compilaron.|  
|RuntimeRequiresInvoker0|La operación de distribución requiere un invocador.|  
|ServiceHasZeroAppEndpoints|El Servicio especificado no tiene puntos de conexión de aplicación (sin infraestructura). Esto podría deberse a que no se encontrón ningún archivo de configuración para su aplicación o a que no se encontró ningún elemento de servicio que coincidiese con el nombre del servicio en el archivo de configuración o porque no se definió ningún extremo en el elemento de servicio.|  
|SFxActionMismatch|No se puede crear un mensaje escrito debido a una desigualdad de acción. Se esperaba la acción especificada se pero encontró otra|  
|SFxAnonymousTypeNotSupported|La parte especificada en el mensaje especificado no se puede exportar con RPC ni codificar porque es de tipo anónimo.|  
|SFxBadMetadataLocationNoAppropriateBaseAddress|La dirección URL proporcionada a ServiceMetadataBehavior que utiliza la propiedad ExternalMetadataLocation o el atributo externalMetadataLocation en la sección serviceMetadata de la sección de configuración era una dirección URL relativa y no hay ninguna dirección base con la que resolverla.|  
|SFxBadMetadataMustBePolicy|Debe proporcionar un XmlElement de directiva que tiene el nombre y espacio de nombres especificado. El XmlElement tiene el nombre y espacio de nombres especificado.|  
|SFxBodyObjectTypeCannotBeInherited|El tipo especificado no puede heredar de ninguna clase que no sea el objeto que se va a utilizar como objeto de cuerpo en estilo RPC.|  
|SFxBodyObjectTypeCannotBeInterface|El tipo especificado implementa la interfaz especificada, que no se admite para el objeto de cuerpo en estilo RPC.|  
|SFxCallbackBehaviorAttributeOnlyOnDuplex|CallbackBehaviorAttribute solo se puede ejecutar como un comportamiento en un punto de conexión con un contrato dúplex. El contrato especificado no es dúplex y no contiene ninguna operación de devolución de llamada.|  
|SFxCallbackRequestReplyInOrder1|La respuesta no se puede recibir desde esta operación hasta que el Mensaje actual complete el procesamiento. Si desea permitir el procesamiento de mensajes descompuestos, especifique ConcurrencyMode de Reentrante o Varios en los especificados.|  
|SfxCallbackTypeCannotBeNull|Para utilizar el contrato especificado con DuplexChannelFactory, el contrato debe especificar un contrato de devolución de llamada válido. Si su contrato tiene un contrato de devolución de llamada, utilice ChannelFactory en lugar de DuplexChannelFactory.|  
|SFxCannotGetMetadataFromLocation|MetadataExchangeClient solo puede recibir los metadatos de MetadataLocations HTTPS y HTTP. No puede recibir metadatos de los especificados.|  
|SFxCannotHttpGetMetadataFromAddress|El MetadataExchangeClient solo puede recibir metadatos de direcciones HTTP o HTTPS al utilizar MetadataExchangeClientMode HttpGet. No puede recibir metadatos de los especificados.|  
|SFxCannotImportAsParameters_Bare|Generación del contrato de mensaje porque la operación especificada no es ni RPC ni ajustada en documento.|  
|SFxCannotImportAsParameters_DifferentWrapperName|Generación del contrato de mensaje porque el nombre del contenedor del mensaje especificado no coincide con el valor predeterminado.|  
|SFxCannotImportAsParameters_DifferentWrapperNs|Generación del contrato de mensaje porque el nombre de espacios del contenedor del mensaje especificado no coincide con el valor predeterminado.|  
|SFxCannotImportAsParameters_ElementIsNotNillable|Generación de un contrato de mensaje porque el nombre de elemento especificado del espacio de nombres especificado no se marca como que acepta valores NIL.|  
|SFxCannotImportAsParameters_HeadersAreUnsupported|Generación del contrato de mensaje porque el mensaje especificado tiene encabezados.|  
|SFxCannotImportAsParameters_Message|Generación de un contrato de mensaje porque la operación especificada tiene un Mensaje sin tipo como argumento o tipo de valor devuelto.|  
|SFxCannotImportAsParameters_MessageHasProtectionLevel|Generación del contrato de mensaje porque el mensaje especificado requiere protección.|  
|SFxCannotImportAsParameters_NamespaceMismatch|Generación del contrato de mensaje porque el nombre de espacios de la parte del mensaje especificado no coincide con el valor predeterminado.|  
|SFxCannotRequireBothSessionAndDatagram3|El contrato especificado especifica SessionMode.NotAllowed y el contrato especificado especifica SessionMode.Required. Cambie uno de los valores SessionMode o especifique una dirección diferente, o ListenURI, para cada punto de conexión.|  
|SFxCannotSetExtensionsByIndex|Esta colección no permite establecer las extensiones por índice. Utilice el InsertItem o los métodos RemoveItem.|  
|SFxChannelDispatcherDifferentHost0|El ChannelDispatcher no está adjunto actualmente al ServiceHost que se proporcionó.|  
|SFxChannelDispatcherMultipleHost0|El ChannelDispatcher no se puede agregar a más de un ServiceHost.|  
|SFxChannelDispatcherNoHost0|No se puede abrir el ChannelDispatcher porque no está adjunto a un ServiceHost.|  
|SfxChannelFactoryDisposed|No se puede abrir este ChannelFactory puesto que ya se ha dispuesto el ChannelFactory. Cree de nuevo el ChannelFactory antes de utilizarlo.|  
|SFxChannelFactoryNoBinding|No se puede abrir el ChannelFactory porque no se ha asociado ningún enlace a su extremo. Especifique un enlace con el constructor o la propiedad del punto de conexión.|  
|SFxChannelTerminated0|Una operación marcada como IsTerminating ya se ha invocado en este canal, haciendo que se termine la conexión del canal. No se pueden invocar más operaciones en este canal. Recree el canal para continuar la comunicación.|  
|SFxCloseTimedOut1|La operación de cierre de ServiceHost se detuvo después de lo especificado. Esto podría deberse a que un cliente no cerró un canal con sesión en el tiempo requerido. Puede que el tiempo permitido para esta operación sea parte de un tiempo de espera mayor.|  
|SfxCloseTimedOutWaitingForDispatchToComplete|Se superó el tiempo de espera del proceso de cierre mientras se esperaba que se completase la distribución del servicio.|  
|SFxCodeGenIsNotAssignableFrom|Lo especificado no se puede asignar.|  
|SFxConfigChannelConfigurationNotFound|No se puede encontrar el elemento del extremo con el nombre y contrato especificados en la sección de configuración de cliente de ServiceModel.|  
|SFxConflictingGlobalElement|El elemento del lenguaje de marcado extensible del nivel superior con el nombre especificado en el espacio de nombres especificado no puede hacer referencia al tipo especificado. Ya hace referencia a un tipo diferente. Utilice un nombre de operación diferente o MessageBodyAttribute para especificar un nombre diferente para el mensaje o para partes del mensaje.|  
|SFxContractHasZeroInitiatingOperations|Un contrato debe tener al menos una operación IsInitiating=true.|  
|SFxContractHasZeroOperations|Un contrato debe tener al menos una operación.|  
|SFxContractInheritanceRequiresInterfaces|La clase de servicio del tipo especificado define un ServiceContract y hereda un ServiceContract del tipo especificado. La herencia del contrato solo se puede utilizar entre tipos de interfaz. Si una clase se marca con ServiceContractAttribute, debe ser el único tipo en la jerarquía con ServiceContractAttribute.  Mueva el ServiceContractAttribute en el tipo especificado a una interfaz independiente que implemente el tipo especificado.|  
|SFxCreateDuplexChannel1|El contrato de devolución de llamada del contrato especificado no existe o no define ninguna operación. Si no es un contrato dúplex, utilice ChannelFactory en lugar de DuplexChannelFactory.|  
|SFxCreateDuplexChannelNoCallback|Esta sobrecarga de CreateChannel no se puede llamar en esta instancia de DuplexChannelFactory. El DuplexChannelFactory no se inicializó con un InstanceContext. Llame a la sobrecarga de CreateChannel que toma un InstanceContext.|  
|SFxCreateDuplexChannelNoCallback1|Esta sobrecarga de CreateChannel no se puede llamar en esta instancia de DuplexChannelFactory. El DuplexChannelFactory se inicializó con un Tipo y no se proporcionó ningún InstanceContext válido. Llame a la sobrecarga de CreateChannel que toma un InstanceContext.|  
|SFxCreateDuplexChannelNoCallbackUserObject|Esta sobrecarga de CreateChannel no se puede llamar en esta instancia de DuplexChannelFactory. El InstanceContext proporcionado al DuplexChannelFactory no contiene un UserObject válido.|  
|SFxCreateNonDuplexChannel1|ChannelFactory no admite el contrato especificado. ChannelFactory define un contrato de devolución de llamada con una o más operaciones. Utilice DuplexChannelFactory en lugar de ChannelFactory.|  
|SFxCustomBindingNeedsTransport1|El CustomBinding en el ServiceEndpoint con el contrato especificado no tiene un TransportBindingElement. Cada enlace debe tener al menos un elemento de enlace que derive de TransportBindingElement.|  
|SFxCustomBindingWithoutTransport|El Esquema no se puede calcular para este enlace personalizado porque no tiene un TransportBindingElement. Cada enlace debe tener al menos un elemento de enlace que derive de TransportBindingElement.|  
|SFxDataContractSerializerDoesNotSupportBareArray|DataContractSerializer no admite la colección especificada en el elemento especificado.|  
|SFxDictionaryIsEmpty|La operación no se puede realizar porque el diccionario está vacío.|  
|SFxDocEncodedNotSupported|Error que refleja lo especificado. No se admite la codificación por documento. Cambie “Uso” a Literal o “Estilo” a RPC.|  
|SFxDuplicateInitiatingActionAtSameVia|Este servicio tiene varios puntos de conexión que escuchan al especificado. Los puntos de conexión comparten la misma acción de iniciación especificada. Los mensajes con esta acción se quitarían porque el distribuidor no sería capaz de determinar el extremo correcto para administrar el mensaje.|  
|SFXEndpointBehaviorUsedOnWrongSide|El IEndpointBehavior especificado no se puede utilizar en el servidor. Este comportamiento solo se puede aplicar a los clientes.|  
|SFxEndpointNoMatchingScheme|No se puede encontrar la dirección base que coincide con el esquema especificado para el extremo con el enlace especificado. Se especifican los esquemas de direcciones base registrados.|  
|SFxErrorCreatingMtomReader|Se produjo un error al crear un lector para el mensaje del mecanismo de optimización de la transmisión de mensajes.|  
|SFxErrorDeserializingFault|El servidor devolvió un error de protocolo de acceso de objeto simple no válido. Consulte InnerException para obtener más información".|  
|SFxErrorDeserializingHeader|Se produjo un error al deserializar uno de los encabezados en el mensaje especificado. Consulte InnerException para obtener más detalles.|  
|SFxErrorReflectingOnMethod3|Se produjo un error al cargar el atributo especificado en el método especificado en el tipo especificado.  Consulte InnerException para obtener más información".|  
|SFxErrorReflectingOnParameter4|Se produjo un error al cargar el atributo especificado en el parámetro especificado del método especificado en el tipo especificado. Consulte InnerException para obtener más información".|  
|SFxErrorReflectingOnType2|Se produjo un error al cargar el atributo especificado en el tipo especificado.  Consulte InnerException para obtener más información".|  
|SFxErrorSerializingBody|Se produjo un error al serializar el cuerpo del mensaje especificado. Consulte InnerException para obtener más información".|  
|SFxErrorSerializingHeader|Se produjo un error al deserializar uno de los encabezados en el mensaje especificado. Consulte InnerException para obtener más información".|  
|SFxExpectedIMethodCallMessage|Error interno. El mensaje debe ser un IMethodCallMessage válido.|  
|SFxExportMustHaveType|No se puede exportar la Parte especificada en la operación especificada ya que no tiene un tipo CLR válido.|  
|SFxHeaderNotUnderstood|No se procesó el mensaje. El destinatario de este mensaje no entendió el encabezado especificado del espacio de nombres especificado. Este error indica normalmente que el remitente de este mensaje ha habilitado un protocolo de comunicaciones que el receptor no puede procesar. Asegúrese de que la configuración del enlace del cliente es coherente con el enlace del servicio.|  
|SFxHeadersAreNotSupportedInEncoded|El mensaje especificado no debe tener encabezados que se vayan a utilizar en el estilo codificado de llamada de procedimiento remoto.|  
|SFxInconsistentWsdlOperationStyleInMessageParts|Todas las partes del mensaje en la operación especificada deben contener un tipo o un elemento.|  
|SFxInconsistentWsdlOperationStyleInOperationMessages|El estilo especificado deducido de los mensajes en la operación especificada no coincide con el estilo esperado especificado mediante enlaces.|  
|SFxInvalidCallbackIAsyncResult|IAsyncResult no se proporciona o es del tipo equivocado.|  
|SFxInvalidMessageBody|El OperationFormatter encontró un cuerpo de mensaje no válido. Se esperaba el tipo de nodo 'Elemento' con el nombre y espacio de nombres especificado. Se encontró el tipo de nodo especificado con el nombre y espacio de nombres especificado.|  
|SFxInvalidMessageBodyEmptyMessage|El OperationFormatter no puede deserializar ninguna información del mensaje porque el mensaje está vacío.|  
|SFxInvalidMessageBodyErrorDeserializingParameter|Se produjo un error al intentar deserializar el parámetro especificado. Consulte InnerException para obtener más información.|  
|SFxInvalidMessageBodyErrorSerializingParameter|Se produjo un error al intentar serializar el parámetro especificado. Se especificó el mensaje de InnerException.  Consulte InnerException para obtener más información".|  
|SFxInvalidMessageBodyUnexpectedNode|Se encontró el nodo no esperado especificado, del espacio de nombres especificado al deserializar los parámetros.|  
|SFxInvalidMessageContractSignature|La operación especificada tiene un parámetro o un tipo de valor de devolución que se marca con el MessageContractAttribute. Al utilizar un contrato de mensaje para representar un mensaje de solicitud, la operación debe tener un parámetro único que esté marcado con el MessageContractAttribute. Al utilizar un contrato de mensaje para representar el mensaje de respuesta, el valor devuelto de la operación debe ser un tipo marcado con el MessageContractAttribute. La operación no puede tener ningún parámetro 'fuera' ni 'ref'.|  
|SFxInvalidReplyAction|El mensaje de respuesta de salida para la operación tiene la Acción especificada, pero el contrato para esa operación especifica otra ReplyAction. La Acción especificada en el mensaje debe coincidir con ReplyAction en el contrato, o el contrato de operación debe especificar ReplyAction = '*.'|  
|SFxInvalidRequestAction|El mensaje de solicitud de salida para la operación tiene la Acción especificada, pero el contrato para esa operación especifica otra RequestAction. La Acción especificada en el mensaje debe coincidir con RequestAction en el contrato, o el contrato de operación debe especificar RequestAction = '*.'|  
|SFxInvalidStaticOverloadCalledForDuplexChannelFactory1|El método estático CreateChannel no se puede utilizar con el contrato especificado porque ese contrato define un contrato de devolución de llamada. Use una de las sobrecargas de CreateChannel estáticas en DuplexChannelFactory \<TChannel> .|  
|SFxInvalidStreamInRequest|Para que la solicitud en la operación especificada sea una secuencia, la operación debe tener un parámetro único cuyo tipo sea de Secuencia.|  
|SFxInvalidStreamInResponse|Para que la respuesta en la operación especificada sea una secuencia, la operación debe tener un parámetro único out cuyo tipo sea de Secuencia.|  
|SFxInvalidStreamInTypedMessage|Para utilizar secuencias con el modelo de programación de contrato de mensaje, el tipo especificado debe tener un miembro MessageBody único cuyo tipo sea de Secuencia.|  
|SFxInvalidUseOfPrimitiveOperationFormatter|Se proporcionó un parámetro o tipo de valor devuelto al PrimitiveOperationFormatter que éste no admite.|  
|SFxMessageContractBaseTypeNotValid|El tipo especificado define un MessageContract y se deriva a partir un tipo especificado que no define un MessageContract. Todos los objetos en la jerarquía de herencia especificada deben definir un MessageContract.|  
|SFxMethodNotSupported1|El método especificado no se admite en este objeto. Esto puede pasar si el método no se marca con OperationContractAttribute o si el tipo de interfaz no se marca con ServiceContractAttribute.|  
|SFxMethodNotSupportedByType2|El tipo de implementación de ServiceHost especificado no implementa el contrato de servicio especificado.|  
|SFxMethodNotSupportedOnCallback1|No se admite el método de devolución de llamada especificado. Esto puede pasar si el método no se marca con OperationContractAttribute o si su tipo de interfaz no es el destino del CallbackContract del ServiceContractAttribute.|  
|SFxMismatchedOperationParent|Una DispatchOperation o ClientOperation solo se puede agregar respectivamente a su DispatchRuntime o ClientRuntime primario.|  
|SFxNameCannotBeEmpty|La propiedad Name no puede ser una cadena vacía.|  
|SfxNoTypeSpecifiedForParameter|No se especificó ningún tipo CLR para el parámetro, lo que evita que se genere la operación.|  
|SFxOperationBehaviorAttributeOnlyOnServiceClass|El OperationBehaviorAttribute solo puede ir en la clase de servicio. No se puede colocar en la interfaz ServiceContract. El método especificado en el tipo especificado infringe esto.|  
|SFxOperationContractOnNonServiceContract|El método especificado se marca con OperationContractAttribute, pero el tipo especificado que lo encierra no se marca con ServiceContractAttribute. OperationContractAttribute solo se puede utilizar en métodos en tipos ServiceContractAttribute o en sus tipos CallbackContract.|  
|SFxParameterCountMismatch|Se produjo una desigualdad entre el número de argumentos proporcionados y el número de argumentos esperados. Específicamente, el argumento especificado tiene el número especificado de elementos mientras que el argumento esperado tiene el número especificado de elementos.|  
|SFxPartNameMustBeUniqueInRpc|El nombre de la parte del mensaje especificado no es único en un mensaje de llamada de procedimiento remoto.|  
|SFxReplyActionMismatch3|Se recibió un mensaje de respuesta para la operación especificada con la acción especificada. Sin embargo, su código de cliente requiere la acción especificada.|  
|SFxRequestReplyNone|Se recibió un mensaje con un encabezado ReplyTo o FaultTo de WS-Addressing cuyo destino es la dirección "None". Estos valores no son válidos para operaciones de solicitud-respuesta. Utilice una operación unidireccional o habilite ManualAddressing si necesita admitir valores “None" de ReplyTo o FaultTo.|  
|SFxRequestTimedOut1|Esta operación de solicitud no recibió una respuesta dentro del tiempo configurado especificado. El tiempo permitido puede haber formado parte de un tiempo de espera más largo. Esto puede deberse a que el servicio todavía está procesando la operación o a que el servicio no pudo enviar un mensaje de respuesta.|  
|SFxRequestTimedOut2|La operación de solicitud enviada a la ubicación especificada no recibió una respuesta dentro del tiempo configurado especificado. El tiempo permitido puede haber formado parte de un tiempo de espera más largo. Esto puede deberse a que el servicio todavía está procesando la operación o a que el servicio no pudo enviar un mensaje de respuesta.|  
|SFxSchemaDoesNotContainType|El esquema con el espacio de nombres de destino especificado no contiene un tipo con el nombre especificado.|  
|SfxServiceContractAttributeNotFound|Al tipo de contrato especificado no se le atribuye ServiceContractAttribute. Para definir un contrato válido, debe atribuirse ServiceContractAttribute al tipo especificado. El tipo puede ser o una interfaz de contrato o una clase de servicio.|  
|SFxServiceContractGeneratorConfigRequired|Para generar información de configuración mediante el método GenerateServiceEndpoint, la instancia de ServiceContractGenerator debe inicializarse mediante  un objeto de configuración válido.|  
|SFxServiceHostBaseCannotAddEndpointAfterOpen|No se pueden agregar extremos después de que ServiceHost esté en uno de los siguientes estados:<br /><br /> -Abierto<br />-Error<br />-Terminado<br />-Cerrado|  
|SFxServiceHostBaseCannotAddEndpointWithoutDescription|Los extremos no se pueden agregar antes de que se inicie la propiedad Description.|  
|SFxServiceMetadataBehaviorNoHttpBaseAddress|La propiedad HttpGetEnabled de ServiceMetadataBehavior está definida como true y la propiedad HttpGetUrl es una dirección relativa, pero no hay ninguna dirección base HTTP. Proporcione una dirección base HTTP o defina HttpGetUrl como una dirección absoluta.|  
|SFxServiceMetadataBehaviorNoHttpsBaseAddress|La propiedad HttpsGetEnabled de ServiceMetadataBehavior está definida como true y la propiedad HttpsGetUrl es una dirección relativa, pero no hay ninguna dirección base HTTPS. Proporcione una dirección base HTTPS o defina HttpsGetUrl como una dirección absoluta.|  
|SFxServiceMetadataBehaviorUrlMustBeHttpOrRelative|La URL de comportamiento debe ser un identificador uniforme de recursos relativo o un identificador uniforme de recursos absoluto con el esquema especificado. La URL especificada es un identificador uniforme de recursos absoluto con el esquema especificado.|  
|SFxStreamRequestMessageClosed|Se ha cerrado el mensaje que contiene esta secuencia. No se puede tener acceso a las secuencias de solicitud después de que se restablezca el servicio.|  
|SFxStreamResponseMessageClosed|Se ha cerrado el mensaje que contiene esta secuencia.|  
|SFxTerminateRequestProcessingException|Una extensión en la canalización de la operación debe dejar de procesar este mensaje.|  
|SFxTerminatingOperationAlreadyCalled1|Este canal no puede enviar más mensaje porque se llamó la operación IsTerminating.|  
|SFxThrottleLimitMustBeGreaterThanZero0|El límite del acelerador debe ser mayor de cero. Para deshabilitar el límite del acelerador, establezca el valor en Int32.MaxValue.|  
|SFxTypedOrUntypedMessageCannotBeMixedWithVoidInRpc|Al utilizar el estilo codificado por RPC, no se pueden usar los tipos de contrato de mensaje o el tipo System.ServiceModel.Channels.Message si la operación no tiene ningún parámetro o tiene un valor devuelto nulo. Agregue un tipo de contrato de mensaje en blanco como un parámetro o tipo de valor devuelto a la operación especificada.|  
|SFxUserCodeThrewException|La operación especificada por el usuario produjo una excepción que no se controla en código de usuario. Si éste es un problema recurrente, puede indicar que hay un error en la implementación del método especificado.|  
|SfxUseTypedMessageForCustomAttributes|El parámetro especificado no puede estar asignado al parámetro de operación porque requiere atributos adicionales.|  
|SFxVersionMismatchInOperationContextAndMessage2|No se puede agregar encabezados de salida al mensaje porque MessageVersion en OperationContext.Current no coincide con la versión de encabezado del mensaje que se procesa|  
|SFxWellKnownNonSingleton0|Para utilizar uno de los constructores ServiceHost que toma una instancia del servicio, el InstanceContextMode del servicio debe establecerse en InstanceContextMode.Single. Esto se puede configurar mediante el ServiceBehaviorAttribute. De lo contrario, utilice los constructores ServiceHost que toman un argumento de tipo.|  
|SFxWrapperTypeHasMultipleNamespaces|El tipo de contenedor para el mensaje especificado no se puede proyectar como un tipo de contrato de datos porque tiene varios espacios de nombres. Utilice el XmlSerializer.|  
|UriMustBeAbsolute|El URI debe ser absoluto.|
