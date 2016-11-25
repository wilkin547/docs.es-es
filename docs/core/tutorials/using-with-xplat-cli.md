---
title: "Introducción a .NET Core en Windows/Linux/macOS con la línea de comandos"
description: "Introducción a .NET Core en Windows, Linux o macOS con la interfaz de línea de comandos (CLI) de .NET Core"
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: be988f09-7349-43b0-97fb-3a703d4587ce
translationtype: Human Translation
ms.sourcegitcommit: 37e14d5cdf1593f6a8b1ecee9d9828647b023548
ms.openlocfilehash: 5493ccb77e62d20d5101728ef8ab1744ea697fb8

---

# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a>Introducción a .NET Core en Windows/Linux/macOS con la línea de comandos

Esta guía le enseñará a usar las herramientas de la CLI de .NET Core para crear aplicaciones de consola básicas multiplataforma.

Si no está familiarizado con el conjunto de herramientas de la CLI de .NET Core, consulte [la información general del SDK de .NET Core](../sdk.md).

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, asegúrese de que cuenta con las [herramientas más recientes de la CLI de .NET Core](https://www.microsoft.com/net/core). También necesitará un editor de texto.

## <a name="hello-console-app"></a>Hola, aplicación de consola

En primer lugar, vaya a una carpeta existente o cree una nueva con el nombre que desee. "Hello" es el nombre elegido para el código de ejemplo, que se puede encontrar [aquí](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/Hello).

Abra un símbolo del sistema y escriba lo siguiente:

```
$ dotnet new
$ dotnet restore
$ dotnet run
```

Veamos un tutorial rápido:

1. `$ dotnet new`

   [`dotnet new`](../tools/dotnet-new.md) crea un archivo `project.json` actualizado con las dependencias de NuGet necesarias para crear una aplicación de consola.  Además, se crea un archivo `Program.cs`, un archivo básico que contiene el punto de entrada para la aplicación.
   
   `project.json`:
   ```json
   {
        "version": "1.0.0-*",
        "buildOptions": {
            "emitEntryPoint": true
        },
        "dependencies": {
            "Microsoft.NETCore.App": {
                "type": "platform",
                "version": "1.0.0"
            }
        },   
       "frameworks": {
            "netcoreapp1.0": {
                "imports": "dnxcore50"
            }
        }
   }
   ```
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

2. `$ dotnet restore`

   [`dotnet restore`](../tools/dotnet-restore.md) llama a NuGet para restaurar el árbol de dependencias. NuGet analiza el archivo `project.json`, descarga las dependencias descritas en el archivo (o las toma de la memoria caché en la máquina) y escribe el archivo `project.lock.json`.  El archivo `project.lock.json` es necesario para realizar la compilación y ejecución.
   
   El archivo `project.lock.json` es un conjunto completo y persistente del gráfico de dependencias de NuGet y cualquier otra información que describa a una aplicación.  Este archivo se lee por otras herramientas, como `dotnet build` y `dotnet run`, que les permite procesar el código fuente con un conjunto correcto de las dependencias de NuGet y resoluciones de enlace.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) llama a `dotnet build` para asegurarse de que los destinos de la compilación se han creado y, a después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.
   
```
$ dotnet run
Hello, World!
```

También puede ejecutar [`dotnet build`](../tools/dotnet-build.md) para compilar el código sin ejecutar las aplicaciones de consola de la compilación.

### <a name="building-a-self-contained-application"></a>Creación de una aplicación independiente

Vamos a intentar compilar una aplicación independiente en lugar de una aplicación portátil. Puede leer más sobre los [tipos de portabilidad de .NET Core](../deploying/index.md) para obtener información acerca de los diferentes tipos de aplicación y cómo se implementan.

Debe realizar algunos cambios en el archivo `project.json` para dirigir las herramientas para crear una aplicación independiente. Puede verlos en el proyecto [HelloNative](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/HelloNative) del directorio de ejemplos.

El primer cambio consiste en quitar el elemento `"type": "platform"` de todas las dependencias. Hasta ahora la única dependencia de este proyecto es `"Microsoft.NETCore.App"`. La sección `dependencies` debe ser similar a esta:

