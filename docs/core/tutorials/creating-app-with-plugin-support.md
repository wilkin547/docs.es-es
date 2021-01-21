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
# <a name="create-a-net-core-application-with-plugins"></a><span data-ttu-id="0612d-103">Creación de una aplicación de .NET Core con complementos</span><span class="sxs-lookup"><span data-stu-id="0612d-103">Create a .NET Core application with plugins</span></span>

<span data-ttu-id="0612d-104">Este tutorial muestra cómo crear un contexto <xref:System.Runtime.Loader.AssemblyLoadContext> personalizado para cargar complementos.</span><span class="sxs-lookup"><span data-stu-id="0612d-104">This tutorial shows you how to create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load plugins.</span></span> <span data-ttu-id="0612d-105">Se usa un elemento <xref:System.Runtime.Loader.AssemblyDependencyResolver> para resolver las dependencias del complemento.</span><span class="sxs-lookup"><span data-stu-id="0612d-105">An <xref:System.Runtime.Loader.AssemblyDependencyResolver> is used to resolve the dependencies of the plugin.</span></span> <span data-ttu-id="0612d-106">El tutorial aísla correctamente las dependencias del complemento de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="0612d-106">The tutorial correctly isolates the plugin's dependencies from the hosting application.</span></span> <span data-ttu-id="0612d-107">Aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="0612d-107">You'll learn how to:</span></span>

- <span data-ttu-id="0612d-108">Estructurar un proyecto para admitir los complementos.</span><span class="sxs-lookup"><span data-stu-id="0612d-108">Structure a project to support plugins.</span></span>
- <span data-ttu-id="0612d-109">Crear un elemento <xref:System.Runtime.Loader.AssemblyLoadContext> personalizado para cargar cada complemento.</span><span class="sxs-lookup"><span data-stu-id="0612d-109">Create a custom <xref:System.Runtime.Loader.AssemblyLoadContext> to load each plugin.</span></span>
- <span data-ttu-id="0612d-110">Usar el tipo <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> para permitir que los complementos tengan dependencias.</span><span class="sxs-lookup"><span data-stu-id="0612d-110">Use the <xref:System.Runtime.Loader.AssemblyDependencyResolver?displayProperty=fullName> type to allow plugins to have dependencies.</span></span>
- <span data-ttu-id="0612d-111">Crear complementos que se puedan implementar fácilmente con solo copiar los artefactos de compilación.</span><span class="sxs-lookup"><span data-stu-id="0612d-111">Author plugins that can be easily deployed by just copying the build artifacts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0612d-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0612d-112">Prerequisites</span></span>

