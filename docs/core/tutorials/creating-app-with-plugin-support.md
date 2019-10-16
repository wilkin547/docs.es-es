---
title: Creación de una aplicación de .NET Core con complementos
description: Obtenga información sobre cómo crear una aplicación .NET Core que admita complementos.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: 54f616a7b2b20b7682963e9f5d503878bb512c90
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250159"
---
# <a name="create-a-net-core-application-with-plugins"></a>Creación de una aplicación de .NET Core con complementos

En este tutorial se le enseñará a hacer lo siguiente:

- Estructurar un proyecto para admitir los complementos.
- Crear un elemento <xref:System.Runtime.Loader.AssemblyLoadContext> personalizado para cargar cada complemento.
- Usar el tipo `System.Runtime.Loader.AssemblyDependencyResolver` para permitir que los complementos tengan dependencias.
- Crear complementos que se puedan implementar fácilmente con solo copiar los artefactos de compilación.

## <a name="prerequisites"></a>Requisitos previos

- Instale [.NET Core 3.0](https://dotnet.microsoft.com/download) o una versión más reciente.

## <a name="create-the-application"></a>Crear la aplicación

El primer paso es crear la aplicación:

1. Cree una carpeta nueva y, en ella, ejecute el siguiente comando:

    ```dotnetcli
    dotnet new console -o AppWithPlugin
    ```

2. Para facilitar la compilación del proyecto, cree un archivo de solución de Visual Studio en la misma carpeta. Ejecute el siguiente comando:

    ```dotnetcli
    dotnet new sln
    ```

3. Ejecute el siguiente comando para agregar el proyecto de aplicación a la solución:

    ```dotnetcli
    dotnet sln add AppWithPlugin/AppWithPlugin.csproj
    ```

Ahora ya se puede rellenar el esqueleto de la aplicación. Reemplace el código del archivo *AppWithPlugin/Program.cs* con el código siguiente:

```csharp
using PluginBase;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Reflection;

namespace AppWithPlugin
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                if (args.Length == 1 && args[0] == "/d")
                {
                    Console.WriteLine("Waiting for any key...");
                    Console.ReadLine();
                }

                // Load commands from plugins.

                if (args.Length == 0)
                {
                    Console.WriteLine("Commands: ");
                    // Output the loaded commands.
                }
                else
                {
                    foreach (string commandName in args)
                    {
                        Console.WriteLine($"-- {commandName} --");

                        // Execute the command with the name passed as an argument.

                        Console.WriteLine();
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex);
            }
        }
    }
}

```

## <a name="create-the-plugin-interfaces"></a>Creación de las interfaces de complemento

El paso siguiente en la creación de una aplicación con complementos consiste en definir la interfaz que los complementos tienen que implementar. Se recomienda crear una biblioteca de clases que contenga los tipos que se van a usar para la comunicación entre la aplicación y los complementos. Esta división permite publicar la interfaz de complemento como un paquete sin tener que enviar la aplicación completa.

En la carpeta raíz del proyecto, ejecute `dotnet new classlib -o PluginBase`. Además, ejecute `dotnet sln add PluginBase/PluginBase.csproj` para agregar el proyecto al archivo de la solución. Elimine el archivo `PluginBase/Class1.cs` y cree uno en la carpeta `PluginBase` con el nombre `ICommand.cs` con la definición de interfaz siguiente:

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

Esta interfaz `ICommand` es la que van a implementar todos los complementos.

Ahora que se ha definido la interfaz `ICommand`, el proyecto de aplicación se puede rellenar un poco más. Agregue una referencia desde el proyecto `AppWithPlugin` al proyecto `PluginBase` con el comando `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` desde la carpeta raíz.

Reemplace el comentario `// Load commands from plugins` con el fragmento de código siguiente para habilitarlo para cargar complementos desde rutas de acceso de archivo determinadas:

```csharp
string[] pluginPaths = new string[]
{
    // Paths to plugins to load.
};

IEnumerable<ICommand> commands = pluginPaths.SelectMany(pluginPath =>
{
    Assembly pluginAssembly = LoadPlugin(pluginPath);
    return CreateCommands(pluginAssembly);
}).ToList();
```

Después, reemplace el comentario `// Output the loaded commands` por el fragmento de código siguiente:

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

Reemplace el comentario `// Execute the command with the name passed as an argument` por el fragmento de código siguiente:

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

Y, por último, agregue los métodos estáticos denominados `LoadPlugin` y `CreateCommands` a la clase `Program`, como se muestra aquí:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    throw new NotImplementedException();
}