```json
"dependencies": {
    "Microsoft.NETCore.App": {
        "version": "1.0.0"
    }
},
```

Después, debe agregar un nodo `runtimes` para especificar todos los entornos de ejecución de destino. Por ejemplo, el nodo `runtimes` siguiente indica al sistema de compilación que cree archivos ejecutables para la versión de 64 bits de Windows 10 y la versión de 64 bits de Mac OS X versión 10.11.
El sistema de compilación generará ejecutables nativos para el entorno actual. Si está siguiendo estos pasos en una máquina Windows, va a crear un ejecutable de Windows. Si está siguiendo estos pasos en un Mac, va a crear un ejecutable de OS X.

```json 
"runtimes": {
  "win10-x64": {},
  "osx.10.11-x64": {}
}
```

Consulte la lista completa de sistemas en tiempo de ejecución compatibles en el [catálogo de RID](../rid-catalog.md). 
 
Después de realizar estos dos cambios, ejecute `dotnet restore`, seguido de `dotnet build` para crear el ejecutable nativo. Después, ejecute el archivo ejecutable nativo generado. 

El ejemplo siguiente muestra los comandos para Windows. El ejemplo muestra dónde se genera el archivo ejecutable nativo y supone que el directorio del proyecto se denomina HelloNative.

```
$ dotnet restore 
$ dotnet build 
$ .\bin\Debug\netcoreapp1.0\win10-x64\HelloNative.exe
Hello World!
```

Puede observar que la aplicación nativa tarda ligeramente más tiempo en compilarse, pero se ejecuta un poco más rápido. Este comportamiento se vuelve más evidente a medida que crece la aplicación.

El proceso de compilación genera varios archivos más cuando `project.json` crea una compilación nativa. Estos archivos se crean en `bin\Debug\netcoreapp1.0\<platform>` donde `<platform>` es el RID elegido. Además del `HelloNative.dll` del proyecto, hay un `HelloNative.exe` que carga el tiempo de ejecución e inicia la aplicación.
Tenga en cuenta que el nombre de la aplicación generada ha cambiado porque ha cambiado el nombre del directorio de proyecto.  

Puede empaquetar esta aplicación para ejecutarla en una máquina que no incluya el sistema en tiempo de ejecución de .NET.
Puede hacerlo mediante el comando `dotnet publish`. El comando `dotnet publish` crea un nuevo subdirectorio en el directorio `./bin/Debug/netcoreapp1.0/<platform>` llamado `publish`. Copia el archivo ejecutable, todos los archivos DLL dependientes y la plataforma en este subdirectorio. Puede empaquetar ese directorio en otro equipo (o en un contenedor) y ejecutar la aplicación allí. 

Vamos a compararlo con el comportamiento de `dotnet publish` en el primer ejemplo de Hello World. La aplicación es una *aplicación portable*, que es el tipo predeterminado de aplicación para .NET Core. Una aplicación portable requiere que .NET Core esté instalado en el equipo de destino. Las aplicaciones portables se pueden crear en una máquina y ejecutarse en cualquier lugar. Las aplicaciones nativas deben crearse de manera independiente para cada máquina de destino. `dotnet publish`crea un directorio que tiene el archivo DLL de la aplicación, así como los archivos DLL dependientes que no forman parte de la instalación de la plataforma.

### <a name="augmenting-the-program"></a>Aumento del programa

