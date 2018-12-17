---
title: Interoperabilidad nativa
description: Obtenga información sobre cómo interactuar con componentes nativos en .NET.
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
ms.openlocfilehash: 2f427eb5d8f41f730d4263425e268213db92236d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143193"
---
# <a name="native-interoperability"></a><span data-ttu-id="a1e30-103">Interoperabilidad nativa</span><span class="sxs-lookup"><span data-stu-id="a1e30-103">Native Interoperability</span></span>

<span data-ttu-id="a1e30-104">En este documento se profundiza un poco más en las tres formas de obtener "interoperabilidad nativa" disponibles mediante .NET.</span><span class="sxs-lookup"><span data-stu-id="a1e30-104">In this document, we will dive a little bit deeper into all three ways of doing "native interoperability" that are available using .NET.</span></span>

<span data-ttu-id="a1e30-105">Existen varios motivos por los que puede interesarle llamar a código nativo:</span><span class="sxs-lookup"><span data-stu-id="a1e30-105">There are a few of reasons why you would want to call into native code:</span></span>

*   <span data-ttu-id="a1e30-106">Los sistemas operativos incluyen un elevado volumen de API que no están presentes en las bibliotecas de clases administradas.</span><span class="sxs-lookup"><span data-stu-id="a1e30-106">Operating Systems come with a large volume of APIs that are not present in the managed class libraries.</span></span> <span data-ttu-id="a1e30-107">Un buen ejemplo de esto sería el acceso al hardware o a funciones de administración del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a1e30-107">A prime example for this would be access to hardware or operating system management functions.</span></span>
*   <span data-ttu-id="a1e30-108">La comunicación con otros componentes que tienen o pueden generar ABI de estilo C (ABI nativos).</span><span class="sxs-lookup"><span data-stu-id="a1e30-108">Communicating with other components that have or can produce C-style ABIs (native ABIs).</span></span> <span data-ttu-id="a1e30-109">Esto incluye, por ejemplo, código Java que se expone a través de [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) o cualquier lenguaje administrado que pueda producir un componente nativo.</span><span class="sxs-lookup"><span data-stu-id="a1e30-109">This covers, for example, Java code that is exposed via [Java Native Interface (JNI)](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/) or any other managed language that could produce a native component.</span></span>
*   <span data-ttu-id="a1e30-110">En Windows, la mayor parte del software que se instala, como el conjunto de aplicaciones de Microsoft Office, registra los componentes COM que representan sus programas y permiten a los desarrolladores automatizarlos o usarlos.</span><span class="sxs-lookup"><span data-stu-id="a1e30-110">On Windows, most of the software that gets installed, such as Microsoft Office suite, registers COM components that represent their programs and allow developers to automate them or use them.</span></span> <span data-ttu-id="a1e30-111">Esto también requiere interoperabilidad nativa.</span><span class="sxs-lookup"><span data-stu-id="a1e30-111">This also requires native interoperability.</span></span>

<span data-ttu-id="a1e30-112">Por supuesto, la lista anterior no cubre todas las posibles situaciones y escenarios en los que el desarrollador puede querer o necesitar interactuar con componentes nativos.</span><span class="sxs-lookup"><span data-stu-id="a1e30-112">Of course, the list above does not cover all of the potential situations and scenarios in which the developer would want/like/need to interface with native components.</span></span> <span data-ttu-id="a1e30-113">La biblioteca de clases. NET, por ejemplo, usa la compatibilidad con la interoperabilidad nativa para implementar bastantes de sus API, como la compatibilidad con la consola y su manipulación, el acceso al sistema de archivos, etc.</span><span class="sxs-lookup"><span data-stu-id="a1e30-113">.NET class library, for instance, uses the native interoperability support to implement a fair number of its APIs, like console support and manipulation, file system access and others.</span></span> <span data-ttu-id="a1e30-114">Pero es importante tener en cuenta que existe la opción de hacerlo, en caso de que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a1e30-114">However, it is important to note that there is an option, should one need it.</span></span>

