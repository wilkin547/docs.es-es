---
title: Uso y depuración de la descargabilidad de ensamblado en .NET Core
description: Obtenga información sobre cómo usar AssemblyLoadContext recopilable para cargar y descargar ensamblados administrados y cómo depurar los problemas que impiden que la descarga se realice correctamente.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 267c2209556b66ab3541c9c79c99d7eceb2024da
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159746"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Uso y depuración de la descargabilidad de ensamblado en .NET Core

A partir de .NET Core 3.0, se admite la capacidad de cargar y posteriormente descargar un conjunto de ensamblados. Para este fin, en .NET Framework se usaban dominios de aplicación personalizados, pero .NET Core solo admite un dominio de aplicación predeterminado único.

.NET Core 3.0 y versiones posteriores admiten la descargabilidad a través de <xref:System.Runtime.Loader.AssemblyLoadContext>. Puede cargar un conjunto de ensamblados en un `AssemblyLoadContext` recopilable, ejecutar métodos en ellos o simplemente inspeccionarlos mediante reflexión y, por último, descargar el `AssemblyLoadContext`. Esa acción descarga los ensamblados cargados en el `AssemblyLoadContext`.

Cabe destacar una diferencia entre la descarga mediante `AssemblyLoadContext` y mediante AppDomains. Con AppDomains, se fuerza la descarga. En el momento de la descarga, se anulan todos los subprocesos que se ejecutan en la instancia de AppDomain de destino, se destruyen los objetos COM administrados creados en la AppDomain de destino, etc. Con `AssemblyLoadContext`, la descarga es "cooperativa". La llamada al método <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType> simplemente inicia la descarga. La descarga finaliza una vez que:

- Ningún subproceso tiene métodos de los ensamblados cargados en el `AssemblyLoadContext` en sus pilas de llamadas.
- Ninguno de los elementos siguientes hace referencia a los tipos de los ensamblados cargados en el `AssemblyLoadContext`, a las instancias de esos tipos ni a los ensamblados mismos:
  - Referencias fuera del `AssemblyLoadContext`, excepto las referencias parciales (<xref:System.WeakReference> o <xref:System.WeakReference%601>).
  - Un recolector de elementos no utilizados (GC) potente controla ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) o [GCHandleType.Pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) desde dentro y fuera de `AssemblyLoadContext`.

## <a name="use-collectible-assemblyloadcontext"></a>Uso de un AssemblyLoadContext recopilable

En esta sección se incluye un tutorial detallado paso a paso que muestra una manera sencilla de cargar una aplicación de .NET Core en un `AssemblyLoadContext` recopilable, ejecutar su punto de entrada y, luego, descargarlo. Puede encontrar un ejemplo completo en [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).

### <a name="create-a-collectible-assemblyloadcontext"></a>Creación de un AssemblyLoadContext recopilable

Debe derivar la clase del <xref:System.Runtime.Loader.AssemblyLoadContext> y sobrecargar su método <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>. Ese método resuelve las referencias a todos los ensamblados que son dependencias de los ensamblados cargados en ese `AssemblyLoadContext`.

El código siguiente es un ejemplo del `AssemblyLoadContext` personalizado más sencillo:

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

Como puede ver, el método `Load` devuelve `null`. Esto significa que todos los ensamblados de dependencias se cargan en el contexto predeterminado y el contexto nuevo solo incluye los ensamblados que se cargaron explícitamente en él.

Si quiere cargar algunas o todas las dependencias también en el `AssemblyLoadContext`, puede usar `AssemblyDependencyResolver` en el método `Load`. `AssemblyDependencyResolver` resuelve los nombres de ensamblado en rutas de acceso absoluto a archivos de ensamblado. El solucionador utiliza el archivo *.deps.json* y los archivos de ensamblado en el directorio del ensamblado principal que se cargó en el contexto.

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a>Uso de un AssemblyLoadContext recopilable personalizado

En esta sección se presupone que se usa la versión más sencilla del `TestAssemblyLoadContext`.

Puede crear una instancia del `AssemblyLoadContext` personalizado y cargar en él un ensamblado como se indica a continuación:

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

Para cada uno de los ensamblados a los que hace referencia el ensamblado cargado, se llama al método `TestAssemblyLoadContext.Load` para que el `TestAssemblyLoadContext` pueda decidir desde dónde obtener el ensamblado. En nuestro caso, devuelve `null` para indicar que se debe cargar en el contexto predeterminado desde las ubicaciones que el runtime usa para cargar los ensamblados de manera predeterminada.

Ahora que se cargó un ensamblado, puede ejecutar un método desde él. Ejecute el método `Main`:

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

