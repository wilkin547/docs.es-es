---
title: "SOS.dll (Extensi&#243;n de depuraci&#243;n de SOS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "extensiones de depuración"
  - "extensiones de depuración SOS"
  - "SOS.dll"
ms.assetid: 9ac1b522-77ab-4cdc-852a-20fcdc9ae498
caps.latest.revision: 55
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 55
---
# SOS.dll (Extensi&#243;n de depuraci&#243;n de SOS)
La extensión de depuración de SOS (SOS.dll) ayuda a depurar programas administrados en Visual Studio y en el depurador de Windows (WinDbg.exe); para ello, proporciona información sobre el entorno interno de Common Language Runtime (CLR). Esta herramienta requiere que el proyecto tenga habilitada la depuración no administrada. SOS.dll se instala automáticamente con .NET Framework. Para usar SOS.dll en Visual Studio, instale la [Windows Driver Kit (WDK)](http://msdn.microsoft.com/windows/hardware/hh852362).  
  
> [!NOTE]
>  Si utiliza [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], se admite el archivo SOS.dll en el depurador de Windows en Visual Studio, pero no en la ventana Inmediato del depurador de Visual Studio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
![command] [options]   
```  
  
## <a name="commands"></a>Comandos  
  
|Comando|Descripción|  
|-------------|-----------------|  
|**AnalyzeOOM** (**PC**)|Muestra la información sobre el último OOM que se produjo en una solicitud de asignación al montón de recolección de elementos no utilizados. (En la recolección de elementos no utilizados del servidor, se muestra OOM, si hubiera alguno, en cada montón de recolección de elementos no utilizados).|  
|**BPMD** [**-nofuturemodule**] [*module name*> *method name*>] [**-md** <`MethodDesc`>] **-list** **-clear** \<*pending breakpoint number*> **-clearall**|Crea un punto de interrupción en el método especificado en el módulo especificado.<br /><br /> Si no se han cargado el módulo y el método especificados, antes de crear el punto de interrupción, este comando espera una notificación de que el módulo se ha cargado y se ha compilado Just-In-Time (JIT).<br /><br /> Puede administrar la lista de puntos de interrupción pendientes mediante el **-lista**, **-borrar**, y **- clearall** opciones:<br /><br /> El **-lista** opción genera una lista de todos los puntos de interrupción pendientes. Si un punto de interrupción pendiente tiene un identificador de módulo distinto de cero, el punto de interrupción es específico de una función de ese módulo cargado en particular. Si el punto de interrupción pendiente tiene un identificador de módulo cuyo valor es cero, el punto de interrupción se aplica a los módulos que no se han cargado todavía.<br /><br /> Utilice la **-borrar** o **- clearall** opción para quitar de la lista de puntos de interrupción pendientes.|  
|**CLRStack** [**-a**] [**-l**] [**-p**] [**-n**]|Proporciona un seguimiento de pila del código administrado únicamente.<br /><br /> El **-p** opción muestra los argumentos para la función administrada.<br /><br /> El **-l** opción muestra información sobre las variables locales en un marco. La extensión de depuración de SOS no puede recuperar nombres locales, por lo que es el resultado para los nombres locales en el formato *dirección local*> **=** \<*valor*>.<br /><br /> El **-**opción (todos) es un acceso directo para **-l** y **-p**combinada.<br /><br /> El **- n** opción deshabilita la presentación de nombres de archivo de origen y los números de línea. Si el depurador tiene especificada la opción SYMOPT_LOAD_LINES, SOS buscará los símbolos para cada marco administrado y, si los encuentra, mostrará el nombre del archivo de código fuente y el número de línea correspondientes. El **- n** (sin números de línea) para deshabilitar este comportamiento se puede especificar el parámetro.<br /><br /> La extensión de depuración de SOS no muestra marcos de transición en plataformas basadas en IA-64 y x64.|  
|**COMState**|Muestra el modelo de apartamento COM para cada subproceso y un puntero `Context`, si está disponible.|  
|**DumpArray** [**-start** \<*startIndex*>] [**-length** \<*length*>] [**-details**] [**-nofields**] *array object address*><br /><br /> O bien<br /><br /> **DA** [**-start** \<*startIndex*>] [**-length** \<*length*>] [**-detail**] [**-nofields**] *array object address*>|Examina los elementos de un objeto de matriz.<br /><br /> El **-iniciar** opción especifica el índice inicial en el que se va a mostrar los elementos.<br /><br /> El **-longitud** opción especifica el número de elementos para mostrar.<br /><br /> El **-detalles** opción muestra los detalles del elemento en el **DumpObj** y **DumpVC** formatos.<br /><br /> El **- nofields** opción evita que las matrices se muestre. Esta opción sólo está disponible cuando la **-detalle** se especifica la opción.|  
|**DumpAssembly** \<*dirección de ensamblado*>|Muestra información sobre de un ensamblado.<br /><br /> El **DumpAssembly** comando muestra varios módulos, si existen.<br /><br /> Puede obtener una dirección de ensamblado mediante la **DumpDomain** comando.|  
|**DumpClass** \<*dirección de EEClass*>|Muestra información sobre la estructura `EEClass` asociada a un tipo.<br /><br /> El **DumpClass** comando muestra los valores de campo estático, pero no muestra los valores de campo no estático.<br /><br /> Utilice la **DumpMT**, **DumpObj**, **Name2EE**, o **Token2EE** comando para obtener una `EEClass` dirección de la estructura.|  
|**DumpDomain** [*dirección de dominio*>]|Enumera cada <xref:System.Reflection.Assembly> objeto que se cargan dentro de lo especificado <xref:System.AppDomain> dirección del objeto.  Cuando se llama sin parámetros, el **DumpDomain** comando enumera todas <xref:System.AppDomain> objetos en un proceso.|  
|**DumpHeap** [**-stat**] [**-strings**] [**-short**] [**-min** \<*size*>] [**-max** \<*size*>] [**-thinlock**] [**-startAtLowerBound**] [**-mt** \<*MethodTable address*>] [**-type** \<*partial type name*>][*start* [*end*]]|Muestra información sobre el montón de recolección de elementos no utilizados y estadísticas de recolección de los objetos.<br /><br /> El **DumpHeap** comando muestra una advertencia si detecta una fragmentación excesiva en el montón del recolector de elementos no utilizados.<br /><br /> El **-stat** opción restringe el resultado a un resumen estadístico de tipos.<br /><br /> El **-cadenas** opción limita la salida a un valor de cadena estadístico resumen.<br /><br /> El **-breve** opción limita la salida a la dirección de cada objeto. Esto permite canalizar fácilmente la salida del comando a otro comando del depurador para su automatización.<br /><br /> El **-min** opción omite los objetos que son menor que el `size` parámetro, especificado en bytes.<br /><br /> El **-max** opción omite los objetos que son más grandes que el `size` parámetro, especificado en bytes.<br /><br /> El **thinlock -** opción informes ThinLocks.  Para obtener más información, consulte el **SyncBlk** comando.<br /><br /> La opción `-startAtLowerBound` obliga al montón a iniciar su recorrido en el límite inferior del intervalo de direcciones especificado. Durante la fase de planeación, con frecuencia el montón no es transitable porque los objetos se están moviendo. Esta opción obliga a **DumpHeap** para iniciar su recorrido en el límite inferior especificado. Para que esta opción funcione, debe proporcionar la dirección de un objeto válido como el límite inferior. Puede mostrar la memoria en la dirección de un objeto no válido para encontrar manualmente la siguiente tabla de métodos. Si la recolección de elementos no utilizados se encuentra actualmente en una llamada a `memcopy`, puede que también encuentre la dirección del objeto siguiente agregando el tamaño a la dirección de inicio, que se proporciona como un parámetro.<br /><br /> El **- mt** opción muestra sólo los objetos que corresponden a los especificados `MethodTable` estructura.<br /><br /> El **-tipo** opción muestra sólo los objetos cuyo nombre de tipo es una subcadena de la cadena especificada.<br /><br /> El parámetro `start` inicia la lista en la dirección especificada.<br /><br /> El parámetro `end` detiene la lista en la dirección especificada.|  
|**DumpIL** \<*objeto administrado DynamicMethod*> |       *DynamicMethodDesc puntero*> |        *MethodDesc puntero*>|Muestra el Lenguaje intermedio de Microsoft (MSIL) que está asociado a un método administrado.<br /><br /> Tenga en cuenta que el MSIL dinámico se emite de manera diferente que el MSIL que se carga desde un ensamblado. El MSIL dinámico hace referencia a objetos de una matriz de objetos administrada en lugar de a tokens de metadatos.|  
|**DumpLog** [**-addr** \<*addressOfStressLog*>] [*Filenam*`e`>]|Escribe el contenido de un registro de esfuerzo existente en memoria en el archivo especificado. Si no se especifica un nombre, este comando crea un archivo denominado StressLog.txt en el directorio actual.<br /><br /> El registro de esfuerzo existente en memoria ayuda en el diagnóstico de los errores de esfuerzo sin usar bloqueos ni E/S. Para habilitar el registro de esfuerzo, establezca las siguientes claves del registro bajo HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework:<br /><br /> (DWORD) StressLog = 1<br /><br /> (DWORD) LogFacility = 0xffffffff<br /><br /> (DWORD) StressLogSize = 65536<br /><br /> La opción `-addr` opcional permite especificar un registro de esfuerzo distinto del registro predeterminado.|  
|**DumpMD** \<*dirección de MethodDesc*>|Muestra información sobre una estructura `MethodDesc` en la dirección especificada.<br /><br /> Puede usar el **IP2MD** comando para obtener la `MethodDesc` dirección de una función administrada de la estructura.|  
|**DumpMT** [**-MD**] *dirección de MethodTable*>|Muestra información sobre una tabla de métodos en la dirección especificada. Especificar el **-MD** opción muestra una lista de todos los métodos definidos con el objeto.<br /><br /> Cada objeto administrado contiene un puntero a la tabla de métodos.|  
|**DumpMethodSig** \<*dirección de la firma*> *moduleadd*`r`>|Muestra información sobre una estructura `MethodSig` en la dirección especificada.|  
|**DumpModule** [**- mt**] *dirección del módulo*>|Muestra información sobre un módulo en la dirección especificada. El **- mt** opción muestra los tipos definidos en un módulo y los tipos de referencia del módulo<br /><br /> Puede usar el **DumpDomain** o **DumpAssembly** comando para recuperar la dirección de un módulo.|  
|**DumpObj** [**- nofields**] *dirección del objeto*><br /><br /> O bien<br /><br /> **HACER** \<*dirección del objeto*>|Muestra información sobre un objeto en la dirección especificada. El **DumpObj** comando muestra los campos del `EEClass` estructura de información, la tabla de métodos y el tamaño del objeto.<br /><br /> Puede usar el **DumpStackObjects** comando para recuperar la dirección de un objeto.<br /><br /> Tenga en cuenta que puede ejecutar la **DumpObj** comando en campos de tipo `CLASS` porque también son objetos.<br /><br /> El `-` **nofields** opción evita que los campos del objeto se muestren, es útil para objetos como String.|  
|**DumpRuntimeTypes**|Muestra los objetos de tipo en tiempo de ejecución del montón del recolector de elementos no utilizados y enumera las tablas de métodos y los nombres de tipo asociados.|  
|**DumpStack** [**-EE**] [**-n**] [`top` *stack* [`bottom` *stac*`k`]]|Muestra un seguimiento de la pila.<br /><br /> El **- EE** opción causas la **DumpStack** comando para mostrar sólo las funciones administradas. Use los parámetros `top` y `bottom` para limitar los marcos de pila mostrados en las plataformas x86.<br /><br /> El **- n** opción deshabilita la presentación de nombres de archivo de origen y los números de línea. Si el depurador tiene especificada la opción SYMOPT_LOAD_LINES, SOS buscará los símbolos para cada marco administrado y, si los encuentra, mostrará el nombre del archivo de código fuente y el número de línea correspondientes. El **- n** (sin números de línea) para deshabilitar este comportamiento se puede especificar el parámetro.<br /><br /> En las plataformas de x86 y x64, la **DumpStack** comando crea un seguimiento de pila detallado.<br /><br /> En plataformas basadas en IA-64, el **DumpStack** comando imita el depurador **K** comando. Los parámetros `top` y `bottom` se omiten en las plataformas basadas en IA-64.|  
|**DumpSig** \<*dirección de la firma*> *dirección del módulo*>|Muestra información sobre una estructura `Sig` en la dirección especificada.|  
|**DumpSigElem** \<*dirección de la firma*> *dirección del módulo*>|Muestra un único elemento de un objeto de firma. En la mayoría de los casos, debe usar **DumpSig** para examinar los objetos de firma individuales. Sin embargo, si una firma se ha dañado de alguna manera, puede usar **DumpSigElem** para leer las partes válidas.|  
|**DumpStackObjects** [**-verify**] [`top` *stack* [`bottom` *stack*]]<br /><br /> O bien<br /><br /> **DSO** [**-verify**] [`top` *stack* [`bottom` *stack*]]|Muestra todos los objetos administrados que se han encontrado dentro de los límites de la pila actual.<br /><br /> El **-comprobar** opción valida cada no estático `CLASS` campo de un campo de objeto.<br /><br /> Utilice la **DumpStackObject** comandos con comandos de seguimiento de pila como el **K** comando y la **CLRStack** comando para determinar los valores de las variables locales y parámetros.|  
|**DumpVC** \<*dirección de MethodTable*> *dirección*>|Muestra información sobre los campos de una clase de valor en la dirección especificada.<br /><br /> El **MethodTable** parámetro permite la **DumpVC** comando interprete los campos correctamente. Las clases de valor no tienen una tabla de métodos como primer campo.|  
|**EEHeap** [**-gc**] [**-loader**]|Muestra información sobre la memoria de proceso que usan las estructuras de datos internas de Common Language Runtime.<br /><br /> El **-gc** y **-cargador** opciones limitan el resultado de este comando a las estructuras de datos del recolector de elementos no utilizados o del cargador.<br /><br /> La información del recolector de elementos no utilizados muestra los intervalos de cada segmento del montón administrado.  Si el puntero se encuentra dentro de un intervalo de segmento proporcionado por **-gc**, el puntero es un puntero de objeto.|  
|**EEStack** [**-short**] [**-EE**]|Se ejecuta el **DumpStack** comando en todos los subprocesos del proceso.<br /><br /> El **- EE** opción se pasa directamente a la **DumpStack** comando. El **-breve** parámetro limita la salida a los siguientes tipos de subprocesos:<br /><br /> Subprocesos que han tomado un bloqueo.<br /><br /> Subprocesos que se han detenido para permitir la recolección de elementos no utilizados.<br /><br /> Subprocesos que están actualmente en el código administrado.|  
|**EEVersion**|Muestra la versión de Common Language Runtime.|  
|**EHInfo** [*dirección de MethodDesc*>] [*código dirección*>]|Muestra los bloques de control de excepciones de un método especificado.  Este comando muestra los desplazamientos y las direcciones de código para el bloque de cláusulas (el bloque `try`) y el bloque del controlador (el bloque `catch`).|  
|**PREGUNTAS MÁS FRECUENTES**|Muestra las preguntas más frecuentes.|  
|**FinalizeQueue** [**-detalle**] | [**-allReady**] [**-short**]|Muestra todos los objetos registrados para su finalización.<br /><br /> El **-detalle** opción muestra información adicional sobre los `SyncBlocks` que necesitan limpieza y los `RuntimeCallableWrappers` (RCW) que espera de limpieza. Al ejecutarse, el subproceso del finalizador almacena en la memoria caché y limpia ambas estructuras de datos.<br /><br /> La opción `-allReady` muestra todos los objetos que están listos para la finalización, sin tener en cuenta si la recolección de elementos no utilizados los ha marcado ya como tales, o si los marcará la siguiente recolección de elementos no utilizados. Los objetos que están en la lista "listos para la finalización" son objetos susceptibles de finalización que ya no tienen raíz. Esta opción puede consumir muchos recursos porque comprueba si todos los objetos de las colas susceptibles de finalización siguen teniendo raíz.<br /><br /> La opción `-short` limita la salida a la dirección de cada objeto. Si se utiliza junto con **- ya**, enumera todos los objetos que tienen un finalizador que ya no tienen raíz. Si se usa de manera independiente, enumera todos los objetos que están en las colas "susceptibles de finalización" y "listos para la finalización".|  
|**FindAppDomain** \<*dirección del objeto*>|Determina el dominio de aplicación de un objeto en la dirección especificada.|  
|**FindRoots** **-gen** \<*N*> | **-gen any** |* dirección del objeto*>|Hace que el depurador interrumpa el código que se está depurando en la recolección siguiente de la generación especificada. El efecto se restablece tan pronto como se produce la interrupción. Para interrumpir la recolección siguiente, vuelva a emitir el comando. El * <object></object> \> * forma de este comando se usa después de la interrupción provocada por la **-gen** o **-gen. cualquiera** se ha producido. En ese momento, el depurador está en el estado correcto para **FindRoots** identifique las raíces para los objetos del actual generaciones inutilizadas.|  
|**GCHandles** [**perdomain -**]|Muestra estadísticas acerca de los identificadores del recolector de elementos no utilizados existentes en el proceso.<br /><br /> El **perdomain -** opción organiza las estadísticas por dominio de aplicación.<br /><br /> Utilice la **GCHandles** comando para encontrar pérdidas de memoria producidas por pérdidas de identificadores del recolector de elementos no utilizados. Una pérdida de memoria se produce, por ejemplo, cuando el código conserva una matriz grande porque un identificador seguro del recolector de elementos no utilizados todavía señala a dicha matriz y el identificador se descarta sin liberarla.|  
|**GCHandleLeaks**|Busca en la memoria cualquier referencia a identificadores seguros y anclados del recolector de elementos no utilizados existentes en el proceso y muestra los resultados. Si se encuentra un identificador, el **GCHandleLeaks** comando muestra la dirección de la referencia. Si no se encuentra ningún identificador en memoria, este comando muestra una notificación.|  
|**GCInfo** \<*dirección de MethodDesc*>\<*código dirección*>|Muestra datos que indican en qué momento los registros o las ubicaciones de la pila contienen objetos administrados. Si se produce una recolección de elementos no utilizados, el recolector debe conocer las ubicaciones de las referencias a los objetos para poder actualizarlas con los nuevos valores de puntero de objeto.|  
|**GCRoot** [**- nostacks**] *dirección del objeto*>|Muestra información acerca de las referencias (o raíces) a un objeto en la dirección especificada.<br /><br /> El **GCRoot** comando examina todo el montón administrado y la tabla de identificadores dentro de otros objetos y administra en la pila. Después, se buscan punteros a objetos en cada pila y en la cola del finalizador.<br /><br /> Este comando no determina si una raíz de la pila es válida o se ha descartado. Utilice la **CLRStack** y **U** comandos para desensamblar el marco al que pertenece el valor de argumento o local para determinar si la raíz de la pila todavía está en uso.<br /><br /> El **nostacks -** opción restringe la búsqueda a objetos accesibles y de identificadores del recolector de elementos no utilizados.|  
|**GCWhere**  *<object></object>\>*|Muestra la ubicación y el tamaño en el montón de recolección de elementos no utilizados del argumento que se ha pasado. Cuando el argumento permanece en el montón administrado, pero no es una dirección de objeto válida, el tamaño se muestra como 0 (cero).|  
|**help** [*command*>] [`faq`]|Cuando no se especifica ningún parámetro, muestra todos los comandos disponibles, o bien muestra ayuda detallada acerca del comando especificado.<br /><br /> El parámetro `faq` muestra respuestas a las preguntas más frecuentes.|  
|**HeapStat** [**- inclUnrooted** | **-iu**]|Muestra los tamaños de generación de cada montón y el espacio total disponible en cada generación de cada montón. Si-**inclUnrooted** se especifica la opción, el informe incluye información sobre los objetos administrados en el montón de elementos no utilizados que ya no se basa.|  
|**HistClear**|Libera los recursos usados por la familia de comandos `Hist`.<br /><br /> Generalmente, no tiene que llamar explícitamente a `HistClear`, puesto que cada comando `HistInit` limpia los recursos anteriores.|  
|**HistInit**|Inicializa las estructuras SOS del registro de esfuerzo guardado en el código que se está depurando.|  
|**HistObj***<obj_address>*</obj_address>|Examina todos los registros de reubicación del registro de esfuerzo y muestra la cadena de reubicaciones de recolección de elementos no utilizados que pueden haber conducido a la dirección que se ha pasado como argumento.|  
|**HistObjFind**  *<obj_address>*</obj_address>|Muestra todas las entradas de registro que hacen referencia a un objeto en la dirección especificada.|  
|**HistRoot***<>\>*|Muestra información relacionada con las promociones y las reubicaciones de la raíz especificada.<br /><br /> El valor de raíz se puede usar para realizar el seguimiento del movimiento de un objeto a través de las recolecciones de elementos no utilizados.|  
|**IP2MD** \<*código dirección*>|Muestra la estructura `MethodDesc` en la dirección especificada en el código compilado JIT.|  
|`ListNearObj`(`lno`)*<obj_address>*</obj_address>|Muestra los objetos anteriores y posteriores a la dirección especificada. El comando busca en el montón de recolección de elementos no utilizados la dirección que parece un principio válido de un objeto administrado (basándose en una tabla de métodos válida) y el objeto que sigue a la dirección del argumento.|  
|**MinidumpMode** [**0**] [**1**]|Evita que se ejecuten comandos no seguros al usar un minivolcado.<br /><br /> Pasar **0** para deshabilitar esta característica o **1** para habilitar esta característica. De forma predeterminada, el **MinidumpMode** el valor **0**.<br /><br /> Minivolcados creados con la **/m .dump** comando o **.dump** comando tienen datos limitados específicos de CLR y permiten ejecutar sólo un subconjunto de comandos de SOS correctamente. Algunos comandos pueden producir errores inesperados porque no se hayan asignado, o solo se hayan asignado parcialmente, áreas de memoria necesarias. Esta opción le impide ejecutar comandos no seguros en minivolcados.|  
|**Name2EE** \<*nombre del módulo*> *nombre de tipo o método*><br /><br /> O bien<br /><br /> **Name2EE** \<*module name*>**!** \< *nombre de tipo o método*>|Muestra la estructura `MethodTable` y la estructura `EEClass` para el tipo o método especificado del módulo especificado.<br /><br /> El módulo especificado se debe cargar en el proceso.<br /><br /> Para obtener el nombre del tipo correcto, examine el módulo mediante el [Ildasm.exe (Desensamblador IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md). También puede pasar `*` como parámetro de nombre de módulo para buscar en todos los módulos administrados cargados. El *nombre del módulo* parámetro también puede ser el nombre del depurador para un módulo, como `mscorlib` o `image00400000`.<br /><br /> Este comando es compatible con la sintaxis del depurador de Windows de `module` > `!` < `type`>. El nombre del tipo debe ser completo.|  
|**ObjSize** [*dirección del objeto*>] | [**-aggregate**] [**-stat**]|Muestra el tamaño del objeto especificado. Si no especifica ningún parámetro, el **ObjSize** comando muestra el tamaño de todos los objetos encontrados en subprocesos administrados, muestra todos los identificadores del recolector de elementos no utilizados en el proceso y suma el tamaño de los objetos que señalan esos identificadores. El **ObjSize** comando incluye el tamaño de todos los objetos secundarios y del objeto primario.<br /><br /> El **-agregado** opción puede utilizarse junto con el **-stat** argumento para obtener una vista detallada de los tipos que siguen teniendo raíz. Mediante el uso de **! dumpheap-stat** y **! objsize-aggregate - stat**, puede determinar qué objetos ya no son raíz y diagnosticar diversos problemas de memoria.|  
|**PrintException** [**-anidada**] [**-líneas**] [*dirección de objeto de excepción*>]<br /><br /> O bien<br /><br /> **PE** [**-anidada**] [*dirección de objeto de excepción*>]|Muestra y da formato a los campos de cualquier objeto derivado de la <xref:System.Exception> (clase) en la dirección especificada. Si no especifica una dirección, el **PrintException** comando muestra la última excepción iniciada en el subproceso actual.<br /><br /> El **-anidada** opción muestra detalles acerca de los objetos de excepción anidados.<br /><br /> El **-líneas** opción muestra la información de origen, si está disponible.<br /><br /> Puede usar este comando para dar formato y ver el campo `_stackTrace`, que es una matriz binaria.|  
|**ProcInfo** [**-env**] [**-time**] [**-mem**]|Muestra variables de entorno del proceso, el tiempo de CPU en modo kernel y estadísticas de uso de la memoria.|  
|**RCWCleanupList** \<*RCWCleanupList dirección*>|Muestra la lista de contenedores RCW (runtime callable wrapper) que se encuentran en la dirección especificada a la espera de limpieza.|  
|**SaveModule** \<*dirección Base*> *nombre de archivo*>|Escribe en el archivo especificado una imagen que está cargada en memoria en la dirección especificada.|  
|**SOSFlush**|Vacía una caché de SOS interna.|  
|**StopOnException** [**-derivados**] [**-crear** | **-create2**] *excepción*> *número de registro pseudo*>|Hace que el depurador se detenga si se inicia la excepción especificada y que continúe ejecutándose si se inician otras excepciones.<br /><br /> El **-derivado** opción detecta la excepción especificada y todas las excepciones que se derivan de la excepción especificada.|  
|**SyncBlk** [**-all** | *número de syncblk*>]|Muestra la estructura `SyncBlock` especificada o todas las estructuras `SyncBlock`.  Si no pasa ningún argumento, el **SyncBlk** comando muestra el `SyncBlock` estructura correspondiente a los objetos que pertenecen a un subproceso.<br /><br /> Una estructura `SyncBlock` es un contenedor de información adicional que no es necesario crear para cada objeto. Puede contener datos de interoperabilidad COM, códigos hash e información de bloqueo de operaciones seguras para subprocesos.|  
|**Grupo de subprocesos**|Muestra información acerca del grupo de subprocesos administrados, como el número de solicitudes de trabajo que hay en cola, el número de subprocesos de puerto de finalización y el número de temporizadores.|  
|**Token2EE** \<*nombre del módulo*> *token*>|Convierte el token de metadatos especificado del módulo especificado en una estructura `MethodTable` o `MethodDesc`.<br /><br /> Se puede pasar `*` como parámetro de nombre de módulo para averiguar qué tiene asignado ese token en cada módulo administrado cargado. También se puede pasar el nombre del depurador para un módulo, como `mscorlib` o `image00400000`.|  
|**Threads** [**-live**] [**-special**]|Muestra todos los subprocesos administrados del proceso.<br /><br /> El **subprocesos** comando muestra el depurador identificador abreviado, el identificador de subproceso de common language runtime y el identificador de subproceso del sistema operativo.  Además, el **subprocesos** comando muestra una columna Domain en la que indica el dominio de aplicación en el que se ejecuta un subproceso, una columna APT en la que se muestra el modo de apartamento COM y una columna Exception en la que se muestra la última excepción iniciada en el subproceso.<br /><br /> El **-live** opción muestra los subprocesos asociados a un subproceso activo.<br /><br /> El **-especial** opción muestra todos los subprocesos especiales creados por CLR. Subprocesos especiales son subprocesos de la colección de elementos no utilizados (en recolección simultánea y servidor), subprocesos auxiliares del depurador, subprocesos de finalizador, <xref:System.AppDomain> descarga subprocesos y los subprocesos de temporizador de grupo.|  
|**ThreadState ** *campo de valor de estado***>**|Muestra el estado del subproceso. El `value` parámetro es el valor de la `State` en el **subprocesos** salida del informe.<br /><br /> Ejemplo:<br /><br /> `0:003> !Threads     ThreadCount:      2     UnstartedThread:  0     BackgroundThread: 1     PendingThread:    0     DeadThread:       0     Hosted Runtime:   no                                           PreEmptive   GC Alloc           Lock            ID OSID ThreadOBJ    State     GC       Context       Domain   Count APT Exception        0    1  250 0019b068      a020 Disabled 02349668:02349fe8 0015def0     0 MTA        2    2  944 001a6020      b220 Enabled  00000000:00000000 0015def0     0 MTA (Finalizer)     0:003> !ThreadState b220         Legal to Join         Background         CLR Owns         CoInitialized         In Multi Threaded Apartment`|  
|**TraverseHeap** [**- xml**] *nombre de archivo*>|Escribe información del montón en el archivo especificado, en un formato reconocido por el generador de perfiles CLR. El **- xml** opción causas la **TraverseHeap** comando para dar formato al archivo como XML.<br /><br /> Puede descargar el generador de perfiles de CLR de la [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=67325).|  
|**U** [**-gcinfo**] [**-ehinfo**] [**-n**] *MethodDesc address*> | *Dirección de código*>|Muestra un desensamblado anotado de un método administrado especificado mediante un puntero a la estructura `MethodDesc` para el método o mediante una dirección de código dentro del cuerpo del método. El **U** comando muestra el método completo de principio a fin, con las anotaciones que convierten los tokens de metadatos en nombres.<br /><br /> El **- gcinfo** opción causas la **U** comando para mostrar la `GCInfo` estructura para el método.<br /><br /> El **- ehinfo** opción muestra la información de excepción para el método. También puede obtener esta información con el **EHInfo** comando.<br /><br /> El **- n** opción deshabilita la presentación de nombres de archivo de origen y los números de línea. Si el depurador tiene especificada la opción SYMOPT_LOAD_LINES, SOS mejora los símbolos para cada marco administrado y, si lo hace correctamente, muestra el nombre de archivo de código fuente y el número de línea correspondientes. Puede especificar el **- n** opción para deshabilitar este comportamiento.|  
|**VerifyHeap**|Comprueba el montón del recolector de elementos no utilizados en busca de indicios de daños, y muestra los errores encontrados.<br /><br /> Los daños del montón pueden deberse a invocaciones de plataforma construidas de forma incorrecta.|  
|**VerifyObj** \<*dirección del objeto*>|Comprueba el objeto que se pasa como argumento en busca de indicios de daños.|  
|**VMMap**|Recorre el espacio de direcciones virtuales y muestra el tipo de protección aplicado a cada área.|  
|**VMStat**|Proporciona una vista de resumen del espacio de direcciones virtuales, ordenada según el tipo de protección que se ha aplicado a esa memoria (libre, reservada, confirmada, privada, asignada, imagen). La columna TOTAL muestra el resultado de multiplicar la columna AVERAGE por la columna BLK COUNT.|  
  
## <a name="remarks"></a>Comentarios  
 La extensión de depuración de SOS permite ver información acerca del código que se ejecuta en Common Language Runtime. Por ejemplo, puede usar la extensión de depuración de SOS para mostrar información acerca del montón administrado, buscar daños en el montón, mostrar tipos de datos internos usados por el runtime y ver información acerca de todo el código administrado que se ejecuta en el runtime.  
  
 Para usar la extensión de depuración de SOS en Visual Studio, instale la [Windows Driver Kit (WDK)](http://msdn.microsoft.com/windows/hardware/hh852362). Para obtener información sobre el entorno de depuración integrado en Visual Studio, consulte [entornos de depuración](http://msdn.microsoft.com/library/windows/hardware/hh406268.aspx) en el centro de desarrollo de Windows.  
  
 También puede utilizar la extensión de depuración de SOS cargándola en el depurador WinDbg.exe, que está disponible en la [sitio Web de herramientas de desarrollo y WDK](http://go.microsoft.com/fwlink/?LinkId=103787)y ejecutar comandos de WinDbg.exe.  
  
 Para cargar la extensión de depuración de SOS en el depurador WinDbg.exe, ejecute el siguiente comando en la herramienta:  
  
```  
.loadby sos clr  
```  
  
 WinDbg.exe y Visual Studio usan una versión de SOS.dll que corresponde a la versión de Mscorwks.dll actualmente en uso. En las versiones 1.1 y 2.0 de .NET Framework, SOS.dll se instala en el mismo directorio que Mscorwks.dll. De forma predeterminada, debería utilizar la versión de SOS.dll que coincide con la versión actual de Mscorwks.dll.  
  
 Para usar un archivo de volcado de memoria creado en otro equipo, asegúrese de que el archivo Mscorwks.dll incluido en esa instalación está en su ruta de acceso de símbolos y cargue la versión correspondiente de SOS.dll.  
  
 Para cargar una versión concreta de SOS.dll, escriba el comando siguiente en el Depurador de Windows:  
  
```  
.load <full path to sos.dll>  
```  
  
## <a name="examples"></a>Ejemplos  
 El comando siguiente muestra el contenido de una matriz en la dirección `00ad28d0`.  La presentación empieza en el segundo elemento e incluye cinco elementos.  
  
```  
!dumparray -start 2 -length 5 -detail 00ad28d0   
```  
  
 El comando siguiente muestra el contenido de un ensamblado en la dirección `1ca248`.  
  
```  
!dumpassembly 1ca248  
```  
  
 El comando siguiente muestra información acerca del montón del recolector de elementos no utilizados.  
  
```  
!dumpheap  
```  
  
 El comando siguiente escribe el contenido del registro de esfuerzo en memoria en un archivo (predeterminado) denominado StressLog.txt en el directorio actual.  
  
```  
!DumpLog  
```  
  
 El comando siguiente muestra la estructura `MethodDesc` en la dirección `902f40`.  
  
```  
!dumpmd 902f40  
```  
  
 El comando siguiente muestra información acerca de un módulo en la dirección `1caa50`.  
  
```  
!dumpmodule 1caa50  
```  
  
 El comando siguiente muestra información acerca de un objeto en la dirección `a79d40`.  
  
```  
!DumpObj a79d40  
```  
  
 El comando siguiente muestra los campos de una clase de valor en la dirección `00a79d9c` usando la tabla de métodos en la dirección `0090320c`.  
  
```  
!DumpVC 0090320c 00a79d9c  
```  
  
 El comando siguiente muestra la memoria de proceso usada por el recolector de elementos no utilizados.  
  
```  
!eeheap -gc  
```  
  
 El comando siguiente muestra todos los objetos programados para su finalización.  
  
```  
!finalizequeue  
```  
  
 El comando siguiente determina el dominio de aplicación de un objeto en la dirección `00a79d98`.  
  
```  
!findappdomain 00a79d98  
```  
  
 El comando siguiente muestra todos los identificadores del recolector de elementos no utilizados del proceso actual.  
  
```  
!gcinfo 5b68dbb8   
```  
  
 El comando siguiente muestra las estructuras `MethodTable` y `EEClass` para el método `Main` de la clase `MainClass` del módulo `unittest.exe`.  
  
```  
!name2ee unittest.exe MainClass.Main  
```  
  
 El comando siguiente muestra información acerca del token de metadatos en la dirección `02000003` del módulo `unittest.exe`.  
  
```  
!token2ee unittest.exe 02000003  
```  
  
## <a name="see-also"></a>Vea también  
 [Herramientas](../../../docs/framework/tools/index.md)   
 [Símbolo del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)