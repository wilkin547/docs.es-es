---
title: Creación de una aplicación de .NET Core con complementos
description: Obtenga información sobre cómo crear una aplicación .NET Core que admita complementos.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 10/16/2019
ms.openlocfilehash: d3b532ae72a80eef9603fc6f3ada8c11cae966dd
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98187904"
---
# <a name="create-a-net-core-application-with-plugins"></a>Creación de una aplicación de .NET Core con complementos

Este tutorial muestra cómo crear un contexto <xref:System.Runtime.Loader.AssemblyLoadContext> personalizado para cargar complementos. Se usa un elemento <xref:System.Runtime.Loader.AssemblyDependencyResolver> para resolver las dependencias del complemento. El tutorial aísla correctamente las dependencias del complemento de la aplicación host. Aprenderá a:

- Estructurar un proyecto para admitir los complementos.
- Crear un elemento <xref:System.Runtime.Loader.AssemblyLoadContext> personalizado para cargar cada complemento.
- Usar el tipo <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> para permitir que los complementos tengan dependencias.
- Crear complementos que se puedan implementar fácilmente con solo copiar los artefactos de compilación.

## <a name="prerequisites"></a>Requisitos previos

- Instale el [SDK de .NET 5](https://dotnet.microsoft.com/download) o una versión más reciente.

> [!NOTE]
> El código de ejemplo tiene como destino .NET 5, pero todas las características que usa se incluyeron en .NET Core 3.0 y están disponibles en todas las versiones de .NET desde entonces.

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

[!code-csharp[the-plugin-interface](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/PluginBase/ICommand.cs)]

Esta interfaz `ICommand` es la que van a implementar todos los complementos.

Ahora que se ha definido la interfaz `ICommand`, el proyecto de aplicación se puede rellenar un poco más. Agregue una referencia desde el proyecto `AppWithPlugin` al proyecto `PluginBase` con el comando `dotnet add AppWithPlugin/AppWithPlugin.csproj reference PluginBase/PluginBase.csproj` desde la carpeta raíz.

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

[!code-csharp[loading-plugins](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/AppWithPlugin/PluginLoadContext.cs)]

El tipo `PluginLoadContext` se deriva de <xref:System.Runtime.Loader.AssemblyLoadContext>. El tipo `AssemblyLoadContext` es un tipo especial en el runtime que permite a los desarrolladores aislar los ensamblados cargados en grupos diferentes para asegurarse de que las versiones de ensamblado no entren en conflicto. Además, un elemento `AssemblyLoadContext` personalizado puede elegir otras rutas de acceso desde las que cargar los ensamblados e invalidar el comportamiento predeterminado. El elemento `PluginLoadContext` usa una instancia del tipo `AssemblyDependencyResolver` que se introdujo en .NET Core 3.0 para resolver los nombres de ensamblado en rutas de acceso. El objeto `AssemblyDependencyResolver` se construye con la ruta de acceso a una biblioteca de clases .NET. Resuelve los ensamblados y las bibliotecas nativas en sus rutas de acceso relativas en función del archivo *deps.json* para la biblioteca de clases cuya ruta de acceso se haya pasado al constructor `AssemblyDependencyResolver`. El elemento `AssemblyLoadContext` personalizado permite que los complementos tengan sus propias dependencias y el elemento `AssemblyDependencyResolver` facilita la tarea de cargar correctamente las dependencias.

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

## <a name="simple-plugin-with-no-dependencies"></a>Complemento simple sin dependencias

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

[!code-csharp[the-hello-plugin](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/HelloPlugin/HelloCommand.cs)]

Ahora, abra el archivo *HelloPlugin.csproj*. Debería tener un aspecto similar al siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net5</TargetFramework>
  </PropertyGroup>

</Project>

```

Entre las etiquetas `<Project>`, agregue los elementos siguientes:

```xml
<ItemGroup>
    <ProjectReference Include="..\PluginBase\PluginBase.csproj">
        <Private>false</Private>
        <ExcludeAssets>runtime</ExcludeAssets>
    </ProjectReference>
</ItemGroup>
```

El elemento `<Private>false</Private>` es importante. Indica a MSBuild que no copie *PluginBase.dll* en el directorio de salida para HelloPlugin. Si el ensamblado *PluginBase.dll* está presente en el directorio de salida, `PluginLoadContext` encontrará el ensamblado y lo cargará cuando cargue el ensamblado *HelloPlugin.dll*. En este momento, el tipo `HelloPlugin.HelloCommand` implementará la interfaz `ICommand` de *PluginBase.dll* en el directorio de salida del proyecto `HelloPlugin`, no la interfaz `ICommand` que se carga en el contexto de carga predeterminado. Como el runtime considera que estos dos tipos son tipos diferentes de ensamblados distintos, el método `AppWithPlugin.Program.CreateCommands` no encontrará los comandos. Como resultado, los metadatos `<Private>false</Private>` son necesarios para la referencia al ensamblado que contiene las interfaces de complemento.

Del mismo modo, el elemento `<ExcludeAssets>runtime</ExcludeAssets>` también es importante si `PluginBase` hace referencia a otros paquetes. Esta configuración tiene el mismo efecto que `<Private>false</Private>` pero funciona en las referencias de paquete que pueden incluir el proyecto `PluginBase` o una de sus dependencias.

Ahora que se ha completado el proyecto `HelloPlugin`, se debe actualizar el proyecto `AppWithPlugin` para saber dónde se puede encontrar el complemento `HelloPlugin`. Después del comentario `// Paths to plugins to load`, agregue `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` (esta ruta de acceso podría ser diferente en función de la versión de .NET Core que use) como un elemento de la matriz de `pluginPaths`.

## <a name="plugin-with-library-dependencies"></a>Complemento con dependencias de biblioteca

Casi todos los complementos son más complejos que un simple ejemplo "Hola mundo", y muchos tienen dependencias en otras bibliotecas. En los proyectos de complemento `JsonPlugin` y `OldJson` del ejemplo se muestran dos ejemplos de complementos con dependencias de paquetes NuGet en `Newtonsoft.Json`. Los propios archivos del proyecto no tienen información especial para las referencias del proyecto y, después de agregar las rutas de acceso de complemento a la matriz `pluginPaths`, los complementos se ejecutan perfectamente, incluso en la misma ejecución de la aplicación AppWithPlugin. Pero estos proyectos no copian los ensamblados a los que se hace referencia en su directorio de salida, por lo que los ensamblados deben estar presentes en la máquina del usuario para que los complementos funcionen. Hay dos maneras de solucionar este problema. La primera opción consiste en usar el comando `dotnet publish` para publicar la biblioteca de clases. Como alternativa, si quiere poder usar la salida de `dotnet build` para el complemento, puede agregar la propiedad `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` entre las etiquetas `<PropertyGroup>` del archivo de proyecto del complemento. Vea el proyecto de complemento `XcopyablePlugin` para obtener un ejemplo.

## <a name="other-examples-in-the-sample"></a>Otros ejemplos en la muestra

Puede encontrar el código fuente completo para este tutorial en el [repositorio dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin). El ejemplo completo incluye algunos otros ejemplos de comportamiento `AssemblyDependencyResolver`. Por ejemplo, el objeto `AssemblyDependencyResolver` también puede resolver las bibliotecas nativas, así como los ensamblados satélite localizados en paquetes NuGet. `UVPlugin` y `FrenchPlugin` en el repositorio de ejemplos demuestran estos escenarios.

## <a name="reference-a-plugin-interface-from-a-nuget-package"></a>Referencia a una interfaz de complemento desde un paquete NuGet

Supongamos que hay una aplicación A que tiene una interfaz de complemento definida en el paquete NuGet denominado `A.PluginBase`. ¿Cómo se hace referencia correctamente al paquete en el proyecto de complemento? Para las referencias de proyecto, el uso de los metadatos `<Private>false</Private>` en el elemento `ProjectReference` del archivo de proyecto ha impedido que el archivo DLL se copiara en la salida.

Para hacer referencia correctamente al paquete `A.PluginBase`, le interesará cambiar el elemento `<PackageReference>` del archivo de proyecto por lo siguiente:

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

Esto evita que los ensamblados `A.PluginBase` se copien en el directorio de salida del complemento y asegura que el complemento use la versión de `A.PluginBase` la aplicación A.

## <a name="plugin-target-framework-recommendations"></a>Recomendaciones para plataformas de destino de complemento

Como en la carga de dependencias de complemento se usa el archivo *deps.json*, hay un problema relacionado con la plataforma de destino del complemento. En concreto, los complementos deben tener como destino un entorno de ejecución como .NET 5, en lugar de una versión de .NET Standard. El archivo *.deps.json* se genera en función de la plataforma de destino del proyecto y, como muchos paquetes compatibles con .NET Standard incluyen ensamblados de referencia para compilar en .NET Standard y ensamblados de implementación para runtimes específicos, es posible que el archivo *.deps.json* no vea correctamente los ensamblados de implementación, o bien que tome la versión de .NET Standard de un ensamblado en lugar de la de .NET Core que se espera.

## <a name="plugin-framework-references"></a>Referencias del marco de trabajo de complementos

En la actualidad, los complementos no pueden introducir nuevos marcos en el proceso. Por ejemplo, no puede cargar un complemento que use el marco `Microsoft.AspNetCore.App` en una aplicación en la que solo se use el marco `Microsoft.NETCore.App` raíz. La aplicación host debe declarar referencias a todos los marcos de trabajo necesarios para los complementos.