static IEnumerable<ICommand> CreateCommands(Assembly assembly)
{
    int count = 0;

    foreach (Type type in assembly.GetTypes())
    {
        if (typeof(ICommand).IsAssignableFrom(type))
        {
            ICommand result = Activator.CreateInstance(type) as ICommand;
            if (result != null)
            {
                count++;
                yield return result;
            }
        }
    }

    if (count == 0)
    {
        string availableTypes = string.Join(",", assembly.GetTypes().Select(t => t.FullName));
        throw new ApplicationException(
            $"Can't find any type which implements ICommand in {assembly} from {assembly.Location}.\n" +
            $"Available types: {availableTypes}");
    }
}
```

## <a name="load-plugins"></a>Carga de complementos

Ahora la aplicación puede cargar correctamente y crear instancias de los comandos a partir de los ensamblados de complemento cargados, pero todavía no puede cargar los ensamblados de complemento. Cree un archivo denominado *PluginLoadContext.cs* en la carpeta *AppWithPlugin* con el contenido siguiente:

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

El tipo `PluginLoadContext` se deriva de <xref:System.Runtime.Loader.AssemblyLoadContext>. El tipo `AssemblyLoadContext` es un tipo especial en el tiempo de ejecución que permite a los desarrolladores aislar los ensamblados cargados en grupos diferentes para asegurarse de que las versiones de ensamblado no entren en conflicto. Además, un elemento `AssemblyLoadContext` personalizado puede elegir otras rutas de acceso desde las que cargar los ensamblados e invalidar el comportamiento predeterminado. El elemento `PluginLoadContext` usa una instancia del tipo `AssemblyDependencyResolver` que se introdujo en .NET Core 3.0 para resolver los nombres de ensamblado en rutas de acceso. El objeto `AssemblyDependencyResolver` se construye con la ruta de acceso a una biblioteca de clases .NET. Resuelve los ensamblados y las bibliotecas nativas en sus rutas de acceso relativas en función del archivo *deps.json* para la biblioteca de clases cuya ruta de acceso se haya pasado al constructor `AssemblyDependencyResolver`. El elemento `AssemblyLoadContext` personalizado permite que los complementos tengan sus propias dependencias y el elemento `AssemblyDependencyResolver` facilita la tarea de cargar correctamente las dependencias.

Ahora que el proyecto `AppWithPlugin` tiene el tipo `PluginLoadContext`, actualice el método `Program.LoadPlugin` con el cuerpo siguiente:

```csharp
static Assembly LoadPlugin(string relativePath)
{
    // Navigate up to the solution root
    string root = Path.GetFullPath(Path.Combine(
        Path.GetDirectoryName(
            Path.GetDirectoryName(
                Path.GetDirectoryName(
                    Path.GetDirectoryName(
                        Path.GetDirectoryName(typeof(Program).Assembly.Location)))))));

    string pluginLocation = Path.GetFullPath(Path.Combine(root, relativePath.Replace('\\', Path.DirectorySeparatorChar)));
    Console.WriteLine($"Loading commands from: {pluginLocation}");
    PluginLoadContext loadContext = new PluginLoadContext(pluginLocation);
    return loadContext.LoadFromAssemblyName(new AssemblyName(Path.GetFileNameWithoutExtension(pluginLocation)));
}
```

Al usar una instancia de `PluginLoadContext` diferente para cada complemento, los complementos puede tener dependencias diferentes o incluso en conflicto sin ningún problema.

## <a name="create-a-simple-plugin-with-no-dependencies"></a>Creación de un complemento simple sin dependencias

En la carpeta raíz, siga estos pasos:

1. Ejecute el siguiente comando para crear un nuevo proyecto de biblioteca de clases denominado `HelloPlugin`:
    
    ```dotnetcli
    dotnet new classlib -o HelloPlugin
    ```

2. Ejecute el siguiente comando para agregar el proyecto a la solución `AppWithPlugin`:

    ```dotnetcli
    dotnet sln add HelloPlugin/HelloPlugin.csproj
    ```

3. Reemplace el archivo *HelloPlugin/Class1.cs* con un archivo denominado *HelloCommand.cs* con el contenido siguiente:

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

Ahora, abra el archivo *HelloPlugin.csproj*. Debería tener un aspecto similar al siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

Entre las etiquetas `<Project>`, agregue los elementos siguientes:

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

El elemento `<Private>false</Private>` es muy importante. Indica a MSBuild que no copie *PluginBase.dll* en el directorio de salida para HelloPlugin. Si el ensamblado *PluginBase.dll* está presente en el directorio de salida, `PluginLoadContext` encontrará el ensamblado y lo cargará cuando cargue el ensamblado *HelloPlugin.dll*. En este momento, el tipo `HelloPlugin.HelloCommand` implementará la interfaz `ICommand` de *PluginBase.dll* en el directorio de salida del proyecto `HelloPlugin`, no la interfaz `ICommand` que se carga en el contexto de carga predeterminado. Como el tiempo de ejecución considera que estos dos tipos son tipos diferentes de ensamblados distintos, el método `AppWithPlugin.Program.CreateCommands` no encontrará los comandos. Como resultado, los metadatos `<Private>false</Private>` son necesarios para la referencia al ensamblado que contiene las interfaces de complemento.

Ahora que se ha completado el proyecto `HelloPlugin`, se debe actualizar el proyecto `AppWithPlugin` para saber dónde se puede encontrar el complemento `HelloPlugin`. Después del comentario `// Paths to plugins to load`, agregue `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` como un elemento de la matriz `pluginPaths`.