> [!NOTE]
> <span data-ttu-id="a1e30-115">La mayoría de los ejemplos de este documento se presentarán para las tres plataformas compatibles con .NET Core (Windows, Linux y macOS).</span><span class="sxs-lookup"><span data-stu-id="a1e30-115">Most of the examples in this document will be presented for all three supported platforms for .NET Core (Windows, Linux and macOS).</span></span> <span data-ttu-id="a1e30-116">En cambio, en algunos ejemplos breves e ilustrativos solo se muestra un ejemplo que usa nombres de archivo y extensiones de Windows (es decir, "dll" en el caso de las bibliotecas).</span><span class="sxs-lookup"><span data-stu-id="a1e30-116">However, for some short and illustrative examples, just one sample is shown that uses Windows filenames and extensions (that is, "dll" for libraries).</span></span> <span data-ttu-id="a1e30-117">Esto no significa que esas características no estén disponibles en Linux o macOS, sino que simplemente se buscaba una mayor comodidad.</span><span class="sxs-lookup"><span data-stu-id="a1e30-117">This does not mean that those features are not available on Linux or macOS, it was done merely for convenience sake.</span></span>

## <a name="platform-invoke-pinvoke"></a><span data-ttu-id="a1e30-118">Invocación de plataforma (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="a1e30-118">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="a1e30-119">P/Invoke es una tecnología que permite acceder a estructuras, devoluciones de llamada y funciones de bibliotecas no administradas desde el código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-119">P/Invoke is a technology that allows you to access structs, callbacks and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="a1e30-120">La mayor parte de la API de P/Invoke se encuentra en dos espacios de nombres: `System` y `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="a1e30-120">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="a1e30-121">Mediante estos dos espacios de nombres, puede acceder a los atributos que describen cómo quiere comunicarse con el componente nativo.</span><span class="sxs-lookup"><span data-stu-id="a1e30-121">Using these two namespaces will allow you access to the attributes that describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="a1e30-122">Empecemos por el ejemplo más común, es decir, llamar a funciones no administradas en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-122">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="a1e30-123">Vamos a mostrar un cuadro de mensaje desde una aplicación de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a1e30-123">Let’s show a message box from a command-line application:</span></span>

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

<span data-ttu-id="a1e30-124">El ejemplo anterior es bastante sencillo, pero resalta lo que es necesario para invocar las funciones no administradas desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-124">The example above is pretty simple, but it does show off what is needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="a1e30-125">Veamos en detalle el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a1e30-125">Let’s step through the example:</span></span>

*   <span data-ttu-id="a1e30-126">En la línea 1 se muestra el uso de la instrucción para `System.Runtime.InteropServices`, que es el espacio de nombres que contiene todos los elementos que necesitamos.</span><span class="sxs-lookup"><span data-stu-id="a1e30-126">Line #1 shows the using statement for the `System.Runtime.InteropServices` which is the namespace that holds all of the items we need.</span></span>
*   <span data-ttu-id="a1e30-127">En la línea 5 se introduce el atributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="a1e30-127">Line #5 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="a1e30-128">Este atributo es fundamental, ya que le indica al tiempo de ejecución que debe cargar la DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="a1e30-128">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="a1e30-129">Se trata de la DLL en la que queremos invocar.</span><span class="sxs-lookup"><span data-stu-id="a1e30-129">This is the DLL into which we wish to invoke.</span></span>
*   <span data-ttu-id="a1e30-130">La línea 6 es la esencia del trabajo de P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="a1e30-130">Line #6 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="a1e30-131">Define un método administrado que tiene **exactamente la misma firma** que el no administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-131">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="a1e30-132">Como puede ver, la declaración tiene una nueva palabra clave (`extern`) que le indica al tiempo de ejecución que esto es un método externo y que, cuando se invoca, el tiempo de ejecución debe buscarlo en el archivo DLL especificado en el atributo `DllImport`.</span><span class="sxs-lookup"><span data-stu-id="a1e30-132">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="a1e30-133">El resto del ejemplo simplemente invoca el método como si se tratara de cualquier otro método administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-133">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="a1e30-134">El ejemplo es parecido para macOS.</span><span class="sxs-lookup"><span data-stu-id="a1e30-134">The sample is similar for macOS.</span></span> <span data-ttu-id="a1e30-135">Evidentemente, lo que debe cambiar es el nombre de la biblioteca en el atributo `DllImport`, ya que macOS tiene un esquema diferente para la nomenclatura de bibliotecas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="a1e30-135">One thing that needs to change is, of course, the name of the library in the `DllImport` attribute, as macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="a1e30-136">En el ejemplo siguiente se usa la función `getpid(2)` para obtener el identificador de proceso de la aplicación e imprimirlo en la consola.</span><span class="sxs-lookup"><span data-stu-id="a1e30-136">The sample below uses the `getpid(2)` function to get the process ID of the application and print it out to the console.</span></span>

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

