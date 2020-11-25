---
title: Enumeraciones de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: bdd4b60d068677ae2a0874b589294ba220f0d854
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723004"
---
# <a name="debugging-enumerations"></a>Enumeraciones de depuración

En esta sección se describen las enumeraciones no administradas que utiliza la API de depuración.  
  
## <a name="in-this-section"></a>En esta sección  

 [CLR_DEBUGGING_PROCESS_FLAGS (Enumeración)](clr-debugging-process-flags-enumeration.md)  
 Proporciona valores que usa el método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .  
  
 [CLRDataEnumMemoryFlags (Enumeración)](clrdataenummemoryflags-enumeration.md)  
 Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .  
  
 [COR_PUB_ENUMPROCESS (Enumeración)](cor-pub-enumprocess-enumeration.md)  
 Identifica el tipo de proceso que se va a enumerar.  
  
 [CorDebugBlockingReason (Enumeración)](cordebugblockingreason-enumeration.md)  
 Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.  
  
 CorDebugChainReason  
 Indica el motivo o los motivos para que se inicie una cadena de llamadas.  
  
 [Enumeración CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)  
 Describe cómo una función exportada invoca a código administrado.  
  
 [Enumeración CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)  
 Explica los motivos por los que una función exportada llama a código administrado.  
  
 CorDebugCreateProcessFlags  
 Proporciona opciones de depuración adicionales que se pueden usar en una llamada al método [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .  
  
 [Enumeración CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md)  
 Indica el tipo de evento cuya información se descodifica mediante el método [DecodeEvent](icordebugprocess6-decodeevent-method.md) .  
  
 [Enumeración CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)  
 Proporciona información extra sobre los eventos de depuración en la plataforma Windows.  
  
 CorDebugExceptionCallbackType  
 Indica el tipo de devolución de llamada que se realiza desde un evento [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .  
  
 [CorDebugExceptionFlags (Enumeración)](cordebugexceptionflags-enumeration.md)  
 Proporciona información adicional sobre una excepción.  
  
 CorDebugExceptionUnwindCallbackType  
 Indica el evento que la devolución de llamada señala durante la fase de desenredo.  
  
 [CorDebugGCType (Enumeración)](cordebuggctype-enumeration.md)  
 Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.  
  
 [CorDebugGenerationTypes (Enumeración)](cordebuggenerationtypes-enumeration.md)  
 Especifica la generación de una región de memoria en el montón administrado.  
  
 CorDebugHandleType  
 Indica el tipo de control.  
  
 [CorDebugIlToNativeMappingTypes (Enumeración)](cordebugiltonativemappingtypes-enumeration.md)  
 Indica si un intervalo de instrucciones nativas determinado se corresponde con una región de código especial.  
  
 CorDebugIntercept  
 Indica los tipos de código que se pueden ejecutar paso a paso.  
  
 [CorDebugInterfaceVersion (Enumeración)](cordebuginterfaceversion-enumeration.md)  
 Especifica una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.  
  
 CorDebugInternalFrameType  
 Identifica el tipo de marco de pila.  
  
 [CorDebugJITCompilerFlags (Enumeración)](cordebugjitcompilerflags-enumeration.md)  
 Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.  
  
 [CorDebugJITCompilerFlagsDeprecated (Enumeración)](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Obsoleto. `CORDEBUG_JIT_DEFAULT`En su lugar, use el miembro de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .  
  
 CorDebugMappingResult  
 Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).  
  
 [CorDebugMDAFlags (Enumeración)](cordebugmdaflags-enumeration.md)  
 Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).  
  
 [CorDebugNGenPolicy (Enumeración)](cordebugngenpolicy-enumeration.md)  
 Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.  
  
 [CorDebugPlatform (Enumeración)](cordebugplatform-enumeration.md)  
 Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .  
  
 [Enumeración CorDebugRecordFormat](cordebugrecordformat-enumeration.md)  
 Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.  
  
 CorDebugRegister  
 Especifica los registros asociados con una arquitectura de procesador determinada.  
  
 [CorDebugSetContextFlag (Enumeración)](cordebugsetcontextflag-enumeration.md)  
 Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.  
  
 [Enumeración CorDebugStateChange](cordebugstatechange-enumeration.md)  
 Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.  
  
 CorDebugStepReason  
 Indica el resultado de un paso individual.  
  
 CorDebugThreadState  
 Especifica el estado de un subproceso de depuración.  
  
 \>Cordebugunmappedstop (  
 Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.  
  
 CorDebugUserState  
 Indica el estado de uso de un subproceso.  
  
 [CorGCReferenceType (Enumeración)](corgcreferencetype-enumeration.md)  
 Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.  
  
 [ILCodeKind (Enumeración)](ilcodekind-enumeration.md)  
 Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 [LoggingLevelEnum (Enumeración)](logginglevelenum-enumeration.md)  
 Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.  
  
 [LogSwitchCallReason (Enumeración)](logswitchcallreason-enumeration.md)  
 Indica la operación que se realizó en un conmutador de depuración/seguimiento.  
  
 [Enumeración VariableLocationType](variablelocationtype-enumeration.md)  
 Indica el tipo de ubicación nativa de una variable.  
  
 [WriteableMetadataUpdateMode (Enumeración)](writeablemetadataupdatemode-enumeration.md)  
 Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador.

 [Enumeración ClrDataSourceType](clrdatasourcetype-enumeration.md) Proporciona valores utilizados por la estructura de CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Secciones relacionadas  

 [Coclases para la depuración](debugging-coclasses.md)  
  
 [Interfaces para depuración](debugging-interfaces.md)  
  
 [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)  
  
 [Estructuras de depuración](debugging-structures.md)