Vamos a cambiar un poco el archivo.  Los números de Fibonacci son divertidos, así que vamos a probarlos (con la versión nativa):

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
$ .\bin\Debug\netcoreapp1.0\win10-x64\Fibonacci.exe
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
using static System.Console;
using NumberFun;
```

Y por último, puede crear:

`$ dotnet build`

Ahora lo divertido: vamos a poner en funcionamiento el nuevo archivo.

### <a name="example-a-fibonacci-sequence-generator"></a>Ejemplo: Un generador de secuencia de Fibonacci

Supongamos que desea realizar una compilación fuera del [ejemplo de Fibonacci](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/Fibonacci) anterior almacenando en caché algunos valores Fibonacci y agregando algún estilo recursivo.  El código para un [ejemplo de Fibonacci mejor](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/FibonacciBetter) podría ser similar al siguiente:

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

Tenga en cuenta que el uso de `Dictionary<int, int>` y `IEnumerable<int>` implica la incorporación del espacio de nombres `System.Collections`.
El paquete `Microsoft.NetCore.App` es un *metapaquete* que contiene muchos de los ensamblados básicos de .NET Framework. Al incluir este metapaquete, ya ha incluido el ensamblado `System.Collections.dll` como parte de su proyecto. Puede comprobarlo mediante la ejecución de `dotnet publish` y el examen de los archivos que forman parte del paquete instalado. Verá `System.Collections.dll` en la lista. 

```json
{ 
  "version": "1.0.0-*", 
  "buildOptions": { 
    "debugType": "portable", 
    "emitEntryPoint": true 
  }, 
  "dependencies": {}, 
  "frameworks": { 
    "netcoreapp1.0": { 
      "dependencies": { 
        "Microsoft.NETCore.App": { 
          "version": "1.0.0" 
        } 
      }, 
      "imports": "dnxcore50" 
    } 
  },
  "runtimes": {
    "win10-x64": {},
    "osx.10.11-x64": {}
  }
}
```

Ahora, ajuste el método `Main()` en su archivo `Program.cs`, tal como se muestra a continuación. El ejemplo asume que `Program.cs` tiene una instrucción `using System;`. Si tiene una instrucción `using static System.Console;`, quite `Console.` en `Console.WriteLine`.  

```csharp
public static void Main(string[] args)
{
    var generator = new FibonacciGenerator();
    foreach (var digit in generator.Generate(15))
    {
        WriteLine(digit);
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

## <a name="using-folders-to-organize-code"></a>Uso de carpetas para organizar el código

Supongamos que desea introducir algunos nuevos tipos en los que trabajar.  Puede hacerlo agregando más archivos y asegurándose de concederles los espacios de nombres que se pueden incluir en el archivo `Program.cs`.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__project.json
```

Esto funciona bien cuando el tamaño del proyecto es relativamente pequeño.  Sin embargo, si tiene una aplicación de mayor tamaño con muchos tipos de datos diferentes y potencialmente varias capas, puede organizar las cosas de forma lógica.  Aquí es donde entran en juego las carpetas.  Puede seguir con [el proyecto de ejemplo NewTypes](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypes) que trata esta guía o bien crear sus propios archivos y carpetas.

Para empezar, cree una nueva carpeta en la raíz del proyecto.  `/Model`se elige aquí.

```
/NewTypes
|__/Model
|__Program.cs
|__project.json
```

Ahora agregue algunos tipos nuevos a la carpeta:

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__project.json
```

Ahora, como si fueran archivos del mismo directorio, asígneles a todos el mismo espacio de nombres para incluirlos en su `Program.cs`.

### <a name="example-pet-types"></a>Ejemplo: Tipos de mascota

Este ejemplo crea dos nuevos tipos, `Dog` y `Cat`, y tienen que implementar una interfaz, `IPet`.

Estructura de carpetas:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__project.json
```

`IPet.cs`:
```csharp
using System;

namespace Pets
{
    public interface IPet
    {
        string TalkToOwner();
    }
}
```

`Dog.cs`:
```csharp
using System;

namespace Pets
{
    public class Dog : IPet
    {
        public string TalkToOwner() => "Woof!";
    }
}
```

`Cat.cs`:
```csharp
using System;

namespace Pets
{
    public class Cat : IPet
    {
        public string TalkToOwner() => "Meow!";
    }
}
```

`Program.cs`:
```csharp
using System;
using Pets;
using System.Collections.Generic;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            List<IPet> pets = new List<IPet>
            {
                new Dog(),
                new Cat()  
            };
            
            foreach (var pet in pets)
            {
                Console.WriteLine(pet.TalkToOwner());
            }
        }
    }
}
```

`project.json`:
```json
{
  "version": "1.0.0-*",
  "buildOptions": {
    "emitEntryPoint": true
  },
  "dependencies": {
    "Microsoft.NETCore.App": {
      "type": "platform",
      "version": "1.0.0"
    }
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": "dnxcore50"
    }
  }
}
```

Y si se ejecuta:

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

Se pueden agregar nuevos tipos de mascotas (como un `Bird`), ampliando este proyecto.

## <a name="testing-your-console-app"></a>Prueba de la aplicación de consola

Probablemente estará esperando probar sus proyectos en algún momento.  Esta es una buena forma de hacerlo:

1. Mueva cualquier código fuente del proyecto existente a una nueva carpeta `src`.

   ```
   /Project
   |__/src
   ```

2. Cree un directorio `/test`.

   ```
   /Project
   |__/src
   |__/test
   ```

3. Cree un nuevo archivo `global.json`:

   ```
   /Project
   |__/src
   |__/test
   |__global.json
   ```

   `global.json`:
   ```json
   {
      "projects": [
         "src", "test"
      ]
   }
   ```

   Este archivo indica al sistema de compilación que se trata de un sistema de varios proyectos, que le permite buscar dependencias en algo más que en la carpeta actual en la que está ejecutándose.  Esto es importante porque permite colocar una dependencia en el código sometido a prueba en su proyecto de prueba.
   
### <a name="example-extending-the-newtypes-project"></a>Ejemplo: Ampliación del proyecto NewTypes

Ahora que el sistema del proyecto está en su lugar, puede crear el proyecto de prueba y empezar a escribir pruebas.  De ahora en adelante en esta guía se va a utilizar y a ampliar [el proyecto de tipos de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypes).  Además, utilizará la plataforma de pruebas [Xunit](https://xunit.github.io/).  No dude en seguir leyendo o crear su propio sistema de varios proyectos con las pruebas.


La estructura de todo el proyecto debe tener este aspecto:

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__project.json
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__project.json
|__global.json
```