<span data-ttu-id="a1e30-137">También es similar en Linux.</span><span class="sxs-lookup"><span data-stu-id="a1e30-137">It is also similar on Linux.</span></span> <span data-ttu-id="a1e30-138">El nombre de la función es el mismo, ya que `getpid(2)` es la llamada del sistema estándar de [POSIX](https://en.wikipedia.org/wiki/POSIX).</span><span class="sxs-lookup"><span data-stu-id="a1e30-138">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

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

### <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="a1e30-139">Invocar código administrado desde código no administrado</span><span class="sxs-lookup"><span data-stu-id="a1e30-139">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="a1e30-140">Por supuesto, el tiempo de ejecución permite que la comunicación fluya en ambas direcciones, lo que permite llamar a artefactos administrados desde funciones nativas mediante el uso de punteros de función.</span><span class="sxs-lookup"><span data-stu-id="a1e30-140">Of course, the runtime allows communication to flow both ways which enables you to call into managed artifacts from native functions, using function pointers.</span></span> <span data-ttu-id="a1e30-141">Lo más parecido a un puntero de función en código administrado es un **delegado**, por lo que esto es lo que se usa para permitir las devoluciones de llamada de código nativo a código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-141">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="a1e30-142">La forma en que se usa esta característica se parece al proceso de administrado a nativo que se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a1e30-142">The way to use this feature is similar to managed to native process described above.</span></span> <span data-ttu-id="a1e30-143">En el caso de una devolución de llamada específica, debe definir un delegado que coincida con la firma y pasarlo al método externo.</span><span class="sxs-lookup"><span data-stu-id="a1e30-143">For a given callback, you define a delegate that matches the signature, and pass that into the external method.</span></span> <span data-ttu-id="a1e30-144">El tiempo de ejecución se encargará de todo lo demás.</span><span class="sxs-lookup"><span data-stu-id="a1e30-144">The runtime will take care of everything else.</span></span>

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

<span data-ttu-id="a1e30-145">Antes de examinar nuestro ejemplo, conviene que analicemos las firmas de las funciones no administradas con las que tenemos que trabajar.</span><span class="sxs-lookup"><span data-stu-id="a1e30-145">Before we walk through our example, it is good to go over the signatures of the unmanaged functions we need to work with.</span></span> <span data-ttu-id="a1e30-146">La función a la que queremos llamar para enumerar todas las ventanas tiene la firma siguiente: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="a1e30-146">The function we want to call to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="a1e30-147">El primer parámetro es una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a1e30-147">The first parameter is a callback.</span></span> <span data-ttu-id="a1e30-148">Dicha devolución de llamada tiene la firma siguiente: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="a1e30-148">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="a1e30-149">Teniendo esto en cuenta, examinemos el ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a1e30-149">With this in mind, let’s walk through the example:</span></span>

*   <span data-ttu-id="a1e30-150">En la línea 8 del ejemplo se define un delegado que coincide con la firma de la devolución de llamada desde código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-150">Line #8 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="a1e30-151">Observe cómo se representan los tipos LPARAM y HWND mediante el uso de `IntPtr` en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-151">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="a1e30-152">En las líneas 10 y 11 se introduce la función `EnumWindows` desde la biblioteca user32.dll.</span><span class="sxs-lookup"><span data-stu-id="a1e30-152">Lines #10 and #11 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="a1e30-153">En las líneas de la 13 a la 16 se implementa el delegado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-153">Lines #13 - 16 implement the delegate.</span></span> <span data-ttu-id="a1e30-154">En este sencillo ejemplo, solo queremos generar el identificador de la consola.</span><span class="sxs-lookup"><span data-stu-id="a1e30-154">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="a1e30-155">Por último, en la línea 19, se invoca el método externo y se pasa el delegado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-155">Finally, in line #19 we invoke the external method and pass in the delegate.</span></span>

<span data-ttu-id="a1e30-156">Los ejemplos de Linux y macOS se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="a1e30-156">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="a1e30-157">Para ellos, usamos la función `ftw` que se encuentra en `libc`, la biblioteca de C.</span><span class="sxs-lookup"><span data-stu-id="a1e30-157">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="a1e30-158">Esta función se usa para atravesar las jerarquías de directorio y toma un puntero a una función como uno de sus parámetros.</span><span class="sxs-lookup"><span data-stu-id="a1e30-158">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="a1e30-159">Dicha función tiene la firma siguiente: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="a1e30-159">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

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

<span data-ttu-id="a1e30-160">El ejemplo de macOS usa la misma función. La única diferencia es el argumento del atributo `DllImport`, ya que macOS guarda `libc` en un lugar diferente.</span><span class="sxs-lookup"><span data-stu-id="a1e30-160">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

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

<span data-ttu-id="a1e30-161">Los dos ejemplos anteriores dependen de parámetros y, en ambos casos, los parámetros se proporcionan como tipos administrados.</span><span class="sxs-lookup"><span data-stu-id="a1e30-161">Both of the above examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="a1e30-162">El tiempo de ejecución hace "lo correcto" y los procesa en sus equivalentes en el otro lado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-162">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="a1e30-163">Dado que este proceso es muy importante para escribir código de interoperabilidad nativa de calidad, vamos a ver lo que sucede cuando el tiempo de ejecución _serializa_ los tipos.</span><span class="sxs-lookup"><span data-stu-id="a1e30-163">Since this process is really important to writing quality native interop code, let’s take a look at what happens when the runtime _marshals_ the types.</span></span>

## <a name="type-marshalling"></a><span data-ttu-id="a1e30-164">Serializar tipos</span><span class="sxs-lookup"><span data-stu-id="a1e30-164">Type marshalling</span></span>

<span data-ttu-id="a1e30-165">La **serialización** es el proceso de transformación de tipos cuando tienen que cruzar el límite de administrado a nativo y viceversa.</span><span class="sxs-lookup"><span data-stu-id="a1e30-165">**Marshalling** is the process of transforming types when they need to cross the managed boundary into native and vice versa.</span></span>

<span data-ttu-id="a1e30-166">La serialización es necesaria porque los tipos del código administrado y del código no administrado son diferentes.</span><span class="sxs-lookup"><span data-stu-id="a1e30-166">The reason marshalling is needed is because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="a1e30-167">En el código administrado, por ejemplo, tiene `String`, mientras que en el entorno no administrado, las cadenas pueden ser Unicode ("anchas"), no Unicode, terminadas en un valor nulo, ASCII, etc. De forma predeterminada, el subsistema de P/Invoke intentará hacer "lo correcto" según el [comportamiento predeterminado](../../docs/framework/interop/default-marshaling-behavior.md).</span><span class="sxs-lookup"><span data-stu-id="a1e30-167">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem will try to do the right thing based on the [default behavior](../../docs/framework/interop/default-marshaling-behavior.md).</span></span> <span data-ttu-id="a1e30-168">Pero en aquellas situaciones en las que necesita un control adicional, puede emplear el atributo [MarshalAs](xref:System.Runtime.InteropServicxes.MarshalAs) para especificar qué tipo se espera en el lado no administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-168">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServicxes.MarshalAs) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="a1e30-169">Por ejemplo, si queremos que la cadena se envíe como una cadena ANSI terminada en un valor nulo, podemos hacerlo de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1e30-169">For instance, if we want the string to be sent as a null-terminated ANSI string, we could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

### <a name="marshalling-classes-and-structs"></a><span data-ttu-id="a1e30-170">Serializar clases y estructuras</span><span class="sxs-lookup"><span data-stu-id="a1e30-170">Marshalling classes and structs</span></span>

<span data-ttu-id="a1e30-171">Otro aspecto de la serialización de tipos es cómo pasar una estructura a un método no administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-171">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="a1e30-172">Por ejemplo, algunos métodos no administrados requieren una estructura como parámetro.</span><span class="sxs-lookup"><span data-stu-id="a1e30-172">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="a1e30-173">En estos casos, debemos crear una clase o una estructura correspondiente en la parte administrada del entorno para usarla como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="a1e30-173">In these cases, we need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="a1e30-174">Pero no basta con definir simplemente la clase. También es necesario indicarle al contador de referencias cómo asignar campos de la clase a la estructura no administrada.</span><span class="sxs-lookup"><span data-stu-id="a1e30-174">However, just defining the class is not enough, we also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="a1e30-175">Aquí es donde entra en juego el atributo `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="a1e30-175">This is where the `StructLayout` attribute comes into play.</span></span>

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

<span data-ttu-id="a1e30-176">En el ejemplo anterior se muestra un ejemplo sencillo de una llamada a la función `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="a1e30-176">The example above shows off a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="a1e30-177">La parte interesante está en la línea 4.</span><span class="sxs-lookup"><span data-stu-id="a1e30-177">The interesting bit is on line 4.</span></span> <span data-ttu-id="a1e30-178">El atributo especifica que los campos de la clase se deben asignar secuencialmente a la estructura en el otro lado (el lado no administrado).</span><span class="sxs-lookup"><span data-stu-id="a1e30-178">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="a1e30-179">Esto significa que la denominación de los campos no es importante. Solo su orden es importante, ya que es necesario que coincida con la estructura no administrada, tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="a1e30-179">This means that the naming of the fields is not important, only their order is important, as it needs to correspond to the unmanaged struct, shown below:</span></span>

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

<span data-ttu-id="a1e30-180">Ya vimos el ejemplo de Linux y macOS para esto en el ejemplo anterior,</span><span class="sxs-lookup"><span data-stu-id="a1e30-180">We already saw the Linux and macOS example for this in the previous example.</span></span> <span data-ttu-id="a1e30-181">pero lo mostramos de nuevo a continuación.</span><span class="sxs-lookup"><span data-stu-id="a1e30-181">It is shown again below.</span></span>

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

<span data-ttu-id="a1e30-182">La clase `StatClass` representa una estructura que se devuelve mediante la llamada del sistema `stat` en sistemas UNIX.</span><span class="sxs-lookup"><span data-stu-id="a1e30-182">The `StatClass` class represents a structure that is returned by the `stat` system call on UNIX systems.</span></span> <span data-ttu-id="a1e30-183">Representa información sobre un archivo determinado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-183">It represents information about a given file.</span></span> <span data-ttu-id="a1e30-184">La clase anterior es la representación de estructura estática en código administrado.</span><span class="sxs-lookup"><span data-stu-id="a1e30-184">The class above is the stat struct representation in managed code.</span></span> <span data-ttu-id="a1e30-185">De nuevo, los campos de la clase deben estar en el mismo orden que la estructura nativa (puede encontrarlos si lee con detenimiento las páginas del manual de su implementación de UNIX favorita) y deben ser del mismo tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="a1e30-185">Again, the fields in the class have to be in the same order as the native struct (you can find these by perusing man pages on your favorite UNIX implementation) and they have to be of the same underlying type.</span></span>

## <a name="more-resources"></a><span data-ttu-id="a1e30-186">Más recursos</span><span class="sxs-lookup"><span data-stu-id="a1e30-186">More resources</span></span>

*   <span data-ttu-id="a1e30-187">[Wiki de PInvoke.net](https://www.pinvoke.net/): una wiki excelente con información sobre API comunes de Win32 y cómo llamarlas.</span><span class="sxs-lookup"><span data-stu-id="a1e30-187">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="a1e30-188">P/Invoke on MSDN</span><span class="sxs-lookup"><span data-stu-id="a1e30-188">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="a1e30-189">Documentación de Mono en P/Invoke</span><span class="sxs-lookup"><span data-stu-id="a1e30-189">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
