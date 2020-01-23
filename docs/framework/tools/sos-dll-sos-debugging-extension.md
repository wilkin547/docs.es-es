---
title: SOS.dll (Extensión de depuración de SOS)
ms.date: 03/30/2017
helpviewer_keywords:
- debugging extensions
- SOS debugging extensions
- SOS.dll
ms.assetid: 9ac1b522-77ab-4cdc-852a-20fcdc9ae498
ms.openlocfilehash: 4c3a7f2798791f0c8a6b752f06bc2937fc970d40
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715728"
---
# <a name="sosdll-sos-debugging-extension"></a>SOS.dll (Extensión de depuración de SOS)

La extensión de depuración de SOS (SOS.dll) ayuda a depurar programas administrados en Visual Studio y en el depurador de Windows (WinDbg.exe); para ello, proporciona información sobre el entorno interno de Common Language Runtime (CLR). Esta herramienta requiere que el proyecto tenga habilitada la depuración no administrada. SOS.dll se instala automáticamente con .NET Framework. Para usar SOS.dll en Visual Studio, instale el [Kit para controladores de Windows (WDK)](/windows-hardware/drivers/download-the-wdk).

## <a name="syntax"></a>Sintaxis

```console
![command] [options]
```

## <a name="commands"></a>Comandos

