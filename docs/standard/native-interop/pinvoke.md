---
title: Invocación de plataforma (P/Invoke)
description: Obtenga información sobre cómo llamar a funciones nativas a través de P/Invoke en. NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 4836096e12f6c3d317daa5da91566ab472053ede
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409242"
---
# <a name="platform-invoke-pinvoke"></a>Invocación de plataforma (P/Invoke)

P/Invoke es una tecnología que permite acceder a estructuras, devoluciones de llamada y funciones de bibliotecas no administradas desde el código administrado. La mayor parte de la API de P/Invoke se encuentra en dos espacios de nombres: `System` y `System.Runtime.InteropServices`. Mediante estos dos espacios de nombres puede acceder a las herramientas que describen cómo quiere comunicarse con el componente nativo.

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

El ejemplo anterior es simple, pero resalta lo que es necesario para invocar las funciones no administradas desde código administrado. Veamos en detalle el ejemplo:

*   En la línea 1 se muestra el uso de la instrucción para el espacio de nombres `System.Runtime.InteropServices`, que es el espacio de nombres que contiene todos los elementos que necesitamos.
*   En la línea 7 se introduce el atributo `DllImport`. Este atributo es fundamental, ya que le indica al tiempo de ejecución que debe cargar la DLL no administrada. La cadena que se pasa es la DLL en la que está nuestra función de destino.
*   La línea 8 es la esencia del trabajo de P/Invoke. Define un método administrado que tiene **exactamente la misma firma** que el no administrado. Como puede ver, la declaración tiene una nueva palabra clave (`extern`) que le indica al tiempo de ejecución que esto es un método externo y que, cuando se invoca, el tiempo de ejecución debe buscarlo en el archivo DLL especificado en el atributo `DllImport`.

El resto del ejemplo simplemente invoca el método como si se tratara de cualquier otro método administrado.

El ejemplo es parecido para macOS. El nombre de la biblioteca en el atributo `DllImport` debe cambiarse, ya que macOS tiene un esquema diferente para la nomenclatura de bibliotecas dinámicas. En el ejemplo siguiente se usa la función `getpid(2)` para obtener el identificador de proceso de la aplicación e imprimirlo en la consola:

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

## <a name="invoking-managed-code-from-unmanaged-code"></a>Invocar código administrado desde código no administrado

El entorno de ejecución permite que la comunicación fluya en ambas direcciones, lo que permite llamar a código administrado desde funciones nativas mediante el uso de punteros de función. Lo más parecido a un puntero de función en código administrado es un **delegado**, por lo que esto es lo que se usa para permitir las devoluciones de llamada de código nativo a código administrado.

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

Antes de examinar el ejemplo, conviene que analicemos las firmas de las funciones no administradas con las que tenemos que trabajar. La función a la que queremos llamar para enumerar todas las ventanas tiene la firma siguiente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

El primer parámetro es una devolución de llamada. Dicha devolución de llamada tiene la firma siguiente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

Ahora, examinemos el proceso:

*   En la línea 9 del ejemplo se define un delegado que coincide con la firma de la devolución de llamada desde código no administrado. Observe cómo se representan los tipos LPARAM y HWND mediante el uso de `IntPtr` en el código administrado.
*   En las líneas 13 y 14 se introduce la función `EnumWindows` desde la biblioteca user32.dll.
*   En las líneas de la 17 a la 20 se implementa el delegado. En este sencillo ejemplo, solo queremos generar el identificador de la consola.
*   Por último, en la línea 24, se invoca el método externo y se pasa el delegado.

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
        // represents that struct in managed code.
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

Los dos ejemplos anteriores dependen de parámetros y, en ambos casos, los parámetros se proporcionan como tipos administrados. El tiempo de ejecución hace "lo correcto" y los procesa en sus equivalentes en el otro lado. Obtenga información sobre cómo los tipos se serializan al código nativo en nuestra página en [Serialización de tipos](type-marshalling.md).


## <a name="more-resources"></a>Más recursos

*   [Wiki de PInvoke.net](https://www.pinvoke.net/): una wiki excelente con información sobre API comunes de Windows y cómo llamarlas.
*   [P/Invoke on MSDN](/cpp/dotnet/native-and-dotnet-interoperability)
*   [Documentación de Mono en P/Invoke](https://www.mono-project.com/docs/advanced/pinvoke/)
