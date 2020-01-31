---
title: Información general sobre la generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- managed code, profiling API support
- unmanaged code, combining with managed code in profiling
- notification threads [.NET Framework profiling]
- unmanaged code, profiling
- profiling API [.NET Framework], and COM
- profiling API [.NET Framework], unmanaged code profiling
- profilers, writing
- profiling API [.NET Framework], call stacks
- code profilers, writing
- profiling API [.NET Framework], security considerations
- profiling API [.NET Framework], managed code support
- common language runtime, profiling
- profiling API [.NET Framework], notification threads
- call stacks [.NET Framework profiling]
- profiling API [.NET Framework], stack depth
- common language runtime, writing a profiler
- profiling API [.NET Framework], information retrieval interfaces
- shadow stacks [.NET Framework profiling]
- COM, using in the profiling API
- stack snapshots [.NET Framework profiling]
- profiling API [.NET Framework], supported features
- profiling API [.NET Framework], overview
- security, profiling API considerations
- stack depth [.NET Framework profiling]
ms.assetid: 864c2344-71dc-46f9-96b2-ed59fb6427a8
ms.openlocfilehash: aa8bff374e9698d4b7e032428ec1bdc66901e05d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860920"
---
# <a name="profiling-overview"></a>Información general sobre la generación de perfiles

Un generador de perfiles es una herramienta que supervisa la ejecución de otra aplicación. Un generador de perfiles de Common Language Runtime (CLR) es una biblioteca de vínculos dinámicos (DLL) compuesta de funciones que intercambian mensajes con el CLR utilizando la API de generación de perfiles. CLR carga en tiempo de ejecución la DLL del generador de perfiles.

Las herramientas tradicionales de generación de perfiles se centran en medir la ejecución de la aplicación. Es decir, miden el tiempo que se emplea en cada función o la utilización de memoria de la aplicación a lo largo del tiempo. La API de generación de perfiles se dirige a una clase más amplia de herramientas de diagnóstico tales como las utilidades de cobertura de código e, incluso, las ayudas de depuración avanzadas. Estos usos son diagnósticos por su naturaleza. La API de generación de perfiles no solamente mide, sino que también supervisa la ejecución de una aplicación. Por este motivo, la API de generación de perfiles nunca debe ser utilizada por la propia aplicación, y la ejecución de la aplicación no debe depender del generador de perfiles ni verse afectada por él.

La generación de perfil para una aplicación CLR requiere más soporte que la generación de perfil parea código máquina compilado convencionalmente. Esto es porque CLR introduce conceptos tales como los dominios de aplicación, la recolección de elementos no utilizados, el control de excepciones administrado, la compilación Just-In-Time (JIT) de código (conversión del código de lenguaje intermedio de Microsoft, o MSIL, en código máquina nativo), y características similares. Los mecanismos convencionales de generación de perfiles no pueden identificar o proporcionar información útil sobre estas características. La API de generación de perfiles proporciona eficazmente esta información que falta, con efecto mínimo sobre el rendimiento de CLR y de la aplicación para la que se genera el perfil.

La compilación JIT en tiempo de ejecución proporciona buenas oportunidades para la generación de perfiles. La API de generación de perfiles permite a un generador de perfiles cambiar las secuencias de código de MSIL en memoria para una rutina antes de la compilación JIT. De esta manera, el generador de perfiles puede agregar dinámicamente código instrumental a rutinas determinadas que necesiten una investigación más profunda. Aunque este enfoque es posible en escenarios convencionales, es mucho más fácil de implementar para CLR utilizando la API de generación de perfiles.

## <a name="the-profiling-api"></a>La API de generación de perfiles

Normalmente, la API de generación de perfiles se usa para escribir un *generador de perfiles de código*, que es un programa que supervisa la ejecución de una aplicación administrada.

