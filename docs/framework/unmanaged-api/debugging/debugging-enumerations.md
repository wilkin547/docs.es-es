---
title: Enumeraciones de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: a83b1aa0b2cc068ed2f73dca04083b1085d45201
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789169"
---
# <a name="debugging-enumerations"></a>Enumeraciones de depuración
En esta sección se describen las enumeraciones no administradas que utiliza la API de depuración.  
  
## <a name="in-this-section"></a>Esta sección  
 [CLR_DEBUGGING_PROCESS_FLAGS (enumeración)](clr-debugging-process-flags-enumeration.md)  
 Proporciona valores que usa el método [ICLRDebugging:: openvirtualprocess (](iclrdebugging-openvirtualprocess-method.md) .  
  
 [CLRDataEnumMemoryFlags (enumeración)](clrdataenummemoryflags-enumeration.md)  
 Indica qué regiones de memoria debe incluir una llamada al método [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) .  
  
 [COR_PUB_ENUMPROCESS (enumeración)](cor-pub-enumprocess-enumeration.md)  
 Identifica el tipo de proceso que se va a enumerar.  
  
 [CorDebugBlockingReason (enumeración)](cordebugblockingreason-enumeration.md)  
 Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.  
  
 CorDebugChainReason  
 Indica el motivo o los motivos para que se inicie una cadena de llamadas.  
  
 [CorDebugCodeInvokeKind (enumeración)](cordebugcodeinvokekind-enumeration.md)  
 Describe cómo una función exportada invoca a código administrado.  
  
 [CorDebugCodeInvokePurpose (enumeración)](cordebugcodeinvokepurpose-enumeration.md)  
 Explica los motivos por los que una función exportada llama a código administrado.  
  
 CorDebugCreateProcessFlags  
 Proporciona opciones de depuración adicionales que se pueden usar en una llamada al método [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .  
  
 [CorDebugDebugEventKind (enumeración)](cordebugdebugeventkind-enumeration.md)  
 Indica el tipo de evento cuya información se descodifica mediante el método [DecodeEvent](icordebugprocess6-decodeevent-method.md) .  
  
 [CorDebugDecodeEventFlagsWindows (enumeración)](cordebugdecodeeventflagswindows-enumeration.md)  
 Proporciona información extra sobre los eventos de depuración en la plataforma Windows.  
  
 CorDebugExceptionCallbackType  
 Indica el tipo de devolución de llamada que se realiza desde un evento [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .  
  
 [CorDebugExceptionFlags (enumeración)](cordebugexceptionflags-enumeration.md)  
 Proporciona información adicional sobre una excepción.  
  
 CorDebugExceptionUnwindCallbackType  
 Indica el evento que la devolución de llamada señala durante la fase de desenredo.  
  
 [CorDebugGCType (enumeración)](cordebuggctype-enumeration.md)  
 Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.  
  
 [CorDebugGenerationTypes (enumeración)](cordebuggenerationtypes-enumeration.md)  
 Especifica la generación de una región de memoria en el montón administrado.  
  
 CorDebugHandleType  
 Indica el tipo de control.  
  
 [CorDebugIlToNativeMappingTypes (enumeración)](cordebugiltonativemappingtypes-enumeration.md)  
 Indica si un intervalo de instrucciones nativas determinado se corresponde con una región de código especial.  
  
 CorDebugIntercept  
 Indica los tipos de código que se pueden ejecutar paso a paso.  
  
 [CorDebugInterfaceVersion (enumeración)](cordebuginterfaceversion-enumeration.md)  
 Especifica una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.  
  
 CorDebugInternalFrameType  
 Identifica el tipo de marco de pila.  
  
 [CorDebugJITCompilerFlags (enumeración)](cordebugjitcompilerflags-enumeration.md)  
 Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.  
  
 [CorDebugJITCompilerFlagsDeprecated (enumeración)](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Obsoleta. En su lugar, use el miembro `CORDEBUG_JIT_DEFAULT` de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) .  
  
 CorDebugMappingResult  
 Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).  
  
 [CorDebugMDAFlags (enumeración)](cordebugmdaflags-enumeration.md)  
 Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).  
  
 [CorDebugNGenPolicy (enumeración)](cordebugngenpolicy-enumeration.md)  
 Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.  
  
 [CorDebugPlatform (enumeración)](cordebugplatform-enumeration.md)  
 Proporciona valores de plataforma de destino utilizados por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .  
  
 [CorDebugRecordFormat (enumeración)](cordebugrecordformat-enumeration.md)  
 Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.  
  
 CorDebugRegister  
 Especifica los registros asociados con una arquitectura de procesador determinada.  
  
 [CorDebugSetContextFlag (enumeración)](cordebugsetcontextflag-enumeration.md)  
 Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.  
  
 [CorDebugStateChange (enumeración)](cordebugstatechange-enumeration.md)  
 Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.  
  
 CorDebugStepReason  
 Indica el resultado de un paso individual.  
  
 CorDebugThreadState  
 Especifica el estado de un subproceso de depuración.  
  
 \>CorDebugUnmappedStop  
 Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.  
  
 CorDebugUserState  
 Indica el estado de uso de un subproceso.  
  
 [CorGCReferenceType (enumeración)](corgcreferencetype-enumeration.md)  
 Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.  
  
 [ILCodeKind (enumeración)](ilcodekind-enumeration.md)  
 Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 [LoggingLevelEnum (enumeración)](logginglevelenum-enumeration.md)  
 Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.  
  
 [LogSwitchCallReason (enumeración)](logswitchcallreason-enumeration.md)  
 Indica la operación que se realizó en un conmutador de depuración/seguimiento.  
  
 [VariableLocationType (enumeración)](variablelocationtype-enumeration.md)  
 Indica el tipo de ubicación nativa de una variable.  
  
 [WriteableMetadataUpdateMode (enumeración)](writeablemetadataupdatemode-enumeration.md)  
 Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador. 

 [Enumeración ClrDataSourceType](clrdatasourcetype-enumeration.md) Proporciona valores utilizados por la estructura de CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para la depuración](debugging-coclasses.md)  
  
 [Interfaces de depuración](debugging-interfaces.md)  
  
 [Funciones estáticas globales de depuración](debugging-global-static-functions.md)  
  
 [Estructuras de depuración](debugging-structures.md)