- <span data-ttu-id="0612d-113">Instale el [SDK de .NET 5](https://dotnet.microsoft.com/download) o una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="0612d-113">Install the [.NET 5 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

> [!NOTE]
> <span data-ttu-id="0612d-114">El código de ejemplo tiene como destino .NET 5, pero todas las características que usa se incluyeron en .NET Core 3.0 y están disponibles en todas las versiones de .NET desde entonces.</span><span class="sxs-lookup"><span data-stu-id="0612d-114">The sample code targets .NET 5, but all the features it uses were introduced in .NET Core 3.0 and are available in all .NET releases since then.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="0612d-115">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="0612d-115">Create the application</span></span>

<span data-ttu-id="0612d-116">El primer paso es crear la aplicación:</span><span class="sxs-lookup"><span data-stu-id="0612d-116">The first step is to create the application:</span></span>

1. <span data-ttu-id="0612d-117">Cree una carpeta nueva y, en ella, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0612d-117">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new console -o AppWithPlugin
    ```

2. <span data-ttu-id="0612d-118">Para facilitar la compilación del proyecto, cree un archivo de solución de Visual Studio en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="0612d-118">To make building the project easier, create a Visual Studio solution file in the same folder.</span></span> <span data-ttu-id="0612d-119">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="0612d-119">Run the following command:</span></span>

    ```dotnetcli
    dotnet new sln
    ```

3. <span data-ttu-id="0612d-120">Ejecute el siguiente comando para agregar el proyecto de aplicación a la solución:</span><span class="sxs-lookup"><span data-stu-id="0612d-120">Run the following command to add the app project to the solution:</span></span>

    ```dotnetcli
    dotnet sln add AppWithPlugin/AppWithPlugin.csproj
    ```

<span data-ttu-id="0612d-121">Ahora ya se puede rellenar el esqueleto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0612d-121">Now we can fill in the skeleton of our application.</span></span> <span data-ttu-id="0612d-122">Reemplace el código del archivo *AppWithPlugin/Program.cs* con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-122">Replace the code in the *AppWithPlugin/Program.cs* file with the following code:</span></span>

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

## <a name="create-the-plugin-interfaces"></a><span data-ttu-id="0612d-123">Creación de las interfaces de complemento</span><span class="sxs-lookup"><span data-stu-id="0612d-123">Create the plugin interfaces</span></span>

<span data-ttu-id="0612d-124">El paso siguiente en la creación de una aplicación con complementos consiste en definir la interfaz que los complementos tienen que implementar.</span><span class="sxs-lookup"><span data-stu-id="0612d-124">The next step in building an app with plugins is defining the interface the plugins need to implement.</span></span> <span data-ttu-id="0612d-125">Se recomienda crear una biblioteca de clases que contenga los tipos que se van a usar para la comunicación entre la aplicación y los complementos.</span><span class="sxs-lookup"><span data-stu-id="0612d-125">We suggest that you make a class library that contains any types that you plan to use for communicating between your app and plugins.</span></span> <span data-ttu-id="0612d-126">Esta división permite publicar la interfaz de complemento como un paquete sin tener que enviar la aplicación completa.</span><span class="sxs-lookup"><span data-stu-id="0612d-126">This division allows you to publish your plugin interface as a package without having to ship your full application.</span></span>

<span data-ttu-id="0612d-127">En la carpeta raíz del proyecto, ejecute `dotnet new classlib -o PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="0612d-127">In the root folder of the project, run `dotnet new classlib -o PluginBase`.</span></span> <span data-ttu-id="0612d-128">Además, ejecute `dotnet sln add PluginBase/PluginBase.csproj` para agregar el proyecto al archivo de la solución.</span><span class="sxs-lookup"><span data-stu-id="0612d-128">Also, run `dotnet sln add PluginBase/PluginBase.csproj` to add the project to the solution file.</span></span> <span data-ttu-id="0612d-129">Elimine el archivo `PluginBase/Class1.cs` y cree uno en la carpeta `PluginBase` con el nombre `ICommand.cs` con la definición de interfaz siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-129">Delete the `PluginBase/Class1.cs` file, and create a new file in the `PluginBase` folder named `ICommand.cs` with the following interface definition:</span></span>

[!code-csharp[the-plugin-interface](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/PluginBase/ICommand.cs)]

<span data-ttu-id="0612d-130">Esta interfaz `ICommand` es la que van a implementar todos los complementos.</span><span class="sxs-lookup"><span data-stu-id="0612d-130">This `ICommand` interface is the interface that all of the plugins will implement.</span></span>

<span data-ttu-id="0612d-131">Ahora que se ha definido la interfaz `ICommand`, el proyecto de aplicación se puede rellenar un poco más.</span><span class="sxs-lookup"><span data-stu-id="0612d-131">Now that the `ICommand` interface is defined, the application project can be filled in a little more.</span></span> <span data-ttu-id="0612d-132">Agregue una referencia desde el proyecto `AppWithPlugin` al proyecto `PluginBase` con el comando `dotnet add AppWithPlugin/AppWithPlugin.csproj reference PluginBase/PluginBase.csproj` desde la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="0612d-132">Add a reference from the `AppWithPlugin` project to the `PluginBase` project with the `dotnet add AppWithPlugin/AppWithPlugin.csproj reference PluginBase/PluginBase.csproj`  command from the root folder.</span></span>

<span data-ttu-id="0612d-133">Reemplace el comentario `// Load commands from plugins` con el fragmento de código siguiente para habilitarlo para cargar complementos desde rutas de acceso de archivo determinadas:</span><span class="sxs-lookup"><span data-stu-id="0612d-133">Replace the `// Load commands from plugins` comment with the following code snippet to enable it to load plugins from given file paths:</span></span>

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

<span data-ttu-id="0612d-134">Después, reemplace el comentario `// Output the loaded commands` por el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-134">Then replace the `// Output the loaded commands` comment with the following code snippet:</span></span>

```csharp
foreach (ICommand command in commands)
{
    Console.WriteLine($"{command.Name}\t - {command.Description}");
}
```

<span data-ttu-id="0612d-135">Reemplace el comentario `// Execute the command with the name passed as an argument` por el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-135">Replace the `// Execute the command with the name passed as an argument` comment with the following snippet:</span></span>

```csharp
ICommand command = commands.FirstOrDefault(c => c.Name == commandName);
if (command == null)
{
    Console.WriteLine("No such command is known.");
    return;
}

command.Execute();
```

<span data-ttu-id="0612d-136">Y, por último, agregue los métodos estáticos denominados `LoadPlugin` y `CreateCommands` a la clase `Program`, como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="0612d-136">And finally, add static methods to the `Program` class named `LoadPlugin` and `CreateCommands`, as shown here:</span></span>

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

## <a name="load-plugins"></a><span data-ttu-id="0612d-137">Carga de complementos</span><span class="sxs-lookup"><span data-stu-id="0612d-137">Load plugins</span></span>

<span data-ttu-id="0612d-138">Ahora la aplicación puede cargar correctamente y crear instancias de los comandos a partir de los ensamblados de complemento cargados, pero todavía no puede cargar los ensamblados de complemento.</span><span class="sxs-lookup"><span data-stu-id="0612d-138">Now the application can correctly load and instantiate commands from loaded plugin assemblies, but it's still unable to load the plugin assemblies.</span></span> <span data-ttu-id="0612d-139">Cree un archivo denominado *PluginLoadContext.cs* en la carpeta *AppWithPlugin* con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-139">Create a file named *PluginLoadContext.cs* in the *AppWithPlugin* folder with the following contents:</span></span>

[!code-csharp[loading-plugins](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/AppWithPlugin/PluginLoadContext.cs)]

<span data-ttu-id="0612d-140">El tipo `PluginLoadContext` se deriva de <xref:System.Runtime.Loader.AssemblyLoadContext>.</span><span class="sxs-lookup"><span data-stu-id="0612d-140">The `PluginLoadContext` type derives from <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="0612d-141">El tipo `AssemblyLoadContext` es un tipo especial en el runtime que permite a los desarrolladores aislar los ensamblados cargados en grupos diferentes para asegurarse de que las versiones de ensamblado no entren en conflicto.</span><span class="sxs-lookup"><span data-stu-id="0612d-141">The `AssemblyLoadContext` type is a special type in the runtime that allows developers to isolate loaded assemblies into different groups to ensure that assembly versions don't conflict.</span></span> <span data-ttu-id="0612d-142">Además, un elemento `AssemblyLoadContext` personalizado puede elegir otras rutas de acceso desde las que cargar los ensamblados e invalidar el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0612d-142">Additionally, a custom `AssemblyLoadContext` can choose different paths to load assemblies from and override the default behavior.</span></span> <span data-ttu-id="0612d-143">El elemento `PluginLoadContext` usa una instancia del tipo `AssemblyDependencyResolver` que se introdujo en .NET Core 3.0 para resolver los nombres de ensamblado en rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="0612d-143">The `PluginLoadContext` uses an instance of the `AssemblyDependencyResolver` type introduced in .NET Core 3.0 to resolve assembly names to paths.</span></span> <span data-ttu-id="0612d-144">El objeto `AssemblyDependencyResolver` se construye con la ruta de acceso a una biblioteca de clases .NET.</span><span class="sxs-lookup"><span data-stu-id="0612d-144">The `AssemblyDependencyResolver` object is constructed with the path to a .NET class library.</span></span> <span data-ttu-id="0612d-145">Resuelve los ensamblados y las bibliotecas nativas en sus rutas de acceso relativas en función del archivo *deps.json* para la biblioteca de clases cuya ruta de acceso se haya pasado al constructor `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="0612d-145">It resolves assemblies and native libraries to their relative paths based on the *.deps.json* file for the class library whose path was passed to the `AssemblyDependencyResolver` constructor.</span></span> <span data-ttu-id="0612d-146">El elemento `AssemblyLoadContext` personalizado permite que los complementos tengan sus propias dependencias y el elemento `AssemblyDependencyResolver` facilita la tarea de cargar correctamente las dependencias.</span><span class="sxs-lookup"><span data-stu-id="0612d-146">The custom `AssemblyLoadContext` enables plugins to have their own dependencies, and the `AssemblyDependencyResolver` makes it easy to correctly load the dependencies.</span></span>

<span data-ttu-id="0612d-147">Ahora que el proyecto `AppWithPlugin` tiene el tipo `PluginLoadContext`, actualice el método `Program.LoadPlugin` con el cuerpo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-147">Now that the `AppWithPlugin` project has the `PluginLoadContext` type, update the `Program.LoadPlugin` method with the following body:</span></span>

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

<span data-ttu-id="0612d-148">Al usar una instancia de `PluginLoadContext` diferente para cada complemento, los complementos puede tener dependencias diferentes o incluso en conflicto sin ningún problema.</span><span class="sxs-lookup"><span data-stu-id="0612d-148">By using a different `PluginLoadContext` instance for each plugin, the plugins can have different or even conflicting dependencies without issue.</span></span>

## <a name="simple-plugin-with-no-dependencies"></a><span data-ttu-id="0612d-149">Complemento simple sin dependencias</span><span class="sxs-lookup"><span data-stu-id="0612d-149">Simple plugin with no dependencies</span></span>

<span data-ttu-id="0612d-150">En la carpeta raíz, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0612d-150">Back in the root folder, do the following:</span></span>

1. <span data-ttu-id="0612d-151">Ejecute el siguiente comando para crear un nuevo proyecto de biblioteca de clases denominado `HelloPlugin`:</span><span class="sxs-lookup"><span data-stu-id="0612d-151">Run the following command to create a new class library project named `HelloPlugin`:</span></span>

    ```dotnetcli
    dotnet new classlib -o HelloPlugin
    ```

2. <span data-ttu-id="0612d-152">Ejecute el siguiente comando para agregar el proyecto a la solución `AppWithPlugin`:</span><span class="sxs-lookup"><span data-stu-id="0612d-152">Run the following command to add the project to the `AppWithPlugin` solution:</span></span>

    ```dotnetcli
    dotnet sln add HelloPlugin/HelloPlugin.csproj
    ```

3. <span data-ttu-id="0612d-153">Reemplace el archivo *HelloPlugin/Class1.cs* con un archivo denominado *HelloCommand.cs* con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-153">Replace the *HelloPlugin/Class1.cs* file with a file named *HelloCommand.cs* with the following contents:</span></span>

[!code-csharp[the-hello-plugin](~/samples/snippets/core/tutorials/creating-app-with-plugin-support/csharp/HelloPlugin/HelloCommand.cs)]

<span data-ttu-id="0612d-154">Ahora, abra el archivo *HelloPlugin.csproj*.</span><span class="sxs-lookup"><span data-stu-id="0612d-154">Now, open the *HelloPlugin.csproj* file.</span></span> <span data-ttu-id="0612d-155">Debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-155">It should look similar to the following:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net5</TargetFramework>
  </PropertyGroup>

</Project>

```

<span data-ttu-id="0612d-156">Entre las etiquetas `<Project>`, agregue los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0612d-156">In between the `<Project>` tags, add the following elements:</span></span>

```xml
<ItemGroup>
    <ProjectReference Include="..\PluginBase\PluginBase.csproj">
        <Private>false</Private>
        <ExcludeAssets>runtime</ExcludeAssets>
    </ProjectReference>
</ItemGroup>
```

<span data-ttu-id="0612d-157">El elemento `<Private>false</Private>` es importante.</span><span class="sxs-lookup"><span data-stu-id="0612d-157">The `<Private>false</Private>` element is important.</span></span> <span data-ttu-id="0612d-158">Indica a MSBuild que no copie *PluginBase.dll* en el directorio de salida para HelloPlugin.</span><span class="sxs-lookup"><span data-stu-id="0612d-158">This tells MSBuild to not copy *PluginBase.dll* to the output directory for HelloPlugin.</span></span> <span data-ttu-id="0612d-159">Si el ensamblado *PluginBase.dll* está presente en el directorio de salida, `PluginLoadContext` encontrará el ensamblado y lo cargará cuando cargue el ensamblado *HelloPlugin.dll*.</span><span class="sxs-lookup"><span data-stu-id="0612d-159">If the *PluginBase.dll* assembly is present in the output directory, `PluginLoadContext` will find the assembly there and load it when it loads the *HelloPlugin.dll* assembly.</span></span> <span data-ttu-id="0612d-160">En este momento, el tipo `HelloPlugin.HelloCommand` implementará la interfaz `ICommand` de *PluginBase.dll* en el directorio de salida del proyecto `HelloPlugin`, no la interfaz `ICommand` que se carga en el contexto de carga predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0612d-160">At this point, the `HelloPlugin.HelloCommand` type will implement the `ICommand` interface from the *PluginBase.dll* in the output directory of the `HelloPlugin` project, not the `ICommand` interface that is loaded into the default load context.</span></span> <span data-ttu-id="0612d-161">Como el runtime considera que estos dos tipos son tipos diferentes de ensamblados distintos, el método `AppWithPlugin.Program.CreateCommands` no encontrará los comandos.</span><span class="sxs-lookup"><span data-stu-id="0612d-161">Since the runtime sees these two types as different types from different assemblies, the `AppWithPlugin.Program.CreateCommands` method won't find the commands.</span></span> <span data-ttu-id="0612d-162">Como resultado, los metadatos `<Private>false</Private>` son necesarios para la referencia al ensamblado que contiene las interfaces de complemento.</span><span class="sxs-lookup"><span data-stu-id="0612d-162">As a result, the `<Private>false</Private>` metadata is required for the reference to the assembly containing the plugin interfaces.</span></span>

<span data-ttu-id="0612d-163">Del mismo modo, el elemento `<ExcludeAssets>runtime</ExcludeAssets>` también es importante si `PluginBase` hace referencia a otros paquetes.</span><span class="sxs-lookup"><span data-stu-id="0612d-163">Similarly, the `<ExcludeAssets>runtime</ExcludeAssets>` element is also important if the `PluginBase` references other packages.</span></span> <span data-ttu-id="0612d-164">Esta configuración tiene el mismo efecto que `<Private>false</Private>` pero funciona en las referencias de paquete que pueden incluir el proyecto `PluginBase` o una de sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="0612d-164">This setting has the same effect as `<Private>false</Private>` but works on package references that the `PluginBase` project or one of its dependencies may include.</span></span>

<span data-ttu-id="0612d-165">Ahora que se ha completado el proyecto `HelloPlugin`, se debe actualizar el proyecto `AppWithPlugin` para saber dónde se puede encontrar el complemento `HelloPlugin`.</span><span class="sxs-lookup"><span data-stu-id="0612d-165">Now that the `HelloPlugin` project is complete, you should update the `AppWithPlugin` project to know where the `HelloPlugin` plugin can be found.</span></span> <span data-ttu-id="0612d-166">Después del comentario `// Paths to plugins to load`, agregue `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` (esta ruta de acceso podría ser diferente en función de la versión de .NET Core que use) como un elemento de la matriz de `pluginPaths`.</span><span class="sxs-lookup"><span data-stu-id="0612d-166">After the `// Paths to plugins to load` comment, add `@"HelloPlugin\bin\Debug\netcoreapp3.0\HelloPlugin.dll"` (this path could be different based on the .NET Core version you use) as an element of the `pluginPaths` array.</span></span>

## <a name="plugin-with-library-dependencies"></a><span data-ttu-id="0612d-167">Complemento con dependencias de biblioteca</span><span class="sxs-lookup"><span data-stu-id="0612d-167">Plugin with library dependencies</span></span>

<span data-ttu-id="0612d-168">Casi todos los complementos son más complejos que un simple ejemplo "Hola mundo", y muchos tienen dependencias en otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0612d-168">Almost all plugins are more complex than a simple "Hello World", and many plugins have dependencies on other libraries.</span></span> <span data-ttu-id="0612d-169">En los proyectos de complemento `JsonPlugin` y `OldJson` del ejemplo se muestran dos ejemplos de complementos con dependencias de paquetes NuGet en `Newtonsoft.Json`.</span><span class="sxs-lookup"><span data-stu-id="0612d-169">The `JsonPlugin` and `OldJson` plugin projects in the sample show two examples of plugins with NuGet package dependencies on `Newtonsoft.Json`.</span></span> <span data-ttu-id="0612d-170">Los propios archivos del proyecto no tienen información especial para las referencias del proyecto y, después de agregar las rutas de acceso de complemento a la matriz `pluginPaths`, los complementos se ejecutan perfectamente, incluso en la misma ejecución de la aplicación AppWithPlugin.</span><span class="sxs-lookup"><span data-stu-id="0612d-170">The project files themselves don't have any special information for the project references, and (after adding the plugin paths to the `pluginPaths` array) the plugins run perfectly, even if run in the same execution of the AppWithPlugin app.</span></span> <span data-ttu-id="0612d-171">Pero estos proyectos no copian los ensamblados a los que se hace referencia en su directorio de salida, por lo que los ensamblados deben estar presentes en la máquina del usuario para que los complementos funcionen.</span><span class="sxs-lookup"><span data-stu-id="0612d-171">However, these projects don't copy the referenced assemblies to their output directory, so the assemblies need to be present on the user's machine for the plugins to work.</span></span> <span data-ttu-id="0612d-172">Hay dos maneras de solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="0612d-172">There are two ways to work around this problem.</span></span> <span data-ttu-id="0612d-173">La primera opción consiste en usar el comando `dotnet publish` para publicar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="0612d-173">The first option is to use the `dotnet publish` command to publish the class library.</span></span> <span data-ttu-id="0612d-174">Como alternativa, si quiere poder usar la salida de `dotnet build` para el complemento, puede agregar la propiedad `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` entre las etiquetas `<PropertyGroup>` del archivo de proyecto del complemento.</span><span class="sxs-lookup"><span data-stu-id="0612d-174">Alternatively, if you want to be able to use the output of `dotnet build` for your plugin, you can add the `<CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>` property between the `<PropertyGroup>` tags in the plugin's project file.</span></span> <span data-ttu-id="0612d-175">Vea el proyecto de complemento `XcopyablePlugin` para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0612d-175">See the `XcopyablePlugin` plugin project for an example.</span></span>

## <a name="other-examples-in-the-sample"></a><span data-ttu-id="0612d-176">Otros ejemplos en la muestra</span><span class="sxs-lookup"><span data-stu-id="0612d-176">Other examples in the sample</span></span>

<span data-ttu-id="0612d-177">Puede encontrar el código fuente completo para este tutorial en el [repositorio dotnet/samples](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span><span class="sxs-lookup"><span data-stu-id="0612d-177">The complete source code for this tutorial can be found in [the dotnet/samples repository](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin).</span></span> <span data-ttu-id="0612d-178">El ejemplo completo incluye algunos otros ejemplos de comportamiento `AssemblyDependencyResolver`.</span><span class="sxs-lookup"><span data-stu-id="0612d-178">The completed sample includes a few other examples of `AssemblyDependencyResolver` behavior.</span></span> <span data-ttu-id="0612d-179">Por ejemplo, el objeto `AssemblyDependencyResolver` también puede resolver las bibliotecas nativas, así como los ensamblados satélite localizados en paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="0612d-179">For example, the `AssemblyDependencyResolver` object can also resolve native libraries as well as localized satellite assemblies included in NuGet packages.</span></span> <span data-ttu-id="0612d-180">`UVPlugin` y `FrenchPlugin` en el repositorio de ejemplos demuestran estos escenarios.</span><span class="sxs-lookup"><span data-stu-id="0612d-180">The `UVPlugin` and `FrenchPlugin` in the samples repository demonstrate these scenarios.</span></span>

## <a name="reference-a-plugin-interface-from-a-nuget-package"></a><span data-ttu-id="0612d-181">Referencia a una interfaz de complemento desde un paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="0612d-181">Reference a plugin interface from a NuGet package</span></span>

<span data-ttu-id="0612d-182">Supongamos que hay una aplicación A que tiene una interfaz de complemento definida en el paquete NuGet denominado `A.PluginBase`.</span><span class="sxs-lookup"><span data-stu-id="0612d-182">Let's say that there is an app A that has a plugin interface defined in the NuGet package named `A.PluginBase`.</span></span> <span data-ttu-id="0612d-183">¿Cómo se hace referencia correctamente al paquete en el proyecto de complemento?</span><span class="sxs-lookup"><span data-stu-id="0612d-183">How do you reference the package correctly in your plugin project?</span></span> <span data-ttu-id="0612d-184">Para las referencias de proyecto, el uso de los metadatos `<Private>false</Private>` en el elemento `ProjectReference` del archivo de proyecto ha impedido que el archivo DLL se copiara en la salida.</span><span class="sxs-lookup"><span data-stu-id="0612d-184">For project references, using the `<Private>false</Private>` metadata on the `ProjectReference` element in the project file prevented the dll from being copied to the output.</span></span>

<span data-ttu-id="0612d-185">Para hacer referencia correctamente al paquete `A.PluginBase`, le interesará cambiar el elemento `<PackageReference>` del archivo de proyecto por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0612d-185">To correctly reference the `A.PluginBase` package, you want to change the `<PackageReference>` element in the project file to the following:</span></span>

```xml
<PackageReference Include="A.PluginBase" Version="1.0.0">
    <ExcludeAssets>runtime</ExcludeAssets>
</PackageReference>
```

<span data-ttu-id="0612d-186">Esto evita que los ensamblados `A.PluginBase` se copien en el directorio de salida del complemento y asegura que el complemento use la versión de `A.PluginBase` la aplicación A.</span><span class="sxs-lookup"><span data-stu-id="0612d-186">This prevents the `A.PluginBase` assemblies from being copied to the output directory of your plugin and ensures that your plugin will use A's version of `A.PluginBase`.</span></span>

## <a name="plugin-target-framework-recommendations"></a><span data-ttu-id="0612d-187">Recomendaciones para plataformas de destino de complemento</span><span class="sxs-lookup"><span data-stu-id="0612d-187">Plugin target framework recommendations</span></span>

<span data-ttu-id="0612d-188">Como en la carga de dependencias de complemento se usa el archivo *deps.json*, hay un problema relacionado con la plataforma de destino del complemento.</span><span class="sxs-lookup"><span data-stu-id="0612d-188">Because plugin dependency loading uses the *.deps.json* file, there is a gotcha related to the plugin's target framework.</span></span> <span data-ttu-id="0612d-189">En concreto, los complementos deben tener como destino un entorno de ejecución como .NET 5, en lugar de una versión de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="0612d-189">Specifically, your plugins should target a runtime, such as .NET 5, instead of a version of .NET Standard.</span></span> <span data-ttu-id="0612d-190">El archivo *.deps.json* se genera en función de la plataforma de destino del proyecto y, como muchos paquetes compatibles con .NET Standard incluyen ensamblados de referencia para compilar en .NET Standard y ensamblados de implementación para runtimes específicos, es posible que el archivo *.deps.json* no vea correctamente los ensamblados de implementación, o bien que tome la versión de .NET Standard de un ensamblado en lugar de la de .NET Core que se espera.</span><span class="sxs-lookup"><span data-stu-id="0612d-190">The *.deps.json* file is generated based on which framework the project targets, and since many .NET Standard-compatible packages ship reference assemblies for building against .NET Standard and implementation assemblies for specific runtimes, the *.deps.json* may not correctly see implementation assemblies, or it may grab the .NET Standard version of an assembly instead of the .NET Core version you expect.</span></span>

## <a name="plugin-framework-references"></a><span data-ttu-id="0612d-191">Referencias del marco de trabajo de complementos</span><span class="sxs-lookup"><span data-stu-id="0612d-191">Plugin framework references</span></span>

<span data-ttu-id="0612d-192">En la actualidad, los complementos no pueden introducir nuevos marcos en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0612d-192">Currently, plugins can't introduce new frameworks into the process.</span></span> <span data-ttu-id="0612d-193">Por ejemplo, no puede cargar un complemento que use el marco `Microsoft.AspNetCore.App` en una aplicación en la que solo se use el marco `Microsoft.NETCore.App` raíz.</span><span class="sxs-lookup"><span data-stu-id="0612d-193">For example, you can't load a plugin that uses the `Microsoft.AspNetCore.App` framework into an application that only uses the root `Microsoft.NETCore.App` framework.</span></span> <span data-ttu-id="0612d-194">La aplicación host debe declarar referencias a todos los marcos de trabajo necesarios para los complementos.</span><span class="sxs-lookup"><span data-stu-id="0612d-194">The host application must declare references to all frameworks needed by plugins.</span></span>