La API de generación de perfiles la utiliza una DLL de generación de perfiles, que se carga en el mismo proceso que la aplicación para la que se está generando el perfil. La DLL del generador de perfiles implementa una interfaz de devolución de llamada ([ICorProfilerCallback](icorprofilercallback-interface.md) en la .NET Framework versión 1,0 y 1,1, [ICorProfilerCallback2](icorprofilercallback2-interface.md) en la versión 2,0 y posteriores). CLR llama a los métodos de esa interfaz para notificar al generador de perfiles eventos en el proceso perfilado. El generador de perfiles puede volver a llamar al motor en tiempo de ejecución mediante los métodos de las interfaces [ICorProfilerInfo](icorprofilerinfo-interface.md) e [ICorProfilerInfo2](icorprofilerinfo2-interface.md) para obtener información sobre el estado de la aplicación de la que se van a crear perfiles.

> [!NOTE]
> Sólo la parte de recolección de datos de la solución del generador de perfiles debe estar en ejecución en el mismo proceso que la aplicación para la que se genera el perfil. Toda la interfaz de usuario y el análisis de datos se deben ejecutar en un proceso independiente.

La ilustración siguiente muestra cómo interactúa la DLL del generador de perfiles con la aplicación para la que se está generando el perfil y CLR.

![Captura de pantalla que muestra la arquitectura de generación de perfiles.](./media/profiling-overview/profiling-architecture.png)

### <a name="the-notification-interfaces"></a>Las interfaces de notificación

