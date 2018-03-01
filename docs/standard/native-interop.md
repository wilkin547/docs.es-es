---
title: Interoperabilidad nativa
description: "Obtenga información sobre cómo interactuar con componentes nativos en .NET."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 11a93f4014734130f7c4e33cf215c6d49d2554c5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="native-interoperability"></a>Interoperabilidad nativa

En este documento se profundiza un poco más en las tres formas de obtener "interoperabilidad nativa" disponibles mediante .NET.

Existen varios motivos por los que puede interesarle llamar a código nativo:

*   Los sistemas operativos incluyen un elevado volumen de API que no están presentes en las bibliotecas de clases administradas. Un buen ejemplo de esto sería el acceso al hardware o a funciones de administración del sistema operativo.
*   La comunicación con otros componentes que tienen o pueden generar ABI de estilo C (ABI nativos). Esto incluye, por ejemplo, código Java que se expone a través de [Java Native Interface (JNI)](http://docs.oracle.com/javase/8/docs/technotes/guides/jni/) o cualquier lenguaje administrado que pueda producir un componente nativo.
*   En Windows, la mayor parte del software que se instala, como el conjunto de aplicaciones de Microsoft Office, registra los componentes COM que representan sus programas y permiten a los desarrolladores automatizarlos o usarlos. Esto también requiere interoperabilidad nativa.

Por supuesto, la lista anterior no cubre todas las posibles situaciones y escenarios en los que el desarrollador puede querer o necesitar interactuar con componentes nativos. La biblioteca de clases. NET, por ejemplo, usa la compatibilidad con la interoperabilidad nativa para implementar bastantes de sus API, como la compatibilidad con la consola y su manipulación, el acceso al sistema de archivos, etc. Pero es importante tener en cuenta que existe la opción de hacerlo, en caso de que sea necesario.

> [!NOTE]
> La mayoría de los ejemplos de este documento se presentarán para las tres plataformas compatibles con .NET Core (Windows, Linux y macOS). En cambio, en algunos ejemplos breves e ilustrativos solo se muestra un ejemplo que usa nombres de archivo y extensiones de Windows (es decir, "dll" en el caso de las bibliotecas). Esto no significa que esas características no estén disponibles en Linux o macOS, sino que simplemente se buscaba una mayor comodidad.

## <a name="platform-invoke-pinvoke"></a>Invocación de plataforma (P/Invoke)

P/Invoke es una tecnología que permite acceder a estructuras, devoluciones de llamada y funciones de bibliotecas no administradas desde el código administrado. La mayor parte de la API de P/Invoke se encuentra en dos espacios de nombres: `System` y `System.Runtime.InteropServices`. Mediante estos dos espacios de nombres, puede acceder a los atributos que describen cómo quiere comunicarse con el componente nativo.

Empecemos por el ejemplo más común, es decir, llamar a funciones no administradas en el código administrado. Vamos a mostrar un cuadro de mensaje desde una aplicación de línea de comandos:

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

El ejemplo anterior es bastante sencillo, pero resalta lo que es necesario para invocar las funciones no administradas desde código administrado. Veamos en detalle el ejemplo:

*   En la línea 1 se muestra el uso de la instrucción para `System.Runtime.InteropServices`, que es el espacio de nombres que contiene todos los elementos que necesitamos.
*   En la línea 5 se introduce el atributo `DllImport`. Este atributo es fundamental, ya que le indica al tiempo de ejecución que debe cargar la DLL no administrada. Se trata de la DLL en la que queremos invocar.
*   La línea 6 es la esencia del trabajo de P/Invoke. Define un método administrado que tiene **exactamente la misma firma** que el no administrado. Como puede ver, la declaración tiene una nueva palabra clave (`extern`) que le indica al tiempo de ejecución que esto es un método externo y que, cuando se invoca, el tiempo de ejecución debe buscarlo en el archivo DLL especificado en el atributo `DllImport`.

El resto del ejemplo simplemente invoca el método como si se tratara de cualquier otro método administrado.

El ejemplo es parecido para macOS. Evidentemente, lo que debe cambiar es el nombre de la biblioteca en el atributo `DllImport`, ya que macOS tiene un esquema diferente para la nomenclatura de bibliotecas dinámicas. En el ejemplo siguiente se usa la función `getpid(2)` para obtener el identificador de proceso de la aplicación e imprimirlo en la consola.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

También es similar en Linux. El nombre de la función es el mismo, ya que `getpid(2)` es la llamada del sistema estándar de [POSIX](https://en.wikipedia.org/wiki/POSIX).

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

### <a name="invoking-managed-code-from-unmanaged-code"></a>Invocar código administrado desde código no administrado

Por supuesto, el tiempo de ejecución permite que la comunicación fluya en ambas direcciones, lo que permite llamar a artefactos administrados desde funciones nativas mediante el uso de punteros de función. Lo más parecido a un puntero de función en código administrado es un **delegado**, por lo que esto es lo que se usa para permitir las devoluciones de llamada de código nativo a código administrado.

La forma en que se usa esta característica se parece al proceso de administrado a nativo que se ha descrito anteriormente. En el caso de una devolución de llamada específica, debe definir un delegado que coincida con la firma y pasarlo al método externo. El tiempo de ejecución se encargará de todo lo demás.

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

Antes de examinar nuestro ejemplo, conviene que analicemos las firmas de las funciones no administradas con las que tenemos que trabajar. La función a la que queremos llamar para enumerar todas las ventanas tiene la firma siguiente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

El primer parámetro es una devolución de llamada. Dicha devolución de llamada tiene la firma siguiente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

Teniendo esto en cuenta, examinemos el ejemplo:

*   En la línea 8 del ejemplo se define un delegado que coincide con la firma de la devolución de llamada desde código no administrado. Observe cómo se representan los tipos LPARAM y HWND mediante el uso de `IntPtr` en el código administrado.
*   En las líneas 10 y 11 se introduce la función `EnumWindows` desde la biblioteca user32.dll.
*   En las líneas de la 13 a la 16 se implementa el delegado. En este sencillo ejemplo, solo queremos generar el identificador de la consola.
*   Por último, en la línea 19, se invoca el método externo y se pasa el delegado.

Los ejemplos de Linux y macOS se muestran a continuación. Para ellos, usamos la función `ftw` que se encuentra en `libc`, la biblioteca de C. Esta función se usa para atravesar las jerarquías de directorio y toma un puntero a una función como uno de sus parámetros. Dicha función tiene la firma siguiente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

El ejemplo de macOS usa la misma función. La única diferencia es el argumento del atributo `DllImport`, ya que macOS guarda `libc` en un lugar diferente.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code. You can find more information
        // about this in the section on marshalling below.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

Los dos ejemplos anteriores dependen de parámetros y, en ambos casos, los parámetros se proporcionan como tipos administrados. El tiempo de ejecución hace "lo correcto" y los procesa en sus equivalentes en el otro lado. Dado que este proceso es muy importante para escribir código de interoperabilidad nativa de calidad, vamos a ver lo que sucede cuando el tiempo de ejecución _serializa_ los tipos.

## <a name="type-marshalling"></a>Serializar tipos

La **serialización** es el proceso de transformación de tipos cuando tienen que cruzar el límite de administrado a nativo y viceversa.

La serialización es necesaria porque los tipos del código administrado y del código no administrado son diferentes. En el código administrado, por ejemplo, tiene `String`, mientras que en el entorno no administrado, las cadenas pueden ser Unicode ("anchas"), no Unicode, terminadas en un valor nulo, ASCII, etc. De forma predeterminada, el subsistema de P/Invoke intentará hacer "lo correcto" según el comportamiento predeterminado que se puede ver en [MSDN](../../docs/framework/interop/default-marshaling-behavior.md). Pero en aquellas situaciones en las que necesita un control adicional, puede emplear el atributo `MarshalAs` para especificar qué tipo se espera en el lado no administrado. Por ejemplo, si queremos que la cadena se envíe como una cadena ANSI terminada en un valor nulo, podemos hacerlo de la manera siguiente:

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

### <a name="marshalling-classes-and-structs"></a>Serializar clases y estructuras

Otro aspecto de la serialización de tipos es cómo pasar una estructura a un método no administrado. Por ejemplo, algunos métodos no administrados requieren una estructura como parámetro. En estos casos, debemos crear una clase o una estructura correspondiente en la parte administrada del entorno para usarla como un parámetro. Pero no basta con definir simplemente la clase. También es necesario indicarle al contador de referencias cómo asignar campos de la clase a la estructura no administrada. Aquí es donde entra en juego el atributo `StructLayout`.

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

En el ejemplo anterior se muestra un ejemplo sencillo de una llamada a la función `GetSystemTime()`. La parte interesante está en la línea 4. El atributo especifica que los campos de la clase se deben asignar secuencialmente a la estructura en el otro lado (el lado no administrado). Esto significa que la denominación de los campos no es importante. Solo su orden es importante, ya que es necesario que coincida con la estructura no administrada, tal como se muestra a continuación:

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

Ya vimos el ejemplo de Linux y macOS para esto en el ejemplo anterior, pero lo mostramos de nuevo a continuación.

```csharp
[StructLayout(LayoutKind.Sequential)]
public class StatClass {
        public uint DeviceID;
        public uint InodeNumber;
        public uint Mode;
        public uint HardLinks;
        public uint UserID;
        public uint GroupID;
        public uint SpecialDeviceID;
        public ulong Size;
        public ulong BlockSize;
        public uint Blocks;
        public long TimeLastAccess;
        public long TimeLastModification;
        public long TimeLastStatusChange;
}
```

La clase `StatClass` representa una estructura que se devuelve mediante la llamada del sistema `stat` en sistemas UNIX. Representa información sobre un archivo determinado. La clase anterior es la representación de estructura estática en código administrado. De nuevo, los campos de la clase deben estar en el mismo orden que la estructura nativa (puede encontrarlos si lee con detenimiento las páginas del manual de su implementación de UNIX favorita) y deben ser del mismo tipo subyacente.

## <a name="more-resources"></a>Más recursos

*   [Wiki de PInvoke.net](http://www.pinvoke.net): una wiki excelente con información sobre API comunes de Win32 y cómo llamarlas.
*   [P/Invoke on MSDN](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [Documentación de Mono en P/Invoke](http://www.mono-project.com/docs/advanced/pinvoke/)
