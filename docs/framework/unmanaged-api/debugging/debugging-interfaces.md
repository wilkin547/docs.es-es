---
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097192"
---
# <a name="debugging-interfaces"></a>Interfaces para depuración
En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>En esta sección  
 [ICLRDataEnumMemoryRegions (interfaz](iclrdataenummemoryregions-interface.md) )\
 Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.  
  
 \ de la [interfaz ICLRDataEnumMemoryRegionsCallback (](iclrdataenummemoryregionscallback-interface.md)
 Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.  
  
 [ICLRDataTarget (interfaz](iclrdatatarget-interface.md) )\
 Proporciona métodos para la interacción con un proceso de CLR de destino.  
  
 \ de la [interfaz ICLRDataTarget2](iclrdatatarget2-interface.md)
 Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.  
  
 \ de la [interfaz ICLRDataTarget3](iclrdatatarget3-interface.md)
 Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a la información de la excepción.  
  
 \ de la [interfaz ICLRDebugging](iclrdebugging-interface.md)
 Proporciona métodos que controlan la carga y descarga de módulos para depuración.  
  
 \ de la [interfaz ICLRDebuggingLibraryProvider (](iclrdebugginglibraryprovider-interface.md)
 Incluye el método del [método ProvideLibrary (](iclrdebugginglibraryprovider-providelibrary-method.md) , que obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite buscar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime.  
  
 \ de la [interfaz iclrmetadatalocator (](iclrmetadatalocator-interface.md)
 Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.  
  
 [ICorDebug (interfaz](icordebug-interface.md) )\
 Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.  
  
 [ICorDebugAppDomain (interfaz](icordebugappdomain-interface.md) )\
 Proporciona métodos para depurar dominios de aplicación.  
  
 \ de la [interfaz ICorDebugAppDomain2](icordebugappdomain2-interface.md)
 Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef. Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.  
  
 \ de la [interfaz ICorDebugAppDomain3](icordebugappdomain3-interface.md)
 Proporciona métodos para trabajar con los tipos de Windows Runtime en un dominio de aplicación. Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 \ de la [interfaz ICorDebugAppDomain4](icordebugappdomain4-interface.md)
 Extiende lógicamente la interfaz [ICorDebugAppDomain](icordebugappdomain-interface.md) para obtener un objeto administrado desde un contenedor com invocable.  
  
 \ de la [interfaz ICorDebugAppDomainEnum (](icordebugappdomainenum-interface.md)
 Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.  
  
 [ICorDebugArrayValue (interfaz](icordebugarrayvalue-interface.md) )\
 Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.  
  
 [ICorDebugAssembly (interfaz](icordebugassembly-interface.md) )\
 Representa un ensamblado.  
  
 \ de la [interfaz icordebugassembly2 (](icordebugassembly2-interface.md)
 Representa un ensamblado. Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.  
  
 \ de la [interfaz método icordebugassembly3](icordebugassembly3-interface.md)
 Extiende lógicamente la interfaz [ICorDebugAssembly](icordebugassembly-interface.md) para proporcionar compatibilidad con los ensamblados de contenedor y sus ensamblados incluidos. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.  
  
 \ de la [interfaz ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)
 Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 \ de la [interfaz ICorDebugBoxValue (](icordebugboxvalue-interface.md)
 Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.  
  
 [ICorDebugBreakpoint (interfaz](icordebugbreakpoint-interface.md) )\
 Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
 \ de la [interfaz ICorDebugBreakpointEnum (](icordebugbreakpointenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.  
  
 [ICorDebugChain (interfaz](icordebugchain-interface.md) )\
 Representa un segmento de una pila de llamadas física o lógica.  
  
 \ de la [interfaz ICorDebugChainEnum (](icordebugchainenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.  
  
 [ICorDebugClass (interfaz](icordebugclass-interface.md) )\
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
 \ de la [interfaz ICorDebugClass2](icordebugclass2-interface.md)
 Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>. Esta interfaz extiende `ICorDebugClass`.  
  
 [ICorDebugCode (interfaz](icordebugcode-interface1.md) )\
 Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
 \ de la [interfaz ICorDebugCode2](icordebugcode2-interface.md)
 Proporciona métodos que amplían las funciones de `ICorDebugCode`.  
  
 \ de la [interfaz ICorDebugCode3](icordebugcode3-interface.md)
 Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.  
  
 \ de la [interfaz interfaces icordebugcode4](icordebugcode4-interface.md)
 Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos de una función.  
  
 \ de la [interfaz ICorDebugCodeEnum (](icordebugcodeenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.  
  
 \ de la [interfaz ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)
 Proporciona métodos para recuperar objetos de la interfaz en caché.  
  
 \ de la [interfaz icordebugcontext (](icordebugcontext-interface.md)
 Representa un objeto de contexto. Esta interfaz no se ha implementado todavía.  
  
 [ICorDebugController (interfaz](icordebugcontroller-interface.md) )\
 Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.  
  
 \ de la [interfaz ICorDebugDataTarget](icordebugdatatarget-interface.md)
 Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.  
  
 \ de la [interfaz método icordebugdatatarget2](icordebugdatatarget2-interface.md)
 Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) . **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
 Extiende lógicamente la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para proporcionar información sobre los módulos cargados. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugDebugEvent](icordebugdebugevent-interface.md)
 Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)
 Obsoleto. No utilice esta interfaz.  
  
 \ de la [interfaz ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEnum (interfaz](icordebugenum-interface1.md) )\
 Actúa como la interfaz base abstracta para la depuración de enumeradores.  
  
 \ de la [interfaz icordebugerrorinfoenum (](icordebugerrorinfoenum-interface.md)
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEval (interfaz](icordebugeval-interface.md) )\
 Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.  
  
 \ de la [interfaz ICorDebugEval2](icordebugeval2-interface.md)
 Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.  
  
 \ de la [interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
 Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md)
 Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.  
  
 \ de la [interfaz icordebugexceptionobjectvalue (](icordebugexceptionobjectvalue-interface.md)
 Extiende la interfaz [ICorDebugObjectValue](icordebugobjectvalue-interface.md) para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.  
  
 [ICorDebugFrame (interfaz](icordebugframe-interface.md) )\
 Representa un marco en la pila actual.  
  
 \ de la [interfaz ICorDebugFrameEnum (](icordebugframeenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.  
  
 [ICorDebugFunction (interfaz](icordebugfunction-interface1.md) )\
 Representa una función o un método administrado.  
  
 [ICorDebugFunction2 (interfaz](icordebugfunction2-interface.md) )\
 Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".  
  
 \ de la [interfaz icordebugfunction3 (](icordebugfunction3-interface.md)
 Extiende lógicamente la interfaz [ICorDebugFunction](icordebugfunction-interface1.md) para proporcionar acceso al código desde una solicitud ReJIT.  
  
 \ de la [interfaz ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)
 Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.  
  
 \ de la [interfaz icordebuggcreferenceenum (](icordebuggcreferenceenum-interface.md)
 Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
 \ de la [interfaz ICorDebugGenericValue](icordebuggenericvalue-interface.md)
 Subclase de `ICorDebugValue` que se aplica a todos los valores. Esta interfaz proporciona métodos Get y Set para el valor.  
  
 \ de la [interfaz icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md)
 Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.  
  
 [ICorDebugHandleValue (interfaz](icordebughandlevalue-interface.md) )\
 Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.  
  
 \ de la [interfaz icordebugheapenum (](icordebugheapenum-interface.md)
 Proporciona un enumerador para los objetos del montón administrado.  
  
 \ de la [interfaz icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md)
 Proporciona un enumerador para las regiones de memoria del montón administrado.  
  
 [ICorDebugHeapValue (interfaz](icordebugheapvalue-interface.md) )\
 Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.  
  
 \ de la [interfaz icordebugheapvalue2 (](icordebugheapvalue2-interface1.md)
 Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.  
  
 \ de la [interfaz ICorDebugHeapValue3](icordebugheapvalue3-interface.md)
 Expone las propiedades de bloqueo de monitor de objetos.  
  
 \ de la [interfaz ICorDebugILCode](icordebugilcode-interface.md)
 Representa un segmento de código de lenguaje intermedio (IL).  
  
 \ de la [interfaz ICorDebugILCode2](icordebugilcode2-interface.md)
 Extiende lógicamente la interfaz [ICorDebugILCode](icordebugilcode-interface.md) para proporcionar métodos que devuelven el token de la firma de variable local de una función y que asignan los desplazamientos del lenguaje intermedio INSTRUMENTADO (IL) del generador de perfiles a los desplazamientos de Il del método original.  
  
 [ICorDebugILFrame (interfaz](icordebugilframe-interface.md) )\
 Representa un marco de pila de código de MSIL.  
  
 \ de la [interfaz ICorDebugILFrame2](icordebugilframe2-interface.md)
 Extensión lógica de `ICorDebugILFrame`.  
  
 \ de la [interfaz ICorDebugILFrame3](icordebugilframe3-interface.md)
 Proporciona un método que encapsula el valor devuelto de una función.  
  
 \ de la [interfaz ICorDebugILFrame4](icordebugilframe4-interface.md)
 Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL). Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 \ de la [interfaz ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
 Representa la información de símbolos de depuración para un campo de instancia. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugInternalFrame (](icordebuginternalframe-interface.md)
 Identifica los tipos de marco del depurador.  
  
 \ de la [interfaz ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
 Proporciona información sobre los marcos internos, incluida la dirección de pila y la posición en relación con los objetos [ICorDebugFrame](icordebugframe-interface.md) .  
  
 \ de la [interfaz ICorDebugLoadedModule](icordebugloadedmodule-interface.md)
 Proporciona información acerca de un módulo cargado. **Solo está disponible en .NET Native.**  
  
 [ICorDebugManagedCallback (interfaz](icordebugmanagedcallback-interface.md) )\
 Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
 \ de la [interfaz ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
 Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA). `ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.  
  
 \ de la [interfaz ICorDebugManagedCallback3 (](icordebugmanagedcallback3-interface.md)
 Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.  
  
 [ICorDebugMDA (interfaz](icordebugmda-interface.md) )\
 Representa un mensaje del asistente para la depuración administrada (MDA).  
  
 \ de la [interfaz ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
 Representa un búfer en memoria. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
 Proporciona información acerca de un ensamblado combinado. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugMetaDataLocator (](icordebugmetadatalocator-interface.md)
 Proporciona información de metadatos al depurador.  
  
 [ICorDebugModule (interfaz](icordebugmodule-interface.md) )\
 Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
 \ de la [interfaz ICorDebugModule2](icordebugmodule2-interface.md)
 Actúa como una extensión lógica de `ICorDebugModule`.  
  
 \ de la [interfaz ICorDebugModule3](icordebugmodule3-interface.md)
 Crea un lector de símbolos para un módulo dinámico.  
  
 \ de la [interfaz ICorDebugModuleBreakpoint (](icordebugmodulebreakpoint-interface.md)
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.  
  
 \ de la [interfaz ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)
 Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugModuleEnum (](icordebugmoduleenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.  
  
 \ de la [interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)
 Extiende la interfaz [ICorDebugDataTarget](icordebugdatatarget-interface.md) para admitir destinos de datos mutables.  
  
 [ICorDebugNativeFrame (interfaz](icordebugnativeframe-interface.md) )\
 Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.  
  
 \ de la [interfaz ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
 Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.  
  
 \ de la [interfaz ICorDebugObjectEnum (](icordebugobjectenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).  
  
 [ICorDebugObjectValue (interfaz](icordebugobjectvalue-interface.md) )\
 Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.  
  
 \ de la [interfaz icordebugobjectvalue2 (](icordebugobjectvalue2-interface.md)
 Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.  
  
 [ICorDebugProcess (interfaz](icordebugprocess-interface.md) )\
 Representa un proceso que ejecuta código administrado.  
  
 \ de la [interfaz ICorDebugProcess2](icordebugprocess2-interface1.md)
 Extensión lógica de `ICorDebugProcess`.  
  
 \ de la [interfaz ICorDebugProcess3 (](icordebugprocess3-interface.md)
 Controla las notificaciones del depurador personalizadas.

 \ de la [interfaz ICorDebugProcess4](icordebugprocess4-interface.md)
 Proporciona compatibilidad para el control de ejecución fuera de proceso.
  
 \ de la [interfaz ICorDebugProcess5](icordebugprocess5-interface.md)
 Extiende la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la memoria caché de imágenes nativas local de la aplicación.  
  
 \ de la [interfaz método icordebugprocess6](icordebugprocess6-interface.md)
 Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar características como la descodificación de eventos de depuración administrados codificados en eventos de depuración de excepción nativa y la división de módulos virtuales. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz icordebugprocess7 (](icordebugprocess7-interface.md)
 Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.  
  
 \ de la [interfaz ICorDebugProcess8](icordebugprocess8-interface.md)
 Extiende lógicamente la interfaz [ICorDebugProcess](icordebugprocess-interface.md) para habilitar o deshabilitar determinados tipos de devoluciones de llamada de excepción [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
 \ de la [interfaz icordebugprocessenum (](icordebugprocessenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.  
  
 [ICorDebugReferenceValue (interfaz](icordebugreferencevalue-interface.md) )\
 Subclase de `ICorDebugValue` que admite tipos de referencia.  
  
 [ICorDebugRegisterSet (interfaz](icordebugregisterset-interface.md) )\
 Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.  
  
 \ de la [interfaz ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
 Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.  
  
 \ de la [interfaz ICorDebugRemote](icordebugremote-interface.md)
 Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.  
  
 \ de la [interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
 Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.  
  
 \ de la [interfaz icordebugruntimeunwindableframe (](icordebugruntimeunwindableframe-interface.md)
 Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.  
  
 [ICorDebugStackWalk (interfaz](icordebugstackwalk-interface.md) )\
 Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
 \ de la [interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
 Representa la información de símbolos de depuración para un campo estático. **Solo está disponible en .NET Native.**  
  
 [ICorDebugStepper (interfaz](icordebugstepper-interface.md) )\
 Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
 \ de la [interfaz icordebugstepper2 (](icordebugstepper2-interface1.md)
 Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).  
  
 \ de la [interfaz ICorDebugStepperEnum (](icordebugstepperenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.  
  
 [ICorDebugStringValue (interfaz](icordebugstringvalue-interface.md) )\
 Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.  
  
 \ de la [interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
 Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz icordebugsymbolprovider2 (](icordebugsymbolprovider2-interface.md)
 Extiende lógicamente la interfaz [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) para recuperar información de símbolos de depuración adicional. **Solo está disponible en .NET Native.**  
  
 [ICorDebugThread (interfaz](icordebugthread-interface.md) )\
 Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
 \ de la [interfaz ICorDebugThread2](icordebugthread2-interface.md)
 Actúa como una extensión lógica de `ICorDebugThread`.  
  
 \ de la [interfaz ICorDebugThread3](icordebugthread3-interface.md)
 Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.  
  
 \ de la [interfaz ICorDebugThread4](icordebugthread4-interface.md)
 Proporciona información de bloqueo de subprocesos.  
  
 \ de la [interfaz ICorDebugThreadEnum (](icordebugthreadenum-interface1.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.  
  
 [ICorDebugType (interfaz](icordebugtype-interface.md) )\
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
 \ de la [interfaz ICorDebugType2](icordebugtype2-interface.md)
 Extiende la interfaz [ICorDebugType](icordebugtype-interface.md) para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).  
  
 [ICorDebugTypeEnum (interfaz](icordebugtypeenum-interface.md) )\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.  
  
 \ de la [interfaz ICorDebugUnmanagedCallback (](icordebugunmanagedcallback-interface.md)
 Proporciona notificación de eventos nativos no relacionados directamente con CLR.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Representa un valor de escritura o lectura en el proceso que se va a depurar.  
  
 \ [ICorDebugValue2](icordebugvalue2-interface.md)
 Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.  
  
 \ de la [interfaz icordebugvalue3 (](icordebugvalue3-interface.md)
 Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.  
  
 \ [icordebugvaluebreakpoint (](icordebugvaluebreakpoint-interface.md)
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.  
  
 \ [ICorDebugValueEnum](icordebugvalueenum-interface.md)
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.  
  
 \ de la [interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
 Representa una variable local o un argumento de una función.  
  
 \ de la [interfaz ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
 Proporciona un enumerador para las variables locales y los argumentos de una función.  
  
 \ de la [interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
 Recupera la información de símbolos de depuración para una variable. **Solo está disponible en .NET Native.**  
  
 \ de la [interfaz ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)
 Proporciona métodos que ayudan al desenredo de la pila. **Solo está disponible en .NET Native.**  
  
 [ICorPublish (interfaz](icorpublish-interface.md) )\
 Actúa como interfaz general para los procesos de publicación.  
  
 [ICorPublishAppDomain (interfaz](icorpublishappdomain-interface.md) )\
 Representa y proporciona información sobre un dominio de aplicación.  
  
 \ de la [interfaz ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md)
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.  
  
 [ICorPublishEnum (interfaz](icorpublishenum-interface.md) )\
 Actúa como la base abstracta para los enumeradores de publicación.  
  
 [Interfaz ICorPublishProcess](icorpublishprocess-interface.md)\
 Proporciona métodos que tienen acceso a información de un proceso.  
  
 \ de la [interfaz ICorPublishProcessEnum (](icorpublishprocessenum-interface.md)
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.  

 \ de la [interfaz ISOSDacInterface](isosdacinterface-interface.md)
 Proporciona métodos auxiliares para tener acceso a los datos de `SOS`.

 \ de la [interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)
 Proporciona métodos para consultar información sobre una definición de método.
 
 \ de la [interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)
 Proporciona métodos para consultar información sobre una instancia de método.
 
 \ de la [interfaz IXCLRDataModule](ixclrdatamodule-interface.md)
 Proporciona métodos para consultar información sobre un módulo cargado.
 
 \ de la [interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)
 Proporciona métodos para consultar información sobre un proceso.
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases de Depuración](debugging-coclasses.md)\
 [Funciones estáticas globales de Depuración](debugging-global-static-functions.md)\
 [Depuración de enumeraciones](debugging-enumerations.md)\
 \ de [estructuras de depuración](debugging-structures.md)