[ICorProfilerCallback](icorprofilercallback-interface.md) y [ICorProfilerCallback2](icorprofilercallback2-interface.md) se pueden considerar interfaces de notificación. Estas interfaces se componen de métodos como [classloadstarted (](icorprofilercallback-classloadstarted-method.md), [classloadfinished (](icorprofilercallback-classloadfinished-method.md)y [JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md). Cada vez que CLR carga o descarga una clase, compila una función, etc., llama al método correspondiente de la interfaz `ICorProfilerCallback` o `ICorProfilerCallback2` del generador de perfiles.

Por ejemplo, un generador de perfiles podría medir el rendimiento del código a través de dos funciones de notificación: [FunctionEnter2](functionenter2-function.md) y [FunctionLeave2](functionleave2-function.md). Simplemente marca el tiempo de cada notificación, acumula los resultados y genera una lista que indica qué funciones consumieron la mayoría del tiempo de CPU o de reloj durante la ejecución de la aplicación.

### <a name="the-information-retrieval-interfaces"></a>Las interfaces de recuperación de información

Las otras interfaces principales implicadas en la generación de perfiles son [ICorProfilerInfo](icorprofilerinfo-interface.md) e [ICorProfilerInfo2](icorprofilerinfo2-interface.md). El generador de perfiles llama a estas interfaces según es necesario para obtener más información como ayuda para su análisis. Por ejemplo, cada vez que CLR llama a la función [FunctionEnter2](functionenter2-function.md) , proporciona un identificador de función. El generador de perfiles puede obtener más información sobre esa función llamando al método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) para detectar la clase primaria de la función, su nombre, etc.

## <a name="supported-features"></a>Características compatibles

La API de generación de perfiles proporciona información sobre diversos eventos y acciones que se producen en Common Language Runtime. Puede usar esta información para supervisar los mecanismos internos de los procesos y para analizar el rendimiento de la aplicación .NET Framework.

La API de generación de perfiles recupera información sobre los siguientes eventos y acciones que se producen en el CLR:

- Eventos de inicio y cierre de CLR.

- Eventos de creación y cierre de dominio de aplicación.

- Eventos de carga y descarga de ensamblados.

- Eventos de carga y descarga de módulos.

- Eventos de creación y destrucción de vtable COM.

- Eventos de compilación Just-In-Time (JIT) y eliminación de código nativo.

- Eventos de carga y descarga de clase.

- Eventos de creación y destrucción de subprocesos.

- Eventos de entrada y salida de función.

- Excepciones.

- Transiciones entre la ejecución de código administrado y no administrado.

- Transiciones entre diferentes contextos de tiempo de ejecución.

- Información sobre suspensiones de tiempo de ejecución.

- Información sobre el montón de memoria de tiempo de ejecución y la actividad de recolección de elementos no utilizados.

Se puede llamar a la API de generación de perfiles desde cualquier lenguaje compatible con COM (no administrado).

La API es eficaz con respecto a CPU y al consumo de memoria. La generación de perfiles no implica cambios en la aplicación para la que se genera el perfil que sean lo bastante significativos como para producir resultados engañosos.

La API de generación de perfiles es útil tanto para los generadores de perfiles de muestreo como no de muestreo. Un *generador de perfiles de muestreo* inspecciona el perfil en TICs de reloj normales, por ejemplo, a 5 milisegundos de distancia. Un *generador de perfiles de muestreo no* se informa de un evento sincrónicamente con el subproceso que provoca el evento.

### <a name="unsupported-functionality"></a>Funcionalidad incompatible

La API de generación de perfiles no admite la funcionalidad siguiente:

- Código no administrado, que se debe perfilar usando métodos de Win32 convencionales. Sin embargo, el generador de perfiles de CLR incluye eventos de transición para determinar los límites entre el código administrado y no administrado.

- Aplicaciones que modifican su propio código para propósitos tales como la programación orientada a aspectos.

- Comprobación de límites, ya que la API de generación de perfiles no proporciona esta información. CLR proporciona compatibilidad intrínseca para la comprobación de límites de todo el código administrado.

- Generación de perfiles remota, que no se admite por las siguientes razones:

  - La generación remota de perfiles prolonga el tiempo de ejecución. Cuando usa las interfaces de generación de perfiles, debe minimizar el tiempo de ejecución de modo que los resultados de la generación de perfiles no se vean excesivamente afectados. Esto es especialmente cierto cuando se supervisa el rendimiento de la ejecución. Sin embargo, la generación remota de perfiles no es una limitación cuando las interfaces de generación de perfiles se emplean para supervisar el uso de memoria o para obtener información en tiempo de ejecución sobre marcos de pila, objetos, etc.

  - El generador de perfiles del código de CLR debe registrar una o más interfaces de devolución de llamada con el motor en tiempo de ejecución en el equipo local en el que se está ejecutando la aplicación para la que se genera el perfil. Esto limita la capacidad para crear un generador de perfiles de código remoto.

- Generación de perfiles en entornos de producción con requisitos de alta disponibilidad. La API de generación de perfiles fue creada para admitir diagnósticos en tiempo de desarrollo. No se ha sometido a las rigurosas pruebas exigidas para la compatibilidad de entornos de producción.

## <a name="notification-threads"></a>Subprocesos de notificación

En la mayoría de los casos, el subproceso que genera un evento ejecuta también las notificaciones. Estas notificaciones (por ejemplo, [FunctionEnter (](functionenter-function.md) y [FunctionLeave (](functionleave-function.md)) no necesitan proporcionar el `ThreadID`explícito. Además, el generador de perfiles puede decidir utilizar almacenamiento local de subproceso para almacenar y actualizar sus bloques de análisis, en lugar de indizar los bloques de análisis en almacenamiento global, en función del `ThreadID` del subproceso afectado.

Tenga en cuenta que estas devoluciones de llamada no se serializan. Los usuarios deben proteger su código creando estructuras de datos seguras para subprocesos y bloqueando el código del generador de perfiles donde sea necesario para evitar el acceso paralelo desde varios subprocesos. Por consiguiente, en ciertos casos puede recibir una secuencia poco habitual de devoluciones de llamada. Por ejemplo, suponga que una aplicación administrada está generando dos subprocesos que está ejecutando código idéntico. En este caso, es posible recibir un evento [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) para alguna función de un subproceso y una devolución de llamada de `FunctionEnter` desde el otro subproceso antes de recibir la devolución de llamada [ICorProfilerCallback:: JITCompilationFinished (](icorprofilercallback-jitcompilationfinished-method.md) . En este caso, el usuario recibirá una devolución de llamada `FunctionEnter` para una función que puede no haberse compilado totalmente Just-In-Time (JIT) todavía.

## <a name="security"></a>de seguridad

Una DLL del generador de perfiles es una DLL no administrada que se ejecuta como parte del motor de ejecución de Common Language Runtime. Como resultado, el código de la DLL del generador de perfiles no está sujeto a las restricciones de seguridad de acceso del código administrado. Las únicas limitaciones sobre la DLL del generador de perfiles son las impuestas por el sistema operativo sobre el usuario que está ejecutando la aplicación para la que se ha generado el perfil.

Los autores del generador de perfiles deben tomar las precauciones adecuadas para evitar problemas relacionados con la seguridad. Por ejemplo, durante la instalación, la DLL del generador de perfiles debe agregarse a una lista de control de acceso (ACL) para que los usuarios malintencionados no puedan modificarla.

## <a name="combining-managed-and-unmanaged-code-in-a-code-profiler"></a>Combinar código administrado y no administrado en un generador de perfiles de código

Un generador de perfiles incorrectamente escrito puede provocar referencias circulares a sí mismo, produciendo un comportamiento imprevisible.

Una revisión de la API de generación de perfiles de CLR puede crear la impresión de que se puede escribir un generador de perfiles que contenga componentes administrados y no administrados, que de llaman entre sí a través de interoperabilidad COM o llamadas indirectas.

Aunque esto es posible desde la perspectiva del diseño, la API de generación de perfiles no admite componentes administrados. Un generador de perfiles de CLR debe ser completamente no administrado. Los intentos de combinar código administrado y código no administrado en un generador de perfiles de CLR pueden provocar infracciones de acceso, errores de programa o interbloqueos. Los componentes administrados del generador de perfiles devolverán eventos a sus componentes no administrados, que llamarán de nuevo, como consecuencia, a los componentes administrados, produciendo referencias circulares.

La única ubicación donde un generador de perfiles de CLR puede llamar sin ningún riesgo a código administrado es en el cuerpo de un método de lenguaje intermedio de Microsoft (MSIL). La práctica recomendada para modificar el cuerpo de MSIL es usar los métodos de recompilación JIT en la interfaz [ICorProfilerCallback4](icorprofilercallback4-interface.md) .

También es posible usar los métodos de instrumentación más antiguos para modificar MSIL. Antes de que se complete la compilación Just-in-Time (JIT) de una función, el generador de perfiles puede insertar llamadas administradas en el cuerpo de MSIL de un método y, a continuación, compilarla JIT (vea el método [ICorProfilerInfo:: getilfunctionbody (](icorprofilerinfo-getilfunctionbody-method.md) ). Esta técnica se puede utilizar con éxito para el instrumental selectivo de código administrado o para recopilar estadísticas y datos de rendimiento sobre JIT.

Como alternativa, un generador de perfiles de código puede insertar enlaces nativos en el cuerpo de MSIL de cada función administrada que llame a código no administrado. Esta técnica se puede utilizar para instrumental y cobertura. Por ejemplo, un generador de perfiles de código puede insertar enlaces de instrumental después de cada bloque de MSIL para asegurarse de que se ha ejecutado el bloque. La modificación del cuerpo MSIL de un método es una operación muy delicada y hay muchos factores que se deben tener en cuenta.

## <a name="profiling-unmanaged-code"></a>Código no administrado de generación de perfiles

La API de generación de perfiles de Common Language Runtime (CLR) proporciona la compatibilidad mínima para el código no administrado de generación de perfiles. Se proporciona la funcionalidad siguiente:

- Enumeración de cadenas de pila. Esta característica permite a un generador de perfiles de código determinar el límite entre el código administrado y el código no administrado.

- Determinación de si una cadena de pila corresponde a código administrado o código nativo.

En las versiones 1.0 y 1.1 de .NET Framework, estos métodos están disponibles a través del subconjunto en proceso de la API de depuración de CLR. Se definen en el archivo CorDebug.idl.

En el .NET Framework 2,0 y versiones posteriores, puede usar el método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) para esta funcionalidad.

## <a name="using-com"></a>Utilizar COM

Aunque las interfaces de generación de perfiles se definen como interfaces COM, Common Language Runtime (CLR) no inicializa realmente COM para utilizar estas interfaces. La razón es evitar tener que establecer el modelo de subprocesos usando la función [CoInitialize](/windows/desktop/api/objbase/nf-objbase-coinitialize) antes de que la aplicación administrada haya tenido la oportunidad de especificar su modelo de subprocesos deseado. De igual forma, el propio generador de perfiles no debe llamar a `CoInitialize`, porque puede elegir un modelo de subprocesos que sea incompatible con la aplicación para la que se está generando el perfil y puede hacer que la aplicación no funcione correctamente.

## <a name="call-stacks"></a>Pilas de llamadas

La API de generación de perfiles proporciona dos maneras de obtener pilas de llamadas: un método de instantánea de pila, que habilita la recolección dispersa de pilas de llamadas, y un método de pila de sombra, que realiza el seguimiento de la pila de llamadas en cada momento.

### <a name="stack-snapshot"></a>Instantánea de pila

Una instantánea de pila es un registro de la pila de un subproceso en un momento determinado. La API de generación de perfiles permite la traza de funciones administradas en la pila, pero deja la traza de las funciones no administradas al rastreador de pila propio del generador de perfiles.

Para obtener más información sobre cómo programar el generador de perfiles para recorrer pilas administradas, vea el método [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) en este conjunto de documentación y [el recorrido de la pila del generador de perfiles en el .NET Framework 2,0: Basics y versiones posteriores](https://docs.microsoft.com/previous-versions/dotnet/articles/bb264782(v=msdn.10)).

### <a name="shadow-stack"></a>Pila sombra

Utilizar el método de instantánea con demasiada frecuencia puede crear rápidamente un problema de rendimiento. Si desea tomar los seguimientos de la pila con frecuencia, el generador de perfiles debe crear en su lugar una pila de instantáneas usando las devoluciones de llamada de excepción [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), [FunctionTailcall2](functiontailcall2-function.md)y [ICorProfilerCallback2](icorprofilercallback2-interface.md) . La pila sombra es siempre actual y se copia rápidamente al almacenamiento cada vez que se necesita una instantánea de la pila.

Una pila sombra puede obtener argumentos de función, valores devueltos e información sobre las instancias genéricas. Esta información solamente está disponible a través de la pila sombra y puede obtenerse cuando se entrega el control a una función. Sin embargo, es posible que esta información no esté disponible más tarde, durante la ejecución de la función.

## <a name="callbacks-and-stack-depth"></a>Devoluciones de llamada y profundidad de la pila

Las devoluciones de llamada del generador de perfiles se pueden emitir en circunstancias muy restringidas por la pila y un desbordamiento de pila en una devolución de llamada del generador de perfiles conducirá a una inmediata salida del proceso. Un generador de perfiles debe asegurarse de usar la mínima pila posible en respuesta a las devoluciones de llamada. Si el generador de perfiles está destinado a usarse contra procesos robustos contra el desbordamiento de pila, el propio generador de perfiles deberá también evitar activar el desbordamiento de pila.

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Configuración de un entorno de generación de perfiles](setting-up-a-profiling-environment.md)|Explica cómo inicializar un generador de perfiles, establecer notificaciones de eventos y generar perfiles para un servicio de Windows.|
|[Interfaces para generación de perfiles](profiling-interfaces.md)|Describe las interfaces no administradas que utiliza la API de generación de perfiles.|
|[Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)|Describe las funciones estáticas globales no administradas que utiliza la API de generación de perfiles.|
|[Enumeraciones para generación de perfiles](profiling-enumerations.md)|Describe las enumeraciones no administradas que utiliza la API de generación de perfiles.|
|[Estructuras para generación de perfiles](profiling-structures.md)|Describe las estructuras no administradas que utiliza la API de generación de perfiles.|
