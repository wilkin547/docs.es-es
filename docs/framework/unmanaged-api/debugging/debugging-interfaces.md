---
title: Interfaces para depuración
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 991e333c53101a2be2a8a19d3960c3d0879619be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-interfaces"></a>Interfaces para depuración
En esta sección se describen las interfaces no administradas que controlan la depuración de un programa que se ejecuta en Common Language Runtime (CLR).  
  
## <a name="in-this-section"></a>En esta sección  
 [ICLRDataEnumMemoryRegions (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 Proporciona un método para enumerar las regiones de memoria especificadas por los llamadores.  
  
 [ICLRDataEnumMemoryRegionsCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 Proporciona un método de devolución de llamada para que `EnumMemoryRegions` notifique al depurador el resultado de un intento de enumerar un área de memoria concreta.  
  
 [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 Proporciona métodos para la interacción con un proceso de CLR de destino.  
  
 [ICLRDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 Subclase de `ICLRDataTarget` que se utiliza la capa de servicios de acceso a datos para manipular las áreas de la memoria virtual en el proceso de destino.  
  
 [ICLRDataTarget3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 Una subclase de [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) que proporciona acceso a información de excepción.  
  
 [ICLRDebugging (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 Proporciona métodos que controlan la carga y descarga de módulos para depuración.  
  
 [ICLRDebuggingLibraryProvider (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 Incluye el [ProvideLibrary (método)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) método, que obtiene un proveedor de bibliotecas de interfaz de devolución de llamada que permite a common language bibliotecas de depuración específicas de la versión en tiempo de ejecución buscar y cargar a petición.  
  
 [ICLRMetadataLocator (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 Interfaz utilizada por la capa de servicios de acceso a datos para buscar los metadatos de los ensamblados en un proceso de destino.  
  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 Proporciona métodos que permiten a los desarrolladores depurar las aplicaciones en el entorno de CLR.  
  
 [ICorDebugAppDomain (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 Proporciona métodos para depurar dominios de aplicación.  
  
 [ICorDebugAppDomain2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 Proporciona métodos para trabajar con matrices, punteros, punteros a función y tipos ByRef. Esta interfaz es una extensión de la interfaz `ICorDebugAppDomain`.  
  
 [ICorDebugAppDomain3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 Proporciona métodos para trabajar con tipos [!INCLUDE[wrt](../../../../includes/wrt-md.md)] en un dominio de aplicación. Esta interfaz es una extensión de las interfaces `ICorDebugAppDomain` e `ICorDebugAppDomain2`.  
  
 [ICorDebugAppDomain4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 Extiende lógicamente la [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) interfaz para obtener un objeto administrado desde un contenedor CCW.  
  
 [ICorDebugAppDomainEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 Proporciona un método que devuelve un número especificado de valores de `ICorDebugAppDomain` que comienzan en la siguiente posición de la enumeración.  
  
 [ICorDebugArrayValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 Subclase de `ICorDebugHeapValue` que representa una matriz unidimensional o multidimensional.  
  
 [ICorDebugAssembly (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 Representa un ensamblado.  
  
 [ICorDebugAssembly2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 Representa un ensamblado. Esta interfaz es una extensión de la interfaz `ICorDebugAssembly`.  
  
 [ICorDebugAssembly3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 Extiende lógicamente la [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) interfaz para proporcionar compatibilidad con los ensamblados de contenedor y sus contenidos. **Disponible solo en .NET Native.**  
  
 [ICorDebugAssemblyEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugAssembly`.  
  
 [ICorDebugBlockingObjectEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 Proporciona un enumerador para una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.  
  
 [ICorDebugBoxValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 Subclase de `ICorDebugHeapValue` que representa un objeto de clase de valor al que se ha aplicado la conversión boxing.  
  
 [ICorDebugBreakpoint (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 Representa un punto de interrupción en una función o un punto de inspección en un valor.  
  
 [ICorDebugBreakpointEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugBreakpoint`.  
  
 [ICorDebugChain (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 Representa un segmento de una pila de llamadas física o lógica.  
  
 [ICorDebugChainEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugChain`.  
  
 [ICorDebugClass (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugClass` representa el tipo genérico sin instancias.  
  
 [ICorDebugClass2 (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 Representa una clase genérica o una clase con un parámetro de método de tipo <xref:System.Type>. Esta interfaz extiende `ICorDebugClass`.  
  
 [ICorDebugCode (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 Representa un segmento de código de lenguaje intermedio de Microsoft (MSIL) o código nativo.  
  
 [ICorDebugCode2 (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 Proporciona métodos que amplían las funciones de `ICorDebugCode`.  
  
 [ICorDebugCode3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 Proporciona un método que extiende [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) y [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) para proporcionar información sobre un valor devuelto administrado.  
  
 [ICorDebugCode4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 Proporciona un método que permite a un depurador enumerar las variables locales y argumentos en una función.  
  
 [ICorDebugCodeEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugCode`.  
  
 [ICorDebugComObjectValue (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 Proporciona métodos para recuperar objetos de la interfaz en caché.  
  
 [ICorDebugContext (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 Representa un objeto de contexto. Esta interfaz no se ha implementado todavía.  
  
 [ICorDebugController (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.  
  
 [ICorDebugDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.  
  
 [ICorDebugDataTarget2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz. **Disponible solo en .NET Native.**  
  
 [ICorDebugDataTarget3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 Extiende lógicamente la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para proporcionar información sobre los módulos cargados. **Disponible solo en .NET Native.**  
  
 [ICorDebugDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 Define la interfaz base de la que derivan todos los eventos de depuración `ICorDebug`. **Disponible solo en .NET Native.**  
  
 [ICorDebugEditAndContinueErrorInfo (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEditAndContinueSnapshot (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 Actúa como la interfaz base abstracta para la depuración de enumeradores.  
  
 [ICorDebugErrorInfoEnum (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 Obsoleto. No utilice esta interfaz.  
  
 [ICorDebugEval (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 Proporciona métodos que permiten al depurador ejecutar código en el contexto del código que se está depurando.  
  
 [ICorDebugEval2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 Extiende `ICorDebugEval` para proporcionar compatibilidad con los tipos genéricos.  
  
 [ICorDebugExceptionDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de excepción. **Disponible solo en .NET Native.**  
  
 [ICorDebugExceptionObjectCallStackEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción.  
  
 [ICorDebugExceptionObjectValue (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 Extiende la [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) interfaz para proporcionar información de seguimiento de pila de un objeto de excepción administrada.  
  
 [ICorDebugFrame (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 Representa un marco en la pila actual.  
  
 [ICorDebugFrameEnum (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugFrame`.  
  
 [ICorDebugFunction (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 Representa una función o un método administrado.  
  
 [ICorDebugFunction2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 Extiende `ICorDebugFunction` de manera lógica para ofrecer compatibilidad con la depuración paso a paso de "Sólo mi código".  
  
 [ICorDebugFunction3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 Extiende lógicamente la [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) interfaz para proporcionar acceso al código desde una solicitud ReJIT.  
  
 [ICorDebugFunctionBreakpoint (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 Amplía `ICorDebugBreakpoint` para admitir los puntos de interrupción dentro de las funciones.  
  
 [ICorDebugGCReferenceEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
 [ICorDebugGenericValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 Subclase de `ICorDebugValue` que se aplica a todos los valores. Esta interfaz proporciona métodos Get y Set para el valor.  
  
 [ICorDebugGuidToTypeEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 Proporciona un enumerador para un objeto que asigna GUID y sus objetos `ICorDebugType` correspondientes.  
  
 [ICorDebugHandleValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 Subclase de `ICorDebugReferenceValue` que representa un valor de referencia para el cual el depurador ha creado un identificador para la recolección de elementos no utilizados.  
  
 [ICorDebugHeapEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 Proporciona un enumerador para los objetos del montón administrado.  
  
 [ICorDebugHeapSegmentEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 Proporciona un enumerador para las regiones de memoria del montón administrado.  
  
 [ICorDebugHeapValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 Subclase de `ICorDebugValue` que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de CLR.  
  
 [ICorDebugHeapValue2 (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 Extensión de `ICorDebugHeapValue` que proporciona compatibilidad con los identificadores del motor en tiempo de ejecución.  
  
 [ICorDebugHeapValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 Expone las propiedades de bloqueo de monitor de objetos.  
  
 [ICorDebugILCode (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 Representa un segmento de código de lenguaje intermedio (IL).  
  
 [ICorDebugILCode2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 Extiende lógicamente la [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interfaz para proporcionar métodos que devuelven el token de firma de variable local de una función e instrumentada un lenguaje intermedio del generador de perfiles (IL) que asignan los desplazamientos al IL del método original desplazamientos.  
  
 [ICorDebugILFrame (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 Representa un marco de pila de código de MSIL.  
  
 [ICorDebugILFrame2 (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 Extensión lógica de `ICorDebugILFrame`.  
  
 [ICorDebugILFrame3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 Proporciona un método que encapsula el valor devuelto de una función.  
  
 [ICorDebugILFrame4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 Proporciona métodos que permiten acceder a las variables locales y al código en un marco de pila de código de lenguaje intermedio (IL). Un parámetro especifica si el depurador tiene acceso a las variables y al código agregados en la instrumentación ReJIT del generador de perfiles.  
  
 [ICorDebugInstanceFieldSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 Representa la información de símbolos de depuración para un campo de instancia. **Disponible solo en .NET Native.**  
  
 [ICorDebugInternalFrame (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 Identifica los tipos de marco del depurador.  
  
 [ICorDebugInternalFrame2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 Proporciona información sobre los marcos internos, incluyendo la dirección de pila y la posición con respecto a [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) objetos.  
  
 [ICorDebugLoadedModule (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 Proporciona información acerca de un módulo cargado. **Disponible solo en .NET Native.**  
  
 [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
 [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA). `ICorDebugManagedCallback2` es una extensión lógica de `ICorDebugManagedCallback`.  
  
 [ICorDebugManagedCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.  
  
 [ICorDebugMDA (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 Representa un mensaje del asistente para la depuración administrada (MDA).  
  
 [ICorDebugMemoryBuffer (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 Representa un búfer en memoria. **Disponible solo en .NET Native.**  
  
 [ICorDebugMergedAssemblyRecord (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 Proporciona información acerca de un ensamblado combinado. **Disponible solo en .NET Native.**  
  
 [ICorDebugMetaDataLocator (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 Proporciona información de metadatos al depurador.  
  
 [ICorDebugModule (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 Representa un módulo de CLR, que es un archivo ejecutable o una biblioteca de vínculos dinámicos (DLL).  
  
 [ICorDebugModule2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 Actúa como una extensión lógica de `ICorDebugModule`.  
  
 [ICorDebugModule3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 Crea un lector de símbolos para un módulo dinámico.  
  
 [ICorDebugModuleBreakpoint (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a módulos específicos.  
  
 [ICorDebugModuleDebugEvent (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de nivel de módulo. **Disponible solo en .NET Native.**  
  
 [ICorDebugModuleEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugModule`.  
  
 [ICorDebugMutableDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 Extiende la [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaz para admitir destinos de datos mutables.  
  
 [ICorDebugNativeFrame (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 Implementación especializada de `ICorDebugFrame` que se utiliza para los marcos nativos.  
  
 [ICorDebugNativeFrame2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 Proporciona métodos que comprueban las relaciones entre marcos primarios y secundarios.  
  
 [ICorDebugObjectEnum (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).  
  
 [ICorDebugObjectValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 Subclase de `ICorDebugValue` que representa un valor que contiene un objeto.  
  
 [ICorDebugObjectValue2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 Extiende `ICorDebugObjectValue` para ofrecer compatibilidad con la herencia y los reemplazos.  
  
 [ICorDebugProcess (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 Representa un proceso que ejecuta código administrado.  
  
 [ICorDebugProcess2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 Extensión lógica de `ICorDebugProcess`.  
  
 [ICorDebugProcess3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 Controla las notificaciones del depurador personalizadas.  
  
 [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 Extiende la [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) local de la interfaz para admitir el acceso al montón administrado, para proporcionar información sobre la recolección de los objetos administrados y para determinar si un depurador carga imágenes desde la aplicación caché de imágenes nativas.  
  
 [ICorDebugProcess6 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 Extiende lógicamente la [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaz para habilitar características como la descodificación de eventos de depuración administrados que están codificados en eventos de depuración de excepción nativos o la división de módulos virtuales. **Disponible solo en .NET Native.**  
  
 [ICorDebugProcess7 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 Proporciona un método que configura el depurador para controlar las actualizaciones en memoria de los metadatos en el proceso de destino.  
  
 [ICorDebugProcess8 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 Extiende lógicamente la [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) interfaz para habilitar o deshabilitar ciertos tipos de [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) las devoluciones de llamada de excepción.  
  
 [ICorDebugProcessEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugProcess`.  
  
 [ICorDebugReferenceValue (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 Subclase de `ICorDebugValue` que admite tipos de referencia.  
  
 [ICorDebugRegisterSet (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 Representa el conjunto de registros disponibles en el equipo que está ejecutando el código.  
  
 [ICorDebugRegisterSet2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 Extiende la funcionalidad de `ICorDebugRegisterSet` para plataformas hardware que tienen más de 64 registros.  
  
 [ICorDebugRemote (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 Proporciona la capacidad de iniciar o de adjuntar un depurador administrado a un proceso remoto de destino.  
  
 [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 Proporciona métodos que permiten depurar aplicaciones basadas en Silverlight en el entorno de CLR.  
  
 [ICorDebugRuntimeUnwindableFrame (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.  
  
 [ICorDebugStackWalk (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.  
  
 [ICorDebugStaticFieldSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 Representa la información de símbolo de depuración para un campo estático. **Disponible solo en .NET Native.**  
  
 [ICorDebugStepper (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.  
  
 [ICorDebugStepper2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 Proporciona compatibilidad con la depuración de "Sólo mi código" (JMC).  
  
 [ICorDebugStepperEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugStepper`.  
  
 [ICorDebugStringValue (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 Subclase de `ICorDebugHeapValue` que se aplica a los valores de cadena.  
  
 [ICorDebugSymbolProvider (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 Proporciona métodos que pueden usarse para recuperar información de símbolos de depuración. **Disponible solo en .NET Native.**  
  
 [ICorDebugSymbolProvider2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 Extiende lógicamente la [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interfaz para recuperar información de símbolos de depuración adicional. **Disponible solo en .NET Native.**  
  
 [ICorDebugThread (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 Representa un subproceso de un proceso. El período de duración de una instancia de `ICorDebugThread` es el mismo que el del subproceso que representa.  
  
 [ICorDebugThread2 (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 Actúa como una extensión lógica de `ICorDebugThread`.  
  
 [ICorDebugThread3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 Proporciona el punto de entrada a la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.  
  
 [ICorDebugThread4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 Proporciona información de bloqueo de subprocesos.  
  
 [ICorDebugThreadEnum (Interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugThread`.  
  
 [ICorDebugType (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 Representa un tipo, que puede ser básico o complejo (es decir, definido por el usuario). Si el tipo es genérico, `ICorDebugType` representa el tipo genérico con instancias.  
  
 [ICorDebugType2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 Extiende la [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) interfaz para recuperar el identificador de tipo de un tipo base o un tipo complejo (definido por el usuario).  
  
 [ICorDebugTypeEnum (interfaz1)](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugType`.  
  
 [ICorDebugUnmanagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 Proporciona notificación de eventos nativos no relacionados directamente con CLR.  
  
 "ICorDebugValue"  
 Representa un valor de escritura o lectura en el proceso que se va a depurar.  
  
 "ICorDebugValue2"  
 Extiende `ICorDebugValue` para proporcionar compatibilidad con `ICorDebugType`.  
  
 [ICorDebugValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.  
  
 "ICorDebugValueBreakpoint"  
 Extiende `ICorDebugBreakpoint` para proporcionar acceso a valores concretos.  
  
 "ICorDebugValueEnum"  
 Implementa los métodos de `ICorDebugEnum` y enumera las matrices de `ICorDebugValue`.  
  
 [ICorDebugVariableHome (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 Representa una variable local o un argumento de una función.  
  
 [ICorDebugVariableHomeEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 Proporciona un enumerador para las variables locales y argumentos en una función.  
  
 [ICorDebugVariableSymbol (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 Recupera la información de símbolos de depuración para una variable. **Disponible solo en .NET Native.**  
  
 [ICorDebugVirtualUnwinder (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 Proporciona métodos que ayudan al desenredo de la pila. **Disponible solo en .NET Native.**  
  
 [ICorPublish (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 Actúa como interfaz general para los procesos de publicación.  
  
 [ICorPublishAppDomain (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 Representa y proporciona información sobre un dominio de aplicación.  
  
 [ICorPublishAppDomainEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishAppDomain` que actualmente existen dentro de un proceso.  
  
 [ICorPublishEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 Actúa como la base abstracta para los enumeradores de publicación.  
  
 [ICorPublishProcess (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 Proporciona métodos que tienen acceso a información de un proceso.  
  
 [ICorPublishProcessEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 Proporciona métodos que atraviesan una colección de objetos `ICorPublishProcess`.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Coclases para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
