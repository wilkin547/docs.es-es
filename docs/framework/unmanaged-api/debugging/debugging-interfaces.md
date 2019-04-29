---
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d939063aaefb00d4db3de604df0dbd1b2175bf95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698426"
---
# <a name="debugging-interfaces"></a>Interfaces para depuración
En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>En esta sección  
 [ICLRDataEnumMemoryRegions (interfaz)](iclrdataenummemoryregions-interface.md)\
 Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.  
  
 [ICLRDataEnumMemoryRegionsCallback (interfaz)](iclrdataenummemoryregionscallback-interface.md)\
 Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.  
  
 [ICLRDataTarget (interfaz)](iclrdatatarget-interface.md)\
 Proporciona métodos para la interacción con un proceso de CLR de destino.  
  
 [ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)\
 Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.  
  
 [ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)\
 Una subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.  
  
 [ICLRDebugging (interfaz)](iclrdebugging-interface.md)\
 Proporciona métodos que controlan la carga y descarga de módulos para depuración.  
  
 [ICLRDebuggingLibraryProvider (interfaz)](iclrdebugginglibraryprovider-interface.md)\
 Incluye el [ProvideLibrary (método)](iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de la biblioteca de interfaz de devolución de llamada que permite a common language runtime bibliotecas de depuración específica de la versión a buscar y cargar a petición.  
  
 [ICLRMetadataLocator (interfaz)](iclrmetadatalocator-interface.md)\
 Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.  
  
 [ICorDebug (interfaz)](icordebug-interface.md)\
 Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.  
  
 [ICorDebugAppDomain (interfaz)](icordebugappdomain-interface.md)\
 Proporciona métodos para depurar dominios de aplicación.  
  
 [ICorDebugAppDomain2 (interfaz)](icordebugappdomain2-interface.md)\
 Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef. Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.  
  
 [ICorDebugAppDomain3 (interfaz)](icordebugappdomain3-interface.md)\
 Proporciona métodos para trabajar con tipos [!INCLUDE[wrt](../../../../includes/wrt-md.md)] en un dominio de aplicación. Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [ICorDebugAppDomain4 (interfaz)](icordebugappdomain4-interface.md)\
 Extiende lógicamente la [ICorDebugAppDomain](icordebugappdomain-interface.md) interfaz para obtener un objeto administrado desde un contenedor CCW.  
  
 [ICorDebugAppDomainEnum (interfaz)](icordebugappdomainenum-interface.md)\
 Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.  
  
 [ICorDebugArrayValue (interfaz)](icordebugarrayvalue-interface.md)\
 Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.  
  
 [ICorDebugAssembly (interfaz)](icordebugassembly-interface.md)\
 Representa un ensamblado.  
  
 [ICorDebugAssembly2 (interfaz)](icordebugassembly2-interface.md)\
 Representa un ensamblado. Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.  
  
 [ICorDebugAssembly3 (interfaz)](icordebugassembly3-interface.md)\
 Extiende lógicamente la [ICorDebugAssembly](icordebugassembly-interface.md) interfaz para proporcionar compatibilidad con los ensamblados de contenedor y los ensamblados. **Disponible solo en .NET Native.**  
  
 [ICorDebugAssemblyEnum (interfaz)](icordebugassemblyenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.  
  
 [ICorDebugBlockingObjectEnum (interfaz)](icordebugblockingobjectenum-interface.md)\
 Proporciona un enumerador para una lista de [CorDebugBlockingObject](cordebugblockingobject-structure.md) estructuras.  
  
 [ICorDebugBoxValue (interfaz)](icordebugboxvalue-interface.md)\
 Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.  
  
 [ICorDebugBreakpoint (interfaz)](icordebugbreakpoint-interface.md)\
 Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
 [ICorDebugBreakpointEnum (interfaz)](icordebugbreakpointenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.  
  
 [ICorDebugChain (interfaz)](icordebugchain-interface.md)\
 Representa un segmento de una pila de llamadas física o lógica.  
  
 [ICorDebugChainEnum (interfaz)](icordebugchainenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.  
  
 [ICorDebugClass (interfaz)](icordebugclass-interface.md)\
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
 [ICorDebugClass2 (interfaz)](icordebugclass2-interface.md)\
 Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>. Esta interfaz extiende `ICorDebugClass`.  
  
 [ICorDebugCode (interfaz)](icordebugcode-interface1.md)\
 Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
 [ICorDebugCode2 (interfaz)](icordebugcode2-interface.md)\
 Proporciona métodos que amplían las funciones de `ICorDebugCode`.  
  
 [ICorDebugCode3 (interfaz)](icordebugcode3-interface.md)\
 Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.  
  
 [ICorDebugCode4 (interfaz)](icordebugcode4-interface.md)\
 Proporciona un método que permite a un depurador enumerar las variables locales y los argumentos en una función.  
  
 [ICorDebugCodeEnum (interfaz)](icordebugcodeenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.  
  
 [ICorDebugComObjectValue (interfaz)](icordebugcomobjectvalue-interface.md)\
 Proporciona métodos para recuperar objetos de la interfaz en caché.  
  
 [ICorDebugContext (interfaz)](icordebugcontext-interface.md)\
 Representa un objeto de contexto. Esta interfaz no se ha implementado todavía.  
  
 [ICorDebugController (interfaz)](icordebugcontroller-interface.md)\
 Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.  
  
 [ICorDebugDataTarget (interfaz)](icordebugdatatarget-interface.md)\
 Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.  
  
 [ICorDebugDataTarget2 (interfaz)](icordebugdatatarget2-interface.md)\
 Extiende lógicamente la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz. **Disponible solo en .NET Native.**  
  
 [ICorDebugDataTarget3 (interfaz)](icordebugdatatarget3-interface.md)\
 Extiende lógicamente la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz para proporcionar información sobre los módulos cargados. **Disponible solo en .NET Native.**  
  
 [ICorDebugDebugEvent (interfaz)](icordebugdebugevent-interface.md)\
 Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`. **Disponible solo en .NET Native.**  
  
 [ICorDebugEditAndContinueErrorInfo (interfaz)](icordebugeditandcontinueerrorinfo-interface.md)\
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEditAndContinueSnapshot (interfaz)](icordebugeditandcontinuesnapshot-interface.md)\
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEnum (interfaz)](icordebugenum-interface1.md)\
 Actúa como la interfaz base abstracta para la depuración de enumeradores.  
  
 [ICorDebugErrorInfoEnum (interfaz)](icordebugerrorinfoenum-interface.md)\
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEval (interfaz)](icordebugeval-interface.md)\
 Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.  
  
 [ICorDebugEval2 (interfaz)](icordebugeval2-interface.md)\
 Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.  
  
 [ICorDebugExceptionDebugEvent (interfaz)](icordebugexceptiondebugevent-interface.md)\
 Extiende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaz para admitir eventos de excepción. **Disponible solo en .NET Native.**  
  
 [ICorDebugExceptionObjectCallStackEnum (interfaz)](icordebugexceptionobjectcallstackenum-interface.md)\
 Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.  
  
 [ICorDebugExceptionObjectValue (interfaz)](icordebugexceptionobjectvalue-interface.md)\
 Extiende la [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interfaz para proporcionar información de seguimiento de pila de un objeto de excepción administrado.  
  
 [ICorDebugFrame (interfaz)](icordebugframe-interface.md)\
 Representa un marco en la pila actual.  
  
 [ICorDebugFrameEnum (interfaz)](icordebugframeenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.  
  
 [ICorDebugFunction (interfaz)](icordebugfunction-interface1.md)\
 Representa una función o un método administrado.  
  
 [ICorDebugFunction2 (interfaz)](icordebugfunction2-interface.md)\
 Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".  
  
 [ICorDebugFunction3 (interfaz)](icordebugfunction3-interface.md)\
 Extiende lógicamente la [ICorDebugFunction](icordebugfunction-interface1.md) interfaz para proporcionar acceso a código desde una solicitud ReJIT.  
  
 [ICorDebugFunctionBreakpoint (interfaz)](icordebugfunctionbreakpoint-interface.md)\
 Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.  
  
 [ICorDebugGCReferenceEnum (interfaz)](icordebuggcreferenceenum-interface.md)\
 Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
 [ICorDebugGenericValue (interfaz)](icordebuggenericvalue-interface.md)\
 Subclase de `ICorDebugValue` que se aplica a todos los valores. Esta interfaz proporciona métodos Get y Set para el valor.  
  
 [ICorDebugGuidToTypeEnum (interfaz)](icordebugguidtotypeenum-interface.md)\
 Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.  
  
 [ICorDebugHandleValue (interfaz)](icordebughandlevalue-interface.md)\
 Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.  
  
 [ICorDebugHeapEnum (interfaz)](icordebugheapenum-interface.md)\
 Proporciona un enumerador para los objetos del montón administrado.  
  
 [ICorDebugHeapSegmentEnum (interfaz)](icordebugheapsegmentenum-interface.md)\
 Proporciona un enumerador para las regiones de memoria del montón administrado.  
  
 [ICorDebugHeapValue (interfaz)](icordebugheapvalue-interface.md)\
 Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.  
  
 [ICorDebugHeapValue2 (interfaz)](icordebugheapvalue2-interface1.md)\
 Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.  
  
 [ICorDebugHeapValue3 (interfaz)](icordebugheapvalue3-interface.md)\
 Expone las propiedades de bloqueo de monitor de objetos.  
  
 [ICorDebugILCode (interfaz)](icordebugilcode-interface.md)\
 Representa un segmento de código de lenguaje intermedio (IL).  
  
 [ICorDebugILCode2 (interfaz)](icordebugilcode2-interface.md)\
 Extiende lógicamente la [ICorDebugILCode](icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token de firma de variable local de una función, e instrumentada un lenguaje intermedio del generador de perfiles (IL) que asignan los desplazamientos al IL del método original desplazamientos.  
  
 [ICorDebugILFrame (interfaz)](icordebugilframe-interface.md)\
 Representa un marco de pila de código de MSIL.  
  
 [ICorDebugILFrame2 (interfaz)](icordebugilframe2-interface.md)\
 Extensión lógica de `ICorDebugILFrame`.  
  
 [ICorDebugILFrame3 (interfaz)](icordebugilframe3-interface.md)\
 Proporciona un método que encapsula el valor devuelto de una función.  
  
 [ICorDebugILFrame4 (interfaz)](icordebugilframe4-interface.md)\
 Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL). Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 [ICorDebugInstanceFieldSymbol (interfaz)](icordebuginstancefieldsymbol-interface.md)\
 Representa la información de símbolos de depuración para un campo de instancia. **Disponible solo en .NET Native.**  
  
 [ICorDebugInternalFrame (interfaz)](icordebuginternalframe-interface.md)\
 Identifica los tipos de marco del depurador.  
  
 [ICorDebugInternalFrame2 (interfaz)](icordebuginternalframe2-interface.md)\
 Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición en relación con [ICorDebugFrame](icordebugframe-interface.md) objetos.  
  
 [ICorDebugLoadedModule (interfaz)](icordebugloadedmodule-interface.md)\
 Proporciona información acerca de un módulo cargado. **Disponible solo en .NET Native.**  
  
 [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)\
 Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
 [ICorDebugManagedCallback2 (interfaz)](icordebugmanagedcallback2-interface.md)\
 Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA). `ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.  
  
 [ICorDebugManagedCallback3 (interfaz)](icordebugmanagedcallback3-interface.md)\
 Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.  
  
 [ICorDebugMDA (interfaz)](icordebugmda-interface.md)\
 Representa un mensaje del asistente para la depuración administrada (MDA).  
  
 [ICorDebugMemoryBuffer (interfaz)](icordebugmemorybuffer-interface.md)\
 Representa un búfer en memoria. **Disponible solo en .NET Native.**  
  
 [ICorDebugMergedAssemblyRecord (interfaz)](icordebugmergedassemblyrecord-interface.md)\
 Proporciona información acerca de un ensamblado combinado. **Disponible solo en .NET Native.**  
  
 [ICorDebugMetaDataLocator (interfaz)](icordebugmetadatalocator-interface.md)\
 Proporciona información de metadatos al depurador.  
  
 [ICorDebugModule (interfaz)](icordebugmodule-interface.md)\
 Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
 [ICorDebugModule2 (interfaz)](icordebugmodule2-interface.md)\
 Actúa como una extensión lógica de `ICorDebugModule`.  
  
 [ICorDebugModule3 (interfaz)](icordebugmodule3-interface.md)\
 Crea un lector de símbolos para un módulo dinámico.  
  
 [ICorDebugModuleBreakpoint (interfaz)](icordebugmodulebreakpoint-interface.md)\
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.  
  
 [ICorDebugModuleDebugEvent (interfaz)](icordebugmoduledebugevent-interface.md)\
 Extiende la [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaz para admitir los eventos de nivel de módulo. **Disponible solo en .NET Native.**  
  
 [ICorDebugModuleEnum (interfaz)](icordebugmoduleenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.  
  
 [ICorDebugMutableDataTarget (interfaz)](icordebugmutabledatatarget-interface.md)\
 Extiende la [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz para admitir destinos de datos mutables.  
  
 [ICorDebugNativeFrame (interfaz)](icordebugnativeframe-interface.md)\
 Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.  
  
 [ICorDebugNativeFrame2 (interfaz)](icordebugnativeframe2-interface.md)\
 Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.  
  
 [ICorDebugObjectEnum (interfaz)](icordebugobjectenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).  
  
 [ICorDebugObjectValue (interfaz)](icordebugobjectvalue-interface.md)\
 Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.  
  
 [ICorDebugObjectValue2 (interfaz)](icordebugobjectvalue2-interface.md)\
 Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.  
  
 [ICorDebugProcess (interfaz)](icordebugprocess-interface.md)\
 Representa un proceso que ejecuta código administrado.  
  
 [ICorDebugProcess2 (interfaz)](icordebugprocess2-interface1.md)\
 Extensión lógica de `ICorDebugProcess`.  
  
 [ICorDebugProcess3 (interfaz)](icordebugprocess3-interface.md)\
 Controla las notificaciones del depurador personalizadas.

 [Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)\
 Proporciona compatibilidad para fuera del control de ejecución del proceso.
  
 [ICorDebugProcess5 (interfaz)](icordebugprocess5-interface.md)\
 Extiende la [ICorDebugProcess](icordebugprocess-interface.md) de la interfaz para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de objetos administrados y para determinar si un depurador carga imágenes desde la aplicación local caché de imágenes nativas.  
  
 [ICorDebugProcess6 (interfaz)](icordebugprocess6-interface.md)\
 Extiende lógicamente la [ICorDebugProcess](icordebugprocess-interface.md) interfaz para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos y división de módulos virtuales. **Disponible solo en .NET Native.**  
  
 [ICorDebugProcess7 (interfaz)](icordebugprocess7-interface.md)\
 Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.  
  
 [ICorDebugProcess8 (interfaz)](icordebugprocess8-interface.md)\
 Extiende lógicamente la [ICorDebugProcess](icordebugprocess-interface.md) interfaz para habilitar o deshabilitar ciertos tipos de [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) devoluciones de llamada de excepción.  
  
 [ICorDebugProcessEnum (interfaz)](icordebugprocessenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.  
  
 [ICorDebugReferenceValue (interfaz)](icordebugreferencevalue-interface.md)\
 Subclase de `ICorDebugValue` que admite tipos de referencia.  
  
 [ICorDebugRegisterSet (interfaz)](icordebugregisterset-interface.md)\
 Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.  
  
 [ICorDebugRegisterSet2 (interfaz)](icordebugregisterset2-interface.md)\
 Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.  
  
 [ICorDebugRemote (interfaz)](icordebugremote-interface.md)\
 Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.  
  
 [ICorDebugRemoteTarget (interfaz)](icordebugremotetarget-interface.md)\
 Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.  
  
 [ICorDebugRuntimeUnwindableFrame (interfaz)](icordebugruntimeunwindableframe-interface.md)\
 Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.  
  
 [ICorDebugStackWalk (interfaz)](icordebugstackwalk-interface.md)\
 Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
 [ICorDebugStaticFieldSymbol (interfaz)](icordebugstaticfieldsymbol-interface.md)\
 Representa la información de símbolos de depuración para un campo estático. **Disponible solo en .NET Native.**  
  
 [ICorDebugStepper (interfaz)](icordebugstepper-interface.md)\
 Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
 [ICorDebugStepper2 (interfaz)](icordebugstepper2-interface1.md)\
 Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).  
  
 [ICorDebugStepperEnum (interfaz)](icordebugstepperenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.  
  
 [ICorDebugStringValue (interfaz)](icordebugstringvalue-interface.md)\
 Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.  
  
 [ICorDebugSymbolProvider (interfaz)](icordebugsymbolprovider-interface.md)\
 Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración. **Disponible solo en .NET Native.**  
  
 [ICorDebugSymbolProvider2 (interfaz)](icordebugsymbolprovider2-interface.md)\
 Extiende lógicamente la [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional. **Disponible solo en .NET Native.**  
  
 [ICorDebugThread (interfaz)](icordebugthread-interface.md)\
 Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
 [ICorDebugThread2 (interfaz)](icordebugthread2-interface.md)\
 Actúa como una extensión lógica de `ICorDebugThread`.  
  
 [ICorDebugThread3 (interfaz)](icordebugthread3-interface.md)\
 Proporciona el punto de entrada a la [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.  
  
 [ICorDebugThread4 (interfaz)](icordebugthread4-interface.md)\
 Proporciona información de bloqueo de subprocesos.  
  
 [ICorDebugThreadEnum (interfaz)](icordebugthreadenum-interface1.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.  
  
 [ICorDebugType (interfaz)](icordebugtype-interface.md)\
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
 [ICorDebugType2 (interfaz)](icordebugtype2-interface.md)\
 Extiende la [ICorDebugType](icordebugtype-interface.md) interfaz para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).  
  
 [ICorDebugTypeEnum (interfaz)](icordebugtypeenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.  
  
 [ICorDebugUnmanagedCallback (interfaz)](icordebugunmanagedcallback-interface.md)\
 Proporciona notificación de eventos nativos no relacionados directamente con CLR.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Representa un valor de escritura o lectura en el proceso que se va a depurar.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.  
  
 [ICorDebugValue3 (interfaz)](icordebugvalue3-interface.md)\
 Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad para matrices que son superiores a 2 GB.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.  
  
 [ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)\
 Representa una variable local o argumento de una función.  
  
 [ICorDebugVariableHomeEnum (interfaz)](icordebugvariablehomeenum-interface.md)\
 Proporciona un enumerador para los argumentos en una función y las variables locales.  
  
 [ICorDebugVariableSymbol (interfaz)](icordebugvariablesymbol-interface.md)\
 Recupera la información de símbolos de depuración para una variable. **Disponible solo en .NET Native.**  
  
 [ICorDebugVirtualUnwinder (interfaz)](icordebugvirtualunwinder-interface.md)\
 Proporciona métodos que ayudan al desenredo de la pila. **Disponible solo en .NET Native.**  
  
 [ICorPublish (interfaz)](icorpublish-interface.md)\
 Actúa como interfaz general para los procesos de publicación.  
  
 [ICorPublishAppDomain (interfaz)](icorpublishappdomain-interface.md)\
 Representa y proporciona información sobre un dominio de aplicación.  
  
 [ICorPublishAppDomainEnum (interfaz)](icorpublishappdomainenum-interface.md)\
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.  
  
 [ICorPublishEnum (interfaz)](icorpublishenum-interface.md)\
 Actúa como la base abstracta para los enumeradores de publicación.  
  
 [ICorPublishProcess (interfaz)](icorpublishprocess-interface.md)\
 Proporciona métodos que tienen acceso a información de un proceso.  
  
 [ICorPublishProcessEnum (interfaz)](icorpublishprocessenum-interface.md)\
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.  

 [Interfaz ISOSDacInterface](isosdacinterface-interface.md)\
 Proporciona métodos auxiliares para acceder a ellos desde `SOS`.

 [Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Proporciona métodos para consultar información sobre una definición de método.
 
 [Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Proporciona métodos para consultar información sobre una instancia de método.
 
 [Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)\
 Proporciona métodos para consultar información acerca de un módulo cargado.
 
 [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)\
 Proporciona métodos para consultar información sobre un proceso.
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para la depuración](debugging-coclasses.md)\
 [Funciones estáticas globales de depuración](debugging-global-static-functions.md)\
 [Enumeraciones de depuración](debugging-enumerations.md)\
 [Estructuras de depuración](debugging-structures.md)\
