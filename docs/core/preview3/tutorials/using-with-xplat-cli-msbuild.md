---
title: "Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos (SDK Preview 3)"
description: "Introducción a .NET Core en Windows, Linux o macOS con la interfaz de línea de comandos (CLI) de .NET Core"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: be988f09-7349-43b0-97fb-3a703d4587ce
translationtype: Human Translation
ms.sourcegitcommit: ab71aab99505f211fe4adc86957eda4707761f1c
ms.openlocfilehash: 01b17021e79bcdb2dc69f97b709f4aa63dbab9aa

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line-sdk-preview-3"></a>Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos (SDK Preview 3)

Esta guía le enseñará a usar las herramientas de la CLI de .NET Core para crear aplicaciones de consola multiplataforma.  Se iniciará con la aplicación de consola más básica y finalmente abarcará varios proyectos, incluidas las pruebas. Agregue estas características paso a paso, a partir de lo que ya ha visto y compilado.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, consulte [la información general del SDK de .NET Core](../tools/dotnet.md).

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, asegúrese de que tiene [.NET Core CLI Tooling Preview 3 o superior](https://github.com/dotnet/core/blob/master/release-notes/preview3-download.md).  También necesitará un editor de texto.

## <a name="hello-console-app"></a>Hola, aplicación de consola

En primer lugar, navegue o cree una nueva carpeta con el nombre que desee.  "Hello" es el nombre elegido para el código de ejemplo, que se puede encontrar [aquí](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloMsBuild).

Abra un símbolo del sistema y escriba lo siguiente:

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

Veamos un tutorial rápido:

1. `$ dotnet new`

   [`dotnet new`](../tools/dotnet-new.md) crea un archivo de proyecto `Hello.csproj` actualizado con las dependencias necesarias para compilar una aplicación de consola.  Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.
   
   `Hello.csproj`:
   ```xml
    <Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
        <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
        
        <PropertyGroup>
            <OutputType>Exe</OutputType>
            <TargetFramework>netcoreapp1.0</TargetFramework>
        </PropertyGroup>

        <ItemGroup>
            <Compile Include="**\*.cs" />
            <EmbeddedResource Include="**\*.resx" />
        </ItemGroup>

        <ItemGroup>
            <PackageReference Include="Microsoft.NETCore.App">
                <Version>1.0.1</Version>
            </PackageReference>
            <PackageReference Include="Microsoft.NET.Sdk">
                <Version>1.0.0-alpha-20161104-2</Version>
                <PrivateAssets>All</PrivateAssets>
            </PackageReference>
        </ItemGroup>
        
        <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
   ```

   El archivo de proyecto especifica todo lo que es necesario para restaurar las dependencias y compilar el programa.

   * La etiqueta `Import` incluye algunas propiedades que son comunes a todos los proyectos de .NET Core.
   * La etiqueta `OutputType` especifica que estamos creando un archivo ejecutable, es decir, una aplicación de consola.
   * La etiqueta `TargetFramework` especifica el entorno de ejecución de .NET al que nos dirigimos. En un escenario avanzado, puede especificar varios marcos de destino y compilar en todos ellos en una sola operación. En este tutorial, nos centraremos solo en .NET Core 1.0.
   * La etiqueta `Compile` dice al compilador que compile todos los archivos del directorio actual y todos sus directorios que tienen la extensión de archivo `.cs`, en otras palabras, todos los archivos de C# del proyecto. En escenarios avanzados, es posible excluir archivos, pero en este tutorial y en la mayoría de los escenarios simples, esta línea se puede dejar como está.
   * La etiqueta `EmbeddedResource` indica al sistema de compilación que incruste archivos de localización con la extensión `.resx` en el ejecutable compilado. En este tutorial no usaremos esta característica.
   * Las etiquetas `PackageReference` especifican qué paquetes de dependencias se deben restaurar e incluir al compilar la aplicación. Cada referencia de paquete especifica el nombre del paquete en el atributo `Include` y un número de versión. En escenarios más avanzados, agregaría más referencias de paquete. También es posible hacer referencia a otros proyectos del disco.

   `Program.cs`:
   ```csharp
   using System;

   namespace ConsoleApplication
   {
       public class Program
       {
           public static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   El programa se inicia mediante `using System`, lo que significa "llevar cada cosa del espacio de nombres `System` al ámbito de este archivo". El espacio de nombres `System` incluye construcciones básicas, como `string` o tipos numéricos.

   A continuación, definimos un espacio de nombres denominado "aplicación de consola". Puede cambiar esto por cualquier cosa que desee. Se define una clase llamada "Program" dentro del espacio de nombres, con un método `Main` que toma una matriz de cadenas como argumento. Esta matriz contendrá la lista de argumentos pasados cuando se llame al programa compilado. Tal y como está, esta matriz no se usa: todo lo que hace el programa es escribir "¡Hola a todos!" en la consola. Podemos hacer cosas un poco más interesante cambiando el elemento `Console.WriteLine` en el código siguiente.

   ```csharp
   if (args.Length > 0)
   {
       Console.WriteLine($"Hello {args[0]}!");
   }
   else
   {
       Console.WriteLine("Hello World!");
   }
   ```

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) llama a [NuGet](http://nuget.org) (el administrador de paquetes de .NET) para restaurar el árbol de dependencias. NuGet analiza el archivo `Hello.csproj`, descarga las dependencias descritas en el archivo (o las toma de la memoria caché en la máquina) y escribe el archivo `obj/project.assets.json`.  El archivo `project.assets.json` es necesario para realizar la compilación y ejecución.
   
   El archivo `project.assets.json` es un conjunto completo y persistente del gráfico de dependencias de NuGet y cualquier otra información que describa a una aplicación.  Este archivo se lee por otras herramientas, como `dotnet build` y `dotnet run`, que les permite procesar el código fuente con un conjunto correcto de las dependencias de NuGet y resoluciones de enlace.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) llama a `dotnet build` para asegurarse de que los destinos de la compilación se han creado y, a después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.
   
    ```
    $ dotnet run
    Hello World!
    ```

    También puede ejecutar [`dotnet build`](../tools/dotnet-build.md) para compilar el código sin ejecutar las aplicaciones de consola de compilación. El resultado es una aplicación compilada `bin/Debug/netcoreapp1.0/Hello.dll` que se puede ejecutar con `dotnet bin\Debug\netcoreapp1.0\Hello.dll` en Windows, y `dotnet bin/Debug/netcoreapp1.0/Hello.dll` en otros sistemas. Puede especificar un parámetro adicional en la línea de comandos (suponiendo que se encuentre en Windows):

    ```
    $ dotnet bin\Debug\netcoreapp1.0\Hello.dll .NET
    Hello .NET!
    ```

    Como escenario avanzado, es posible compilar la aplicación como un conjunto autocontenido de archivos específicos de la plataforma que se puede implementar y ejecutar en una máquina que no tiene necesariamente instalado .NET Core. Consulte [Implementación de aplicaciones .NET Core](../deploying/index.md) para más información.

### <a name="augmenting-the-program"></a>Aumento del programa

Vamos a cambiar un poco el archivo.  Los números de Fibonacci son divertidos, así que vamos a probarlos:

`Program.cs`:

```csharp
using static System.Console;

namespace ConsoleApplication
{
    public class Program
    {
        public static int FibonacciNumber(int n)
        {
            int a = 0;
            int b = 1;
            int tmp;
            
            for (int i = 0; i < n; i++)
            {
                tmp = a;
                a = b;
                b += tmp;
            }
            
            return a;   
        }
        
        public static void Main(string[] args)
        {
            WriteLine("Hello World!");
            WriteLine("Fibonacci Numbers 1-15:");
            
            for (int i = 0; i < 15; i++)
            {
                WriteLine($"{i+1}: {FibonacciNumber(i)}");
            }
        }
    }
}
```

Y se ejecuta el programa (suponiendo que se encuentra en Windows y que ha cambiado el nombre del directorio de proyecto a Fibonacci):

```
$ dotnet build
$ dotnet bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
1: 0
2: 1
3: 1
4: 2
5: 3
6: 5
7: 8
8: 13
9: 21
10: 34
11: 55
12: 89
13: 144
14: 233
15: 377
```

Y listo.  Puede aumentar `Program.cs` como desee.

## <a name="adding-some-new-files"></a>Adición de algunos archivos nuevos

Los archivos únicos están bien para los programas sencillos de uso único, pero lo más probable es que quiera desglosar todo en varios archivos si va a crear cualquier cosa que tenga varios componentes.  Varios archivos son una forma de hacerlo.

Cree un nuevo archivo y asígnele un único espacio de nombres:

```csharp
using System;

namespace NumberFun
{
    // code can go here
} 
```

Después, inclúyalo en el archivo `Program.cs`:

```csharp
using NumberFun;
```

Y por último, puede crear:

`$ dotnet build`

Ahora lo divertido: vamos a poner en funcionamiento el nuevo archivo.

### <a name="example-a-fibonacci-sequence-generator"></a>Ejemplo: Un generador de secuencia de Fibonacci

Supongamos que desea realizar una compilación fuera del ejemplo de Fibonacci anterior almacenando en caché algunos valores Fibonacci y agregando algún estilo recursivo.  El código para un [ejemplo mejor de Fibonacci](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetterMsBuild) podría usar un nuevo archivo `FibonacciGenerator.cs` con el siguiente código.

```csharp
using System;
using System.Collections.Generic;

namespace NumberFun
{
    public class FibonacciGenerator
    {
        private Dictionary<int, int> _cache = new Dictionary<int, int>();
        
        private int Fib(int n) => n < 2 ? n : FibValue(n - 1) + FibValue(n - 2);
        
        private int FibValue(int n)
        {
            if (!_cache.ContainsKey(n))
            {
                _cache.Add(n, Fib(n));
            }
            
            return _cache[n];
        }
        
        public IEnumerable<int> Generate(int n)
        {
            for (int i = 0; i < n; i++)
            {
                yield return FibValue(i);
            }
        }
    }
}
```

Ahora, ajuste el método `Main()` en su archivo `Program.cs`, tal como se muestra a continuación.

```csharp
using System;
using NumberFun;

class Program
{
    static void Main(string[] args)
    {
        var generator = new FibonacciGenerator();
        foreach (var digit in generator.Generate(15))
        {
            Console.WriteLine(digit);
        }
    }
}
```

Por último, ejecute la aplicación.

```
$ dotnet run
0
1
1
2
3
5
8
13
21
34
55
89
144
233
377
```

Y listo.

## <a name="conclusion"></a>Conclusión
 
Espero que esta guía le ha ayudado a aprender a crear una aplicación de consola .NET Core, desde los aspectos básicos hasta un sistema de varios proyectos con pruebas unitarias.  El siguiente paso consiste en crear increíbles aplicaciones de consola usted mismo.
 
Si le interesa un ejemplo más avanzado de una aplicación de consola, consulte el tutorial: [Organización y prueba de proyectos con la línea de comandos de .NET Core (SDK Preview 3)](using-with-xplat-cli-msbuild-folders.md).



<!--HONumber=Nov16_HO3-->


