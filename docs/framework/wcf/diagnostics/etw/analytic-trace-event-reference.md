---
title: Referencia de evento de traza analítica
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF]. reference
ms.assetid: e44540cf-44a1-4efc-b965-7fbfd2131d73
ms.openlocfilehash: 4aa8e7a7d22edde02272dc4c3850b5695347b2bb
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609517"
---
# <a name="analytic-trace-event-reference"></a>Referencia de evento de traza analítica
En la tabla siguiente se definen los niveles de evento, los identificadores y los mensajes asociados a la traza analítica de WCF.  
  
## <a name="event-reference"></a>Referencia de eventos  
  
|Id. de evento|Nivel de evento|Mensaje del evento|Palabras clave|  
|--------------|-----------------|-------------------|--------------|  
|[131 - BufferPoolAllocation](131-bufferpoolallocation.md)|Verbose|Asignación de grupo %1 Bytes.|Infraestructura|  
|[132 - BufferPoolChangeQuota](132-bufferpoolchangequota.md)|Verbose|BufferPool de tamaño %1, cambiar la cuota por %2.|Infraestructura|  
|[133 - ActionItemScheduled](133-actionitemscheduled.md)|Verbose|Devolución de llamada del programador de subprocesos de E/S invocada.|Infraestructura|  
|[134 - ActionItemCallbackInvoked](134-actionitemcallbackinvoked.md)|Verbose|Devolución de llamada del programador de subprocesos de E/S invocada.|Infraestructura|  
|[201 - ClientMessageInspectorAfterReceiveInvoked](201-clientmessageinspectorafterreceiveinvoked.md)|Información|El distribuidor invocó 'AfterReceiveReply' en un ClientMessageInspector de tipo '%1'.|Troubleshooting, ServiceModel|  
|[202 - ClientMessageInspectorBeforeSendInvoked](202-clientmessageinspectorbeforesendinvoked.md)|Información|El distribuidor invocó 'BeforeSendRequest' en un ClientMessageInspector de tipo '%1'.|Troubleshooting, ServiceModel|  
|[203 - ClientParameterInspectorAfterCallInvoked](203-clientparameterinspectoraftercallinvoked.md)|Información|El distribuidor invocó 'AfterCall' en un ClientParameterInspector. del tipo '%1'.|Troubleshooting, ServiceModel|  
|[204 - ClientParameterInspectorBeforeCallInvoked](204-clientparameterinspectorbeforecallinvoked.md)|Información|El distribuidor invocó 'BeforeCall' en un ClientParameterInspector de tipo '%1'.|Troubleshooting, ServiceModel|  
|[205 - OperationInvoked](205-operationinvoked.md)|Información|Un OperationInvoker invocó el método '%1'.|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[206 - ErrorHandlerInvoked](206-errorhandlerinvoked.md)|Información|El distribuidor invocó un ErrorHandler del tipo '%1' con una excepción del tipo '%3'.  ErrorHandled == '%2'.|Troubleshooting, ServiceModel|  
|[207 - FaultProviderInvoked](207-faultproviderinvoked.md)|Información|El distribuidor invocó un FaultProvider del tipo '%1' con una excepción del tipo '%2'.|Troubleshooting, ServiceModel|  
|[208 - MessageInspectorAfterReceiveInvoked](208-messageinspectorafterreceiveinvoked.md)|Información|El distribuidor invocó 'AfterReceiveReply' en un MessageInspector del tipo '%1'.|Troubleshooting, ServiceModel|  
|[209 - MessageInspectorBeforeSendInvoked](209-messageinspectorbeforesendinvoked.md)|Información|El distribuidor invocó 'BeforeSendRequest' en un MessageInspector de tipo '%1'.|Troubleshooting, ServiceModel|  
|[210 - MessageThrottleExceeded](210-messagethrottleexceeded.md)|Advertencia|Se alcanzó el límite '%1' de '%2'.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[211 - ParameterInspectorAfterCallInvoked](211-parameterinspectoraftercallinvoked.md)|Información|El distribuidor invocó 'AfterCall' en un ParameterInspector de tipo '%1'.|Troubleshooting, ServiceModel|  
|[212 - ParameterInspectorBeforeCallInvoked](212-parameterinspectorbeforecallinvoked.md)|Información|El distribuidor invocó 'BeforeCall' en un ParameterInspector de tipo '%1'.|Troubleshooting, ServiceModel|  
|[213 - ServiceHostStarted](213-servicehoststarted.md)|LogAlways|ServiceHost iniciado: '%1'.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[214 - OperationCompleted](214-operationcompleted.md)|Información|Un OperationInvoker completó la llamada al método '%1'.  La duración de la llamada al método fue de '%2' ms.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[215 - MessageReceivedByTransport](215-messagereceivedbytransport.md)|Información|El transporte ha recibido un mensaje de '%1'.|Troubleshooting, ServiceModel|  
|[216 - MessageSentByTransport](216-messagesentbytransport.md)|Información|El transporte ha enviado un mensaje a '%1'.|Troubleshooting, ServiceModel|  
|[217 - ClientOperationPrepared](217-clientoperationprepared.md)|Información|El cliente está ejecutando la operación '%1' definida en el contrato '%2'. El mensaje se enviará a '%3'.|Troubleshooting, ServiceModel|  
|[218 - ClientOperationCompleted](218-clientoperationcompleted.md)|Información|El cliente completó la ejecución de la operación '%1' definida en el contrato '%2'. El mensaje se envió a '%3'.|Troubleshooting, ServiceModel|  
|[219 - ServiceException](219-serviceexception.md)|Error|Excepción no controlada del tipo '%2' durante el procesamiento de mensajes.  ToString de excepción completa: %1.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[220 - MessageSentToTransport](220-messagesenttotransport.md)|Información|El distribuidor envió un mensaje al transporte. Id. de correlación == '%1'.|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[221 - MessageReceivedFromTransport](221-messagereceivedfromtransport.md)|Información|El distribuidor recibió un mensaje del transporte. Id. de correlación == '%1'.|EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[222 - OperationFailed](222-operationfailed.md)|Advertencia|El método '%1' produjo una excepción no controlada al invocarse por OperationInvoker. La duración de la llamada al método fue de '%2' ms.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[223 - OperationFaulted](223-operationfaulted.md)|Advertencia|El método '% 1' produjo una FaultException al invocarse por OperationInvoker. La duración de la llamada al método fue de '%2' ms.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[224 - MessageThrottleAtSeventyPercent](224-messagethrottleatseventypercent.md)|Advertencia|La limitación '%1' de '%2' se encuentra al 70%.|HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[226 - IdleServicesClosed](226-idleservicesclosed.md)|LogAlways|Quedan %1 servicios inactivos de un total de %2 servicios activados cerrados.|HealthMonitoring WebHost|  
|[301 - UserDefinedErrorOccurred](301-userdefinederroroccurred.md)|Error|Nombre: '%1', referencia: '%2', carga: %3.|UserEvents, HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[302 - UserDefinedWarningOccurred](302-userdefinedwarningoccurred.md)|Advertencia|Nombre: '%1', referencia: '%2', carga: %3.|UserEvents, HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[303 - UserDefinedInformationEventOccured](303-userdefinedinformationeventoccured.md)|Información|Nombre: '%1', referencia: '%2', carga: %3.|UserEvents, HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel|  
|[401- StopSignPostEvent](401-stopsignpostevent.md)|Información|Límite de la actividad.|Solución de problemas|  
|[402 - StartSignpostEvent](402-startsignpostevent.md)|Información|Límite de la actividad.|Solución de problemas|  
|[403 - SuspendSignpostEvent](403-suspendsignpostevent.md)|Información|Límite de la actividad.|Solución de problemas|  
|[404 - ResumeSignpostEvent](404-resumesignpostevent.md)|Información|Límite de la actividad.|Solución de problemas|  
|[451 - MessageLogInfo](451-messageloginfo.md)|Información|%1|Solución de problemas, WCFMessageLogging|  
|[452 - MessageLogWarning](452-messagelogwarning.md)|Advertencia|%1|Solución de problemas, WCFMessageLogging|  
|[499 - TransferEmitted](499-transferemitted.md)|LogAlways|Evento de transferencia emitido.|Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging|  
|[501 - CompilationStart](501-compilationstart.md)|Información|Comenzar compilación.|WebHost|  
|[502 - CompilationStop](502-compilationstop.md)|Información|Finalizar compilación.|WebHost|  
|[503 - ServiceHostFactoryCreationStart](503-servicehostfactorycreationstart.md)|Información|Comienzo de creación de ServiceHostFactory.|WebHost|  
|[504 - ServiceHostFactoryCreationStop](504-servicehostfactorycreationstop.md)|Información|Finalización de creación de ServiceHostFactory.|WebHost|  
|[505 - CreateServiceHostStart](505-createservicehoststart.md)|Información|Comenzar CreateServiceHost.|WebHost|  
|[506 - CreateServiceHostStop](506-createservicehoststop.md)|Información|Finalizar CreateServiceHost.|WebHost|  
|[507 - HostedTransportConfigurationManagerConfigInitStart](507-hostedtransportconfigurationmanagerconfiginitstart.md)|Información|Inicialización de configuración de comienzo de HostedTransportConfigurationManager.|WebHost|  
|[508 - HostedTransportConfigurationManagerConfigInitStop](508-hostedtransportconfigurationmanagerconfiginitstop.md)|Información|Inicialización de configuración de finalización de HostedTransportConfigurationManager.|WebHost|  
|[509 - ServiceHostOpenStart](509-servicehostopenstart.md)|Información|Inicialización de configuración de finalización de HostedTransportConfigurationManager.|ServiceHost|  
|[510 - ServiceHostOpenStop](510-servicehostopenstop.md)|Información|Se completó la apertura de ServiceHost.|ServiceHost|  
|[513 - WebHostRequestStart](513-webhostrequeststart.md)|Información|Solicitud recibida con ruta de acceso virtual '%2' desde AppDomain '%1'.|WebHost|  
|[514 - WebHostRequestStop](514-webhostrequeststop.md)|Información|Detención de WebHostRequest.|WebHost|  
|[601 - CBAEntryRead](601-cbaentryread.md)|Verbose|Dirección relativa del elemento ServiceActivation procesada:'%1' dirección relativa normalizada '%2' .||  
|[602 - CBAMatchFound](602-cbamatchfound.md)|Verbose|La solicitud entrante coincide con un elemento ServiceActivation con la dirección '%1'.||  
|[603 - AspNetRoutingService](603-aspnetroutingservice.md)|Verbose|La solicitud entrante coincide con un servicio WCF definido en la ruta ASP.NET con la dirección %1.|RoutingServices|  
|[604 - AspNetRoute](604-aspnetroute.md)|Verbose|Se ha agregado una nueva ruta de ASP.NET ' %1 ' con serviceType ' %2 ' y serviceHostFactoryType ' %3 '.|RoutingServices|  
|[605 - IncrementBusyCount](605-incrementbusycount.md)|Verbose|Se llamó a IncrementBusyCount. Origen: %1|WebHost|  
|[606 - DecrementBusyCount](606-decrementbusycount.md)|Verbose|Llamado a DecrementBusyCount. Origen: %1|WebHost|  
|[701 - ServiceChannelOpenStart](701-servicechannelopenstart.md)|Verbose|Se inició ServiceChannelOpen.|WebHost|  
|[702 - ServiceChannelOpenStop](702-servicechannelopenstop.md)|Información|Se completó ServiceChannelOpen.|ServiceModel|  
|[703 - ServiceChannelCallStart](703-servicechannelcallstart.md)|Información|Se inició ServiceChannelCall.|ServiceModel|  
|[704 - ServiceChannelBeginCallStart](704-servicechannelbegincallstart.md)|Información|Se iniciaron llamadas asincrónicas de ServiceChannel.|ServiceModel|  
|[706 - HttpSendMessageStart](706-httpsendmessagestart.md)|Verbose|Inicio de la solicitud de envío HTTP.|HTTP|  
|[707 - HttpSendStop](707-httpsendstop.md)|Verbose|Detención de la solicitud de envío HTTP.|HTTP|  
|[708 - HttpMessageReceiveStart](708-httpmessagereceivestart.md)|Verbose|Mensaje recibido desde el transporte HTTP.|HTTP|  
|[709 - DispatchMessageStart](709-dispatchmessagestart.md)|Información|Se inició la distribución de mensajes.|ServiceModel|  
|[710 - HttpContextBeforeProcessAuthentication](710-httpcontextbeforeprocessauthentication.md)|Verbose|Iniciar la autenticación de la distribución de mensajes.|ServiceModel|  
|[711 - DispatchMessageBeforeAuthorization](711-dispatchmessagebeforeauthorization.md)|Verbose|Iniciar la autorización de la distribución de mensajes.|ServiceModel|  
|[712 - DispatchMessageStop](712-dispatchmessagestop.md)|Información|Distribución de mensajes completada.|ServiceModel|  
|[715 - ClientChannelOpenStart](715-clientchannelopenstart.md)|Información|Inicio de apertura de ServiceChannel.|ServiceModel|  
|[716 - ClientChannelOpenStop](716-clientchannelopenstop.md)|Información|Detención de apertura de ServiceChannel.|ServiceModel|  
|[717 - HttpSendStreamedMessageStart](717-httpsendstreamedmessagestart.md)|Información|Se inició el mensaje de secuencia de envío HTTP.|HTTP|  
|[1400 - ChannelInitializationTimeout](1400-channelinitializationtimeout.md)|Error|1 %|ServiceModel|  
|[1401 - CloseTimeout](1401-closetimeout.md)|Error|1 %|ServiceModel|  
|[1402 - IdleTimeout](1402-idletimeout.md)|Error|%1 Clave de grupo de conexión: %2|ServiceModel|  
|[1403 - LeaseTimeout](1403-leasetimeout.md)|Información|%1 Clave de grupo de conexión: %2|ServiceModel|  
|[1405 - OpenTimeout](1405-opentimeout.md)|Error|%1|ServiceModel|  
|[1406 - ReceiveTimeout](1406-receivetimeout.md)|Error|%1|ServiceModel|  
|[1407 - SendTimeout](1407-sendtimeout.md)|Error|%1|ServiceModel|  
|[1409 - InactivityTimeout](1409-inactivitytimeout.md)|Información|%1|ServiceModel|  
|[1416 - MaxReceivedMessageSizeExceeded](1416-maxreceivedmessagesizeexceeded.md)|Error|%1|Quota|  
|[1417 - MaxSentMessageSizeExceeded](1417-maxsentmessagesizeexceeded.md)|Error|%1|Quota|  
|[1418 - MaxOutboundConnectionsPerEndpointExceeded](1418-maxoutboundconnectionsperendpointexceeded.md)|Información|%1|Quota|  
|[1419 - MaxPendingConnectionsExceeded](1419-maxpendingconnectionsexceeded.md)|Información|%1|Quota|  
|[1420 - ReaderQuotaExceeded](1420-readerquotaexceeded.md)|Error|%1|Quota|  
|[1422 - NegotiateTokenAuthenticatorStateCacheExceeded](1422-negotiatetokenauthenticatorstatecacheexceeded.md)|Error|%1|Quota|  
|[1423 - NegotiateTokenAuthenticatorStateCacheRatio](1423-negotiatetokenauthenticatorstatecacheratio.md)|Verbose|Negociar la proporción de la memoria caché del estado del autenticador de tokens: %1/%2|Quota|  
|[1424 - SecuritySessionRatio](1424-securitysessionratio.md)|Verbose|Proporción de sesiones de seguridad: %1/%2|Quota|  
|[1430 - PendingConnectionsRatio](1430-pendingconnectionsratio.md)|Verbose|Proporción de conexiones pendientes: %1/%2|Quota|  
|[1431 - ConcurrentCallsRatio](1431-concurrentcallsratio.md)|Verbose|Proporción de sesiones simultáneas: %1/%2|Quota|  
|[1432 - ConcurrentSessionsRatio](1432-concurrentsessionsratio.md)|Verbose|Proporción de sesiones simultáneas: %1/%2|Quota|  
|[1433 - OutboundConnectionsPerEndpointRatio](1433-outboundconnectionsperendpointratio.md)|Verbose|Proporción de conexiones salientes por extremo: %1/%2|Quota|  
|[1436 - PendingMessagesPerChannelRatio](1436-pendingmessagesperchannelratio.md)|Verbose|Proporción de mensajes pendientes por canal: %1/%2|Quota|  
|[1438 - ConcurrentInstancesRatio](1438-concurrentinstancesratio.md)|Verbose|Proporción de instancias simultáneas: %1/%2|Quota|  
|[1439 - PendingAcceptsAtZero](1439-pendingacceptsatzero.md)|Información|Quedan cero aceptaciones pendientes|Quota|  
|[1441 - MaxSessionSizeReached](1441-maxsessionsizereached.md)|Advertencia|1 %|Quota|  
|[1442 - ReceiveRetryCountReached](1442-receiveretrycountreached.md)|Advertencia|Número de reintentos de recepción alcanzado en un mensaje de MSMQ con el identificador '%1'|Quota|  
|[1443 - MaxRetryCyclesExceededMsmq](1443-maxretrycyclesexceededmsmq.md)|Error|Ciclos de reintentos máximos superados en un mensaje de MSMQ con el identificador '%1'|Quota|  
|[1445 - ReadPoolMiss](1445-readpoolmiss.md)|Verbose|Creado nuevo '%1'|Quota|  
|[1446 - WritePoolMiss](1446-writepoolmiss.md)|Verbose|Creado nuevo '%1'|Quota|  
|[1451 - MaxRetryCyclesExceeded](1451-maxretrycyclesexceeded.md)|Error|1 %|Quota|  
|[3300 - ReceiveContextCompleteFailed](3300-receivecontextcompletefailed.md)|Advertencia|No se pudo completar %1.|Canal|  
|[3301 - ReceiveContextAbandonFailed](3301-receivecontextabandonfailed.md)|Advertencia|No se pudo abandonar %1.|Canal|  
|[3303 - ReceiveContextAbandonWithException](3303-receivecontextabandonwithexception.md)|Advertencia|Error en el contexto de recepción.|ServiceModel|  
|[3303 - ReceiveContextAbandonWithException](3303-receivecontextabandonwithexception.md)|Información|%1 se abandonó con la excepción %2.|Canal|  
|[3305 - ClientBaseCachedChannelFactoryCount](3305-clientbasecachedchannelfactorycount.md)|Información|El número de generadores de canales en caché es: '%1'.  Como máximo, se pueden almacenar en caché '%2' generadores de canales.|ServiceModel|  
|[3306 - ClientBaseChannelFactoryAgedOutofCache](3306-clientbasechannelfactoryagedoutofcache.md)|Información|Un generador de canales se ha eliminado de la memoria caché al alcanzarse su límite de '%1'.|ServiceModel|  
|[3307 - ClientBaseChannelFactoryCacheHit](3307-clientbasechannelfactorycachehit.md)|Información|Se encontró un generador de canales coincidente en la memoria caché.|ServiceModel|  
|[3308 - ClientBaseUsingLocalChannelFactory](3308-clientbaseusinglocalchannelfactory.md)|Información|No se usa el generador de canales de la memoria caché, es decir, almacenamiento en caché deshabilitado para la instancia.|ServiceModel|  
|[3309 - QueryCompositionExecuted](3309-querycompositionexecuted.md)|Información|Se ejecutó la composición de consultas '%1' en el URI de solicitud: '%2'.|ServiceModel|  
|[3310 - DispatchFailed](3310-dispatchfailed.md)|Error|La operación '%1' se distribuyó con errores.|ServiceModel|  
|[3311 - DispatchSuccessful](3311-dispatchsuccessful.md)|Información|La operación '%1' se distribuyó correctamente.|ServiceModel|  
|[3312 - MessageReadByEncoder](3312-messagereadbyencoder.md)|Información|El codificador leyó un mensaje de '%1' bytes de tamaño.|Canal|  
|[3312 - MessageReadByEncoder](3312-messagereadbyencoder.md)|Información|El codificador escribió un mensaje de '%1' bytes de tamaño.|Canal|  
|[3314 - SessionIdleTimeout](3314-sessionidletimeout.md)|Error|Anulando la sesión para el canal inactivo al URI:'%1'.|ServiceModel|  
|[3319 - SocketAcceptEnqueued](3319-socketacceptenqueued.md)|Verbose|Aceptación de la conexión iniciada.|TCP|  
|[3320 - SocketAccepted](3320-socketaccepted.md)|Verbose|ListenerId:%1 aceptó SocketId:%2.|TCP|  
|[3321 - ConnectionPoolMiss](3321-connectionpoolmiss.md)|Verbose|El grupo de %1 no tiene una conexión disponible y %2 conexiones ocupadas.|Canal|  
|[3322 - DispatchFormatterDeserializeRequestStart](3322-dispatchformatterdeserializerequeststart.md)|Verbose|El mensaje de solicitud de deserialización se inició el distribuidor.|ServiceModel|  
|[3323 - DispatchFormatterDeserializeRequestStop](3323-dispatchformatterdeserializerequeststop.md)|Verbose|El distribuidor completó la deserialización del mensaje de solicitud.|ServiceModel|  
|[3324 - DispatchFormatterSerializeReplyStart](3324-dispatchformatterserializereplystart.md)|Verbose|El distribuidor inició la serialización del mensaje de respuesta.|ServiceModel|  
|[3325 - DispatchFormatterSerializeReplyStop](3325-dispatchformatterserializereplystop.md)|Verbose|El distribuidor completó la serialización del mensaje de respuesta.|ServiceModel|  
|[3326 - ClientFormatterSerializeRequestStart](3326-clientformatterserializerequeststart.md)|Verbose|Se inició la serialización de la solicitud de cliente.|ServiceModel|  
|[3327 - ClientFormatterSerializeRequestStop](3327-clientformatterserializerequeststop.md)|Verbose|El cliente completó la serialización del mensaje de solicitud.|ServiceModel|  
|[3328 - ClientFormatterDeserializeReplyStart](3328-clientformatterdeserializereplystart.md)|Verbose|El cliente inició la deserialización del mensaje de respuesta.|ServiceModel|  
|[3329 - ClientFormatterDeserializeReplyStop](3329-clientformatterdeserializereplystop.md)|Verbose|El cliente completó la deserialización del mensaje de respuesta.|ServiceModel|  
|[3330 - SecurityNegotiationStart](3330-securitynegotiationstart.md)|Verbose|Se inició la negociación de seguridad.|Seguridad|  
|[3331 - SecurityNegotiationStop](3331-securitynegotiationstop.md)|Verbose|Se completó la negociación de seguridad.|Seguridad|  
|[3332 - SecurityTokenProviderOpened](3332-securitytokenprovideropened.md)|Verbose|Se completó la apertura de SecurityTokenProvider.|Seguridad|  
|[3333 - OutgoingMessageSecured](3333-outgoingmessagesecured.md)|Verbose|Se protegió el mensaje saliente.|Seguridad|  
|[3334 - IncomingMessageVerified](3334-incomingmessageverified.md)|Verbose|Se comprobó el mensaje entrante.|ServiceModel de seguridad|  
|[3335 - GetServiceInstanceStart](3335-getserviceinstancestart.md)|Verbose|Se inició la recuperación de la instancia de servicio.|ServiceModel|  
|[3336 - GetServiceInstanceStop](3336-getserviceinstancestop.md)|Verbose|Se recuperó la instancia de servicio.|ServiceModel|  
|[3337 - ChannelReceiveStart](3337-channelreceivestart.md)|Verbose|ChannelHandlerId:%1 - Se inició el bucle de recepción de mensajes.|Canal|  
|[3338 - ChannelReceiveStop](3338-channelreceivestop.md)|Verbose|ChannelHandlerId:%1 - Se detuvo el bucle de recepción de mensajes.|Canal|  
|[3339 - ChannelFactoryCreated](3339-channelfactorycreated.md)|Verbose|Se creó ChannelFactory.|ServiceModel|  
|[3340 - PipeConnectionAcceptStart](3340-pipeconnectionacceptstart.md)|Verbose|Se inició la aceptación de la conexión de canalización en %1.|Canal|  
|[3341 - PipeConnectionAcceptStop](3341-pipeconnectionacceptstop.md)|Verbose|Se aceptó la conexión de canalización.|Canal|  
|[3342 - EstablishConnectionStart](3342-establishconnectionstart.md)|Verbose|Se inició el establecimiento de la conexión para %1.|Canal|  
|[3343 - EstablishConnectionStop](3343-establishconnectionstop.md)|Verbose|Conexión establecida.|Canal|  
|[3345 - SessionPreambleUnderstood](3345-sessionpreambleunderstood.md)|Verbose|Se entendió el preámbulo de la sesión para '%1'|Canal|  
|[3346 - ConnectionReaderSendFault](3346-connectionreadersendfault.md)|Error|Error en el envío del lector de conexión '%1'.|Canal|  
|[3347 - SocketAcceptClosed](3347-socketacceptclosed.md)|Verbose|Se cerró la aceptación del socket.|TCP|  
|[3348 - ServiceHostFaulted](3348-servicehostfaulted.md)|Crítico|Error en el host de servicio.|TCP|  
|[3349 - ListenerOpenStart](3349-listeneropenstart.md)|Verbose|Abriendo agente de escucha para '%1'.|Canal|  
|[3350 - ListenerOpenStop](3350-listeneropenstop.md)|Verbose|Apertura del agente de escucha completada.|Canal|  
|[3351 - ServerMaxPooledConnectionsQuotaReached](3351-servermaxpooledconnectionsquotareached.md)|Verbose|Se alcanzó la cuota del número máximo de conexiones agrupadas de servidor.|Quota|  
|[3352 - TcpConnectionTimedOut](3352-tcpconnectiontimedout.md)|Error|Se agotó el tiempo de espera de SocketId:%1 en la dirección remota %2.|TCP|  
|[3353 - TcpConnectionResetError](3353-tcpconnectionreseterror.md)|Advertencia|Error al restablecer la conexión de SocketId:%1 a la dirección remota %2.|TCP|  
|[3354 - ServiceSecurityNegotiationCompleted](3354-servicesecuritynegotiationcompleted.md)|Verbose|Se completó la negociación de seguridad del servicio.|Seguridad|  
|[3355 - SecurityNegotiationProcessingFailure](3355-securitynegotiationprocessingfailure.md)|Error|Error al procesar la negociación de seguridad.|Seguridad|  
|[3356 - SecurityIdentityVerificationSuccess](3356-securityidentityverificationsuccess.md)|Verbose|La comprobación de seguridad se realizó correctamente.|Seguridad|  
|[3357 - SecurityIdentityVerificationFailure](3357-securityidentityverificationfailure.md)|Error|Error de comprobación de seguridad.|Seguridad|  
|[3358 - PortSharingDuplicatedSocket](3358-portsharingduplicatedsocket.md)|Verbose|Socket duplicado para %1.|ActivationServices|  
|[3359 - SecurityImpersonationSuccess](3359-securityimpersonationsuccess.md)|Verbose|La suplantación de seguridad se realizó correctamente.|Seguridad|  
|[3360 - SecurityImpersonationFailure](3360-securityimpersonationfailure.md)|Advertencia|Error de suplantación de seguridad.|Seguridad|  
|[3361 - HttpChannelRequestAborted](3361-httpchannelrequestaborted.md)|Advertencia|Se anuló la solicitud de canal de HTTP.|HTTP|  
|[3362 - HttpChannelResponseAborted](3362-httpchannelresponseaborted.md)|Advertencia|Se anuló la respuesta de canal de HTTP.|HTTP|  
|[3363 - HttpAuthFailed](3363-httpauthfailed.md)|Advertencia|Error de autenticación HTTP.|HTTP|  
|[3364 - SharedListenerProxyRegisterStart](3364-sharedlistenerproxyregisterstart.md)|Verbose|Registro de SharedListenerProxy iniciado para el URI '%1'.|ActivationServices|  
|[3365 - SharedListenerProxyRegisterStop](3365-sharedlistenerproxyregisterstop.md)|Verbose|Detención de registro de SharedListenerProxy.|ActivationServices|  
|[3366 - SharedListenerProxyRegisterFailed](3366-sharedlistenerproxyregisterfailed.md)|Error|Error en el registro de SharedListenerProxy con el estado '%1'.|ActivationServices|  
|[3367 - ConnectionPoolPreambleFailed](3367-connectionpoolpreamblefailed.md)|Error|ConnectionPoolPreambleFailed.|Canal|  
|[3368 - SslOnInitiateUpgrade](3368-ssloninitiateupgrade.md)|Verbose|SslOnAcceptUpgradeStart|Seguridad|  
|[3369 - SslOnAcceptUpgrade](3369-sslonacceptupgrade.md)|Verbose|SslOnAcceptUpgradeStop|Seguridad|  
|[3370 - BinaryMessageEncodingStart](3370-binarymessageencodingstart.md)|Verbose|BinaryMessageEncoder inició la codificación del mensaje.|Canal|  
|[3371 - MtomMessageEncodingStart](3371-mtommessageencodingstart.md)|Verbose|MtomMessageEncoder inició la codificación del mensaje.|Canal|  
|[3372 - TextMessageEncodingStart](3372-textmessageencodingstart.md)|Verbose|TextMessageEncoder inició la codificación del mensaje.|Canal|  
|[3373 - BinaryMessageDecodingStart](3373-binarymessagedecodingstart.md)|Verbose|BinaryMessageEncoder inició la descodificación del mensaje.|Canal|  
|[3374 - MtomMessageDecodingStart](3374-mtommessagedecodingstart.md)|Verbose|MtomMessageEncoder inició la descodificación del mensaje.|Canal|  
|[3375 - TextMessageDecodingStart](3375-textmessagedecodingstart.md)|Verbose|TextMessageEncoder inició la descodificación del mensaje.|Canal|  
|[3376 - HttpResponseReceiveStart](3376-httpresponsereceivestart.md)|Información|El transporte HTTP comenzó a recibir un mensaje.|HTTP|  
|[3377 - SocketReadStop](3377-socketreadstop.md)|Verbose|SocketId:%1 leer bytes '%2' leídos de '%3'.|TCP|  
|[3378 - SocketAsyncReadStop](3378-socketasyncreadstop.md)|Verbose|SocketId:%1 leer bytes '%2' leídos de '%3'.|TCP|  
|[3379 - SocketWriteStart](3379-socketwritestart.md)|Verbose|SocketId:%1 escribiendo '%2' bytes en '%3'.|TCP|  
|[3380 - SocketAsyncWriteStart](3380-socketasyncwritestart.md)|Verbose|SocketId:%1 escribiendo '%2' bytes en '%3'.|TCP|  
|[3381 - SequenceAcknowledgementSent](3381-sequenceacknowledgementsent.md)|Verbose|Enviada la confirmación de SessionId:%1|Canal|  
|[3382 - ClientReliableSessionReconnect](3382-clientreliablesessionreconnect.md)|Información|Volviendo a conectar SessionId:%1.|Canal|  
|[3383 - ReliableSessionChannelFaulted](3383-reliablesessionchannelfaulted.md)|Información|Error de SessionId:%1|Canal|  
|[3384 - WindowsStreamSecurityOnInitiateUpgrade](3384-windowsstreamsecurityoninitiateupgrade.md)|Verbose|Actualización de seguridad inicial de WindowsStreamSecurity.|Seguridad|  
|[3385 - WindowsStreamSecurityOnAcceptUpgrade](3385-windowsstreamsecurityonacceptupgrade.md)|Verbose|Seguridad de transmisión por secuencias de Windows al aceptar la actualización.|Seguridad|  
|[3386 - SocketConnectionAbort](3386-socketconnectionabort.md)|Advertencia|Anulando el SocketId:%1|TCP|  
|[3388 - HttpGetContextStart](3388-httpgetcontextstart.md)|Verbose|Inicio de HttpGetContext.|HTTP|  
|[3389 - ClientSendPreambleStart](3389-clientsendpreamblestart.md)|Verbose|Cliente enviando el inicio del preámbulo.|Canal|  
|[3390 - ClientSendPreambleStop](3390-clientsendpreamblestop.md)|Verbose|Cliente enviando la detención del preámbulo.|Canal|  
|[3391 - HttpMessageReceiveFailed](3391-httpmessagereceivefailed.md)|Advertencia|Error en la recepción del mensaje HTTP.|HTTP|  
|[3392 - TransactionScopeCreate](3392-transactionscopecreate.md)|Información|TransactionScope se va a crear con LocalIdentifier:'%1 y DistributedIdentifier:'%2'.|ServiceModel|  
|[3393 - StreamedMessageReadByEncoder](3393-streamedmessagereadbyencoder.md)|Información|El codificador leyó un mensaje transmitido por secuencias.|Canal|  
|[3394 - StreamedMessageWrittenByEncoder](3394-streamedmessagewrittenbyencoder.md)|Información|El codificador escribió un mensaje transmitido por secuencias.|Canal|  
|[3395 - MessageWrittenAsynchronouslyByEncoder](3395-messagewrittenasynchronouslybyencoder.md)|Información|El codificador escribió un mensaje asincrónicamente.|Canal|  
|[3396 - BufferedAsyncWriteStart](3396-bufferedasyncwritestart.md)|Información|BufferId:%1 completó la escritura de bytes '%2' en el flujo subyacente.|Canal|  
|[3397 - BufferedAsyncWriteStop](3397-bufferedasyncwritestop.md)|Información|El codificador escribió un mensaje asincrónicamente.|Canal|  
|[3398 - PipeSharedMemoryCreated](3398-pipesharedmemorycreated.md)|Verbose|Se creó memoria compartida de canalización en '%1'.|Canal|  
|[3399 - NamedPipeCreated](3399-namedpipecreated.md)|Verbose|Se creó la NamedPipe '%1'.|Canal|  
|[3401 - SignatureVerificationStart](3401-signatureverificationstart.md)|Verbose|Se inició la comprobación de la signatura.|Seguridad|  
|[3402 - SignatureVerificationSuccess](3402-signatureverificationsuccess.md)|Verbose|La comprobación de la signatura se ha realizado correctamente.|Seguridad|  
|[3403 - WrappedKeyDecryptionStart](3403-wrappedkeydecryptionstart.md)|Verbose|Se inició el descifrado de la clave ajustada.|Seguridad|  
|[3404 - WrappedKeyDecryptionSuccess](3404-wrappedkeydecryptionsuccess.md)|Verbose|El descifrado de la clave ajustada se realizó correctamente.|Seguridad|  
|[3405 - EncryptedDataProcessingStart](3405-encrypteddataprocessingstart.md)|Verbose|Se inició el procesamiento de los datos cifrados.|Seguridad|  
|[3406 - EncryptedDataProcessingSuccess](3406-encrypteddataprocessingsuccess.md)|Verbose|El procesamiento de los datos cifrados se realizó correctamente.|Seguridad|  
|[3407 - HttpPipelineProcessInboundRequestStart](3407-httppipelineprocessinboundrequeststart.md)|Verbose|El controlador de mensajes HTTP comenzó el procesamiento de la solicitud entrante.|HTTP|  
|[3408 - HttpPipelineBeginProcessInboundRequestStart](3408-httppipelinebeginprocessinboundrequeststart.md)|Verbose|El controlador de mensajes HTTP comenzó el procesamiento de la solicitud entrante asincrónicamente.|HTTP|  
|[3409 - HttpPipelineProcessInboundRequestStop](3409-httppipelineprocessinboundrequeststop.md)|Verbose|El controlador de mensajes HTTP completó el procesamiento de una solicitud entrante.|HTTP|  
|[3410 - HttpPipelineFaulted](3410-httppipelinefaulted.md)|Advertencia|El controlador de mensajes HTTP tiene errores.|HTTP|  
|[3411 - HttpPipelineTimeoutException](3411-httppipelinetimeoutexception.md)|Error|Tiempo de espera agotado para la conexión WebSocket.|HTTP|  
|[3412 - HttpPipelineProcessResponseStart](3412-httppipelineprocessresponsestart.md)|Verbose|El controlador de mensajes HTTP comenzó el procesamiento de la respuesta.|HTTP|  
|[3413 - HttpPipelineBeginProcessResponseStart](3413-httppipelinebeginprocessresponsestart.md)|Verbose|El controlador de mensajes HTTP comenzó el procesamiento de la respuesta asincrónicamente.|HTTP|  
|[3414 - HttpPipelineProcessResponseStop](3414-httppipelineprocessresponsestop.md)|Verbose|El controlador de mensajes HTTP completó el procesamiento de la respuesta.|HTTP|  
|[3415 - WebSocketConnectionRequestSendStart](3415-websocketconnectionrequestsendstart.md)|Verbose|Solicitud de conexión de WebSocket para inicio de envío de '%1'.|HTTP|  
|[3416 - WebSocketConnectionRequestSendStop](3416-websocketconnectionrequestsendstop.md)|Verbose|Solicitud de conexión WebSocketId:%1 enviada.|HTTP|  
|[3417 - WebSocketConnectionAcceptStart](3417-websocketconnectionacceptstart.md)|Verbose|Inicio de aceptación de conexión de WebSocket.|HTTP|  
|[3418 - WebSocketConnectionAccepted](3418-websocketconnectionaccepted.md)|Verbose|WebSocketId:%1 conexión aceptada.|HTTP|  
|[3419 - WebSocketConnectionDeclined](3419-websocketconnectiondeclined.md)|Error|Conexión de WebSocket rechazada con el código de estado '%1'|HTTP|  
|[3420 - WebSocketConnectionFailed](3420-websocketconnectionfailed.md)|Error|Error de solicitud conexión de WebSocket: '%1'|HTTP|  
|[3421 - WebSocketConnectionAborted](3421-websocketconnectionaborted.md)|Error|WebSocketId:%1 solicitud de conexión anulada.|HTTP|  
|[3422 - WebSocketAsyncWriteStart](3422-websocketasyncwritestart.md)|Verbose|WebSocketId:%1 escribiendo '%2' bytes en '%3'|HTTP|  
|[3423 - WebSocketAsyncWriteStop](3423-websocketasyncwritestop.md)|Verbose|WebSocketId:%1 detención de escritura asincrónica.|HTTP|  
|[3424 - WebSocketAsyncReadStart](3424-websocketasyncreadstart.md)|Verbose|WebSocketId:%1 inicio de lectura.|HTTP|  
|[3425 - WebSocketAsyncReadStop](3425-websocketasyncreadstop.md)|Verbose|WebSocketId:%1 leer '%2' bytes de '%3'.|HTTP|  
|[3426 - WebSocketCloseSent](3426-websocketclosesent.md)|Verbose|WebSocketId:%1 enviando mensaje de cierre a '%2' con estado de cierre '%3'.|HTTP|  
|[3427 - WebSocketCloseOutputSent](3427-websocketcloseoutputsent.md)|Verbose|WebSocketId:%1 enviando mensaje de salida de cierre a '%2' con estado de cierre '%3'.|HTTP|  
|[3428 - WebSocketConnectionClosed](3428-websocketconnectionclosed.md)|Verbose|WebSocketId:%1 conexión cerrada.|HTTP|  
|[3429 - WebSocketCloseStatusReceived](3429-websocketclosestatusreceived.md)|Verbose|WebSocketId:%1 mensaje de cierre de conexión recibido con el estado '%2'.|HTTP|  
|[3430 - WebSocketUseVersionFromClientWebSocketFactory](3430-websocketuseversionfromclientwebsocketfactory.md)|Verbose|Usando el WebSocketVersion de un generador de WebSocket cliente de tipo '%1'.|HTTP|  
|[3431 - WebSocketCreateClientWebSocketWithFactory](3431-websocketcreateclientwebsocketwithfactory.md)|Verbose|Creando el WebSocket cliente con un generador de tipo '%1'.|HTTP|  
|[3553 - XamlServicesLoadStart](3553-xamlservicesloadstart.md)|Información|Inicio de XamlServicesLoad|WebHost|  
|[3554 - XamlServicesLoadStop](3554-xamlservicesloadstop.md)|Información|Detención de XamlServicesLoad|WebHost|  
|[3555 - CreateWorkflowServiceHostStart](3555-createworkflowservicehoststart.md)|Información|Inicio de CreateWorkflowServiceHost|WebHost|  
|[3556 - CreateWorkflowServiceHostStop](3556-createworkflowservicehoststop.md)|Información|Detención de CreateWorkflowServiceHost|WebHost|  
|[3558 - ServiceActivationStart](3558-serviceactivationstart.md)|Información|Inicio de la activación del servicio|WebHost|  
|[3559 - ServiceActivationStop](3559-serviceactivationstop.md)|Información|Detención de la activación del servicio|WebHost|  
|[3560 - ServiceActivationAvailableMemory](3560-serviceactivationavailablememory.md)|Verbose|Memoria disponible (bytes): %1|Quota|  
|[3800 - RoutingServiceClosingClient](3800-routingserviceclosingclient.md)|Información|El servicio de enrutamiento está cerrando el cliente '%1'.|RoutingServices|  
|[3800 - RoutingServiceClosingClient](3800-routingserviceclosingclient.md)|Advertencia|El cliente del servicio de enrutamiento '%1' generó un error.|RoutingServices|  
|[3802 - RoutingServiceCompletingOneWay](3802-routingservicecompletingoneway.md)|Información|Se está completando un mensaje unidireccional del servicio de enrutamiento.|RoutingServices|  
|[3803 - RoutingServiceProcessingFailure](3803-routingserviceprocessingfailure.md)|Error|Error en el servicio de enrutamiento al procesar un mensaje en el extremo con la dirección '%1'.|RoutingServices|  
|[3804 - RoutingServiceCreatingClientForEndpoint](3804-routingservicecreatingclientforendpoint.md)|Información|El servicio de enrutamiento está creando un cliente para el extremo: '%1'.|RoutingServices|  
|[3805 - RoutingServiceDisplayConfig](3805-routingservicedisplayconfig.md)|Verbose|El Servicio de enrutamiento está configurado con RouteOnHeadersOnly: %1, SoapProcessingEnabled: %2, EnsureOrderedDispatch: %3.|RoutingServices|  
|[3807 - RoutingServiceCompletingTwoWay](3807-routingservicecompletingtwoway.md)|Información|Se está completando un mensaje de respuesta a solicitudes del servicio de enrutamiento.|RoutingServices|  
|[3809 - RoutingServiceMessageRoutedToEndpoints](3809-routingservicemessageroutedtoendpoints.md)|Verbose|El Servicio de enrutamiento enrutó el mensaje con identificador: '%1' en %2 listas de extremos.|RoutingServices|  
|[3810 - RoutingServiceConfigurationApplied](3810-routingserviceconfigurationapplied.md)|Información|Se ha aplicado un nuevo elemento RoutingConfiguration al servicio de enrutamiento.|RoutingServices|  
|[3815 - RoutingServiceProcessingMessage](3815-routingserviceprocessingmessage.md)|Información|El Servicio de enrutamiento está procesando un mensaje con identificador: '%1', acción: '%2', dirección URL de entrada: '%3' recibido en la transacción: %4.|RoutingServices|  
|[3816 - RoutingServiceTransmittingMessage](3816-routingservicetransmittingmessage.md)|Información|El Servicio de enrutamiento está transmitiendo el mensaje con identificador: '%1' [operación %2] a '%3'.|RoutingServices|  
|[3817 - RoutingServiceCommittingTransaction](3817-routingservicecommittingtransaction.md)|Información|El servicio de enrutamiento está confirmando una transacción con id.: '%1'.|RoutingServices|  
|[3818 - RoutingServiceDuplexCallbackException](3818-routingserviceduplexcallbackexception.md)|Error|Excepción de devolución de llamada dúplex en el componente %1 del servicio de enrutamiento.|RoutingServices|  
|[3819 - RoutingServiceMovedToBackup](3819-routingservicemovedtobackup.md)|Información|Mensaje del servicio de enrutamiento con identificador: '%1' [operación %2] movido al punto de conexión auxiliar '%3'.|RoutingServices|  
|[3820 - RoutingServiceCreatingTransaction](3820-routingservicecreatingtransaction.md)|Información|El servicio de enrutamiento creó una nueva transacción con id. '%1' para procesar los mensajes.|RoutingServices|  
|[3821 - RoutingServiceCloseFailed](3821-routingserviceclosefailed.md)|Advertencia|El servicio de enrutamiento no pudo cerrar el cliente de salida '%1'.|RoutingServices|  
|[3822 - RoutingServiceSendingResponse](3822-routingservicesendingresponse.md)|Información|El servicio de enrutamiento está devolviendo un mensaje de respuesta con la acción '%1'|RoutingServices|  
|[3823 - RoutingServiceSendingFaultResponse](3823-routingservicesendingfaultresponse.md)|Advertencia|El servicio de enrutamiento está devolviendo un mensaje de respuesta de error con la acción '%1'.|RoutingServices|  
|[3824 - RoutingServiceCompletingReceiveContext](3824-routingservicecompletingreceivecontext.md)|Verbose|El servicio de enrutamiento está llamando a ReceiveContext.Complete para un mensaje con id.: '%1'.|RoutingServices|  
|[3825 - RoutingServiceAbandoningReceiveContext](3825-routingserviceabandoningreceivecontext.md)|Advertencia|El servicio de enrutamiento está llamando a ReceiveContext.Abandon para un mensaje con id.: '%1'.|RoutingServices|  
|[3826 - RoutingServiceUsingExistingTransaction](3826-routingserviceusingexistingtransaction.md)|Verbose|El servicio de enrutamiento enviará mensajes con la transacción existente '%1'.|RoutingServices|  
|[3827 - RoutingServiceTransmitFailed](3827-routingservicetransmitfailed.md)|Advertencia|Error en el servicio de enrutamiento al enviar a '%1'.|RoutingServices|  
|[3828 - RoutingServiceFilterTableMatchStart](3828-routingservicefiltertablematchstart.md)|Información|Inicio de coincidencia de MessageFilterTable del servicio de enrutamiento.|RoutingServices|  
|[3829 - RoutingServiceFilterTableMatchStop](3829-routingservicefiltertablematchstop.md)|Información|Detención de coincidencia de MessageFilterTable del servicio de enrutamiento.|RoutingServices|  
|[3830 - RoutingServiceAbortingChannel](3830-routingserviceabortingchannel.md)|Verbose|El servicio de enrutamiento está llamando a una operación de anulación en el canal: '%1'.|RoutingServices|  
|[3831 - RoutingServiceHandledException](3831-routingservicehandledexception.md)|Verbose|El servicio de enrutamiento ha controlado una excepción.|RoutingServices|  
|[3832 - RoutingServiceTransmitSucceeded](3832-routingservicetransmitsucceeded.md)|Información|El Servicio de enrutamiento transmitió correctamente el mensaje con identificador: '%1 [operación %2] a '%3'.|RoutingServices|  
|[4001 - TransportListenerSessionsReceived](4001-transportlistenersessionsreceived.md)|Verbose|La sesión de escucha de transporte se recibió a través de '%1'|ActivationServices|  
|[4002 - FailFastException](4002-failfastexception.md)|Crítico|FailFastException.|ActivationServices|  
|[4003 - ServiceStartPipeError](4003-servicestartpipeerror.md)|Error|Error de canalización del inicio de servicio.|ActivationServices|  
|[4008 - DispatchSessionStart](4008-dispatchsessionstart.md)|Verbose|Se inició la distribución de la sesión.|ActivationServices|  
|[4008 - DispatchSessionStart](4008-dispatchsessionstart.md)|Advertencia|Error en la distribución de la sesión de '%1'. La cola de sesiones pendientes está llena con '%2' elementos pendientes.|ActivationServices|  
|[4011 - MessageQueueRegisterStart](4011-messagequeueregisterstart.md)|Verbose|Inicio del registro de cola de mensajes.|ActivationServices|  
|[4012 - MessageQueueRegisterAbort](4012-messagequeueregisterabort.md)|Error|Se anuló el registro de la cola de mensajes con el estado:'%1' para el URI:'%2'.|ActivationServices|  
|[4013 - MessageQueueUnregisterSucceeded](4013-messagequeueunregistersucceeded.md)|Verbose|Anulación correcta del registro de la cola de mensajes para el URI:'%1'.|ActivationServices|  
|[4014 - MessageQueueRegisterFailed](4014-messagequeueregisterfailed.md)|Error|Error en el registro de la cola de mensajes para el URI: '%1' con el estado:'%2'.|ActivationServices|  
|[4015 - MessageQueueRegisterCompleted](4015-messagequeueregistercompleted.md)|Información|Registro de la cola de mensajes completado para el URI '%1'.|ActivationServices|  
|[4016 - MessageQueueDuplicatedSocketError](4016-messagequeueduplicatedsocketerror.md)|Error|La cola de mensajes no pudo duplicar el socket.|ActivationServices|  
|[4019 - MessageQueueDuplicatedSocketComplete](4019-messagequeueduplicatedsocketcomplete.md)|Verbose|MessageQueueDuplicatedSocketComplete|ActivationServices|  
|[4020 - TcpTransportListenerListeningStart](4020-tcptransportlistenerlisteningstart.md)|Verbose|El agente de escucha de transporte TCP empieza a escuchar en el URI:'%1'.|ActivationServices|  
|[4021 - TcpTransportListenerListeningStop](4021-tcptransportlistenerlisteningstop.md)|Verbose|Escucha de transporte de TCP a la escucha.|ActivationServices|  
|[4022 - WebhostUnregisterProtocolFailed](4022-webhostunregisterprotocolfailed.md)|Error|Código de error:%1|ActivationServices|  
|[4023 - WasCloseAllListenerChannelInstancesCompleted](4023-wasclosealllistenerchannelinstancescompleted.md)|Información|Completado el cierre de todas las instancias del canal de escucha.|ActivationServices|  
|[4024 - WasCloseAllListenerChannelInstancesFailed](4024-wasclosealllistenerchannelinstancesfailed.md)|Error|Código de error:%1|ActivationServices|  
|[4025 - OpenListenerChannelInstanceFailed](4025-openlistenerchannelinstancefailed.md)|Error|Código de error:%1|ActivationServices|  
|[4026 - WasConnected](4026-wasconnected.md)|Verbose|WAS conectado.|ActivationServices|  
|[4027 - WasDisconnected](4027-wasdisconnected.md)|Verbose|WAS desconectado.|ActivationServices|  
|[4028 - PipeTransportListenerListeningStart](4028-pipetransportlistenerlisteningstart.md)|Verbose|La escucha del transporte de canalización se inicia en el URI:%1.|ActivationServices|  
|[4029 - PipeTransportListenerListeningStop](4029-pipetransportlistenerlisteningstop.md)|Verbose|Se detiene la escucha del transporte de canalización.|ActivationServices|  
|[4030 - DispatchSessionSuccess](4030-dispatchsessionsuccess.md)|Información|La distribución de la sesión se realizó correctamente.|ActivationServices|  
|[4031 - DispatchSessionFailed](4031-dispatchsessionfailed.md)|Error|Error en la distribución de la sesión.|ActivationServices|  
|[4032 - WasConnectionTimedout](4032-wasconnectiontimedout.md)|Crítico|Se agotó el tiempo de espera de la conexión WAS.|ActivationServices|  
|[4033 - RoutingTableLookupStart](4033-routingtablelookupstart.md)|Verbose|Se inició la búsqueda de la tabla de enrutamiento.|ActivationServices|  
|[4034 - RoutingTableLookupStop](4034-routingtablelookupstop.md)|Verbose|Se completó la búsqueda de la tabla de enrutamiento.|ActivationServices|  
|[4035 - PendingSessionQueueRatio](4035-pendingsessionqueueratio.md)|Verbose|Proporción de la cola de sesiones pendientes: %1/%2|Quota|  
|[4600 - MessageLogEventSizeExceeded](4600-messagelogeventsizeexceeded.md)|Advertencia|No se puede registrar el mensaje porque excede el tamaño de evento de ETW|WCFMessageLogging|  
|[4801 - DiscoveryClientInClientChannelFailedToClose](4801-discoveryclientinclientchannelfailedtoclose.md)|Advertencia|No se pudo cerrar el DiscoveryClient creado en DiscoveryClientChannel y, por lo tanto, se ha anulado.|Detección|  
|[4802 - DiscoveryClientProtocolExceptionSuppressed](4802-discoveryclientprotocolexceptionsuppressed.md)|Información|Se ha suprimido ProtocolException al cerrar DiscoveryClient. Esto se puede deber a que DiscoveryService todavía está intentando enviar una respuesta a DiscoveryClient.|Detección|  
|[4803 - DiscoveryClientReceivedMulticastSuppression](4803-discoveryclientreceivedmulticastsuppression.md)|Información|DiscoveryClient recibió un mensaje de supresión multidifusión de DiscoveryProxy.|Detección|  
|[4804 - DiscoveryMessageReceivedAfterOperationCompleted](4804-discoverymessagereceivedafteroperationcompleted.md)|Información|DiscoveryClient quitó un mensaje %1 con messageId='%2' porque se completó la operación %3 correspondiente.|Detección|  
|[4805 - DiscoveryMessageWithInvalidContent](4805-discoverymessagewithinvalidcontent.md)|Advertencia|Se eliminó un mensaje %1 con messageId='%2' porque incluía contenido no válido.|Detección|  
|[4806 - DiscoveryMessageWithInvalidRelatesToOrOperationCompleted](4806-discoverymessagewithinvalidrelatestooroperationcompleted.md)|Advertencia|DiscoveryClient eliminó un mensaje %1 con messageId='%2 y relatesTo='%3 porque se completó la operación %4 correspondiente o el valor de relatesTo no es válido.|Detección|  
|[4807 - DiscoveryMessageWithInvalidReplyTo](4807-discoverymessagewithinvalidreplyto.md)|Advertencia|Se quitó un mensaje de solicitud de detección con messageId='%1' porque tenía una dirección ReplyTo no válida.|Detección|  
|[4808 - DiscoveryMessageWithNoContent](4808-discoverymessagewithnocontent.md)|Advertencia|Se eliminó un mensaje %1 porque no incluía contenido.|Detección|  
|[4809 - DiscoveryMessageWithNullMessageId](4809-discoverymessagewithnullmessageid.md)|Advertencia|Se quitó un mensaje %1 porque el encabezado de mensaje no contenía la propiedad MessageId requerida.|Detección|  
|[4810 - DiscoveryMessageWithNullMessageSequence](4810-discoverymessagewithnullmessagesequence.md)|Advertencia|DiscoveryClient quitó un mensaje %1 con messageId='%2' porque no tenía la propiedad DiscoveryMessageSequence.|Detección|  
|[4811 - DiscoveryMessageWithNullRelatesTo](4811-discoverymessagewithnullrelatesto.md)|Advertencia|DiscoveryClient quitó un mensaje %1 con messageId='%2' porque el encabezado de mensaje no contenía la propiedad RelatesTo requerida.|Detección|  
|[4812 - DiscoveryMessageWithNullReplyTo](4812-discoverymessagewithnullreplyto.md)|Advertencia|Se quitó un mensaje de solicitud de detección con messageId='%1' porque no tenía una dirección ReplyTo.|Detección|  
|[4813 - DuplicateDiscoveryMessage](4813-duplicatediscoverymessage.md)|Advertencia|Se quitó un mensaje %1 con messageId='%2' porque era un duplicado.|Detección|  
|[4814 - EndpointDiscoverabilityDisabled](4814-endpointdiscoverabilitydisabled.md)|Información|Se ha deshabilitado la detectabilidad de extremo con EndpointAddress='%1' y ListenUri='%2'.|Detección|  
|[4814 - EndpointDiscoverabilityDisabled](4814-endpointdiscoverabilitydisabled.md)|Información|Se ha habilitado la detectabilidad de extremo con EndpointAddress='%1' y ListenUri='%2'.|Detección|  
|[4816 - FindInitiatedInDiscoveryClientChannel](4816-findinitiatedindiscoveryclientchannel.md)|Verbose|Se inició una operación de búsqueda en el DiscoveryClientChannel para descubrir los extremos.|Detección|  
|[4817 - InnerChannelCreationFailed](4817-innerchannelcreationfailed.md)|Advertencia|DiscoveryClientChannel no pudo crear el canal con un punto de conexión detectado con EndpointAddress='%1' y Via='%2'. DiscoveryClientChannel ahora intentará usar el siguiente extremo detectable disponible.|Detección|  
|[4818 - InnerChannelOpenFailed](4818-innerchannelopenfailed.md)|Advertencia|DiscoveryClientChannel no pudo abrir el canal con un punto de conexión detectado con EndpointAddress='%1' y Via='%2' DiscoveryClientChannel ahora intentará usar el siguiente extremo detectable disponible.|Detección|  
|[4819 - InnerChannelOpenSucceeded](4819-innerchannelopensucceeded.md)|Información|DiscoveryClientChannel detectó correctamente un punto de conexión y abrió el canal con él. El cliente está conectado a un servicio que usa EndpointAddress='%1' y Via='%2'.|Detección|  
|[4820 - SynchronizationContextReset](4820-synchronizationcontextreset.md)|Información|SynchronizationContext se ha restablecido a su valor original de %1 mediante DiscoveryClientChannel.|Detección|  
|[4821 - SynchronizationContextSetToNull](4821-synchronizationcontextsettonull.md)|Información|SynchronizationContext se ha establecido en NULL mediante DiscoveryClientChannel antes de iniciar la operación Find.|Detección|  
|[5001 - DCSerializeWithSurrogateStart](5001-dcserializewithsurrogatestart.md)|Verbose|Inicio de la serialización de DataContract %1 con suplentes.|Serialización|  
|[5002 - DCSerializeWithSurrogateStop](5002-dcserializewithsurrogatestop.md)|Verbose|Detención de la serialización de DataContract con suplentes.|Serialización|  
|[5003 - DCDeserializeWithSurrogateStart](5003-dcdeserializewithsurrogatestart.md)|Verbose|Inicio de la deserialización de DataContract %1 con suplentes.|Serialización|  
|[5004 - DCDeserializeWithSurrogateStop](5004-dcdeserializewithsurrogatestop.md)|Verbose|Detención de la deserialización de DataContract con suplentes.|Serialización|  
|[5005 - ImportKnownTypesStart](5005-importknowntypesstart.md)|Verbose|Inicio de ImportKnownTypes.|Serialización|  
|[5006 - ImportKnownTypesStop](5006-importknowntypesstop.md)|Verbose|Detención de ImportKnownTypes.|Serialización|  
|[5007 - DCResolverResolve](5007-dcresolverresolve.md)|Verbose|Inicio %1 de la resolución del resolvedor de DataContract .|Serialización|  
|[5008 - DCGenWriterStart](5008-dcgenwriterstart.md)|Verbose|Inicio del escritor %1 para %2 de la generación del DataContract .|Serialización|  
|[5009 - DCGenWriterStop](5009-dcgenwriterstop.md)|Verbose|Detención del escritor de la generación de DataContract.|Serialización|  
|[5010 - DCGenReaderStart](5010-dcgenreaderstart.md)|Verbose|Inicio del lector %1 para %2 de la generación de DataContract.|Serialización|  
|[5011 - DCGenReaderStop](5011-dcgenreaderstop.md)|Verbose|Detención de la generación de DataContract.|Serialización|  
|[5012 - DCJsonGenReaderStart](5012-dcjsongenreaderstart.md)|Verbose|Inicio del lector %1 para %2 de la generación de Json.|Serialización|  
|[5013 - DCJsonGenReaderStop](5013-dcjsongenreaderstop.md)|Verbose|Detención de la generación del lector de Json.|Serialización|  
|[5014 - DCJsonGenWriterStart](5014-dcjsongenwriterstart.md)|Verbose|Inicio del escritor %1 para %2 de la generación de Json.|Serialización|  
|[5015 - DCJsonGenWriterStop](5015-dcjsongenwriterstop.md)|Verbose|Detención del escritor de la generación de Json.|Serialización|  
|[5016 - GenXmlSerializableStart](5016-genxmlserializablestart.md)|Verbose|Inicio de Generate Xml serializable para '%1'.|Serialización|  
|[5017 - GenXmlSerializableStop](5017-genxmlserializablestop.md)|Verbose|Detención de Generate Xml serializable.|Serialización|  
|[5203 - JsonMessageDecodingStart](5203-jsonmessagedecodingstart.md)|Verbose|JsonMessageEncoder inició la descodificación del mensaje.|Canal|  
|[5204 - JsonMessageEncodingStart](5204-jsonmessageencodingstart.md)|Verbose|JsonMessageEncoder inició la codificación del mensaje.|Canal|  
|[5402 - TokenValidationStarted](5402-tokenvalidationstarted.md)|Verbose|Se inició la validación de SecurityToken (tipo '%1' e id. '%2').|Seguridad|  
|[5403 - TokenValidationSuccess](5403-tokenvalidationsuccess.md)|Verbose|Validación correcta de SecurityToken (tipo '%1' e id. '%2').|Seguridad|  
|[5404 - TokenValidationFailure](5404-tokenvalidationfailure.md)|Error|Error de validación de SecurityToken (tipo '%1' e id. '%2'). %3|Seguridad|  
|[5405 - GetIssuerNameSuccess](5405-getissuernamesuccess.md)|Verbose|Recuperación correcta del nombre del emisor:%1 desde tokenId:%2 .|Seguridad|  
|[5406 - GetIssuerNameFailure](5406-getissuernamefailure.md)|Error|Error al recuperar el nombre del emisor desde tokenId:%1.|Seguridad|  
|[5600 - FederationMessageProcessingStarted](5600-federationmessageprocessingstarted.md)|Verbose|Se inició el procesamiento de mensajes de la federación.|Seguridad|  
|[5601 - FederationMessageProcessingSuccess](5601-federationmessageprocessingsuccess.md)|Verbose|El procesamiento de mensajes de la federación se realizó correctamente.|Seguridad|  
|[5602 - FederationMessageCreationStarted](5602-federationmessagecreationstarted.md)|Verbose|Se inició la creación del mensaje de federación a partir del formulario post.|Seguridad|  
|[5603 - FederationMessageCreationSuccess](5603-federationmessagecreationsuccess.md)|Verbose|La creación del mensaje de federación a partir del formulario post se realizó correctamente.|Seguridad|  
|[5604 - SessionCookieReadingStarted](5604-sessioncookiereadingstarted.md)|Verbose|Se inició la lectura del token de sesión de la cookie de sesión.|Seguridad|  
|[5605 - SessionCookieReadingSuccess](5605-sessioncookiereadingsuccess.md)|Verbose|La lectura del token de sesión de la cookie de sesión se realizó correctamente.|Seguridad|  
|[5606 - PrincipalSettingFromSessionTokenStarted](5606-principalsettingfromsessiontokenstarted.md)|Verbose|Se inició la configuración principal del token de sesión.|Seguridad|  
|[5607 - PrincipalSettingFromSessionTokenSuccess](5607-principalsettingfromsessiontokensuccess.md)|Verbose|La configuración principal de token de sesión se realizó correctamente.|Seguridad|  
|[57393 - AppDomainUnload](57393-appdomainunload.md)|Información|Descargando AppDomain. AppDomain.FriendlyName %1 ProcessName %2, ProcessId %3.|Infraestructura|  
|[57394 - HandledException](57394-handledexception.md)|Información|Control de una excepción.|Infraestructura|  
|[57395 - ShipAssertExceptionMessage](57395-shipassertexceptionmessage.md)|Error|Error inesperado. Las aplicaciones no deberían intentar controlar este error. Para el diagnóstico, este mensaje en inglés se asocia con el error: %1.|Infraestructura|  
|[57396 - ThrowingException](57396-throwingexception.md)|Advertencia|Generación de una excepción. Origen %1.|Infraestructura|  
|[57397 - UnhandledException](57397-unhandledexception.md)|Crítico|Excepción no controlada.|Infraestructura|  
|[57399 - TraceCodeEventLogCritical](57399-tracecodeeventlogcritical.md)|Crítico|Se escribió en el registro de sucesos.|Infraestructura|  
|[57400 - TraceCodeEventLogError](57400-tracecodeeventlogerror.md)|Error|Se escribió en el registro de sucesos.|Infraestructura|  
|[57401 - TraceCodeEventLogInfo](57401-tracecodeeventloginfo.md)|Información|Se escribió en el registro de sucesos.|Infraestructura|  
|[57402 - TraceCodeEventLogVerbose](57402-tracecodeeventlogverbose.md)|Verbose|Se escribió en el registro de sucesos.|Infraestructura|  
|[57403 - TraceCodeEventLogWarning](57403-tracecodeeventlogwarning.md)|Advertencia|Se escribió en el registro de sucesos.|Infraestructura|  
|[57404 - HandledExceptionWarning](57404-handledexceptionwarning.md)|Advertencia|Control de una excepción.|Infraestructura|  
|[62326 - HttpHandlerPickedForUrl](62326-httphandlerpickedforurl.md)|Información|La dirección URL '%1' hospeda un documento XAML con el tipo de elemento raíz '%2'. El tipo de controlador HTTP '%3' se ha seleccionado para atender todas las solicitudes realizadas a esta dirección URL.|WebHost|
