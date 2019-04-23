---
title: Invocación de plataforma (P/Invoke)
description: Obtenga información sobre cómo llamar a funciones nativas a través de P/Invoke en. NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 1a5f2f9d13429f84d5b5bb58d36f015004fb746b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517868"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="5947d-103">Invocación de plataforma (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="5947d-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="5947d-104">P/Invoke es una tecnología que permite acceder a estructuras, devoluciones de llamada y funciones de bibliotecas no administradas desde el código administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="5947d-105">La mayor parte de la API de P/Invoke se encuentra en dos espacios de nombres: `System` y `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="5947d-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="5947d-106">Mediante estos dos espacios de nombres puede acceder a las herramientas que describen cómo quiere comunicarse con el componente nativo.</span><span class="sxs-lookup"><span data-stu-id="5947d-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="5947d-107">Empecemos por el ejemplo más común, es decir, llamar a funciones no administradas en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="5947d-108">Vamos a mostrar un cuadro de mensaje desde una aplicación de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="5947d-108">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll", CharSet = CharSet.Unicode, SetLastError = true)]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="5947d-109">El ejemplo anterior es simple, pero resalta lo que es necesario para invocar las funciones no administradas desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="5947d-110">Veamos en detalle el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5947d-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="5947d-111">En la línea 1 se muestra el uso de la instrucción para el espacio de nombres `System.Runtime.InteropServices`, que es el espacio de nombres que contiene todos los elementos que necesitamos.</span><span class="sxs-lookup"><span data-stu-id="5947d-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="5947d-112">En la línea 7 se introduce el atributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="5947d-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="5947d-113">Este atributo es fundamental, ya que le indica al tiempo de ejecución que debe cargar la DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="5947d-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="5947d-114">La cadena que se pasa es la DLL en la que está nuestra función de destino.</span><span class="sxs-lookup"><span data-stu-id="5947d-114">The string passed in is the DLL our target function is in.</span></span> <span data-ttu-id="5947d-115">Además, especifica qué [juego de caracteres](./charset.md) se usará para serializar las cadenas.</span><span class="sxs-lookup"><span data-stu-id="5947d-115">Additionally, it specifies which [character set](./charset.md) to use for marshalling the strings.</span></span> <span data-ttu-id="5947d-116">Por último, especifica que esta función llama a [SetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-setlasterror) y que el runtime debe capturar ese código de error para que el usuario pueda recuperarlo a través de <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5947d-116">Finally, it specifies that this function calls [SetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-setlasterror) and that the runtime should capture that error code so the user can retrieve it via <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error?displayProperty=nameWithType>.</span></span>
*   <span data-ttu-id="5947d-117">La línea 8 es la esencia del trabajo de P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="5947d-117">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="5947d-118">Define un método administrado que tiene **exactamente la misma firma** que el no administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-118">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="5947d-119">Como puede ver, la declaración tiene una nueva palabra clave (`extern`) que le indica al tiempo de ejecución que esto es un método externo y que, cuando se invoca, el tiempo de ejecución debe buscarlo en el archivo DLL especificado en el atributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="5947d-119">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="5947d-120">El resto del ejemplo simplemente invoca el método como si se tratara de cualquier otro método administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-120">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="5947d-121">El ejemplo es parecido para macOS.</span><span class="sxs-lookup"><span data-stu-id="5947d-121">The sample is similar for macOS.</span></span> <span data-ttu-id="5947d-122">El nombre de la biblioteca en el atributo `DllImport` debe cambiarse, ya que macOS tiene un esquema diferente para la nomenclatura de bibliotecas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="5947d-122">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="5947d-123">En el ejemplo siguiente se usa la función `getpid(2)` para obtener el identificador de proceso de la aplicación e imprimirlo en la consola:</span><span class="sxs-lookup"><span data-stu-id="5947d-123">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

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

<span data-ttu-id="5947d-124">También es similar en Linux.</span><span class="sxs-lookup"><span data-stu-id="5947d-124">It is also similar on Linux.</span></span> <span data-ttu-id="5947d-125">El nombre de la función es el mismo, ya que `getpid(2)` es la llamada del sistema estándar de [POSIX](https://en.wikipedia.org/wiki/POSIX).</span><span class="sxs-lookup"><span data-stu-id="5947d-125">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

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

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="5947d-126">Invocar código administrado desde código no administrado</span><span class="sxs-lookup"><span data-stu-id="5947d-126">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="5947d-127">El entorno de ejecución permite que la comunicación fluya en ambas direcciones, lo que permite llamar a código administrado desde funciones nativas mediante el uso de punteros de función.</span><span class="sxs-lookup"><span data-stu-id="5947d-127">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="5947d-128">Lo más parecido a un puntero de función en código administrado es un **delegado**, por lo que esto es lo que se usa para permitir las devoluciones de llamada de código nativo a código administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-128">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="5947d-129">La forma en que se usa esta característica se parece al proceso de administrado a nativo que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5947d-129">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="5947d-130">En el caso de una devolución de llamada específica, debe definir un delegado que coincida con la firma y pasarlo al método externo.</span><span class="sxs-lookup"><span data-stu-id="5947d-130">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="5947d-131">El tiempo de ejecución se encargará de todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="5947d-131">The runtime will take care of everything else.</span></span>

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

<span data-ttu-id="5947d-132">Antes de examinar el ejemplo, conviene que analicemos las firmas de las funciones no administradas con las que tenemos que trabajar.</span><span class="sxs-lookup"><span data-stu-id="5947d-132">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="5947d-133">La función a la que queremos llamar para enumerar todas las ventanas tiene la firma siguiente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="5947d-133">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="5947d-134">El primer parámetro es una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5947d-134">The first parameter is a callback.</span></span> <span data-ttu-id="5947d-135">Dicha devolución de llamada tiene la firma siguiente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="5947d-135">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="5947d-136">Ahora, examinemos el proceso:</span><span class="sxs-lookup"><span data-stu-id="5947d-136">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="5947d-137">En la línea 9 del ejemplo se define un delegado que coincide con la firma de la devolución de llamada desde código no administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-137">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="5947d-138">Observe cómo se representan los tipos LPARAM y HWND mediante el uso de `IntPtr` en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="5947d-138">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="5947d-139">En las líneas 13 y 14 se introduce la función `EnumWindows` desde la biblioteca user32.dll.</span><span class="sxs-lookup"><span data-stu-id="5947d-139">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="5947d-140">En las líneas de la 17 a la 20 se implementa el delegado.</span><span class="sxs-lookup"><span data-stu-id="5947d-140">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="5947d-141">En este sencillo ejemplo, solo queremos generar el identificador de la consola.</span><span class="sxs-lookup"><span data-stu-id="5947d-141">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="5947d-142">Por último, en la línea 24, se invoca el método externo y se pasa el delegado.</span><span class="sxs-lookup"><span data-stu-id="5947d-142">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="5947d-143">Los ejemplos de Linux y macOS se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="5947d-143">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="5947d-144">Para ellos, usamos la función `ftw` que se encuentra en `libc`, la biblioteca de C.</span><span class="sxs-lookup"><span data-stu-id="5947d-144">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="5947d-145">Esta función se usa para atravesar las jerarquías de directorio y toma un puntero a una función como uno de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="5947d-145">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="5947d-146">Dicha función tiene la firma siguiente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="5947d-146">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

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

<span data-ttu-id="5947d-147">El ejemplo de macOS usa la misma función. La única diferencia es el argumento del atributo `DllImport`, ya que macOS guarda `libc` en un lugar diferente.</span><span class="sxs-lookup"><span data-stu-id="5947d-147">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

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

<span data-ttu-id="5947d-148">Los dos ejemplos anteriores dependen de parámetros y, en ambos casos, los parámetros se proporcionan como tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="5947d-148">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="5947d-149">El tiempo de ejecución hace "lo correcto" y los procesa en sus equivalentes en el otro lado.</span><span class="sxs-lookup"><span data-stu-id="5947d-149">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="5947d-150">Obtenga información sobre cómo los tipos se serializan al código nativo en nuestra página en [Serialización de tipos](type-marshalling.md).</span><span class="sxs-lookup"><span data-stu-id="5947d-150">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="5947d-151">Más recursos</span><span class="sxs-lookup"><span data-stu-id="5947d-151">More resources</span></span>

*   <span data-ttu-id="5947d-152">[Wiki de PInvoke.net](https://www.pinvoke.net/): una wiki excelente con información sobre API comunes de Windows y cómo llamarlas.</span><span class="sxs-lookup"><span data-stu-id="5947d-152">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Windows APIs and how to call them.</span></span>
*   [<span data-ttu-id="5947d-153">P/Invoke on MSDN</span><span class="sxs-lookup"><span data-stu-id="5947d-153">P/Invoke on MSDN</span></span>](/cpp/dotnet/native-and-dotnet-interoperability)
*   [<span data-ttu-id="5947d-154">Documentación de Mono en P/Invoke</span><span class="sxs-lookup"><span data-stu-id="5947d-154">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
