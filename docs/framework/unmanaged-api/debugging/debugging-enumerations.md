---
title: Enumeraciones de depuración
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5edd6dfb3dac05ce4614c43949f2ec4c19b5f742
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415954"
---
# <a name="debugging-enumerations"></a>Enumeraciones de depuración
En esta sección se describen las enumeraciones no administradas que utiliza la API de depuración.  
  
## <a name="in-this-section"></a>En esta sección  
 [CLR_DEBUGGING_PROCESS_FLAGS (enumeración)](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 Proporciona valores que se usan por el [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método.  
  
 [CLRDataEnumMemoryFlags (enumeración)](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 Indica qué regiones de memoria de una llamada a la [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) debe incluir el método.  
  
 [COR_PUB_ENUMPROCESS (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 Identifica el tipo de proceso que se va a enumerar.  
  
 [CorDebugBlockingReason (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.  
  
 CorDebugChainReason  
 Indica el motivo o los motivos para que se inicie una cadena de llamadas.  
  
 [CorDebugCodeInvokeKind (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 Describe cómo una función exportada invoca a código administrado.  
  
 [CorDebugCodeInvokePurpose (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 Explica los motivos por los que una función exportada llama a código administrado.  
  
 CorDebugCreateProcessFlags  
 Proporciona opciones de depuración adicionales que pueden usarse en una llamada a la [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) método.  
  
 [CorDebugDebugEventKind (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 Indica el tipo de evento cuya información se descodifica mediante la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método.  
  
 [CorDebugDecodeEventFlagsWindows (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 Proporciona información extra sobre los eventos de depuración en la plataforma Windows.  
  
 CorDebugExceptionCallbackType  
 Indica el tipo de devolución de llamada que se realiza desde un [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) eventos.  
  
 [CorDebugExceptionFlags (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 Proporciona información adicional sobre una excepción.  
  
 CorDebugExceptionUnwindCallbackType  
 Indica el evento que la devolución de llamada señala durante la fase de desenredo.  
  
 [CorDebugGCType (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.  
  
 [CorDebugGenerationTypes (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 Especifica la generación de una región de memoria en el montón administrado.  
  
 CorDebugHandleType  
 Indica el tipo de control.  
  
 [CorDebugIlToNativeMappingTypes (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 Indica si un intervalo de instrucciones nativas determinado se corresponde con una región de código especial.  
  
 CorDebugIntercept  
 Indica los tipos de código que se pueden ejecutar paso a paso.  
  
 [CorDebugInterfaceVersion (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 Especifica una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.  
  
 CorDebugInternalFrameType  
 Identifica el tipo de marco de pila.  
  
 [CorDebugJITCompilerFlags (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 Contiene valores que influyen en el comportamiento del compilador Just-In-Time (JIT) administrado.  
  
 [CorDebugJITCompilerFlagsDeprecated (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Obsoleto. Use la `CORDEBUG_JIT_DEFAULT` miembro de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeración en su lugar.  
  
 CorDebugMappingResult  
 Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).  
  
 [CorDebugMDAFlags (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).  
  
 [CorDebugNGenPolicy (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 Proporciona un valor que determina si un depurador carga imágenes nativas (NGen) desde la caché de imágenes nativas.  
  
 [CorDebugPlatform (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 Proporciona valores de plataforma de destino que se usan por el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.  
  
 [CorDebugRecordFormat (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.  
  
 CorDebugRegister  
 Especifica los registros asociados con una arquitectura de procesador determinada.  
  
 [CorDebugSetContextFlag (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.  
  
 [CorDebugStateChange (enumeración)](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.  
  
 CorDebugStepReason  
 Indica el resultado de un paso individual.  
  
 CorDebugThreadState  
 Especifica el estado de un subproceso de depuración.  
  
 \>CorDebugUnmappedStop  
 Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.  
  
 CorDebugUserState  
 Indica el estado de uso de un subproceso.  
  
 [CorGCReferenceType (enumeración)](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 Identifica el origen de un objeto que se va a recolectar como elemento no utilizado.  
  
 [ILCodeKind (enumeración)](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 Proporciona valores que especifican si el depurador puede acceder a las variables locales o al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 [LoggingLevelEnum (enumeración)](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 Indica el nivel de gravedad de un mensaje descriptivo que se escribe en el registro de eventos cuando un subproceso administrado registra un evento.  
  
 [LogSwitchCallReason (enumeración)](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 Indica la operación que se realizó en un conmutador de depuración/seguimiento.  
  
 [VariableLocationType (enumeración)](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 Indica el tipo de ubicación nativa de una variable.  
  
 [WriteableMetadataUpdateMode (enumeración)](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 Proporciona valores que especifican si las actualizaciones en memoria de los metadatos son visibles para un depurador. 

 [Enumeración ClrDataSourceType](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) proporciona valores que son usados por la estructura CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
