---
title: "Implementación de aplicaciones .NET Core | Microsoft Docs"
description: "Implementación de aplicaciones .NET Core"
keywords: ".NET, .NET Core, implementación de .NET Core"
author: rpetrusha
ms.author: ronpet
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: da7a31a0-8072-4f23-82aa-8a19184cb701
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 0e186665619bd76c5ba3d1e605b885a12aa15c66
ms.lasthandoff: 03/07/2017

---

# <a name="net-core-application-deployment"></a>Implementación de aplicaciones .NET Core

Puede crear dos tipos de implementaciones para aplicaciones .NET Core: 

- Implementación dependiente de Framework. Como su nombre indica, la implementación dependiente de Framework (FDD) se basa en la presencia de una versión compartida de .NET Core en todo el sistema en el sistema de destino. Como .NET Core ya está presente, la aplicación también es portátil entre instalaciones de .NET Core. La aplicación solo contiene su propio código y dependencias de terceros que están fuera de las bibliotecas .NET Core. FDD contiene archivos .dll que se pueden iniciar utilizando la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos. Por ejemplo, `dotnet app.dll` ejecuta una aplicación denominada `app`.

- Implementación autocontenida. A diferencia de FDD, una implementación autocontenida (SCD) no depende de que los componentes compartidos estén presentes en el sistema de destino. Todos los componentes, incluidas las bibliotecas y el entorno de ejecución de .NET Core, se incluyen con la aplicación y están aislados de otras aplicaciones .NET Core. Las SCD incluyen un archivo ejecutable (como `app.exe` en plataformas de Windows para una aplicación denominada `app`), que es una versión con otro nombre del host de .NET Core específico de la plataforma y un archivo .dll (como `app.dll`), que es la aplicación real.

## <a name="framework-dependent-deployments-fdd"></a>Implementaciones dependientes de Framework (FDD) ##

En una FDD, solo se implementa su aplicación y cualquier dependencia de terceros. No tiene que implementar .NET Core, puesto que la aplicación usará la versión de .NET Core que esté presente en el sistema de destino. Este es el modelo de implementación predeterminado para aplicaciones .NET Core.

### <a name="why-create-a-framework-dependent-deployment"></a>¿Por qué crear una implementación dependiente del marco? ###

La implementación de FDD tienen varias ventajas:

- No es necesario definir por adelantado los sistemas operativos de destino en los que se ejecutará la aplicación .NET Core. Como .NET Core usa un formato de archivo PE común para archivos ejecutables y bibliotecas independientemente del sistema operativo, .NET Core puede ejecutar la aplicación con independencia del sistema operativo subyacente. Para más información sobre el formato de archivo PE, consulte [.NET Assembly File Format](../../standard/assembly-format.md) (Formato de archivo de ensamblado .NET).

- El tamaño de su paquete de implementación es pequeño. Solo tendrá que implementar la aplicación y sus dependencias, .NET Core propiamente dicho.

- Varias aplicaciones usan la misma instalación de .NET Core, lo que reduce tanto el espacio en disco y el uso de memoria en sistemas host.

Hay también algunas desventajas:

- Su aplicación solo se puede ejecutar si la versión de .NET Core de destino, o una versión posterior, ya está instalada en el sistema host.

- Es posible que el entorno de tiempo de ejecución y las bibliotecas .NET Core cambien en futuras versiones sin su conocimiento. En raras ocasiones, esto puede cambiar el comportamiento de la aplicación.

### <a name="deploying-a-framework-dependent-deployment"></a>Implementación de una implementación dependiente del marco ###

La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso. En el ejemplo se usa la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos; sin embargo, también puede usar un entorno de desarrollo, como Visual Studio o Visual Studio Code para compilar, probar y publicar el ejemplo.

1. Cree un directorio para el proyecto y, en la línea de comandos, escriba `[dotnet new console](../tools/dotnet-new.md)` para crear un nuevo proyecto de consola de C#.

2. Abra el archivo `Program.cs` en un editor y reemplace el código generado automáticamente por el código siguiente. Se pide al usuario que escriba texto y, a continuación, se muestran las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else
              {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) para restaurar las dependencias especificadas en el proyecto.