## <a name="create-a-plugin-with-library-dependencies"></a>Creación de un complemento con dependencias de biblioteca

Casi todos los complementos son más complejos que un simple ejemplo "Hola mundo", y muchos tienen dependencias en otras bibliotecas. En los proyectos de complemento `JsonPlugin` y `OldJson` del ejemplo se muestran dos ejemplos de complementos con dependencias de paquetes NuGet en `Newtonsoft.Json`. Los propios archivos de proyecto no tienen información especial para las referencias del proyecto, y (después de agregar las rutas de acceso de complemento a la matriz `pluginPaths`) los complementos se ejecutan perfectamente, incluso en la misma ejecución de la aplicación AppWithPlugin. Pero estos proyectos no copian los ensamblados a los que se hace referencia en su directorio de salida, por lo que los ensamblados deben estar presentes en el equipo del usuario para que los complementos funcionen. Hay dos maneras de solucionar este problema. La primera opción consiste en usar el comando `dotnet publish` para publicar la biblioteca de clases. Como alternativa, si quiere poder usar la salida de `dotnet build` para el complemento, puede agregar la propiedad `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` entre las etiquetas `<PropertyGroup>` del archivo de proyecto del complemento. Vea el proyecto de complemento `XcopyablePlugin` para obtener un ejemplo.

## <a name="other-plugin-examples-in-the-sample"></a>Otros ejemplos de complemento en el ejemplo

Puede encontrar el código fuente completo para este tutorial en el [repositorio dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin). El ejemplo completo incluye algunos otros ejemplos de comportamiento `AssemblyDependencyResolver`. Por ejemplo, el objeto `AssemblyDependencyResolver` también puede resolver las bibliotecas nativas, así como los ensamblados satélite localizados en paquetes NuGet. `UVPlugin` y `FrenchPlugin` en el repositorio de ejemplos demuestran estos escenarios.

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a>Procedimientos para hacer referencia a un ensamblado de interfaz de complemento definido en un paquete NuGet

Supongamos que hay una aplicación A que tiene una interfaz de complemento definida en el paquete NuGet denominado `A.PluginBase`. ¿Cómo se hace referencia correctamente al paquete en el proyecto de complemento? Para las referencias de proyecto, el uso de los metadatos `<Private>false</Private>` en el elemento `ProjectReference` del archivo de proyecto ha impedido que el archivo DLL se copiara en la salida.

Para hacer referencia correctamente al paquete `A.PluginBase`, le interesará cambiar el elemento `<PackageReference>` del archivo de proyecto por lo siguiente:

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

Esto evita que los ensamblados `A.PluginBase` se copien en el directorio de salida del complemento y asegura que el complemento use la versión de `A.PluginBase` la aplicación A.

## <a name="plugin-target-framework-recommendations"></a>Recomendaciones para plataformas de destino de complemento

Como en la carga de dependencias de complemento se usa el archivo *deps.json*, hay un problema relacionado con la plataforma de destino del complemento. En concreto, los complementos deben tener como destino un runtime como .NET Core 3.0, en lugar de una versión de .NET Standard. El archivo *.deps.json* se genera en función de la plataforma de destino del proyecto y, como muchos paquetes compatibles con .NET Standard incluyen ensamblados de referencia para compilar en .NET Standard y ensamblados de implementación para runtimes específicos, es posible que el archivo *.deps.json* no vea correctamente los ensamblados de implementación, o bien que tome la versión de .NET Standard de un ensamblado en lugar de la de .NET Core que se espera.
