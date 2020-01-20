---
title: MDbg.exe (depurador de línea de comandos .NET Framework)
ms.date: 03/30/2017
helpviewer_keywords:
- command-line debugger [.NET Framework]
- MDbg.exe
ms.assetid: 28a3f509-07e2-4dbe-81df-874c5e969cc4
ms.openlocfilehash: 58502626fed6c9cee52acb673ae34f6024f78b9b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715763"
---
# <a name="mdbgexe-net-framework-command-line-debugger"></a>MDbg.exe (depurador de línea de comandos .NET Framework)
El Depurador de la línea de comandos de .NET Framework ayuda a los proveedores de herramientas y a los programadores de aplicaciones a encontrar y a corregir los errores que pueden producirse en programas orientados al Common Language Runtime de .NET Framework. Esta herramienta utiliza el runtime de la API de depuración para proporcionar servicios de depuración. Puede utilizar MDbg.exe para depurar solo código administrado; no se admite la depuración de código no administrado.  
  
Esta herramienta está disponible mediante NuGet. Para obtener información de instalación, vea [MDbg 0.1.0](https://www.nuget.org/packages/MDbg/0.1.0). Para ejecutar la herramienta, use la Consola del Administrador de paquetes. Para más información sobre cómo usar la Consola del Administrador de paquetes, vea el artículo [Package Manager Console](/nuget/tools/package-manager-console) (Consola del Administrador de paquetes).
  
A petición del Administrador de paquetes, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
MDbg [ProgramName[arguments]] [options]  
```  
  
## <a name="commands"></a>Comandos  
 En el depurador (según lo indicado en el símbolo del sistema **mdbg>** ), escriba uno de los comandos descritos en la sección siguiente:  
  
 **command** [*arguments*]  
  
 Los comandos de MDbg.exe distinguen mayúsculas de minúsculas.  
  
|Comando|Descripción|  
|-------------|-----------------|  
|**ap**[**rocess**] [*number*]|Cambia a otro proceso depurado o imprime los procesos disponibles. Los números no son identificadores de proceso reales (PID), sino una lista indizada por 0.|  
|**a**[**ttach**] [*pid*]|Asocia a un proceso o imprime los procesos disponibles.|  
|**b**[**reak**] [*ClassName.Method* &#124; *FileName:LineNo*]|Establece un punto de interrupción en el método especificado. Los módulos se examinan secuencialmente.<br /><br /> -   **break** *NombreArchivo:NúmLínea* establece un punto de interrupción en una ubicación del origen.<br />-   **break** *~número* establece un punto de interrupción en un símbolo mostrado recientemente con el comando **x**.<br />-   **break** *módulo!NombreClase.Método+DesplazamientoIl* establece un punto de interrupción en la ubicación completa.|  
|**block**[**ingObjects**]|Muestra bloqueos del monitor, que son subprocesos de bloqueo.|  
|**ca**[**tch**] [*exceptionType*]|Hace que el depurador se interrumpa en todas las excepciones, no solo en las excepciones no controladas.|  
|**cl**[**earException**]|Marca la excepción actual como controlada para que la ejecución pueda continuar. Si la causa de la excepción no se ha controlado, la excepción se puede volver a iniciar rápidamente.|  
|**conf**[**ig**] [*option value*]|Muestra todas las opciones que se pueden configurar y cómo se invocan las opciones sin ningún valor opcional. Si se especifica la opción, se establece `value` como la opción actual. Actualmente, están disponibles las siguientes opciones:<br /><br /> -   `extpath` establece la ruta de acceso para buscar extensiones cuando se usa el comando `load`.<br />-   `extpath+` agrega una ruta de acceso para cargar extensiones.|  
|**del**[**ete**]|Elimina un punto de interrupción.|  
|**de**[**tach**]|Desasocia de un proceso depurado.|  
|**d**[**own**] [*frames*]|Mueve el marco de pila activo hacia abajo.|  
|**echo**|Repite un mensaje en la consola.|  
|**enableNotif**[**ication**] *typeName* 0&#124;1|Habilita (1) o deshabilita (0) notificaciones personalizadas para el tipo especificado.|  
|**ex**[**it**] [*exitcode*]|Sale del shell de MDbg.exe y especifica opcionalmente el código de salida de proceso.|  
|**fo**[**reach**] [*OtherCommand*]|Ejecuta un comando en todos los subprocesos. *otroComando* es un comando válido que funciona en un subproceso; **foreach** *otroComando* ejecuta el mismo comando en todos los subprocesos.|  
|**f**[**unceval**] [`-ad` *Núm*] *nombreFunción* [*argumentos ...* ]|Realiza una evaluación de función en el subproceso activo actual donde la función que se va a evaluar es *functionName*. El nombre de la función debe estar completo, incluidos los espacios de nombres.<br /><br /> La opción `-ad` especifica el dominio de aplicación que se utiliza para resolver la función. Si no se especifica la opción `-ad`, el dominio de aplicación para la resolución establece su valor predeterminado en el dominio de aplicación donde esté ubicado el subproceso utilizado para la evaluación de la función.<br /><br /> Si la función que se evalúa no es estática, el primer parámetro pasado debería ser un puntero `this`. En todos los dominios de aplicación se buscan argumentos para la evaluación de función.<br /><br /> Para solicitar un valor de un dominio de aplicación, anteponga la variable con el módulo y el nombre de dominio de aplicación; por ejemplo, `funceval -ad 0 System.Object.ToString hello.exe#0!MyClass.g_rootRef`. Este comando evalúa la función `System.Object.ToString` en el dominio de aplicación `0`. Dado que el método `ToString` es una función de instancia, el primer parámetro debe ser un puntero `this`.|  
|**g**[**o**]|Hace que el programa continúe hasta que encuentre un punto de interrupción, se cierre o se produzca un evento (por ejemplo, una excepción no controlada) que haga que el programa se detenga.|  
|**h**[**elp**] [*command*]<br /><br /> o bien<br /><br /> **?** [*command*]|Muestra una descripción de todos los comandos o una descripción detallada de un comando específico.|  
|**ig**[**nore**] [*event*]|Hace que el depurador solo se detenga en excepciones no controladas.|  
|**int**[**ercept**] *FrameNumber*|Revierte el depurador hasta un número de marco especificado.<br /><br /> Si el depurador encuentra una excepción, utilice este comando para revertir el depurador hasta el número de marco especificado. También puede cambiar el estado del programa mediante el comando **set** y seguir usando el comando **go**.|  
|**k**[**ill**]|Detiene el proceso activo.|  
|**l**[**ist**] [*modules* &#124; *appdomains* &#124; *assemblies*]|Muestra los módulos, dominios de aplicación o ensamblados cargados.|  
|**lo**[**ad**] *assemblyName*|Carga una extensión de la manera siguiente: se carga el ensamblado especificado y se intenta ejecutar el método estático `LoadExtension` del tipo `Microsoft.Tools.Mdbg.Extension.Extension`.|  
|**log** [*eventType*]|Permite establecer o mostrar los eventos que se van a registrar.|  
|**mo**[**de**] [*option on/off*]|Establece las distintas opciones de depurador. Utilice `mode` sin opciones para obtener una lista de los modos de depuración y su configuración actual.|  
|**mon**[**itorInfo**] *monitorReference*|Muestra la información de bloqueo del monitor de objetos.|  
|**newo**[**bj**] *typeName* [*arguments...* ]|Crea un objeto de tipo *typeName*.|  
|**n**[**ext**]|Ejecuta el código y se desplaza a la línea siguiente (incluso cuando la línea siguiente incluye muchas llamadas a funciones).|  
|**Opendump** *rutaArchivoVolcado*|Abre el archivo de volcado de memoria especificado para la depuración.|  
|**o**[**ut**]|Se desplaza al final de la función actual.|  
|**pa**[**th**] [*pathName*]|Busca los archivos de código fuente en la ruta de acceso especificada si la ubicación no está disponible en los archivos binarios.|  
|**p**[**rint**] [*var*] &#124; [`-d`]|Imprime todas las variables del ámbito (**print**), imprime la variable especificada (**print** *var*) o imprime las variables del depurador (**print**`-d`).|  
|**printe**[**xception**] [ *-r*]|Imprime la última excepción del subproceso actual. Use la opción `–r` (recursiva) para atravesar la propiedad `InnerException` del objeto de excepción a fin de obtener información sobre la cadena completa de excepciones.|  
|**pro**[**cessenum**]|Muestra los procesos activos.|  
|**q**[**uit**] [*exitcode*]|Sale del shell de MDbg.exe y, opcionalmente, especifica el código de salida del proceso.|  
|**re**[**sume**] [`*` &#124; [`~`]*threadNumber*]|Reanuda el subproceso actual o el subproceso especificado por el parámetro *threadNumber*.<br /><br /> Si el parámetro *threadNumber* se especifica como `*` o si el número de subproceso comienza con `~`, el comando se aplica a todos los subprocesos excepto al especificado por *threadNumber*.<br /><br /> La reanudación de un subproceso no suspendido no tiene ningún efecto.|  
|**r**[**un**] [`-d`(`ebug`) &#124; -`o`(`ptimize`) &#124;`-enc`] [[*path_to_exe*] [*args_to_exe*]]|Detiene el proceso actual (si existe) e inicia uno nuevo. Si no se pasa ningún argumento ejecutable, este comando ejecuta el programa que se ejecutó previamente con el comando `run`. Si se proporciona un argumento ejecutable, se ejecuta el programa especificado con los argumentos proporcionados de manera opcional.<br /><br /> Si se omiten los eventos de carga de clases, de carga de módulos y de inicio de subprocesos (son la opción predeterminada), el programa se detiene en la primera instrucción ejecutable del subproceso principal.<br /><br /> Puede forzar el depurador para que realice una compilación Just-In-Time (JIT) del código utilizando una de las tres marcas siguientes:<br /><br /> -   `-d` *(* `ebug` *)* deshabilita las optimizaciones. Este es el valor predeterminado de MDbg.exe.<br />-   `-o` *(* `ptimize` *)* fuerza el código para que se ejecute más como lo hace fuera del depurador, aunque también dificulta la experiencia de depuración. Este es el valor predeterminado para usarlo fuera del depurador.<br />-   `-enc` habilita la característica Editar y continuar, pero afecta al rendimiento.|  
|**Set** *variable*=*valor*|Cambia el valor de cualquier variable en el ámbito.<br /><br /> También puede crear sus propias variables de depurador y asignarles valores de referencia desde la aplicación. Estos valores actúan como identificadores del valor original, e incluso el valor original está fuera de ámbito. Todas las variables de depurador deben comenzar con `$` (por ejemplo, `$var`). Borre estos identificadores y déjelos en blanco mediante el comando siguiente:<br /><br /> `set $var=`|  
|**Setip** [`-il`] *number*|Establece el puntero de instrucción (IP) actual del archivo en la posición especificada. Si se especifica la opción `-il`, el número representa un desplazamiento del Lenguaje intermedio de Microsoft (MSIL) en el método. De lo contrario, el número representa un número de línea de código fuente.|  
|**sh**[**ow**] [*lines*]|Especifica el número de líneas que se van a mostrar.|  
|**s**[**tep**]|Pasa la ejecución a la función siguiente en la línea actual o se desplaza a la línea siguiente si no hay ninguna función que procesar paso a paso.|  
|**su**[**spend**] [\* &#124; [~]*threadNumber*]|Suspende el subproceso actual o el subproceso especificado por el parámetro *threadNumber*.  Si *threadNumber* se especifica como `*`, el comando se aplica a todos los subprocesos. Si el número del subproceso comienza con `~`, el comando se aplica a todos los subprocesos excepto al especificado por *threadNumber*. Los subprocesos suspendidos se excluyen de la ejecución cuando el proceso se ejecuta mediante el comando **go** o **step**. Si no hay ningún subproceso no suspendido en el proceso y se emite el comando **go**, el proceso no continuará. En ese caso, presione CTRL-C para interrumpir el proceso.|  
|**sy**[**mbol**] *commandName* [*commandValue*]|Permite especificar uno de los siguientes comandos:<br /><br /> -   `symbol path` [`"value"`]: muestra o establece la ruta de acceso actual a los símbolos.<br />-   `symbol addpath` `"value"`: agrega a la ruta de acceso actual a los símbolos.<br />-   `symbol reload` [`"module"`]: recarga todos los símbolos o los símbolos del módulo especificado.<br />-   `symbol list` [`module`]: muestra los símbolos cargados actualmente para todos los módulos o para el módulo especificado.|  
|**t**[**hread**] [*newThread*] [-*nick nickname*`]`|El comando de subprocesos sin parámetros muestra todos los subprocesos administrados en el proceso actual. Los subprocesos suelen identificarse por sus números de subproceso; sin embargo, si un subproceso tiene asignado un alias, se muestra el alias en su lugar. Puede utilizar el parámetro `-nick` para asignar un alias a un subproceso.<br /><br /> -   **thread** `-nick` *threadName* asigna un alias al subproceso que se está ejecutando actualmente.<br /><br /> Los alias no pueden ser números. Si el subproceso actual ya tiene un alias asignado, el alias anterior se reemplaza con el nuevo. Si el nuevo alias es una cadena vacía (""), el alias del subproceso actual se elimina y no se asigna ninguno nuevo.|  
|**u**[**p**]|Mueve el marco de pila activo hacia arriba.|  
|**uwgc**[**handle**] [*var*] &#124; [*address*]|Imprime la variable en la que un identificador ha realizado el seguimiento. El identificador se puede especificar por nombre o dirección.|  
|**when**|Muestra las instrucciones `when` activas actualmente.<br /><br /> **when** **delete all** &#124; `num` [`num` [`num` …]]: elimina la instrucción `when` especificada por el número, o bien todas las instrucciones `when` si se especifica `all`.<br /><br /> **when** `stopReason` [`specific_condition`] **do**`cmd` [`cmd` [`cmd` …] ]: el parámetro *stopReason* puede tener uno de los siguientes valores:<br /><br /> `StepComplete`, `ProcessExited`, `ThreadCreated`, `BreakpointHit`, `ModuleLoaded`, `ClassLoaded`, `AssemblyLoaded`, `AssemblyUnloaded`, `ControlCTrapped`, `ExceptionThrown`, `UnhandledExceptionThrown`, `AsyncStop`, `AttachComplete`, `UserBreak`, `EvalComplete`, `EvalException`, `RemapOpportunityReached`, `NativeStop`.<br /><br /> *specific_condition* puede ser uno de los siguientes valores:<br /><br /> -   *number*: para `ThreadCreated` y `BreakpointHit`, desencadena la acción solo cuando se detiene a través de un número de identificador de subproceso o de punto de interrupción con el mismo valor.<br />-   [`!`]*name*: para `ModuleLoaded`, `ClassLoaded`, `AssemblyLoaded`, `AssemblyUnloaded`, `ExceptionThrown` y `UnhandledExceptionThrown`, desencadena la acción solo cuando el nombre coincide con el nombre de *stopReason*.<br /><br /> *specific_condition* debe estar vacío para otros valores de *stopReason*.|  
|**w**[**here**] [`-v`] [`-c` *profundidad*] [*idSubproceso*]|Muestra información de depuración sobre los marcos de pila.<br /><br /> - La opción `-v` proporciona información detallada sobre los marcos de pila mostrados.<br />- Al especificar un número para `depth`, se limita el número de marcos que se muestran. Use el comando **all** para mostrar todos los marcos. El valor predeterminado es 100.<br />- Si especifica el parámetro *threadID*, puede controlar los subprocesos que se asocian a la pila. El valor predeterminado es únicamente el subproceso actual. Use el comando **all** para obtener todos los subprocesos.|  
|**x** [`-c`*numSymbols*] [*module*[`!`*pattern*]]|Muestra las funciones que coinciden con `pattern` para un módulo.<br /><br /> Si se especifica *numSymbols*, la salida se limita al número especificado. Si no se especifica `!` (que indica una expresión regular) para *pattern*, se muestran todas las funciones. Si no se proporciona *module*, se muestran todos los módulos cargados. Se pueden usar símbolos ( *~#* ) para establecer puntos de interrupción mediante el comando **break**.|  
  
## <a name="remarks"></a>Comentarios  
 Compile la aplicación que se va a depurar mediante marcas específicas del compilador que hacen que el compilador genere símbolos de depuración. Consulte la documentación del compilador para obtener más información acerca de estas marcas. Puede depurar aplicaciones optimizadas, aunque parte de la información de depuración se perderá. Por ejemplo, muchas variables locales no estarán visibles y las líneas de código fuente serán incorrectas.  
  
 Después de compilar la aplicación, escriba **mdbg** en el símbolo del sistema para iniciar una sesión de depuración, como se muestra en el ejemplo siguiente.  
  
```console  
C:\Program Files\Microsoft Visual Studio 8\VC>mdbg  
MDbg (Managed debugger) v2.0.50727.42 (RTM.050727-4200) started.  
Copyright (C) Microsoft Corporation. All rights reserved.  
  
For information about commands type "help";  
to exit program type "quit".  
mdbg>  
```  
  
 El símbolo del sistema `mdbg>` indica que se encuentra en el depurador.  
  
 Cuando esté en el depurador, use los comandos y argumentos descritos en la sección anterior.  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Símbolos del sistema](developer-command-prompt-for-vs.md)