4. Cree una compilación de depuración de su aplicación mediante el comando [dotnet build](../tools/dotnet-build.md).

5. Después de depurar y probar el programa, puede crear los archivos que se implementarán con la aplicación mediante el comando `dotnet publish -f netcoreapp1.1 -c release`. Con esto se crea una versión (en lugar de una depuración) de la aplicación.

   Los archivos resultantes se colocan en un directorio llamado `publish` que se encuentra en un subdirectorio del subdirectorio `.\bin\release\netcoreapp1.1` del proyecto.

6. Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones; puede elegir no empaquetarlo con los archivos de la aplicación.

El conjunto completo de archivos de la aplicación se puede implementar del modo que quiera. Por ejemplo, puede empaquetarlos en un archivo comprimido, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.

Además de los archivos binarios de la aplicación, el instalador debe también empaquetar el programa de instalación de un marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.  La instalación del marco compartido requiere acceso raíz o de administrador dado que implica a toda la máquina.

### <a name="deploying-a-framework-dependent-deployment-with-third-party-dependencies"></a>Implementación de una implementación dependiente del marco con dependencias de terceros ###

La implementación de una implementación dependiente del marco con una o varias dependencias de terceros implica tres pasos adicionales antes de ejecutar el comando `dotnet restore`:

1. Agregue referencias a las bibliotecas de terceros a la sección `<ItemGroup>` de su archivo `csproj`. En la siguiente sección `<ItemGroup>` se muestra el elemento `<ItemGroup>` que contiene las dependencias del proyecto predeterminado con Json.NET como biblioteca de terceros.

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
      </ItemGroup>
    ```

 Observe que la dependencia del SDK permanece en el ejemplo anterior. Esto es así por diseño, dado que esta dependencia es necesaria para restaurar todos los destinos necesarios para permitir que las herramientas de línea de comandos funcionen.  

2. Si no lo ha hecho ya, descargue el paquete de NuGet que contiene la dependencia de terceros. Para descargar el paquete, ejecute el comando `dotnet restore` después de agregar la dependencia. Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.

Tenga en cuenta que una implementación dependiente del marco con dependencias de terceros solo será tan portátil como sus dependencias de terceros. Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se podrá portar a sistemas Windows. Esto puede ocurrir si la dependencia de terceros propiamente dicha depende del código nativo. Un buen ejemplo de ello es el servidor Kestrel. Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contendrá una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md#what-are-rids) que admita la dependencia nativa (y que exista en su paquete de NuGet).

## <a name="self-contained-deployments-scd"></a>Implementaciones autocontenidas (SCD) ##

En una implementación autocontenida, no solo implementa su aplicación y cualquier dependencia de terceros, sino también la versión de .NET Core con la que compila la aplicación. La creación de una SCD no incluye, sin embargo, las [dependencias nativas de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) propiamente dichas en diversas plataformas (por ejemplo, OpenSSL en macOS) así que es necesario instalarlas antes de ejecutar la aplicación. 

### <a name="why-deploy-a-self-contained-deployment"></a>¿Por qué realizar una implementación autocontenida? ###

La implementación de una implementación autocontenida tiene dos ventajas principales:

- Tiene el control exclusivo de la versión de .NET Core que se implementa con la aplicación. El mantenimiento de .NET Core solo puede realizarlo usted.

- Puede tener la seguridad de que el sistema de destino puede ejecutar su aplicación de .NET Core, dado que usted proporciona la versión de .NET Core en la que se ejecuta.

También tiene algunos inconvenientes:

- Como .NET Core se incluye en el paquete de implementación, debe seleccionar por adelantado las plataformas de destino en las que se compilan los paquetes de implementación.

- El tamaño de su paquete de implementación es relativamente grande, ya que tendrá que incluir .NET Core, así como la aplicación y sus dependencias de terceros.

- La implementación de numerosas aplicaciones .NET Core autocontenidas en un sistema puede consumir importantes cantidades de espacio en disco, puesto que cada aplicación duplica archivos de .NET Core.

### <a name="simpleSelf"></a> Implementación de una implementación autocontenida sencilla ###

La implementación de una implementación autocontenida sin dependencias de terceros implica crear el proyecto, modificar el archivo csproj y compilar, probar y publicar la aplicación.  Un sencillo ejemplo escrito en C# ilustra el proceso. En el ejemplo se usa la utilidad `dotnet` desde la línea de comandos; sin embargo, también puede usar un entorno de desarrollo, como Visual Studio o Visual Studio Code para compilar, probar y publicar el ejemplo.

1. Cree un directorio para el proyecto y, en la línea de comandos, escriba `dotnet new console` para crear un nuevo proyecto de consola de C#.

2. Abra el archivo `Program.cs` en un editor y reemplace el código generado automáticamente por el código siguiente. Se pide al usuario que escriba texto y, a continuación, se muestran las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

    ```cs
    using System;
    using System.Text.RegularExpressions;

    namespace Applications.ConsoleApps
    {
        public class ConsoleParser
        {
            public static void Main()
            {
                 Console.WriteLine("Enter any text, followed by <Enter>:\n");
                 String s = Console.ReadLine();
                 ShowWords(s);
                 Console.Write("\nPress any key to continue... ");
                 Console.ReadKey();
          }

          private static void ShowWords(String s)
          {
              String pattern = @"\w+";
              var matches = Regex.Matches(s, pattern);
              if (matches.Count == 0)
                  Console.WriteLine("\nNo words were identified in your input.");
              else {
                  Console.WriteLine("\nThere are {0} words in your string:", matches.Count);
                  for (int ctr = 0; ctr < matches.Count; ctr++)
                      Console.WriteLine("   #{0,2}: '{1}' at position {2}", ctr,
                                        matches[ctr].Value, matches[ctr].Index);
              }
          }
      }
    }
    ```

3. Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo `csproj` que defina las plataformas a las que se dirige su aplicación, y especifique el identificador de tiempo de ejecución de cada una. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md). Por ejemplo, el ejemplo siguiente indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.

    ```xml
        <PropertyGroup>
          <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
        </PropertyGroup>
    ```
Tenga en cuenta que también debe agregar un punto y coma para separar los RID. Además, tenga en cuenta que el elemento `<RuntimeIdentifier>` puede ir en cualquier `<PropertyGroup>` que tenga en su archivo `csproj`. Más adelante en esta sección aparece un ejemplo completo del archivo `csproj`.

4. Ejecute el comando `dotnet restore` para restaurar las dependencias especificadas en el proyecto.

5. Después de depurar y probar el programa, puede crear los archivos que se implementarán con la aplicación para cada plataforma de destino mediante la ejecución del comando `dotnet publish` en ambas plataformas de destino, de la manera siguiente:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.11-x64
   ```
