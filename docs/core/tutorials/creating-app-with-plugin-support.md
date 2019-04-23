---
title: Creación de una aplicación de .NET Core con complementos
description: Obtenga información sobre cómo crear una aplicación .NET Core que admita complementos.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/28/2019
ms.openlocfilehash: a9431ee28c7df21a8688f845be20e062eca21887
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773433"
---
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="74254-103">Creación de una aplicación de .NET Core con complementos</span><span class="sxs-lookup"><span data-stu-id="74254-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="74254-104">En este tutorial se le enseñará a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="74254-105">Estructurar un proyecto para admitir los complementos.</span><span class="sxs-lookup"><span data-stu-id="74254-105">Structure a project to support plugins.</span></span>
- <span data-ttu-id="74254-106">Crear un elemento <xref:System.Runtime.Loader.AssemblyLoadContext> personalizado para cargar cada complemento.</span><span class="sxs-lookup"><span data-stu-id="74254-106">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="74254-107">Usar el tipo `System.Runtime.Loader.AssemblyDependencyResolver` para permitir que los complementos tengan dependencias.</span><span class="sxs-lookup"><span data-stu-id="74254-107">Use the `System.Runtime.Loader.AssemblyDependencyResolver` type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="74254-108">Crear complementos que se puedan implementar fácilmente con solo copiar los artefactos de compilación.</span><span class="sxs-lookup"><span data-stu-id="74254-108">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74254-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="74254-109">Prerequisites</span></span>

