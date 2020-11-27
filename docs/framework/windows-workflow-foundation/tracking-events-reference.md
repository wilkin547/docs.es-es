---
title: Referencia de eventos de seguimiento
ms.date: 03/30/2017
ms.assetid: c1c1ee87-f80a-449b-acd0-50d81eef116e
ms.openlocfilehash: 7a1bbabbbc122429908b0f9c038c145a5d4a1e7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293356"
---
# <a name="tracking-events-reference"></a>Referencia de eventos de seguimiento

Durante la ejecución, el flujo de trabajo en [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] genera eventos de seguimiento cuando va pasando por sus distintas fases de su duración. El host puede suscribirse a estos eventos y mantenerse actualizado con el estado del progreso del flujo de trabajo todo el tiempo que dure. Los eventos de seguimiento generados se tratan en esta sección.  
  
## <a name="event-reference"></a>Referencia de eventos  
  
|Id. de evento|Nivel de evento|Mensaje del evento|Palabras clave|  
|--------------|-----------------|-------------------|--------------|  
|[100 - WorkflowInstanceRecord](100-workflowinstancerecord.md)|Información|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[101 - WorkflowInstanceUnhandledExceptionRecord](101-workflowinstanceunhandledexceptionrecord.md)|Error|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[102 - WorkflowInstanceAbortedRecord](102-workflowinstanceabortedrecord.md)|Advertencia|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[103 - ActivityStateRecord](103-activitystaterecord.md)|Información|TrackRecord = ActivityStateRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, State = %4, Name=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Arguments=%9, Variables=%10, Annotations=%11, ProfileName = %12|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[104 - ActivityScheduledRecord](104-activityscheduledrecord.md)|Información|TrackRecord = ActivityScheduledRecord, InstanceID = %1,  RecordNumber = %2, EventTime = %3, Name = %4, ActivityId = %5, ActivityInstanceId = %6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[105 - FaultPropagationRecord](105-faultpropagationrecord.md)|Advertencia|TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[106 - CancelRequestRecord](106-cancelrequestrecord.md)|Información|TrackRecord = CancelRequestedRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityId=%5, ActivityInstanceId=%6, ActivityTypeName = %7, ChildActivityName = %8, ChildActivityId = %9, ChildActivityInstanceId = %10, ChildActivityTypeName =%11, Annotations=%12, ProfileName = %13|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[107 -- BookmarkResumptionRecord](107-bookmarkresumptionrecord.md)|Información|TrackRecord = BookmarkResumptionRecord, InstanceID=%1, RecordNumber=%2,EventTime=%3, Name=%4, SubInstanceID=%5, OwnerActivityName=%6, OwnerActivityId =%7, OwnerActivityInstanceId=%8, OwnerActivityTypeName=%9, Annotations=%10, ProfileName = %11|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[108 - CustomTrackingRecordInfo](108-customtrackingrecordinfo.md)|Información|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[110 - CustomTrackingRecordWarning](110-customtrackingrecordwarning.md)|Advertencia|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[111 - CustomTrackingRecordError](111-customtrackingrecorderror.md)|Error|TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3, Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11|UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[112 - WorkflowInstanceSuspendedRecord](112-workflowinstancesuspendedrecord.md)|Información|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[113 - WorkflowInstanceTerminatedRecord](113-workflowinstanceterminatedrecord.md)|Error|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7|EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking|  
|[114 - WorkflowInstanceRecordWithId](114-workflowinstancerecordwithid.md)|Información|TrackRecord= WorkflowInstanceRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[115 - WorkflowInstanceAbortedRecordWithId](115-workflowinstanceabortedrecordwithid.md)|Advertencia|TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[116 - WorkflowInstanceSuspendedRecordWithId](116-workflowinstancesuspendedrecordwithid.md)|Información|TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[117 - WorkflowInstanceTerminatedRecordWithId](117-workflowinstanceterminatedrecordwithid.md)|Error|TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8|HealthMonitoring, WFTracking|  
|[118 - WorkflowInstanceUnhandledExceptionRecordWithId](118-workflowinstanceunhandledexceptionrecordwithid.md)|Error|TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9,  Annotations= %10, ProfileName = %11, WorkflowDefinitionIdentity = %12|HealthMonitoring, WFTrackingHealthMonitoring, WFTracking|  
|[119 - WorkflowInstanceUpdatedRecord](119-workflowinstanceupdatedrecord.md)|Información|TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9|HealthMonitoring, WFTracking|  
|[225 - TraceCorrelationKeys](225-tracecorrelationkeys.md)|Información|Clave de correlación calculada '%1' que usa valores '%2' en el ámbito principal '%3'.|Solucionar problemas de servicios de WF|  
|[440 - StartSignpostEvent1](440-startsignpostevent.md)|Información|Límite de la actividad.|Solucionar problemas de servicios de WF|  
|[441- StopSignpostEvent1](441-stopsignpostevent.md)|Información|Límite de la actividad.|Solucionar problemas de servicios de WF|  
|[1001 - WorkflowApplicationCompleted](1001-workflowapplicationcompleted.md)|Información|WorkflowInstance Id: '%1' se completó en el estado Closed.|WFRuntime|  
|[1002 - WorkflowApplicationTerminated](1002-workflowapplicationterminated.md)|Información|WorkflowApplication Id: '%1' se terminó. Se ha completado con el estado Faulted y con una excepción.|WFRuntime|  
|[1003 - WorkflowInstanceCanceled](1003-workflowinstancecanceled.md)|Información|WorkflowInstance Id: '%1' se completó en el estado Canceled.|WFRuntime|  
|[1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md)|Información|WorkflowInstance Id: '%1' se anuló con una excepción.|WFRuntime|  
|[1005 - WorkflowApplicationIdled](1005-workflowapplicationidled.md)|Información|WorkflowApplication Id: '%1' se desactivó.|WFRuntime|  
|[1006 - WorkflowApplicationUnhandledException](1006-workflowapplicationunhandledexception.md)|Error|WorkflowInstance ID: ' %1 ' ha encontrado una excepción no controlada.  La excepción se originó a partir de la actividad ' %2 ', DisplayName: ' %3 '.  Se realizará la siguiente acción: %4.|WFRuntime|  
|[1007 - WorkflowApplicationPersisted](1007-workflowapplicationpersisted.md)|Información|WorkflowApplication Id: '%1' se conservó.|WFRuntime|  
|[1008 - WorkflowApplicationUnloaded](1008-workflowapplicationunloaded.md)|Información|WorkflowInstance Id: '%1' se descargó.|WFRuntime|  
|[1009 - ActivityScheduled](1009-activityscheduled.md)|Información|Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1010 - ActivityCompleted](1010-activitycompleted.md)|Información|Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1011 - ScheduleExecuteActivityWorkItem](1011-scheduleexecuteactivityworkitem.md)|Verbose|Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1012 - StartExecuteActivityWorkItem](1012-startexecuteactivityworkitem.md)|Verbose|Iniciando la ejecución de un ExecuteActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1013 - CompleteExecuteActivityWorkItem](1013-completeexecuteactivityworkitem.md)|Verbose|Un ExecuteActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1014 - ScheduleCompletionWorkItem](1014-schedulecompletionworkitem.md)|Verbose|Se ha programado un CompletionWorkItem para la actividad primaria ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1015 - StartCompletionWorkItem](1015-startcompletionworkitem.md)|Verbose|Iniciar la ejecución de un CompletionWorkItem para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'. Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1016 - CompleteCompletionWorkItem](1016-completecompletionworkitem.md)|Verbose|Un CompletionWorkItem se ha completado para la actividad primaria '%1', DisplayName: '%2', InstanceId: '%3'. Actividad completada '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1017 - ScheduleCancelActivityWorkItem](1017-schedulecancelactivityworkitem.md)|Verbose|Un CancelActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1018 - StartCancelActivityWorkItem](1018-startcancelactivityworkitem.md)|Verbose|Iniciando la ejecución de un CancelActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1019 - CompleteCancelActivityWorkItem](1019-completecancelactivityworkitem.md)|Verbose|Un CancelActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1020 - CreateBookmark](1020-createbookmark.md)|Verbose|Se ha creado un marcador para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1021 - ScheduleBookmarkWorkItem](1021-schedulebookmarkworkitem.md)|Verbose|Se ha programado un BookmarkWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1022 - StartBookmarkWorkItem](1022-startbookmarkworkitem.md)|Verbose|Iniciando la ejecución de un BookmarkWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1023 - CompleteBookmarkWorkItem](1023-completebookmarkworkitem.md)|Verbose|Un BookmarkWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'. BookmarkName: %4, BookmarkScope: %5.|WFRuntime|  
|[1024 - CreateBookmarkScope](1024-createbookmarkscope.md)|Verbose|Se ha creado un BookmarkScope: %1.|WFRuntime|  
|[1025 - BookmarkScopeInitialized](1025-bookmarkscopeinitialized.md)|Verbose|El objeto BookmarkScope con TemporaryId: '%1' se ha inicializado con el id.: '%2'.|WFRuntime|  
|[1026 - ScheduleTransactionContextWorkItem](1026-scheduletransactioncontextworkitem.md)|Verbose|Un TransactionContextWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1027 - StartTransactionContextWorkItem](1027-starttransactioncontextworkitem.md)|Verbose|Iniciando la ejecución de un TransactionContextWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1028 - CompleteTransactionContextWorkItem](1028-completetransactioncontextworkitem.md)|Verbose|Un TransactionContextWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1029 - ScheduleFaultWorkItem](1029-schedulefaultworkitem.md)|Verbose|Se ha programado un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1030 - StartFaultWorkItem](1030-startfaultworkitem.md)|Verbose|Iniciando la ejecución de un FaultWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1031 - CompleteFaultWorkItem](1031-completefaultworkitem.md)|Verbose|Un FaultWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'. La excepción se propagó desde la actividad '%4', DisplayName: '%5', InstanceId: '%6'.|WFRuntime|  
|[1032 - ScheduleRuntimeWorkItem](1032-scheduleruntimeworkitem.md)|Verbose|Se ha programado un elemento de trabajo en runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1033 - StartRuntimeWorkItem](1033-startruntimeworkitem.md)|Verbose|Iniciando la ejecución de un elemento de trabajo de runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1034 - CompleteRuntimeWorkItem](1034-completeruntimeworkitem.md)|Verbose|Se ha completado un elemento de trabajo en runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.|WFRuntime|  
|[1035 - RuntimeTransactionSet](1035-runtimetransactionset.md)|Verbose|La actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 ' estableció la transacción en tiempo de ejecución.  Ejecución aislada de la actividad ' %4 ', DisplayName: ' %5 ', InstanceId: ' %6 '.|WFRuntime|  
|[1036 - RuntimeTransactionCompletionRequested](1036-runtimetransactioncompletionrequested.md)|Verbose|La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en runtime.|WFRuntime|  
|[1037 - RuntimeTransactionComplete](1037-runtimetransactioncomplete.md)|Verbose|La transacción en runtime se ha completado con el estado '%1'.|WFRuntime|  
|[1038 - EnterNoPersistBlock](1038-enternopersistblock.md)|Verbose|Entrando en un bloque no persistente.|WFRuntime|  
|[1039 - ExitNoPersistBlock](1039-exitnopersistblock.md)|Verbose|Saliendo de un bloque no persistente.|WFRuntime|  
|[1040 - InArgumentBound](1040-inargumentbound.md)|Verbose|El argumento '%1' en la actividad '%2', DisplayName: '%3', InstanceId: '%4' se ha enlazado con el valor: %5.|WFActivities|  
|[1041 - WorkflowApplicationPersistableIdle](1041-workflowapplicationpersistableidle.md)|Información|WorkflowApplication ID: ' %1 ' está inactivo y es persistente.  Se realizará la siguiente acción: %2.|WFRuntime|  
|[1101 - WorkflowActivityStart](1101-workflowactivitystart.md)|Información|Id. de WorkflowInstance: '%1' actividad E2E|WFRuntime|  
|[1102 - WorkflowActivityStop](1102-workflowactivitystop.md)|Información|Id. de WorkflowInstance: '%1' actividad E2E|WFRuntime|  
|[1103 - WorkflowActivitySuspend](1103-workflowactivitysuspend.md)|Información|Id. de WorkflowInstance: '%1' actividad E2E|WFRuntime|  
|[1104 - WorkflowActivityResume](1104-workflowactivityresume.md)|Información|Id. de WorkflowInstance: '%1' actividad E2E|WFRuntime|  
|[1124 - InvokeMethodIsStatic](1124-invokemethodisstatic.md)|Información|InvokeMethod '%1': el método es estático.|WFRuntime|  
|[1125 - InvokeMethodIsNotStatic](1125-invokemethodisnotstatic.md)|Información|InvokeMethod '%1': el método no es estático.|WFRuntime|  
|[1126 - InvokedMethodThrewException](1126-invokedmethodthrewexception.md)|Información|Se produjo una excepción en el método invocado por la actividad '%1' %2|WFRuntime|  
|[1131 - InvokeMethodUseAsyncPattern](1131-invokemethoduseasyncpattern.md)|Información|InvokeMethod '%1': el método usa el patrón asincrónico de '%2' y '%3'.|WFRuntime|  
|[1132 - InvokeMethodDoesNotUseAsyncPattern](1132-invokemethoddoesnotuseasyncpattern.md)|Información|InvokeMethod '%1': el método no usa un patrón asincrónico.|WFRuntime|  
|[1140 - FlowchartStart](1140-flowchartstart.md)|Información|Flowchart '%1': se ha programado el inicio.|WFActivities|  
|[1141 - FlowchartEmpty](1141-flowchartempty.md)|Advertencia|Flowchart '%1' se ejecutó sin nodos. Se produjo una excepción en el método invocado por la actividad '%1' %2|WFActivities|  
|[1143 - FlowchartNextNull](1143-flowchartnextnull.md)|Información|Flowchart '%1'/FlowStep: el nodo siguiente es null. La ejecución del diagrama de flujo va a finalizar.|WFActivities|  
|[1146 - FlowchartSwitchCase](1146-flowchartswitchcase.md)|Información|Flowchart '%1'/FlowSwitch - Se seleccionó el caso '%2'.|WFActivities|  
|[1147 - FlowchartSwitchDefault](1147-flowchartswitchdefault.md)|Información|Flowchart '%1'/FlowSwitch - Se seleccionó el caso predeterminado.|WFActivities|  
|[1148 - FlowchartSwitchCaseNotFound](1148-flowchartswitchcasenotfound.md)|Información|Flowchart '%1'/FlowSwitch no puede encontrar una actividad Case ni un caso predeterminado que coincida con el resultado de la expresión. La ejecución del diagrama de flujo va a finalizar.|WFActivities|  
|[1150 - CompensationState](1150-compensationstate.md)|Información|CompensableActivity '%1' no tiene el estado '%2'.|WFActivities|  
|[1223 - SwitchCaseNotFound](1223-switchcasenotfound.md)|Información|La actividad Switch '%1' no puede encontrar una actividad Case que coincida con el resultado de la expresión.|WFActivities|  
|[1449 - WfMessageReceived](1449-wfmessagereceived.md)|Información|Mensaje recibido por el flujo de trabajo|WFServices|  
|[1450 - WfMessageSent](1450-wfmessagesent.md)|Información|Mensaje enviado desde el flujo de trabajo|WFServices|  
|[2021 - ExecuteWorkItemStart](2021-executeworkitemstart.md)|Verbose|Ejecutar el inicio del elemento de trabajo|WFRuntime|  
|[2022 - ExecuteWorkItemStop](2022-executeworkitemstop.md)|Verbose|Ejecutar la detención del elemento de trabajo|WFRuntime|  
|[2023 - SendMessageChannelCacheMiss](2023-sendmessagechannelcachemiss.md)|Verbose|Falta SendMessageChannelCache|WFRuntime|  
|[2024 - InternalCacheMetadataStart](2024-internalcachemetadatastart.md)|Verbose|InternalCacheMetadata se inicia en la actividad '%1'.|WFRuntime|  
|[2025 - InternalCacheMetadataStop](2025-internalcachemetadatastop.md)|Verbose|InternalCacheMetadata se detiene en la actividad '%1'.|WFRuntime|  
|[2026 - CompileVbExpressionStart](2026-compilevbexpressionstart.md)|Verbose|Compilando expresión de VB '%1'|WFRuntime|  
|[2027 - CacheRootMetadataStart](2027-cacherootmetadatastart.md)|Verbose|CacheRootMetadata se inicia en la actividad '%1'|WFRuntime|  
|[2028 - CacheRootMetadataStop](2028-cacherootmetadatastop.md)|Verbose|CacheRootMetadata se detiene en la actividad %1.|WFRuntime|  
|[2029 - CompileVbExpressionStop](2029-compilevbexpressionstop.md)|Verbose|Terminada la compilación de la expresión de VB.|WFRuntime|  
|[2576 - TryCatchExceptionFromTry](2576-trycatchexceptionfromtry.md)|Información|La actividad TryCatch '%1 ha detectado una excepción de tipo '%2'.|WFActivities|  
|[2577 - TryCatchExceptionDuringCancelation](2577-trycatchexceptionduringcancelation.md)|Advertencia|Una actividad secundaria de la actividad TryCatch '%1' produjo una excepción durante la cancelación.|WFActivities|  
|[2578 - TryCatchExceptionFromCatchOrFinally](2578-trycatchexceptionfromcatchorfinally.md)|Advertencia|Una actividad Catch o Finally asociada a la actividad TryCatch '%1' produjo una excepción.|WFActivities|  
|[3501 - InferredContractDescription](3501-inferredcontractdescription.md)|Información|ContractDescription con Name='%1' y Namespace='%2' se ha inferido de WorkflowService.|WFServices|  
|[3502 - InferredOperationDescription](3502-inferredoperationdescription.md)|Información|OperationDescription con Name='%1' en el contrato '%2' se ha inferido de WorkflowService. IsOneWay=%3.|WFServices|  
|[3503 - DuplicateCorrelationQuery](3503-duplicatecorrelationquery.md)|Advertencia|Se encontró una consulta CorrelationQuery duplicada con Where='%1'. Esta consulta duplicada no se usará al calcular la correlación.|WFServices|  
|[3507 - ServiceEndpointAdded](3507-serviceendpointadded.md)|Información|Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.|WFServices|  
|[3508 - TrackingProfileNotFound](3508-trackingprofilenotfound.md)|Verbose|No se encontró TrackingProfile '%1' para ActivityDefinitionId '%2'. No se encontró TrackingProfile en el archivo de configuración o no coincide el ActivityDefinitionId.|WFServices|  
|[3550 - BufferOutOfOrderMessageNoInstance](3550-bufferoutofordermessagenoinstance.md)|Información|La operación '%1' no se puede realizar en este momento. Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.|WFServices|  
|[3551 - BufferOutOfOrderMessageNoBookmark](3551-bufferoutofordermessagenobookmark.md)|Información|La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento. Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.|WFServices|  
|[3552 - MaxPendingMessagesPerChannelExceeded](3552-maxpendingmessagesperchannelexceeded.md)|Advertencia|Se alcanzó la limitación de 'MaxPendingMessagesPerChannel' de '%1'. Para aumentar este límite, ajuste la propiedad MaxPendingMessagesPerChannel en BufferedReceiveServiceBehavior.|Cuota WFServices|  
|[3557 - TransactedReceiveScopeEndCommitFailed](3557-transactedreceivescopeendcommitfailed.md)|Información|La llamada a EndCommit en la CommittableTransaction con el identificador ='%1' inició una TransactionException con el siguiente mensaje: '%2'.|WFServices|  
|[4201 - EndSqlCommandExecute](4201-endsqlcommandexecute.md)|Verbose|Ejecución de comando SQL final: %1|WFInstanceStore|  
|[4202 - StartSqlCommandExecute](4202-startsqlcommandexecute.md)|Verbose|Ejecución de comando SQL inicial: %1|WFInstanceStore|  
|[4203 - RenewLockSystemError](4203-renewlocksystemerror.md)|Error|Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó. Anulando SqlWorkflowInstanceStore.|WFInstanceStore|  
|[4205 - FoundProcessingError](4205-foundprocessingerror.md)|Error|Error de comando: %1|WFInstanceStore|  
|[4206 - UnlockInstanceException](4206-unlockinstanceexception.md)|Error|Excepción %1 al intentar desbloquear la instancia.|WFInstanceStore|  
|[4207 - MaximumRetriesExceededForSqlCommand](4207-maximumretriesexceededforsqlcommand.md)|Información|Se ha dejado de intentar un comando SQL ya que se ha realizado el número máximo de intentos.|Quota WFInstanceStore|  
|[4208 - RetryingSqlCommandDueToSqlError](4208-retryingsqlcommandduetosqlerror.md)|Información|Reintentando un comando SQL debido al número de error de SQL %1.|WFInstanceStore|  
|[4209 - TimeoutOpeningSqlConnection](4209-timeoutopeningsqlconnection.md)|Error|Se agotó el tiempo de espera al intentar abrir una conexión SQL. La operación no se completó dentro del tiempo de espera asignado de %1. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.|WFInstanceStore|  
|[4210 - SqlExceptionCaught](4210-sqlexceptioncaught.md)|Advertencia|Se detectó la excepción de SQL con el número %1 y el mensaje %2|WFInstanceStore|  
|[4211 - QueuingSqlRetry](4211-queuingsqlretry.md)|Advertencia|Poniendo en cola el reintento SQL con %1 milisegundos de retraso.|WFInstanceStore|  
|[4212 - LockRetryTimeout](4212-lockretrytimeout.md)|Advertencia|Tiempo de espera al intentar adquirir el bloqueo de la instancia.  La operación no se completó dentro del tiempo de espera asignado de %1. El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.|WFInstanceStore|  
|[4213 - RunnableInstancesDetectionError](4213-runnableinstancesdetectionerror.md)|Error|No se pudieron detectar las instancias ejecutables por la siguiente excepción|WFInstanceStore|  
|[4214 - InstanceLocksRecoveryError](4214-instancelocksrecoveryerror.md)|Error|No se pudieron recuperar los bloqueos de instancia por la siguiente excepción|WFInstanceStore|  
|[39456 - TrackingRecordDropped](39456-trackingrecorddropped.md)|Advertencia|El tamaño del registro de seguimiento %1 excede el máximo permitido por la sesión de ETW para el proveedor %2|WFTracking|  
|[39457 - TrackingRecordRaised](39457-trackingrecordraised.md)|Información|Registro de seguimiento %1 desencadenado para %2.|WFRuntime|  
|[39458 - TrackingRecordTruncated](39458-trackingrecordtruncated.md)|Advertencia|Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2. Se han quitado las variables, anotaciones y datos del usuario.|WFTracking|  
|[39459 - TrackingDataExtracted](39459-trackingdataextracted.md)|Verbose|Datos de seguimiento %1 extraídos en la actividad %2.|WFRuntime|  
|[39460 - TrackingValueNotSerializable](39460-trackingvaluenotserializable.md)|Advertencia|La variable o argumento '%1' que se ha extraído no se puede serializar.|WFTracking|  
|[57398 - MaxInstancesExceeded](57398-maxinstancesexceeded.md)|Advertencia|El sistema llegó al límite establecido para el acelerador 'MaxConcurrentInstances'. El límite para este acelerador se estableció en %1. El valor del acelerador puede cambiarse modificando el atributo 'maxConcurrentInstances' del elemento serviceThrottle o la propiedad 'MaxConcurrentInstances' en el comportamiento ServiceThrottlingBehavior.|WFServices|
