---
title: Interfaces para depuración
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: c4b9cdc2bc90096ab7c3b041bd8aa2742b48c35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179160"
---
# <a name="debugging-interfaces"></a>Interfaces para depuración
En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>En esta sección  
 [Interfaz ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)\
 Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.  
  
 [Interfaz ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)\
 Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.  
  
 [Interfaz ICLRDataTarget](iclrdatatarget-interface.md)\
 Proporciona métodos para la interacción con un proceso de CLR de destino.  
  
 [Interfaz ICLRDataTarget2](iclrdatatarget2-interface.md)\
 Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.  
  
 [Interfaz ICLRDataTarget3](iclrdatatarget3-interface.md)\
 Subclase de [ICLRDataTarget2](iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.  
  
 [Interfaz ICLRDebugging](iclrdebugging-interface.md)\
 Proporciona métodos que controlan la carga y descarga de módulos para depuración.  
  
 [Interfaz ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\
 Incluye el método [ProvideLibrary Method,](iclrdebugginglibraryprovider-providelibrary-method.md) que obtiene una interfaz de devolución de llamada del proveedor de biblioteca que permite que las bibliotecas de depuración específicas de la versión de Common Language Runtime se localen y carguen a petición.  
  
 [Interfaz ICLRMetadataLocator](iclrmetadatalocator-interface.md)\
 Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.  
  
 [Interfaz ICorDebug](icordebug-interface.md)\
 Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.  
  
 [Interfaz ICorDebugAppDomain](icordebugappdomain-interface.md)\
 Proporciona métodos para depurar dominios de aplicación.  
  
 [Interfaz ICorDebugAppDomain2](icordebugappdomain2-interface.md)\
 Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef. Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.  
  
 [Interfaz ICorDebugAppDomain3](icordebugappdomain3-interface.md)\
 Proporciona métodos para trabajar con los tipos de Windows Runtime en un dominio de aplicación. Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [Interfaz ICorDebugAppDomain4](icordebugappdomain4-interface.md)\
 Lógicamente extiende el [ICorDebugAppDomain](icordebugappdomain-interface.md) interfaz para obtener un objeto administrado de un contenedor COM invocable.  
  
 [Interfaz ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)\
 Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.  
  
 [Interfaz ICorDebugArrayValue](icordebugarrayvalue-interface.md)\
 Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.  
  
 [Interfaz ICorDebugAssembly](icordebugassembly-interface.md)\
 Representa un ensamblado.  
  
 [Interfaz ICorDebugAssembly2](icordebugassembly2-interface.md)\
 Representa un ensamblado. Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.  
  
 [Interfaz ICorDebugAssembly3](icordebugassembly3-interface.md)\
 Lógicamente extiende el [ICorDebugAssembly](icordebugassembly-interface.md) interfaz para proporcionar compatibilidad con los ensamblados de contenedor y sus ensamblados contenidos. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.  
  
 [Interfaz ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\
 Proporciona un enumerador para una lista de [CorDebugBlockingObject](cordebugblockingobject-structure.md) estructuras.  
  
 [Interfaz ICorDebugBoxValue](icordebugboxvalue-interface.md)\
 Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.  
  
 [Interfaz ICorDebugBreakpoint](icordebugbreakpoint-interface.md)\
 Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
 [Interfaz ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.  
  
 [Interfaz ICorDebugChain](icordebugchain-interface.md)\
 Representa un segmento de una pila de llamadas física o lógica.  
  
 [Interfaz ICorDebugChainEnum](icordebugchainenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.  
  
 [Interfaz ICorDebugClass](icordebugclass-interface.md)\
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
 [Interfaz ICorDebugClass2](icordebugclass2-interface.md)\
 Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>. Esta interfaz extiende `ICorDebugClass`.  
  
 [Interfaz ICorDebugCode](icordebugcode-interface1.md)\
 Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
 [Interfaz ICorDebugCode2](icordebugcode2-interface.md)\
 Proporciona métodos que amplían las funciones de `ICorDebugCode`.  
  
 [Interfaz ICorDebugCode3](icordebugcode3-interface.md)\
 Proporciona un método que extiende [ICorDebugCode](icordebugcode-interface1.md) y [ICorDebugCode2](icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.  
  
 [Interfaz ICorDebugCode4](icordebugcode4-interface.md)\
 Proporciona un método que permite a un depurador enumerar las variables y argumentos locales de una función.  
  
 [Interfaz ICorDebugCodeEnum](icordebugcodeenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.  
  
 [Interfaz ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\
 Proporciona métodos para recuperar objetos de la interfaz en caché.  
  
 [Interfaz ICorDebugContext](icordebugcontext-interface.md)\
 Representa un objeto de contexto. Esta interfaz no se ha implementado todavía.  
  
 [Interfaz ICorDebugController](icordebugcontroller-interface.md)\
 Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.  
  
 [Interfaz ICorDebugDataTarget](icordebugdatatarget-interface.md)\
 Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.  
  
 [Interfaz ICorDebugDataTarget2](icordebugdatatarget2-interface.md)\
 Lógicamente extiende el [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\
 Lógicamente extiende el [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz para proporcionar información acerca de los módulos cargados. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugDebugEvent](icordebugdebugevent-interface.md)\
 Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)\
 Obsoleto. No utilice esta interfaz.  
  
 [Interfaz ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)\
 Obsoleto. No utilice esta interfaz.  
  
 [Interfaz ICorDebugEnum](icordebugenum-interface1.md)\
 Actúa como la interfaz base abstracta para la depuración de enumeradores.  
  
 [Interfaz ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)\
 Obsoleto. No utilice esta interfaz.  
  
 [Interfaz ICorDebugEval](icordebugeval-interface.md)\
 Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.  
  
 [Interfaz ICorDebugEval2](icordebugeval2-interface.md)\
 Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.  
  
 [Interfaz ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)\
 Extiende el [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaz para admitir eventos de excepción. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\
 Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.  
  
 [Interfaz ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\
 Extiende el [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interfaz para proporcionar información de seguimiento de pila de un objeto de excepción administrado.  
  
 [Interfaz ICorDebugFrame](icordebugframe-interface.md)\
 Representa un marco en la pila actual.  
  
 [Interfaz ICorDebugFrameEnum](icordebugframeenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.  
  
 [Interfaz ICorDebugFunction](icordebugfunction-interface1.md)\
 Representa una función o un método administrado.  
  
 [Interfaz ICorDebugFunction2](icordebugfunction2-interface.md)\
 Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".  
  
 [Interfaz ICorDebugFunction3](icordebugfunction3-interface.md)\
 Lógicamente extiende el [ICorDebugFunction](icordebugfunction-interface1.md) interfaz para proporcionar acceso al código desde una solicitud ReJIT.  
  
 [Interfaz ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)\
 Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.  
  
 [Interfaz ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\
 Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
 [Interfaz ICorDebugGenericValue](icordebuggenericvalue-interface.md)\
 Subclase de `ICorDebugValue` que se aplica a todos los valores. Esta interfaz proporciona métodos Get y Set para el valor.  
  
 [Interfaz ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\
 Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.  
  
 [Interfaz ICorDebugHandleValue](icordebughandlevalue-interface.md)\
 Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.  
  
 [Interfaz ICorDebugHeapEnum](icordebugheapenum-interface.md)\
 Proporciona un enumerador para los objetos del montón administrado.  
  
 [Interfaz ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\
 Proporciona un enumerador para las regiones de memoria del montón administrado.  
  
 [Interfaz ICorDebugHeapValue](icordebugheapvalue-interface.md)\
 Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.  
  
 [Interfaz ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\
 Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.  
  
 [Interfaz ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\
 Expone las propiedades de bloqueo de monitor de objetos.  
  
 [Interfaz ICorDebugILCode](icordebugilcode-interface.md)\
 Representa un segmento de código de lenguaje intermedio (IL).  
  
 [Interfaz ICorDebugILCode2](icordebugilcode2-interface.md)\
 Lógicamente extiende el [ICorDebugILCode](icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token para la firma de variable local de una función y que asignan los desplazamientos de lenguaje intermedio instrumentado (IL) de un generador de perfiles a los desplazamientos de IL del método original.  
  
 [Interfaz ICorDebugILFrame](icordebugilframe-interface.md)\
 Representa un marco de pila de código de MSIL.  
  
 [Interfaz ICorDebugILFrame2](icordebugilframe2-interface.md)\
 Extensión lógica de `ICorDebugILFrame`.  
  
 [Interfaz ICorDebugILFrame3](icordebugilframe3-interface.md)\
 Proporciona un método que encapsula el valor devuelto de una función.  
  
 [Interfaz ICorDebugILFrame4](icordebugilframe4-interface.md)\
 Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL). Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 [Interfaz ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\
 Representa la información de símbolos de depuración para un campo de instancia. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugInternalFrame](icordebuginternalframe-interface.md)\
 Identifica los tipos de marco del depurador.  
  
 [Interfaz ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\
 Proporciona información acerca de los marcos internos, incluida la dirección de pila y la posición en relación con [ICorDebugFrame](icordebugframe-interface.md) objetos.  
  
 [Interfaz ICorDebugLoadedModule](icordebugloadedmodule-interface.md)\
 Proporciona información acerca de un módulo cargado. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\
 Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
 [Interfaz ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\
 Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA). `ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.  
  
 [Interfaz ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\
 Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.  
  
 [Interfaz ICorDebugMDA](icordebugmda-interface.md)\
 Representa un mensaje del asistente para la depuración administrada (MDA).  
  
 [Interfaz ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\
 Representa un búfer en memoria. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)\
 Proporciona información acerca de un ensamblado combinado. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\
 Proporciona información de metadatos al depurador.  
  
 [Interfaz ICorDebugModule](icordebugmodule-interface.md)\
 Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
 [Interfaz ICorDebugModule2](icordebugmodule2-interface.md)\
 Actúa como una extensión lógica de `ICorDebugModule`.  
  
 [Interfaz ICorDebugModule3](icordebugmodule3-interface.md)\
 Crea un lector de símbolos para un módulo dinámico.  
  
 [Interfaz ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)\
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.  
  
 [Interfaz ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)\
 Extiende el [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interfaz para admitir eventos de nivel de módulo. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugModuleEnum](icordebugmoduleenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.  
  
 [Interfaz ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)\
 Extiende el [ICorDebugDataTarget](icordebugdatatarget-interface.md) interfaz para admitir destinos de datos mutables.  
  
 [Interfaz ICorDebugNativeFrame](icordebugnativeframe-interface.md)\
 Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.  
  
 [Interfaz ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\
 Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.  
  
 [Interfaz ICorDebugObjectEnum](icordebugobjectenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).  
  
 [Interfaz ICorDebugObjectValue](icordebugobjectvalue-interface.md)\
 Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.  
  
 [Interfaz ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\
 Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.  
  
 [Interfaz ICorDebugProcess](icordebugprocess-interface.md)\
 Representa un proceso que ejecuta código administrado.  
  
 [Interfaz ICorDebugProcess2](icordebugprocess2-interface1.md)\
 Extensión lógica de `ICorDebugProcess`.  
  
 [Interfaz ICorDebugProcess3](icordebugprocess3-interface.md)\
 Controla las notificaciones del depurador personalizadas.

 [Interfaz ICorDebugProcess4](icordebugprocess4-interface.md)\
 Proporciona compatibilidad con el control de ejecución fuera del proceso.
  
 [Interfaz ICorDebugProcess5](icordebugprocess5-interface.md)\
 Extiende el [ICorDebugProcess](icordebugprocess-interface.md) interfaz para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de elementos no utilizados de objetos administrados y para determinar si un depurador carga imágenes desde la caché de imágenes nativas local de la aplicación.  
  
 [Interfaz ICorDebugProcess6](icordebugprocess6-interface.md)\
 Extiende lógicamente el [ICorDebugProcess](icordebugprocess-interface.md) interfaz para habilitar características como la descodificación de eventos de depuración administrados que se codifican en eventos de depuración de excepción nativos y división de módulo virtual. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugProcess7](icordebugprocess7-interface.md)\
 Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.  
  
 [Interfaz ICorDebugProcess8](icordebugprocess8-interface.md)\
 Lógicamente extiende el [ICorDebugProcess](icordebugprocess-interface.md) interfaz para habilitar o deshabilitar ciertos tipos de [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) devoluciones de llamada de excepción.  
  
 [Interfaz ICorDebugProcessEnum](icordebugprocessenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.  
  
 [Interfaz ICorDebugReferenceValue](icordebugreferencevalue-interface.md)\
 Subclase de `ICorDebugValue` que admite tipos de referencia.  
  
 [Interfaz ICorDebugRegisterSet](icordebugregisterset-interface.md)\
 Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.  
  
 [Interfaz ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\
 Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.  
  
 [Interfaz ICorDebugRemote](icordebugremote-interface.md)\
 Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.  
  
 [Interfaz ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\
 Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.  
  
 [Interfaz ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)\
 Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.  
  
 [Interfaz ICorDebugStackWalk](icordebugstackwalk-interface.md)\
 Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
 [Interfaz ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)\
 Representa la información de símbolos de depuración para un campo estático. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugStepper](icordebugstepper-interface.md)\
 Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
 [Interfaz ICorDebugStepper2](icordebugstepper2-interface1.md)\
 Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).  
  
 [Interfaz ICorDebugStepperEnum](icordebugstepperenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.  
  
 [Interfaz ICorDebugStringValue](icordebugstringvalue-interface.md)\
 Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.  
  
 [Interfaz ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)\
 Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\
 Extiende lógicamente el [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolo de depuración adicional. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugThread](icordebugthread-interface.md)\
 Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
 [Interfaz ICorDebugThread2](icordebugthread2-interface.md)\
 Actúa como una extensión lógica de `ICorDebugThread`.  
  
 [Interfaz ICorDebugThread3](icordebugthread3-interface.md)\
 Proporciona el punto de entrada a la [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.  
  
 [Interfaz ICorDebugThread4](icordebugthread4-interface.md)\
 Proporciona información de bloqueo de subprocesos.  
  
 [Interfaz ICorDebugThreadEnum](icordebugthreadenum-interface1.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.  
  
 [Interfaz ICorDebugType](icordebugtype-interface.md)\
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
 [Interfaz ICorDebugType2](icordebugtype2-interface.md)\
 Extiende el [ICorDebugType](icordebugtype-interface.md) interfaz para recuperar el identificador de tipo de un tipo base o tipo complejo (definido por el usuario).  
  
 [Interfaz ICorDebugTypeEnum](icordebugtypeenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.  
  
 [Interfaz ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)\
 Proporciona notificación de eventos nativos no relacionados directamente con CLR.  
  
 [Icordebugvalue](icordebugvalue-interface.md)\
 Representa un valor de escritura o lectura en el proceso que se va a depurar.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.  
  
 [Interfaz ICorDebugValue3](icordebugvalue3-interface.md)\
 Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices de más de 2 GB.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.  
  
 [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)\
 Representa una variable local o argumento de una función.  
  
 [Interfaz ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)\
 Proporciona un enumerador a las variables locales y argumentos de una función.  
  
 [Interfaz ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\
 Recupera la información de símbolos de depuración para una variable. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\
 Proporciona métodos que ayudan al desenredo de la pila. **Disponible solo en .NET Native.**  
  
 [Interfaz ICorPublish](icorpublish-interface.md)\
 Actúa como interfaz general para los procesos de publicación.  
  
 [Interfaz ICorPublishAppDomain](icorpublishappdomain-interface.md)\
 Representa y proporciona información sobre un dominio de aplicación.  
  
 [Interfaz ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)\
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.  
  
 [Interfaz ICorPublishEnum](icorpublishenum-interface.md)\
 Actúa como la base abstracta para los enumeradores de publicación.  
  
 [Interfaz ICorPublishProcess](icorpublishprocess-interface.md)\
 Proporciona métodos que tienen acceso a información de un proceso.  
  
 [Interfaz ICorPublishProcessEnum](icorpublishprocessenum-interface.md)\
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.  

 [Interfaz ISOSDacInterface](isosdacinterface-interface.md)\
 Proporciona métodos auxiliares `SOS`para tener acceso a los datos desde .

 [Interfaz IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Proporciona métodos para consultar información sobre una definición de método.

 [Interfaz IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Proporciona métodos para consultar información sobre una instancia de método.

 [Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)\
 Proporciona métodos para consultar información sobre un módulo cargado.

 [Interfaz IXCLRDataProcess](ixclrdataprocess-interface.md)\
 Proporciona métodos para consultar información sobre un proceso.
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Depuración de coclases](debugging-coclasses.md)\
 [Depuración de funciones estáticas globales](debugging-global-static-functions.md)\
 [Depuración de enumeraciones](debugging-enumerations.md)\
 [Estructuras de depuración](debugging-structures.md)\