Hay dos cosas nuevas que debe asegurarse de que las tiene en su proyecto de prueba:

1. Un archivo `project.json` correcto con lo siguiente:

   * Una referencia a `xunit`
   * Una referencia a `dotnet-test-xunit`
   * Una referencia al espacio de nombres correspondiente al código sometido a prueba

2. Una clase de prueba de Xunit

`NewTypesTests/project.json`:
```json
{
  "version": "1.0.0-*",
  "testRunner": "xunit",

  "dependencies": {
    "Microsoft.NETCore.App": {
      "type":"platform",
      "version": "1.0.0"
    },
    "xunit":"2.2.0-beta2-build3300",
    "dotnet-test-xunit": "2.2.0-preview2-build1029",
    "NewTypes": "1.0.0"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "portable-net45+win8" 
      ]
    }
  }
}
```

`PetTests.cs`: 
```csharp
using System;
using Xunit;
using Pets;
public class PetTests
{
    [Fact]
    public void DogTalkToOwnerTest()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();
        
        Assert.Equal(expected, actual);
    }
    
    [Fact]
    public void CatTalkToOwnerTest()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();
        
        Assert.Equal(expected, actual);
    }
}
```
   
Ahora puede ejecutar las pruebas.  El comando [`dotnet test`](../tools/dotnet-test.md) ejecuta el ejecutor de pruebas que se ha especificado en el proyecto. Asegúrese de que comienza en el directorio de nivel superior.
 
```
$ dotnet restore
$ cd test/NewTypesTests
$ dotnet test
```
 
La salida debe ser similar a la que se muestra a continuación:
 
```
xUnit.net .NET CLI test runner (64-bit win10-x64)
  Discovering: NewTypesTests
  Discovered:  NewTypesTests
  Starting:    NewTypesTests
  Finished:    NewTypesTests
=== TEST EXECUTION SUMMARY ===
   NewTypesTests  Total: 2, Errors: 0, Failed: 0, Skipped: 0, Time: 0.144s
SUMMARY: Total: 1 targets, Passed: 1, Failed: 0.
```
 
## <a name="conclusion"></a>Conclusión
 
Espero que esta guía le ha ayudado a aprender a crear una aplicación de consola .NET Core, desde los aspectos básicos hasta un sistema de varios proyectos con pruebas unitarias.  El siguiente paso consiste en crear increíbles aplicaciones de consola usted mismo.
 
Si le interesa un ejemplo más avanzado de una aplicación de consola, consulte la [guía paso a paso avanzada sobre el uso de las herramientas CLI para escribir aplicaciones de consola](cli-console-app-tutorial-advanced.md).



<!--HONumber=Nov16_HO3-->