Se crea una versión de lanzamiento (en lugar de una depuración) de la aplicación para cada plataforma de destino. Los archivos resultantes se colocan en un subdirectorio denominado `publish` que se encuentra en un subdirectorio del subdirectorio `.\bin\release\netcoreapp1.1\<runtime_identifier>` del proyecto. Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.

6. Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones; puede elegir no empaquetarlo con los archivos de la aplicación.

Los archivos publicados se pueden implementar de la forma que desee. Por ejemplo, puede empaquetarlos en un archivo comprimido, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. 

El siguiente es el archivo `csproj` completo para este proyecto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
    <DebugType>Portable</DebugType>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```


### <a name="deploying-a-self-contained-deployment-with-third-party-dependencies"></a>Implementación de una implementación autocontenida con dependencias de terceros ###

Implementar una implementación autocontenida con una o varias dependencias de terceros implica agregar la dependencia de terceros:

1. Agregue referencias a las bibliotecas de terceros a la sección `<ItemGroup>` de su archivo `csproj`. La siguiente sección `<ItemGroup>` usa Json.NET como biblioteca de terceros.

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
      </ItemGroup>
    ```
2. Si aún no lo ha hecho, descargue el paquete de NuGet que contiene la dependencia de terceros en el sistema. Para que la dependencia esté disponibles para la aplicación, ejecute el comando `dotnet restore` después de agregar la dependencia. Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.