- <span data-ttu-id="74254-110">Instale el [SDK de la versión preliminar 2 de .NET Core 3.0](https://www.microsoft.com/net/core) o una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="74254-110">Install the [.NET Core 3.0 Preview 2 SDK](https://www.microsoft.com/net/core) or a newer version.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="74254-111">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="74254-111">Create the application</span></span>

<span data-ttu-id="74254-112">El primer paso es crear la aplicación:</span><span class="sxs-lookup"><span data-stu-id="74254-112">The first step is to create the application:</span></span>

1. <span data-ttu-id="74254-113">Cree una carpeta y, en ella, ejecute `dotnet new console -o AppWithPlugin`.</span><span class="sxs-lookup"><span data-stu-id="74254-113">Create a new folder, and in that folder run `dotnet new console -o AppWithPlugin`.</span></span> 
2. <span data-ttu-id="74254-114">Para facilitar la compilación del proyecto, cree un archivo de solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="74254-114">To make building the project easier, create a Visual Studio solution file.</span></span> <span data-ttu-id="74254-115">Ejecute `dotnet new sln` en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="74254-115">Run `dotnet new sln` in the same folder.</span></span> 
3. <span data-ttu-id="74254-116">Ejecute `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` para agregar el proyecto de aplicación a la solución.</span><span class="sxs-lookup"><span data-stu-id="74254-116">Run `dotnet sln add AppWithPlugin/AppWithPlugin.csproj` to add the app project to the solution.</span></span>

<span data-ttu-id="74254-117">Ahora ya se puede rellenar el esqueleto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="74254-117">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="74254-118">Reemplace el código del archivo *AppWithPlugin/Program.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-118">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

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

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="74254-119">Creación de las interfaces de complemento</span><span class="sxs-lookup"><span data-stu-id="74254-119">Create the plugin interfaces</span></span>

<span data-ttu-id="74254-120">El paso siguiente en la creación de una aplicación con complementos consiste en definir la interfaz que los complementos tienen que implementar.</span><span class="sxs-lookup"><span data-stu-id="74254-120">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="74254-121">Se recomienda crear una biblioteca de clases que contenga los tipos que se van a usar para la comunicación entre la aplicación y los complementos.</span><span class="sxs-lookup"><span data-stu-id="74254-121">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="74254-122">Esta división permite publicar la interfaz de complemento como un paquete sin tener que enviar la aplicación completa.</span><span class="sxs-lookup"><span data-stu-id="74254-122">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="74254-123">En la carpeta raíz del proyecto, ejecute `dotnet new classlib -o PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="74254-123">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="74254-124">Además, ejecute `dotnet sln add PluginBase/PluginBase.csproj` para agregar el proyecto al archivo de la solución.</span><span class="sxs-lookup"><span data-stu-id="74254-124">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="74254-125">Elimine el archivo `PluginBase/Class1.cs` y cree uno en la carpeta `PluginBase` con el nombre `ICommand.cs` con la definición de interfaz siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-125">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/core/extensions/AppWithPlugin/PluginBase/ICommand.cs)]

<span data-ttu-id="74254-126">Esta interfaz `ICommand` es la que van a implementar todos los complementos.</span><span class="sxs-lookup"><span data-stu-id="74254-126">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="74254-127">Ahora que se ha definido la interfaz `ICommand`, el proyecto de aplicación se puede rellenar un poco más.</span><span class="sxs-lookup"><span data-stu-id="74254-127">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="74254-128">Agregue una referencia desde el proyecto `AppWithPlugin` al proyecto `PluginBase` con el comando `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj` desde la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="74254-128">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin\AppWithPlugin.csproj reference PluginBase\PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="74254-129">Reemplace el comentario `// Load commands from plugins` con el fragmento de código siguiente para habilitarlo para cargar complementos desde rutas de acceso de archivo determinadas:</span><span class="sxs-lookup"><span data-stu-id="74254-129">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

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

<span data-ttu-id="74254-130">Después, reemplace el comentario `// Output the loaded commands` por el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-130">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="74254-131">Reemplace el comentario `// Execute the command with the name passed as an argument` por el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-131">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="74254-132">Y, por último, agregue los métodos estáticos denominados `LoadPlugin` y `CreateCommands` a la clase `Program`, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="74254-132">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

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

## <a name="load-plugins"></a><span data-ttu-id="74254-133">Carga de complementos</span><span class="sxs-lookup"><span data-stu-id="74254-133">Load plugins</span></span>

<span data-ttu-id="74254-134">Ahora la aplicación puede cargar correctamente y crear instancias de los comandos a partir de los ensamblados de complemento cargados, pero todavía no puede cargar los ensamblados de complemento.</span><span class="sxs-lookup"><span data-stu-id="74254-134">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it is still unable to load the plugin assemblies.</span></span> <span data-ttu-id="74254-135">Cree un archivo denominado *PluginLoadContext.cs* en la carpeta *AppWithPlugin* con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-135">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/core/extensions/AppWithPlugin/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="74254-136">El tipo `PluginLoadContext` se deriva de <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="74254-136">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="74254-137">El tipo `AssemblyLoadContext` es un tipo especial en el tiempo de ejecución que permite a los desarrolladores aislar los ensamblados cargados en grupos diferentes para asegurarse de que las versiones de ensamblado no entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="74254-137">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions do not conflict.</span></span> <span data-ttu-id="74254-138">Además, un elemento `AssemblyLoadContext` personalizado puede elegir otras rutas de acceso desde las que cargar los ensamblados e invalidar el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74254-138">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="74254-139">El elemento `PluginLoadContext` usa una instancia del tipo `AssemblyDependencyResolver` que se introdujo en .NET Core 3.0 para resolver los nombres de ensamblado en rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="74254-139">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="74254-140">El objeto `AssemblyDependencyResolver` se construye con la ruta de acceso a una biblioteca de clases .NET.</span><span class="sxs-lookup"><span data-stu-id="74254-140">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="74254-141">Resuelve los ensamblados y las bibliotecas nativas en sus rutas de acceso relativas en función del archivo *deps.json* para la biblioteca de clases cuya ruta de acceso se haya pasado al constructor `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="74254-141">It resolves assemblies and native libraries to their relative paths based on the *deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="74254-142">El elemento `AssemblyLoadContext` personalizado permite que los complementos tengan sus propias dependencias y el elemento `AssemblyDependencyResolver` facilita la tarea de cargar correctamente las dependencias.</span><span class="sxs-lookup"><span data-stu-id="74254-142">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="74254-143">Ahora que el proyecto `AppWithPlugin` tiene el tipo `PluginLoadContext`, actualice el método `Program.LoadPlugin` con el cuerpo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-143">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

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

<span data-ttu-id="74254-144">Al usar una instancia de `PluginLoadContext` diferente para cada complemento, los complementos puede tener dependencias diferentes o incluso en conflicto sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="74254-144">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="create-a-simple-plugin-with-no-dependencies"></a><span data-ttu-id="74254-145">Creación de un complemento simple sin dependencias</span><span class="sxs-lookup"><span data-stu-id="74254-145">Create a simple plugin with no dependencies</span></span>

<span data-ttu-id="74254-146">En la carpeta raíz, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="74254-146">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="74254-147">Ejecute `dotnet new classlib -o HelloPlugin` para crear un proyecto de biblioteca de clases denominado `HelloPlugin`.</span><span class="sxs-lookup"><span data-stu-id="74254-147">Run `dotnet new classlib -o HelloPlugin` to create a new class library project named `HelloPlugin`.</span></span>
2. <span data-ttu-id="74254-148">Ejecute `dotnet sln add HelloPlugin/HelloPlugin.csproj` para agregar el proyecto a la solución `AppWithPlugin`.</span><span class="sxs-lookup"><span data-stu-id="74254-148">Run `dotnet sln add HelloPlugin/HelloPlugin.csproj` to add the project to the `AppWithPlugin` solution.</span></span> 
3. <span data-ttu-id="74254-149">Reemplace el archivo *HelloPlugin/Class1.cs* con un archivo denominado *HelloCommand.cs* con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-149">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/core/extensions/AppWithPlugin/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="74254-150">Ahora, abra el archivo *HelloPlugin.csproj*.</span><span class="sxs-lookup"><span data-stu-id="74254-150">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="74254-151">Debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-151">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="74254-152">Entre las etiquetas `<Project>`, agregue los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="74254-152">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
<ProjectReference Include="..\PluginBase\PluginBase.csproj">
    <Private>false</Private>
</ProjectReference>
</ItemGroup>
```

<span data-ttu-id="74254-153">El elemento `<Private>false</Private>` es muy importante.</span><span class="sxs-lookup"><span data-stu-id="74254-153">The `<Private>false</Private>` element is very important.</span></span> <span data-ttu-id="74254-154">Indica a MSBuild que no copie *PluginBase.dll* en el directorio de salida para HelloPlugin.</span><span class="sxs-lookup"><span data-stu-id="74254-154">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="74254-155">Si el ensamblado *PluginBase.dll* está presente en el directorio de salida, `PluginLoadContext` encontrará el ensamblado y lo cargará cuando cargue el ensamblado *HelloPlugin.dll*.</span><span class="sxs-lookup"><span data-stu-id="74254-155">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="74254-156">En este momento, el tipo `HelloPlugin.HelloCommand` implementará la interfaz `ICommand` de *PluginBase.dll* en el directorio de salida del proyecto `HelloPlugin`, no la interfaz `ICommand` que se carga en el contexto de carga predeterminado.</span><span class="sxs-lookup"><span data-stu-id="74254-156">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="74254-157">Como el tiempo de ejecución considera que estos dos tipos son tipos diferentes de ensamblados distintos, el método `AppWithPlugin.Program.CreateCommands` no encontrará los comandos.</span><span class="sxs-lookup"><span data-stu-id="74254-157">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method will not find the commands.</span></span> <span data-ttu-id="74254-158">Como resultado, los metadatos `<Private>false</Private>` son necesarios para la referencia al ensamblado que contiene las interfaces de complemento.</span><span class="sxs-lookup"><span data-stu-id="74254-158">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="74254-159">Ahora que se ha completado el proyecto `HelloPlugin`, se debe actualizar el proyecto `AppWithPlugin` para saber dónde se puede encontrar el complemento `HelloPlugin`.</span><span class="sxs-lookup"><span data-stu-id="74254-159">Now that the `HelloPlugin` project is complete, we should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="74254-160">Después del comentario `// Paths to plugins to load`, agregue `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` como un elemento de la matriz `pluginPaths`.</span><span class="sxs-lookup"><span data-stu-id="74254-160">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` as an element of the `pluginPaths` array.</span></span>

## <a name="create-a-plugin-with-library-dependencies"></a><span data-ttu-id="74254-161">Creación de un complemento con dependencias de biblioteca</span><span class="sxs-lookup"><span data-stu-id="74254-161">Create a plugin with library dependencies</span></span>

<span data-ttu-id="74254-162">Casi todos los complementos son más complejos que un simple ejemplo "Hola mundo", y muchos tienen dependencias en otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="74254-162">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="74254-163">En los proyectos de complemento `JsonPlugin` y `OldJson` del ejemplo se muestran dos ejemplos de complementos con dependencias de paquetes NuGet en `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="74254-163">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="74254-164">Los propios archivos de proyecto no tienen información especial para las referencias del proyecto, y (después de agregar las rutas de acceso de complemento a la matriz `pluginPaths`) los complementos se ejecutan perfectamente, incluso en la misma ejecución de la aplicación AppWithPlugin.</span><span class="sxs-lookup"><span data-stu-id="74254-164">The project files themselves do not have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="74254-165">Pero estos proyectos no copian los ensamblados a los que se hace referencia en su directorio de salida, por lo que los ensamblados deben estar presentes en el equipo del usuario para que los complementos funcionen.</span><span class="sxs-lookup"><span data-stu-id="74254-165">However, these projects do not copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="74254-166">Hay dos maneras de solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="74254-166">There are two ways to work around this problem.</span></span> <span data-ttu-id="74254-167">La primera opción consiste en usar el comando `dotnet publish` para publicar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="74254-167">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="74254-168">Como alternativa, si quiere poder usar la salida de `dotnet build` para el complemento, puede agregar la propiedad `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` entre las etiquetas `<PropertyGroup>` del archivo de proyecto del complemento.</span><span class="sxs-lookup"><span data-stu-id="74254-168">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="74254-169">Vea el proyecto de complemento `XcopyablePlugin` para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="74254-169">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-plugin-examples-in-the-sample"></a><span data-ttu-id="74254-170">Otros ejemplos de complemento en el ejemplo</span><span class="sxs-lookup"><span data-stu-id="74254-170">Other plugin examples in the sample</span></span>

<span data-ttu-id="74254-171">Puede encontrar el código fuente completo para este tutorial en el [repositorio dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="74254-171">The complete source code for this tutorial can be found in [the dotnet/samples repository](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span> <span data-ttu-id="74254-172">El ejemplo completo incluye algunos otros ejemplos de comportamiento `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="74254-172">The completed sample includes a few other examples of `AssemblyDependencyResolver` behavior.</span></span> <span data-ttu-id="74254-173">Por ejemplo, el objeto `AssemblyDependencyResolver` también puede resolver las bibliotecas nativas, así como los ensamblados satélite localizados en paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="74254-173">For example, the `AssemblyDependencyResolver` object can also resolve native libraries as well as localized satellite assemblies included in NuGet packages.</span></span> <span data-ttu-id="74254-174">`UVPlugin` y `FrenchPlugin` en el repositorio de ejemplos demuestran estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="74254-174">The `UVPlugin` and `FrenchPlugin` in the samples repository demonstrate these scenarios.</span></span>

## <a name="how-to-reference-a-plugin-interface-assembly-defined-in-a-nuget-package"></a><span data-ttu-id="74254-175">Procedimientos para hacer referencia a un ensamblado de interfaz de complemento definido en un paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="74254-175">How to reference a plugin interface assembly defined in a NuGet package</span></span>

<span data-ttu-id="74254-176">Supongamos que hay una aplicación A que tiene una interfaz de complemento definida en el paquete NuGet denominado `A.PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="74254-176">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="74254-177">¿Cómo se hace referencia correctamente al paquete en el proyecto de complemento?</span><span class="sxs-lookup"><span data-stu-id="74254-177">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="74254-178">Para las referencias de proyecto, el uso de los metadatos `<Private>false</Private>` en el elemento `ProjectReference` del archivo de proyecto ha impedido que el archivo DLL se copiara en la salida.</span><span class="sxs-lookup"><span data-stu-id="74254-178">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="74254-179">Para hacer referencia correctamente al paquete `A.PluginBase`, le interesará cambiar el elemento `<PackageReference>` del archivo de proyecto por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="74254-179">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="74254-180">Esto evita que los ensamblados `A.PluginBase` se copien en el directorio de salida del complemento y asegura que el complemento use la versión de `A.PluginBase` la aplicación A.</span><span class="sxs-lookup"><span data-stu-id="74254-180">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="74254-181">Recomendaciones para plataformas de destino de complemento</span><span class="sxs-lookup"><span data-stu-id="74254-181">Plugin target framework recommendations</span></span>

<span data-ttu-id="74254-182">Como en la carga de dependencias de complemento se usa el archivo *deps.json*, hay un problema relacionado con la plataforma de destino del complemento.</span><span class="sxs-lookup"><span data-stu-id="74254-182">Because plugin dependency loading uses the *deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="74254-183">En concreto, los complementos deben tener como destino un runtime como .NET Core 3.0, en lugar de una versión de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="74254-183">Specifically, your plugins should target a runtime, such as .NET Core 3.0, instead of a version of .NET Standard.</span></span> <span data-ttu-id="74254-184">El archivo `deps.json` se genera en función de la plataforma de destino del proyecto y, como muchos paquetes compatibles con .NET Standard incluyen ensamblados de referencia para compilar en .NET Standard y ensamblados de implementación para runtimes específicos, es posible que el archivo `deps.json` no vea correctamente los ensamblados de implementación, o bien que tome la versión de .NET Standard de un ensamblado en lugar de la de .NET Core que se espera.</span><span class="sxs-lookup"><span data-stu-id="74254-184">The `deps.json` file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the `deps.json` may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>
