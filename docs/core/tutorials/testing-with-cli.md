---
title: "Organización y prueba de proyectos con la línea de comandos de .NET Core | Microsoft Docs"
description: "En este tutorial se explica cómo organizar y probar proyectos .NET Core desde la línea de comandos."
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3f401907a59d5427cbcfaa0b785931a7ed82110f
ms.lasthandoff: 03/07/2017

---

# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a>Organización y prueba de proyectos con la línea de comandos de .NET Core

Este tutorial sigue al tutorial [Introducción a .NET Core en Windows, Linux y macOS con la línea de comandos](./using-with-xplat-cli.md) para mostrar cómo ir más allá de los escenarios sencillos "Hola a todos" y allanar el camino para aplicaciones más avanzadas y bien organizadas.

## <a name="using-folders-to-organize-code"></a>Uso de carpetas para organizar el código

Supongamos que desea introducir algunos nuevos tipos en los que trabajar. Puede hacerlo agregando más archivos y asegurándose de concederles espacios de nombres que se puedan incluir en el archivo *Program.cs*.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
```

Esto funciona bien cuando el tamaño del proyecto es relativamente pequeño. En cambio, si tiene una aplicación de mayor tamaño con muchos tipos de datos diferentes y posiblemente varias capas, puede que quiera organizar los elementos de forma lógica. Aquí es donde entran en juego las carpetas. Puede seguir con [el proyecto de ejemplo NewTypes](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild) que trata esta guía o bien crear sus propios archivos y carpetas.

Para empezar, cree una nueva carpeta en la raíz del proyecto. `/Model`se elige aquí.

```
/NewTypes
|__/Model
|__Program.cs
|__NewTypes.csproj
```

Ahora agregue algunos tipos nuevos a la carpeta:

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__NewTypes.csproj
```

Ahora, como si fueran archivos del mismo directorio, asígneles a todos el mismo espacio de nombres para incluirlos en su `Program.cs`.

### <a name="example-pet-types"></a>Ejemplo: Tipos de mascota

En este ejemplo se crean dos nuevos tipos: `Dog` y `Cat`, y tienen implementada una interfaz común, `IPet`.

Estructura de carpetas:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__NewTypes.csproj
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

`NewTypes.csproj`:
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

Y si se ejecuta:

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

Se pueden agregar nuevos tipos de mascotas (como un `Bird`), ampliando este proyecto.

## <a name="testing-your-console-app"></a>Prueba de la aplicación de consola

Probablemente estará esperando probar sus proyectos en algún momento. Esta es una buena forma de hacerlo:

1. Mueva cualquier código fuente del proyecto existente a una nueva carpeta `src`.

   ```
   /Project
   |__/src
   ```

2. Cree un directorio `/test` y use el comando `cd` para cambiar el directorio por él.

   ```
   /Project
   |__/src
   |__/test
   ```

3. Inicialice el directorio con un comando `dotnet new xunit`. Se asume xUnit, pero también puede usar MSTest sustituyendo `xunit` por `mstest`.
   
### <a name="example-extending-the-newtypes-project"></a>Ejemplo: Ampliación del proyecto NewTypes

Ahora que el sistema del proyecto está en su lugar, puede crear el proyecto de prueba y empezar a escribir pruebas. De ahora en adelante en esta guía se va a utilizar y a ampliar [el proyecto de tipos de ejemplo](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild). Además, utilizará la plataforma de pruebas [Xunit](https://xunit.github.io/). No dude en seguir leyendo o crear su propio sistema de varios proyectos con las pruebas.

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
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

Hay dos cosas nuevas que debe asegurarse de que las tiene en su proyecto de prueba:

1. Un archivo *NewTypesTests.csproj* correcto con lo siguiente:

   * Una referencia a `xunit`
   * Una referencia a `dotnet-test-xunit`
   * Una referencia al espacio de nombres correspondiente al código sometido a prueba

   Se puede crear escribiendo `dotnet new xunit` en un símbolo del sistema del directorio *NewTypesTests* y agregando luego una referencia de proyecto al proyecto `NewTypes`.

    `NewTypesTests/NewTypesTests.csproj`:
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
        <PackageReference Include="Microsoft.NET.Test.Sdk">
          <Version>15.0.0-preview-20161024-02</Version>
        </PackageReference>
        <PackageReference Include="xunit">
          <Version>2.2.0-beta3-build3402</Version>
        </PackageReference>
        <PackageReference Include="xunit.runner.visualstudio">
          <Version>2.2.0-beta4-build1188</Version>
        </PackageReference>
        <ProjectReference Include="../../src/NewTypes/NewTypes.csproj"/>
      </ItemGroup>

      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
    ```

2. Una clase de prueba xUnit.

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
   
Ahora puede ejecutar las pruebas. El comando [`dotnet test`](../tools/dotnet-test.md) ejecuta el ejecutor de pruebas que se ha especificado en el proyecto. Asegúrese de que comienza en el directorio de nivel superior.
 
```
$ cd test/NewTypesTests
$ dotnet restore
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