El siguiente es el archivo csproj completo de este proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
    <DebugType>Portable</DebugType>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
  </ItemGroup>
</Project>
```

Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación. Las bibliotecas de terceros no están aún presentes en el sistema en el que se ejecuta la aplicación.

Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca. Esto es parecido a tener dependencias de terceros con dependencias nativas en la implementación dependiente del marco. 

### <a name="deploying-a-self-contained-deployment-with-a-smaller-footprint"></a>Implementación de una implementación autocontenida con una superficie menor ###

Si la disponibilidad de espacio de almacenamiento adecuado en sistemas de destino puede ser un problema, puede reducir la superficie general de la aplicación excluyendo algunos componentes del sistema. Para ello, defina explícitamente los componentes de .NET Core que incluye su aplicación en su archivo csproj.

Para crear una implementación autocontenida con una superficie menor, comience siguiendo los dos primeros pasos para crear una implementación autocontenida. Cuando haya ejecutado el comando `dotnet new console` y agregado el código fuente de C# a la aplicación, haga lo siguiente:

1. Abra el archivo `csproj` y reemplace el elemento `<TargetFramework>` por lo siguiente:

  ```xml
  <TargetFramework>netstandard1.6</TargetFramework>
  ```
Esta operación indica que, en lugar de usar el marco entero `netcoreapp1.0`, que incluye .NET Core CLR, la biblioteca .NET Core y varios otros componentes del sistema, la aplicación emplea solamente la biblioteca estándar. NET.

2. Reemplace el `<ItemGroup>` que contiene las referencias del paquete por lo siguiente:

  ```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.Runtime.CoreCLR" Version="1.0.2" />
    <PackageReference Include="Microsoft.NETCore.DotNetHostPolicy" Version="1.0.1" />
  </ItemGroup>
  ```

   Esto define los componentes del sistema usados por nuestra aplicación. Los componentes del sistema empaquetados con nuestra aplicación incluyen la biblioteca estándar. NET, el entorno de tiempo de ejecución de .NET Core y el host de .NET Core. Esto produce una implementación autocontenida con una superficie menor.

3. Al igual que hizo en el ejemplo [Implementación de una implementación autocontenida sencilla](#simpleSelf), cree un elemento `<RuntimeIdentifiers>` en un elemento `<PropertyGroup>` del archivo `csproj` que defina las plataformas a las que se dirige su aplicación, y especifique el identificador de tiempo de ejecución de cada una. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md). Por ejemplo, el ejemplo siguiente indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.

    ```xml
    <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
    </PropertyGroup>
    ```
    
   Más adelante en esta sección aparece un ejemplo completo del archivo `csproj`.

4. Ejecute el comando `dotnet restore` para restaurar las dependencias especificadas en el proyecto.

5. Después de depurar y probar el programa, puede crear los archivos que se implementarán con la aplicación para cada plataforma de destino mediante la ejecución del comando `dotnet publish` en ambas plataformas de destino, de la manera siguiente:

   ```console
   dotnet publish -c release -r win10-x64
   dotnet publish -c release -r osx.10.11-x64
   ```
Se crea una versión de lanzamiento (en lugar de una depuración) de la aplicación para cada plataforma de destino. Los archivos resultantes se colocan en un subdirectorio denominado `publish` que se encuentra en un subdirectorio del subdirectorio `.\bin\release\netstandard1.6\<runtime_identifier>` del proyecto. Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.

6. Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones; puede elegir no empaquetarlo con los archivos de la aplicación.

Los archivos publicados se pueden implementar de la forma que desee. Por ejemplo, puede empaquetarlos en un archivo comprimido, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. 

El siguiente es el archivo `csproj` completo para este proyecto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netstandard1.6</TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
    <DebugType>Portable</DebugType>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.Runtime.CoreCLR" Version="1.0.2" />
    <PackageReference Include="Microsoft.NETCore.DotNetHostPolicy" Version="1.0.1" />
  </ItemGroup>
</Project>
```


