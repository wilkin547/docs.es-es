---
title: Implementación de aplicaciones de .NET Core con herramientas de la CLI
description: Obtenga información sobre la implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 21e824e6092b0d30e0499ff05c5471a291c8d269
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="deploying-net-core-apps-with-command-line-interface-cli-tools"></a>Implementación de aplicaciones de .NET Core con herramientas de la interfaz de la línea de comandos (CLI)

Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core. Para obtener información general, vea [Implementación de aplicaciones .NET Core](index.md).

En las secciones siguientes se muestra cómo usar las [herramientas de la interfaz de la línea de comandos de .NET Core](../tools/index.md) para crear los siguientes tipos de implementaciones:

- Implementación dependiente de marco de trabajo
- Implementación dependiente de marco de trabajo con dependencias de terceros
- Implementación autocontenida
- Implementación autocontenida con dependencias de terceros

Cuando se trabaja desde la línea de comandos, puede usar un programa editor de su elección. Si el programa editor es [Visual Studio Code](https://code.visualstudio.com), puede abrir una consola de comandos dentro del entorno de Visual Studio Code seleccionando **Vista** > **Terminal integrado**.

## <a name="framework-dependent-deployment"></a>Implementación dependiente de marco de trabajo

La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso. 

1. Crear un directorio de proyecto.

   Cree un directorio para el proyecto y conviértalo en el directorio actual.

1. Crear el proyecto.

   Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.

1. Agregar el código fuente de la aplicación.

   Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente. Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Actualizar las herramientas y las dependencias del proyecto.
 
   Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias especificadas en el proyecto.

1. Crear una versión de depuración de la aplicación.

   Use el comando [dotnet build](../tools/dotnet-build.md) para compilar la aplicación o el comando [dotnet run](../tools/dotnet-run.md) para compilarla y ejecutarla.

1. Implementar la aplicación.

   Después de depurar y probar el programa, cree la implementación mediante el comando siguiente:

      ```console
      dotnet publish -f netcoreapp1.1 -c Release
      ```
   Con esto se crea una versión (en lugar de una depuración) de la aplicación. Los archivos resultantes se colocan en un directorio denominado *publish* que se encuentra en un subdirectorio del directorio *bin* del proyecto.

Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones. Puede decidir no distribuirlo con los archivos de la aplicación. Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.

El conjunto completo de archivos de la aplicación se puede implementar del modo que quiera. Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.

Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.  La instalación del marco compartido requiere acceso raíz o de administrador.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Implementación dependiente de marco de trabajo con dependencias de terceros

La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que esas dependencias estén disponibles para el proyecto. Para poder ejecutar el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) son necesarios otros dos pasos:

1. Agregue referencias a las bibliotecas de terceros requeridas a la sección `<ItemGroup>` del archivo *csproj*. La siguiente sección `<ItemGroup>` contiene una dependencia de [Json.NET](http://www.newtonsoft.com/json) como biblioteca de terceros:

      ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
      ```

1. Si no lo ha hecho ya, descargue el paquete de NuGet que contiene la dependencia de terceros. Para descargar el paquete, ejecute el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) después de agregar la dependencia. Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.

Tenga en cuenta que una implementación dependiente de la plataforma con dependencias de terceros solo será tan portátil como sus dependencias de terceros. Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows. Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo. Un buen ejemplo de esto es [el servidor Kestrel](/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv). Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md) que admita la dependencia nativa (y que exista en su paquete de NuGet).

## <a name="simpleSelf"></a> Implementación independiente sin dependencias de terceros

La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso. En el ejemplo se muestra cómo crear una implementación independiente mediante la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos.

1. Crear un directorio para el proyecto.

   Cree un directorio para el proyecto y conviértalo en el directorio actual.

1. Crear el proyecto.

   Desde la línea de comandos, escriba [dotnet new console](../tools/dotnet-new.md) para crear un nuevo proyecto de consola de C# en ese directorio.

1. Agregar el código fuente de la aplicación.

   Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente. Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Definir las plataformas de destino de la aplicación.

   Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una. Tenga en cuenta que también debe agregar un punto y coma para separar los RID. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md). 

   Por ejemplo, la siguiente sección `<PropertyGroup>` indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.

     ```xml
     <PropertyGroup>
         <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
     </PropertyGroup>
     ```

   Tenga en cuenta que el elemento `<RuntimeIdentifiers>` puede aparecer en cualquier `<PropertyGroup>` del archivo *csproj*. Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.

1. Actualizar las herramientas y las dependencias del proyecto.

   Ejecute el comando [dotnet restore](../tools/dotnet-restore.md) ([vea la nota](#dotnet-restore-note)) para restaurar las dependencias especificadas en el proyecto.

1. Crear una versión de depuración de la aplicación.

   Desde la línea de comandos, use el comando [dotnet build](../tools/dotnet-build.md).

1. Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.

   Use el comando `dotnet publish` para las dos plataformas de destino como sigue:

      ```console
      dotnet publish -c Release -r win10-x64
      dotnet publish -c Release -r osx.10.11-x64
      ```

   Se crea una versión (en lugar de una depuración) de la aplicación para cada plataforma de destino. Los archivos resultantes se colocan en un subdirectorio denominado *publish* que se encuentra en un subdirectorio del subdirectorio *.\bin\Release\netcoreapp1.1\<identificador_TiempoDeEjecución>* del proyecto. Tenga en cuenta que cada subdirectorio contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesario para iniciar la aplicación.

Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones. Puede decidir no empaquetarlo con los archivos de la aplicación. Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.

Implemente los archivos publicados de la forma que quiera. Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.

A continuación se muestra el archivo *csproj* completo para este proyecto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a>Implementación autocontenida con dependencias de terceros

Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias. Para poder ejecutar el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) son necesarios otros dos pasos:

1. Agregue referencias a las bibliotecas de terceros a la sección `<ItemGroup>` del archivo *csproj*. La siguiente sección `<ItemGroup>` usa Json.NET como biblioteca de terceros.

    ```xml
      <ItemGroup>
        <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
      </ItemGroup>
    ```

1. Si aún no lo ha hecho, descargue el paquete de NuGet que contiene la dependencia de terceros en el sistema. Para que la dependencia esté disponible para la aplicación, ejecute el comando `dotnet restore` ([vea la nota](#dotnet-restore-note)) después de agregar la dependencia. Como la dependencia se resuelve fuera de la caché local de NuGet en tiempo de publicación, debe estar disponible en el sistema.

A continuación se muestra el archivo *csproj* completo de este proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación. No se requieren las bibliotecas de terceros en el sistema en el que se ejecuta la aplicación.

Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca. Esto es similar a tener dependencias de terceros con dependencias nativas en una implementación dependiente de la plataforma, donde las dependencias nativas deben ser compatibles con la plataforma en la que se implementa la aplicación.

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

# <a name="see-also"></a>Vea también

[Implementación de aplicaciones .NET Core](index.md)   
[Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)   