Una vez que el método `Main` devuelve algún resultado, puede iniciar la descarga ya sea llamando al método `Unload` en el `AssemblyLoadContext` personalizado o deshaciéndose de la referencia que hace al `AssemblyLoadContext`:

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

Esto es suficiente para descargar el ensamblado de prueba. Para que las referencias de ranura de pila (ya sean variables locales reales o introducidas por JIT) no puedan mantener activos los objetos `TestAssemblyLoadContext`, `Assembly` y `MethodInfo` (el `Assembly.EntryPoint`), pongamos todos los elementos en un método no insertable independiente. Eso podría mantener activo al `TestAssemblyLoadContext` e impedir la descarga.

Además, devuelva una referencia parcial al `AssemblyLoadContext` para que pueda usarlo más adelante para detectar la finalización de la descarga.

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

Ahora puede ejecutar esta función para cargar, ejecutar y descargar el ensamblado.

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

Sin embargo, la descarga no se completa de inmediato. Como se mencionó anteriormente, se basa en el recolector de elementos no utilizados para recopilar todos los objetos desde el ensamblado de prueba. En muchos casos, no es necesario esperar a que se complete la descarga. Sin embargo, hay casos en los que resulta útil saber que la descarga se completó. Por ejemplo, es posible que quiera eliminar el archivo de ensamblado que se cargó en el `AssemblyLoadContext` personalizado del disco. En tal caso, se puede usar el fragmento de código siguiente. Desencadena una recolección de elementos no utilizados y espera a los finalizadores pendientes en un bucle hasta que la referencia parcial al `AssemblyLoadContext` personalizado se establece en `null`, lo que indica que se recopiló el objeto de destino. En la mayoría de los casos, solo se requiere un paso a través del bucle. Sin embargo, en casos más complejos en los que los objetos creados por el código que se ejecutan en el `AssemblyLoadContext` tienen finalizadores, es posible que se necesiten más pasos.

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a>El evento de descarga

En algunos casos, puede ser necesario que el código cargado en un `AssemblyLoadContext` personalizado realice una limpieza cuando se inicie la descarga. Por ejemplo, es posible que tenga que detener subprocesos o limpiar los identificadores de los recolectores de elementos no utilizados seguros, etc. En esos casos, se puede usar el evento `Unloading`. Es posible enlazar a este evento un controlador que realice la limpieza necesaria.

### <a name="troubleshoot-unloadability-issues"></a>Solución de problemas de descargabilidad

Debido a la naturaleza cooperativa de la descarga, resulta fácil olvidarse de que las referencias pueden mantener activo el contenido de un `AssemblyLoadContext` recopilable, lo que impide la descarga. A continuación se muestra un resumen de las entidades (algunas de las cuales no son obvias) que pueden contener las referencias:

- Referencias habituales contenidas desde fuera del `AssemblyLoadContext` recopilable, que se almacenan en una ranura de pila o en un registro de procesador (variables locales de método, ya sea creadas explícitamente por el código de usuario o de manera implícita por el compilador Just-In-Time), una variable estática o un identificador de GC seguro/de anclaje, y que apuntan de manera transitiva a:
  - Un ensamblado cargado en el `AssemblyLoadContext` recopilable.
  - Un tipo de dicho ensamblado.
  - Una instancia de un tipo de dicho ensamblado.
- Subprocesos que ejecutan código de un ensamblado cargado en el `AssemblyLoadContext` recopilable.
- Instancias de tipos de `AssemblyLoadContext` no recopilables personalizados que se crearon dentro del `AssemblyLoadContext` recopilable.
- Instancias de <xref:System.Threading.RegisteredWaitHandle> pendientes con devoluciones de llamada establecidas en métodos en el `AssemblyLoadContext` personalizado.

> [!TIP]
> Se pueden producir referencias a objetos que se almacenan en ranuras de pilas o en los registros de procesador y que podrían impedir la descarga de un `AssemblyLoadContext` en las siguientes situaciones:
>
> - Cuando los resultados de una llamada de función se pasan directamente a otra función incluso si no hay ninguna variable local creada por el usuario.
> - Cuando el compilador JIT mantiene una referencia a un objeto que estaba disponible en algún momento de un método.

## <a name="debug-unloading-issues"></a>Depuración de problemas de descarga

Depurar los problemas con la descarga puede ser un proceso tedioso. Puede haber ocasiones en las que no sepa qué es lo que mantiene activo un `AssemblyLoadContext`, pero se produce un error en la descarga. La mejor herramienta para ayudarlo con eso es WinDbg (LLDB en Unix) con el complemento SOS. Debe buscar qué mantiene activo a un `LoaderAllocator` perteneciente al `AssemblyLoadContext` específico. El complemento SOS permite examinar los objetos del montón de recolección de elementos no utilizados, sus jerarquías y raíces.