|Comando|Descripción|
|-------------|-----------------|
|**AnalyzeOOM** (**ao**)|Muestra la información sobre el último evento de memoria insuficiente (OOM) que se produjo en una solicitud de asignación al montón de recolección de elementos no utilizados. (En la recolección de elementos no utilizados del servidor, se muestra OOM, si hubiera alguno, en cada montón de recolección de elementos no utilizados).|
|**BPMD** [ **-nofuturemodule**] [\<*nombre del módulo*> \<*nombre del método*>] [ **-md** <`MethodDesc`>] **-list** **-clear** \<*número de punto de interrupción pendiente*>  **-clearall**|Crea un punto de interrupción en el método especificado en el módulo especificado.<br /><br /> Si no se han cargado el módulo y el método especificados, antes de crear el punto de interrupción, este comando espera una notificación de que el módulo se ha cargado y se ha compilado Just-In-Time (JIT).<br /><br /> Puede administrar la lista de puntos de interrupción pendientes mediante las opciones **-list**, **-clear** y **-clearall**:<br /><br /> La opción **-list** genera una lista con todos los puntos de interrupción pendientes. Si un punto de interrupción pendiente tiene un identificador de módulo distinto de cero, el punto de interrupción es específico de una función de ese módulo cargado en particular. Si el punto de interrupción pendiente tiene un identificador de módulo cuyo valor es cero, el punto de interrupción se aplica a los módulos que no se han cargado todavía.<br /><br /> Use la opción **-clear** o **-clearall** para quitar los puntos de interrupción pendientes de la lista.|
|**CLRStack** [ **-a**] [ **-l**] [ **-p**] [ **-n**]|Proporciona un seguimiento de pila del código administrado únicamente.<br /><br /> La opción **-p** muestra los argumentos para la función administrada.<br /><br /> La opción **-l** muestra información sobre las variables locales de un marco. La extensión de depuración de SOS no puede recuperar nombres locales, por lo que la salida para los nombres locales tiene el formato \<*local address*>  **=** \<*value*>.<br /><br /> La opción **-a**(all) es un acceso directo para **-l** y **-p** combinados.<br /><br /> La opción **-n** deshabilita la presentación de los nombres de archivo de código fuente y los números de línea. Si el depurador tiene especificada la opción SYMOPT_LOAD_LINES, SOS buscará los símbolos para cada marco administrado y, si los encuentra, mostrará el nombre del archivo de código fuente y el número de línea correspondientes. Para deshabilitar este comportamiento, se puede especificar el parámetro **-n** (sin números de línea).<br /><br /> La extensión de depuración de SOS no muestra marcos de transición en plataformas basadas en IA-64 y x64.|
|**COMState**|Muestra el modelo de apartamento COM para cada subproceso y un puntero `Context`, si está disponible.|
|**DumpArray** [ **-start** \<*índiceDeInicio*>] [ **-length** \<*longitud*>] [ **-details**] [ **-nofields**] \<*dirección de objeto de matriz*><br /><br /> o bien<br /><br /> **DA** [ **-start** \<*índiceDeInicio*>] [ **-length** \<*longitud*>] [ **-detail**] [ **-nofields**] *dirección de objeto de matriz*>|Examina los elementos de un objeto de matriz.<br /><br /> La opción **-start** especifica el índice inicial en el que se mostrarán los elementos.<br /><br /> La opción **-length** especifica el número de elementos que se van a mostrar.<br /><br /> La opción **-details** muestra detalles del elemento en los formatos **DumpObj** y **DumpVC**.<br /><br /> La opción **-nofields** evita que se muestren las matrices. Esta opción solo está disponible cuando se especifica la opción **-detail**.|
|**DumpAssembly** \<*dirección del ensamblado*>|Muestra información sobre de un ensamblado.<br /><br /> El comando **DumpAssembly** muestra varios módulos, si los hay.<br /><br /> Con el comando **DumpDomain** puede obtener la dirección de un ensamblado.|
|**DumpClass** \<*dirección de EEClass*>|Muestra información sobre la estructura `EEClass` asociada a un tipo.<br /><br /> El comando **DumpClass** muestra los valores de campo estático, pero no muestra los valores de campo no estático.<br /><br /> Utilice los comandos **DumpMT**, **DumpObj**, **Name2EE** o **Token2EE** para obtener una dirección de la estructura `EEClass`.|
|**DumpDomain** [\<*dirección de dominio*>]|Enumera todos los objetos <xref:System.Reflection.Assembly> que se han cargado en la dirección del objeto <xref:System.AppDomain> que se ha especificado.  Cuando se llama sin parámetros, el comando **DumpDomain** enumera todos los objetos <xref:System.AppDomain> de un proceso.|
|**DumpHeap** [ **-stat**] [ **-strings**] [ **-short**] [ **-min** \<*tamaño*>] [ **-max** \<*tamaño*>] [ **-thinlock**] [ **-startAtLowerBound**] [ **-mt** \<*dirección de MethodTable*>] [ **-type** \<*nombre de tipo parcial*>][*start* [*end*]]|Muestra información sobre el montón de recolección de elementos no utilizados y estadísticas de recolección de los objetos.<br /><br /> El comando **DumpHeap** muestra una advertencia si detecta una fragmentación excesiva en el montón del recolector de elementos no utilizados.<br /><br /> La opción **-stat** limita la salida a un resumen estadístico de tipos.<br /><br /> La opción **-strings** limita la salida a un resumen estadístico de valores de cadena.<br /><br /> La opción **-short** limita la salida a la dirección de cada objeto. Esto permite canalizar fácilmente la salida del comando a otro comando del depurador para su automatización.<br /><br /> La opción **-min** omite los objetos cuyo tamaño es inferior al valor del parámetro `size`, especificado en bytes.<br /><br /> La opción **-max** omite los objetos cuyo tamaño es superior al valor del parámetro `size`, especificado en bytes.<br /><br /> La opción **-thinlock** genera un informe ThinLocks.  Para más información, consulte el comando **SyncBlk**.<br /><br /> La opción `-startAtLowerBound` obliga al montón a iniciar su recorrido en el límite inferior del intervalo de direcciones especificado. Durante la fase de planeación, con frecuencia el montón no es transitable porque los objetos se están moviendo. Esta opción obliga a **DumpHeap** a iniciar su recorrido en el límite inferior especificado. Para que esta opción funcione, debe proporcionar la dirección de un objeto válido como el límite inferior. Puede mostrar la memoria en la dirección de un objeto no válido para encontrar manualmente la siguiente tabla de métodos. Si la recolección de elementos no utilizados se encuentra actualmente en una llamada a `memcopy`, puede que también encuentre la dirección del objeto siguiente agregando el tamaño a la dirección de inicio, que se proporciona como un parámetro.<br /><br /> La opción **-mt** muestra solo los objetos correspondientes a la estructura `MethodTable` especificada.<br /><br /> La opción **-type** muestra solo los objetos cuyo nombre de tipo es una subcadena de la cadena especificada.<br /><br /> El parámetro `start` inicia la lista en la dirección especificada.<br /><br /> El parámetro `end` detiene la lista en la dirección especificada.|
|**DumpIL** \<*Objeto DynamicMethod administrado*> &#124;       \<*Puntero DynamicMethodDesc*> &#124;        \<*Puntero MethodDesc*>|Muestra el Lenguaje intermedio de Microsoft (MSIL) que está asociado a un método administrado.<br /><br /> Tenga en cuenta que el MSIL dinámico se emite de manera diferente que el MSIL que se carga desde un ensamblado. El MSIL dinámico hace referencia a objetos de una matriz de objetos administrada en lugar de a tokens de metadatos.|
|**DumpLog** [ **-addr** \<*direcciónDelRegistroDeEsfuerzo*>] [<*Filenam*`e`>]|Escribe el contenido de un registro de esfuerzo existente en memoria en el archivo especificado. Si no se especifica un nombre, este comando crea un archivo denominado StressLog.txt en el directorio actual.<br /><br /> El registro de esfuerzo existente en memoria ayuda en el diagnóstico de los errores de esfuerzo sin usar bloqueos ni E/S. Para habilitar el registro de esfuerzo, establezca las siguientes claves del Registro en HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework:<br /><br /> (DWORD) StressLog = 1<br /><br /> (DWORD) LogFacility = 0xffffffff<br /><br /> (DWORD) StressLogSize = 65536<br /><br /> La opción `-addr` opcional permite especificar un registro de esfuerzo distinto del registro predeterminado.|
|**DumpMD** \<*dirección de MethodDesc*>|Muestra información sobre una estructura `MethodDesc` en la dirección especificada.<br /><br /> Puede usar el comando **IP2MD** para obtener la dirección de la estructura `MethodDesc` a partir de una función administrada.|
|**DumpMT** [ **-MD**] \<*dirección de MethodTable*>|Muestra información sobre una tabla de métodos en la dirección especificada. La opción **-MD** muestra una lista de todos los métodos definidos con el objeto.<br /><br /> Cada objeto administrado contiene un puntero a la tabla de métodos.|
|**DumpMethodSig** \<*dirsig*> <*moduleadd*`r`>|Muestra información sobre una estructura `MethodSig` en la dirección especificada.|
|**DumpModule** [ **-mt**] \<*dirección del módulo*>|Muestra información sobre un módulo en la dirección especificada. La opción **-mt** muestra los tipos definidos en un módulo y los tipos a los que el módulo hace referencia.<br /><br /> Puede usar el comando **DumpDomain** o **DumpAssembly** para recuperar la dirección de un módulo.|
|**DumpObj** [ **-nofields**] \<*dirección del objeto*><br /><br /> o bien<br /><br /> **DO** \<*dirección del objeto*>|Muestra información sobre un objeto en la dirección especificada. El comando **DumpObj** muestra los campos, información de la estructura `EEClass`, la tabla de métodos y el tamaño del objeto.<br /><br /> Puede usar el comando **DumpStackObjects** para recuperar la dirección de un objeto.<br /><br /> Tenga presente que puede ejecutar el comando **DumpObj** en campos de tipo `CLASS` porque también son objetos.<br /><br /> La opción `-`**nofields** impide que los campos del objeto se muestren; es útil para objetos como String.|
|**DumpRuntimeTypes**|Muestra los objetos de tipo en tiempo de ejecución del montón del recolector de elementos no utilizados y enumera las tablas de métodos y los nombres de tipo asociados.|
|**DumpStack** [ **-EE**] [ **-n**] [`top` *stack* [`bottom` *stac*`k`]]|Muestra un seguimiento de la pila.<br /><br /> La opción **-EE** hace que el comando **DumpStack** muestre solo funciones administradas. Use los parámetros `top` y `bottom` para limitar los marcos de pila mostrados en las plataformas x86.<br /><br /> La opción **-n** deshabilita la presentación de los nombres de archivo de código fuente y los números de línea. Si el depurador tiene especificada la opción SYMOPT_LOAD_LINES, SOS buscará los símbolos para cada marco administrado y, si los encuentra, mostrará el nombre del archivo de código fuente y el número de línea correspondientes. Para deshabilitar este comportamiento, se puede especificar el parámetro **-n** (sin números de línea).<br /><br /> En las plataformas x86 y x64, el comando **DumpStack** crea un seguimiento de la pila detallado.<br /><br /> En las plataformas basadas en IA-64, el comando **DumpStack** imita el comportamiento del comando **K** del depurador. Los parámetros `top` y `bottom` se omiten en las plataformas basadas en IA-64.|
|**DumpSig** \<*dirsig*> \<*dirdelmódulo*>|Muestra información sobre una estructura `Sig` en la dirección especificada.|
|**DumpSigElem** \<*dirsig*> \<*dirdelmódulo*>|Muestra un único elemento de un objeto de firma. En la mayoría de los casos, deberá usar **DumpSig** para examinar los objetos de firma individuales. Sin embargo, si una firma se ha dañado de alguna manera, puede usar **DumpSigElem** para leer las partes válidas.|
|**DumpStackObjects** [ **-verify**] [`top` *stack* [`bottom` *stack*]]<br /><br /> o bien<br /><br /> **DSO** [ **-verify**] [`top` *stack* [`bottom` *stack*]]|Muestra todos los objetos administrados que se han encontrado dentro de los límites de la pila actual.<br /><br /> La opción **-verify** valida cada campo `CLASS` no estático de un campo de objeto.<br /><br /> Use el comando **DumpStackObject** con comandos de seguimiento de pila como el comando **K** y el comando **CLRStack** para determinar los valores de los parámetros y las variables locales.|
|**DumpVC**\<*dirección de MethodTable*> \<*Dirección*>|Muestra información sobre los campos de una clase de valor en la dirección especificada.<br /><br /> El parámetro **MethodTable** permite que el comando **DumpVC** interprete los campos correctamente. Las clases de valor no tienen una tabla de métodos como primer campo.|
|**EEHeap** [ **-gc**] [ **-loader**]|Muestra información sobre la memoria de proceso que usan las estructuras de datos internas de CLR.<br /><br /> Las opciones **-gc** y **-loader** limitan la salida de este comando a las estructuras de datos del recolector de elementos no utilizados o del cargador.<br /><br /> La información del recolector de elementos no utilizados muestra los intervalos de cada segmento del montón administrado.  Si el puntero se encuentra en un intervalo de segmento proporcionado por **-gc**, se trata de un puntero de objeto.|
|**EEStack** [ **-short**] [ **-EE**]|Ejecuta el comando **DumpStack** en todos los subprocesos del proceso.<br /><br /> La opción **-EE** se pasa directamente al comando **DumpStack**. El parámetro **-short** limita la salida a los siguientes tipos de subprocesos:<br /><br /> Subprocesos que han tomado un bloqueo.<br /><br /> Subprocesos que se han detenido para permitir la recolección de elementos no utilizados.<br /><br /> Subprocesos que están actualmente en el código administrado.|
|**EEVersion**|Muestra la versión de CLR.|
|**EHInfo** [\<*dirección de MethodDesc*>] [\<*dirección de código*>]|Muestra los bloques de control de excepciones de un método especificado.  Este comando muestra los desplazamientos y las direcciones de código para el bloque de cláusulas (el bloque `try`) y el bloque del controlador (el bloque `catch`).|
|**Preguntas más frecuentes**|Muestra las preguntas más frecuentes.|
|**FinalizeQueue** [ **-detail**] &#124; [ **-allReady**] [ **-short**]|Muestra todos los objetos registrados para su finalización.<br /><br /> La opción **-detail** muestra información adicional sobre los `SyncBlocks` que necesitan limpieza y los `RuntimeCallableWrappers` (RCW) que están a la espera de limpieza. Al ejecutarse, el subproceso del finalizador almacena en la memoria caché y limpia ambas estructuras de datos.<br /><br /> La opción `-allReady` muestra todos los objetos que están listos para la finalización, sin tener en cuenta si la recolección de elementos no utilizados los ha marcado ya como tales, o si los marcará la siguiente recolección de elementos no utilizados. Los objetos que están en la lista "listos para la finalización" son objetos susceptibles de finalización que ya no tienen raíz. Esta opción puede consumir muchos recursos porque comprueba si todos los objetos de las colas susceptibles de finalización siguen teniendo raíz.<br /><br /> La opción `-short` limita la salida a la dirección de cada objeto. Si se usa junto con **-allReady**, enumera todos los objetos que tienen un finalizador y que ya no tienen raíz. Si se usa de manera independiente, enumera todos los objetos que están en las colas "susceptibles de finalización" y "listos para la finalización".|
|**FindAppDomain** \<*Dirección del objeto*>|Determina el dominio de aplicación de un objeto en la dirección especificada.|
|**FindRoots** **-gen** \<*N*> &#124; **-gen any** &#124;\<*dirección del objeto*>|Hace que el depurador interrumpa el código que se está depurando en la recolección siguiente de la generación especificada. El efecto se restablece tan pronto como se produce la interrupción. Para interrumpir la recolección siguiente, vuelva a emitir el comando. El formato *\<dirección del objeto>* de este comando se usa después de la interrupción provocada por **-gen** o **-gen any**. En ese momento, el código que se está depurando se encuentra en el estado correcto para que **FindRoots** identifique las raíces para los objetos de las generaciones actualmente inutilizadas.|
|**GCHandles** [ **-perdomain**]|Muestra estadísticas acerca de los identificadores del recolector de elementos no utilizados existentes en el proceso.<br /><br /> La opción **-perdomain** organiza las estadísticas por dominio de aplicación.<br /><br /> Use el comando **GCHandles** para encontrar pérdidas de memoria producidas por la pérdida de identificadores del recolector de elementos no utilizados. Una pérdida de memoria se produce, por ejemplo, cuando el código conserva una matriz grande porque un identificador seguro del recolector de elementos no utilizados todavía señala a dicha matriz y el identificador se descarta sin liberarla.|
|**GCHandleLeaks**|Busca en la memoria cualquier referencia a identificadores seguros y anclados del recolector de elementos no utilizados existentes en el proceso y muestra los resultados. Si se encuentra un identificador, el comando **GCHandleLeaks** muestra la dirección de la referencia. Si no se encuentra ningún identificador en memoria, este comando muestra una notificación.|
|**GCInfo** \<*dirección de MethodDesc*>\<*Dirección de código*>|Muestra datos que indican en qué momento los registros o las ubicaciones de la pila contienen objetos administrados. Si se produce una recolección de elementos no utilizados, el recolector debe conocer las ubicaciones de las referencias a los objetos para poder actualizarlas con los nuevos valores de puntero de objeto.|
|**GCRoot** [ **-nostacks**] \<*dirección del objeto*>|Muestra información acerca de las referencias (o raíces) a un objeto en la dirección especificada.<br /><br /> El comando **GCRoot** busca identificadores dentro de otros objetos y dentro de la pila en todo el montón administrado y en la tabla de identificadores. Después, se buscan punteros a objetos en cada pila y en la cola del finalizador.<br /><br /> Este comando no determina si una raíz de la pila es válida o se ha descartado. Use los comandos **CLRStack** y **U** para desensamblar el marco al que pertenece el valor de argumento o local para determinar si la raíz de la pila todavía está en uso.<br /><br /> La opción **-nostacks** restringe la búsqueda a objetos accesibles y a identificadores del recolector de elementos no utilizados.|
|**GCWhere**  *\<dirección del objeto>*|Muestra la ubicación y el tamaño en el montón de recolección de elementos no utilizados del argumento que se ha pasado. Cuando el argumento permanece en el montón administrado, pero no es una dirección de objeto válida, el tamaño se muestra como 0 (cero).|
|**help** [\<*comando*>] [`faq`]|Cuando no se especifica ningún parámetro, muestra todos los comandos disponibles, o bien muestra ayuda detallada acerca del comando especificado.<br /><br /> El parámetro `faq` muestra respuestas a las preguntas más frecuentes.|
|**HeapStat** [ **-inclUnrooted** &#124; **-iu**]|Muestra los tamaños de generación de cada montón y el espacio total disponible en cada generación de cada montón. Si se especifica la opción -**inclUnrooted**, el informe incluye información sobre los objetos administrados del montón de recolección de elementos no utilizados que ya no tienen raíz.|
|**HistClear**|Libera los recursos usados por la familia de comandos `Hist`.<br /><br /> Generalmente, no tiene que llamar explícitamente a `HistClear`, puesto que cada comando `HistInit` limpia los recursos anteriores.|
|**HistInit**|Inicializa las estructuras SOS del registro de esfuerzo guardado en el código que se está depurando.|
|**HistObj** *\<obj_address>*|Examina todos los registros de reubicación del registro de esfuerzo y muestra la cadena de reubicaciones de recolección de elementos no utilizados que pueden haber conducido a la dirección que se ha pasado como argumento.|
|**HistObjFind**  *\<obj_address>*|Muestra todas las entradas de registro que hacen referencia a un objeto en la dirección especificada.|
|**HistRoot** *\<raíz>*|Muestra información relacionada con las promociones y las reubicaciones de la raíz especificada.<br /><br /> El valor de raíz se puede usar para realizar el seguimiento del movimiento de un objeto a través de las recolecciones de elementos no utilizados.|
|**IP2MD** \<*Dirección de código*>|Muestra la estructura `MethodDesc` en la dirección especificada en el código compilado JIT.|
|`ListNearObj` (`lno`) *\<obj_address>*|Muestra los objetos anteriores y posteriores a la dirección especificada. El comando busca en el montón de recolección de elementos no utilizados la dirección que parece un principio válido de un objeto administrado (basándose en una tabla de métodos válida) y el objeto que sigue a la dirección del argumento.|
|**MinidumpMode** [**0**] [**1**]|Evita que se ejecuten comandos no seguros al usar un minivolcado.<br /><br /> Pase **0** para deshabilitar esta característica o **1** para habilitarla. De forma predeterminada, el valor **MinidumpMode** se establece en **0**.<br /><br /> Los minivolcados creados con el comando **.dump /m** o **.dump** tienen datos limitados específicos de CLR y permiten ejecutar correctamente un único subconjunto de comandos de SOS. Algunos comandos pueden producir errores inesperados porque no se hayan asignado, o solo se hayan asignado parcialmente, áreas de memoria necesarias. Esta opción le impide ejecutar comandos no seguros en minivolcados.|
|**Name2EE** \<*nombre del módulo*> \<*tipo o nombre del método*><br /><br /> o bien<br /><br /> **Name2EE** \<*nombre del módulo*> **!** \<*tipo o nombre del método*>|Muestra la estructura `MethodTable` y la estructura `EEClass` para el tipo o método especificado del módulo especificado.<br /><br /> El módulo especificado se debe cargar en el proceso.<br /><br /> Para obtener el nombre de tipo correcto, examine el módulo mediante [Ildasm.exe (Desensamblador de IL)](ildasm-exe-il-disassembler.md). También puede pasar `*` como parámetro de nombre de módulo para buscar en todos los módulos administrados cargados. El parámetro *nombre del módulo* también puede ser el nombre del depurador de un módulo, como `mscorlib` o `image00400000`.<br /><br /> Este comando admite la sintaxis del depurador de Windows <`module`>`!`<`type`>. El nombre del tipo debe ser completo.|
|**ObjSize** [\<*dirección del objeto*>] &#124; [ **-aggregate**] [ **-stat**]|Muestra el tamaño del objeto especificado. Si no especifica ningún parámetro, el comando **ObjSize** muestra el tamaño de todos los objetos encontrados en subprocesos administrados, muestra todos los identificadores del recolector de elementos no utilizados del proceso, y suma el tamaño de todos los objetos a los que señalan esos identificadores. El comando **ObjSize** incluye el tamaño de todos los objetos secundarios y del objeto primario.<br /><br /> La opción **-aggregate** se puede usar junto con el argumento **-stat** para obtener una vista detallada de los tipos que todavía disponen de raíz. Mediante el uso de **!dumpheap -stat** y **!objsize -aggregate -stat**, puede determinar qué objetos han dejado de tener raíz y diagnosticar diversos problemas de memoria.|
|**PrintException** [ **-nested**] [ **-lines**] [\<*dirección del objeto de excepción*>]<br /><br /> o bien<br /><br /> **PE** [ **-nested**] [\<*dirección del objeto de excepción*>]|Muestra y da formato a los campos de cualquier objeto derivado de la clase <xref:System.Exception> en la dirección especificada. Si no especifica una dirección, el comando **PrintException** muestra la última excepción iniciada en el subproceso actual.<br /><br /> La opción **-nested** muestra detalles acerca de los objetos de excepción anidados.<br /><br /> La opción **-lines** muestra información de origen, si está disponible.<br /><br /> Puede usar este comando para dar formato y ver el campo `_stackTrace`, que es una matriz binaria.|
|**ProcInfo** [ **-env**] [ **-time**] [ **-mem**]|Muestra variables de entorno del proceso, el tiempo de CPU en modo kernel y estadísticas de uso de la memoria.|
|**RCWCleanupList** \<*dirección de RCWCleanupList*>|Muestra la lista de contenedores RCW (runtime callable wrapper) que se encuentran en la dirección especificada a la espera de limpieza.|
|**SaveModule** \<*Dirección base*> \<*Nombre de archivo*>|Escribe en el archivo especificado una imagen que está cargada en memoria en la dirección especificada.|
|**SOSFlush**|Vacía una caché de SOS interna.|
|**StopOnException** [ **-derived**] [ **-create** &#124; **-create2**] \<*excepción*> \<*número de pseudo registro*>|Hace que el depurador se detenga si se inicia la excepción especificada y que continúe ejecutándose si se inician otras excepciones.<br /><br /> La opción **-derived** detecta la excepción especificada y todas las excepciones que se derivan de la misma.|
|**SyncBlk** [ **-all** &#124; \<*número de syncblk*>]|Muestra la estructura `SyncBlock` especificada o todas las estructuras `SyncBlock`.  Si no se pasa ningún argumento, el comando **SyncBlk** muestra la estructura `SyncBlock` que corresponde a los objetos que pertenecen a un subproceso.<br /><br /> Una estructura `SyncBlock` es un contenedor de información adicional que no es necesario crear para cada objeto. Puede contener datos de interoperabilidad COM, códigos hash e información de bloqueo de operaciones seguras para subprocesos.|
|**ThreadPool**|Muestra información acerca del grupo de subprocesos administrados, como el número de solicitudes de trabajo que hay en cola, el número de subprocesos de puerto de finalización y el número de temporizadores.|
|**Token2EE** \<*nombre de módulo*> \<*token*>|Convierte el token de metadatos especificado del módulo especificado en una estructura `MethodTable` o `MethodDesc`.<br /><br /> Se puede pasar `*` como parámetro de nombre de módulo para averiguar qué tiene asignado ese token en cada módulo administrado cargado. También se puede pasar el nombre del depurador para un módulo, como `mscorlib` o `image00400000`.|
|**Threads** [ **-live**] [ **-special**]|Muestra todos los subprocesos administrados del proceso.<br /><br /> El comando **Threads** muestra el identificador abreviado del depurador, el identificador de subproceso de CLR y el identificador de subproceso del sistema operativo.  Además, el comando **Threads** muestra una columna Domain en la que se indica el dominio de aplicación donde se ejecuta un subproceso, una columna APT en la que se muestra el modo de apartamento COM, y una columna Exception en la que se muestra la última excepción iniciada en el subproceso.<br /><br /> La opción **-live** muestra los subprocesos asociados a un subproceso activo.<br /><br /> La opción **-special** muestra todos los subprocesos especiales creados por CLR. Entre los subprocesos especiales se incluyen los subprocesos de recolección de elementos no utilizados (en recolección de elementos no utilizados simultánea y del servidor), subprocesos del asistente del depurador, subprocesos de finalizador, subprocesos de descarga de <xref:System.AppDomain> y subprocesos de temporizador del grupo de subprocesos.|
|**ThreadState \<** *Campo de valor de estado* **>**|Muestra el estado del subproceso. El parámetro `value` es el valor del campo `State` en la salida del informe **Threads**.<br /><br /> Ejemplo:<br /><br /> `0:003> !Threads     ThreadCount:      2     UnstartedThread:  0     BackgroundThread: 1     PendingThread:    0     DeadThread:       0     Hosted Runtime:   no                                           PreEmptive   GC Alloc           Lock            ID OSID ThreadOBJ    State     GC       Context       Domain   Count APT Exception        0    1  250 0019b068      a020 Disabled 02349668:02349fe8 0015def0     0 MTA        2    2  944 001a6020      b220 Enabled  00000000:00000000 0015def0     0 MTA (Finalizer)     0:003> !ThreadState b220         Legal to Join         Background         CLR Owns         CoInitialized         In Multi Threaded Apartment`|
|**TraverseHeap** [ **-xml**] \<*nombre de archivo*>|Escribe información del montón en el archivo especificado, en un formato reconocido por el generador de perfiles CLR. La opción **-xml** hace que el comando **TraverseHeap** dé formato al archivo como XML.<br /><br /> Puede descargar el generador de perfiles CLR desde el [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?LinkID=67325).|
|**U** [ **-gcinfo**] [ **-ehinfo**] [ **-n**] \<*dirección de MethodDesc*> &#124; \<*dirección de código*>|Muestra un desensamblado anotado de un método administrado especificado mediante un puntero a la estructura `MethodDesc` para el método o mediante una dirección de código dentro del cuerpo del método. El comando **U** muestra todo el método de principio a fin, con las anotaciones que convierten los tokens de metadatos en nombres.<br /><br /> La opción **-gcinfo** hace que el comando **U** muestre la estructura `GCInfo` para el método.<br /><br /> La opción **-ehinfo** muestra información de excepción para el método. Esta información también se obtiene con el comando **EHInfo**.<br /><br /> La opción **-n** deshabilita la presentación de los nombres de archivo de código fuente y los números de línea. Si el depurador tiene especificada la opción SYMOPT_LOAD_LINES, SOS mejora los símbolos para cada marco administrado y, si lo hace correctamente, muestra el nombre de archivo de código fuente y el número de línea correspondientes. Puede especificar la opción **-n** para deshabilitar este comportamiento.|
|**VerifyHeap**|Comprueba el montón del recolector de elementos no utilizados en busca de indicios de daños, y muestra los errores encontrados.<br /><br /> Los daños del montón pueden deberse a invocaciones de plataforma construidas de forma incorrecta.|
|**VerifyObj** \<*dirección del objeto*>|Comprueba el objeto que se pasa como argumento en busca de indicios de daños.|
|**VMMap**|Recorre el espacio de direcciones virtuales y muestra el tipo de protección aplicado a cada área.|
|**VMStat**|Proporciona una vista de resumen del espacio de direcciones virtuales, ordenada según el tipo de protección que se ha aplicado a esa memoria (libre, reservada, confirmada, privada, asignada, imagen). La columna TOTAL muestra el resultado de multiplicar la columna AVERAGE por la columna BLK COUNT.|

## <a name="remarks"></a>Comentarios

La extensión de depuración de SOS permite ver información sobre el código que se ejecuta en CLR. Por ejemplo, puede usar la extensión de depuración de SOS para mostrar información acerca del montón administrado, buscar daños en el montón, mostrar tipos de datos internos usados por el runtime y ver información acerca de todo el código administrado que se ejecuta en el runtime.

Para usar la extensión de depuración de SOS en Visual Studio, instale el [Kit para controladores de Windows (WDK)](/windows-hardware/drivers/download-the-wdk). Para más información sobre el entorno de depuración integrado de Visual Studio, vea el tema sobre [entornos de depuración](/windows-hardware/drivers/debugger/debuggers-in-the-debugging-tools-for-windows-package).

También puede usar la extensión de depuración de SOS cargándola en el [depurador WinDbg.exe](/windows-hardware/drivers/debugger/debugger-download-tools) y ejecutando los comandos de WinDbg.exe.

Para cargar la extensión de depuración de SOS en el depurador WinDbg.exe, ejecute el siguiente comando en la herramienta:

```console
.loadby sos clr
```

WinDbg.exe y Visual Studio usan una versión de SOS.dll que corresponde a la versión de Mscorwks.dll actualmente en uso. De forma predeterminada, debería utilizar la versión de SOS.dll que coincide con la versión actual de Mscorwks.dll.

Para usar un archivo de volcado de memoria creado en otro equipo, asegúrese de que el archivo Mscorwks.dll incluido en esa instalación está en su ruta de acceso de símbolos y cargue la versión correspondiente de SOS.dll.

Para cargar una versión concreta de SOS.dll, escriba el comando siguiente en el Depurador de Windows:

```console
.load <full path to sos.dll>
```

## <a name="examples"></a>Ejemplos

El comando siguiente muestra el contenido de una matriz en la dirección `00ad28d0`.  La presentación empieza en el segundo elemento e incluye cinco elementos.

```console
!dumparray -start 2 -length 5 -detail 00ad28d0
```

El comando siguiente muestra el contenido de un ensamblado en la dirección `1ca248`.

```console
!dumpassembly 1ca248
```

El comando siguiente muestra información acerca del montón del recolector de elementos no utilizados.

```console
!dumpheap
```

El comando siguiente escribe el contenido del registro de esfuerzo en memoria en un archivo (predeterminado) denominado StressLog.txt en el directorio actual.

```console
!DumpLog
```

El comando siguiente muestra la estructura `MethodDesc` en la dirección `902f40`.

```console
!dumpmd 902f40
```

El comando siguiente muestra información acerca de un módulo en la dirección `1caa50`.

```console
!dumpmodule 1caa50
```

El comando siguiente muestra información acerca de un objeto en la dirección `a79d40`.

```console
!DumpObj a79d40
```

El comando siguiente muestra los campos de una clase de valor en la dirección `00a79d9c` usando la tabla de métodos en la dirección `0090320c`.

```console
!DumpVC 0090320c 00a79d9c
```

El comando siguiente muestra la memoria de proceso usada por el recolector de elementos no utilizados.

```console
!eeheap -gc
```

El comando siguiente muestra todos los objetos programados para su finalización.

```console
!finalizequeue
```

El comando siguiente determina el dominio de aplicación de un objeto en la dirección `00a79d98`.

```console
!findappdomain 00a79d98
```

El comando siguiente muestra todos los identificadores del recolector de elementos no utilizados del proceso actual.

```console
!gcinfo 5b68dbb8
```

El comando siguiente muestra las estructuras `MethodTable` y `EEClass` para el método `Main` de la clase `MainClass` del módulo `unittest.exe`.

```console
!name2ee unittest.exe MainClass.Main
```

El comando siguiente muestra información acerca del token de metadatos en la dirección `02000003` del módulo `unittest.exe`.

```console
!token2ee unittest.exe 02000003
```

## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