Para cargar el complemento en el depurador, escriba el comando siguiente en la línea de comandos del depurador:

En WinDbg (parece que WinDbg lo hace de manera automática al irrumpir en la aplicación de .NET Core):

```console
.loadby sos coreclr
```

En LLDB:

```console
plugin load /path/to/libsosplugin.so
```

Vamos a depurar un programa de ejemplo que tiene problemas con la descarga. El código de origen se incluye a continuación. Cuando lo ejecuta en WinDbg, el programa irrumpe en el depurador justo después de intentar comprobar que la descarga se realizó correctamente. Luego, puede empezar a buscar a los culpables.

> [!TIP]
> Si realiza la depuración con LLDB en Unix, los comandos de SOS de los ejemplos siguientes no tienen `!` delante de ellos.

```console
!dumpheap -type LoaderAllocator
```

Este comando vuelca todos los objetos con un nombre de tipo que contiene `LoaderAllocator` que se encuentran en el montón de GC. A continuación se muestra un ejemplo:

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48
000002b78000ceb0 00007ffadc93a218       24

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

En la parte "Statistics:" (Estadísticas) que aparece abajo, compruebe el `MT` (`MethodTable`) que pertenece al `System.Reflection.LoaderAllocator`, que es el objeto que nos interesa. Luego, en la lista que aparece al principio, busque la entrada con el `MT` que coincide con ese y obtenga la dirección del objeto mismo. En nuestro caso, se trata de "000002b78000ce40".

Ahora que sabemos la dirección del objeto `LoaderAllocator`, podemos usar otro comando para encontrar sus raíces de GC:

```console
!gcroot -all 0x000002b78000ce40
```

Este comando vuelca la cadena de referencias de objeto que llevan a la instancia `LoaderAllocator`. La lista empieza por la raíz, que es la entidad que mantiene activo el `LoaderAllocator` y, por lo tanto, es la parte fundamental del problema. La raíz puede ser una ranura de pila, un registro de procesador, un identificador de GC o una variable estática.

Este es un ejemplo de la salida del comando `gcroot`:

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

El paso siguiente es averiguar dónde se encuentra la raíz para poder corregirla. El caso más sencillo es cuando la raíz es una ranura de pila o un registro de procesador. En ese caso, `gcroot` muestra el nombre de la función cuyo marco contiene la raíz y el subproceso que ejecuta esa función. El caso difícil es cuando la raíz es una variable estática o un identificador de GC.

En el ejemplo anterior, la primera raíz es una variable local de tipo `System.Reflection.RuntimeMethodInfo` almacenada en el marco de la función `example.Program.Main(System.String[])` en la dirección `rbp-20` (`rbp` es el registro de procesador `rbp` y -20 es un desplazamiento hexadecimal a partir de ese registro).

La segunda raíz es un `GCHandle` normal (seguro) que contiene una referencia a una instancia de la clase `test.Test`.

La tercera raíz es un `GCHandle` anclado. Esta es en realidad una variable estática, pero lamentablemente, no es posible saberlo a ciencia cierta. Las variables estáticas para tipos de referencia se almacenan en una matriz de objetos administrada en estructuras internas de runtime.

Otro caso que puede impedir la descarga de un `AssemblyLoadContext` es cuando un subproceso tiene un marco de un método proveniente de un ensamblado cargado en el `AssemblyLoadContext` en su pila. Puede comprobarlo si vuelca las pilas de llamadas administradas de todos los subprocesos:

```console
~*e !clrstack
```

El comando siguiente "aplicar a todos los subprocesos el comando `!clrstack`". Luego se muestra la salida de ese comando para el ejemplo. Lamentablemente, LLDB en Unix no tiene forma de aplicar un comando a todos los subprocesos, por lo que tendrá que cambiar de manera manual los subprocesos y repetir el comando `clrstack`. Omita todos los subprocesos en los que el depurador indique "Unable to walk the managed stack" (No se puede recorrer la pila administrada).

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998]
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28]
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0]
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568]
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0]

```

Como puede ver, el último subproceso tiene `test.Program.ThreadProc()`. Esta es una función del ensamblado cargado en el `AssemblyLoadContext`, por lo que mantiene activo al `AssemblyLoadContext`.

## <a name="example-source-with-unloadability-issues"></a>Origen de ejemplo con problemas de descargabilidad

El código siguiente se usa en el ejemplo de depuración anterior.

### <a name="main-testing-program"></a>Programa de prueba principal

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a>Programa cargado en TestAssemblyLoadContext

El código siguiente presenta el *test.dll* que se pasa al método `ExecuteAndUnload` en el programa de prueba principal.

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
