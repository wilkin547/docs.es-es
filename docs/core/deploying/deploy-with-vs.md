---
title: Implementación de aplicaciones de .NET Core con Visual Studio
description: Obtenga información sobre la implementación de aplicaciones de .NET Core con Visual Studio
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 238e43149eebb59ecbb25dfc3976f912e0ae8b01
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="deploying-net-core-apps-with-visual-studio"></a>Implementación de aplicaciones de .NET Core con Visual Studio

Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de la aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core. Para obtener información general sobre la implementación de aplicaciones de NET Core, vea [Implementación de aplicaciones .NET Core](index.md).

En las secciones siguientes se muestra cómo usar Microsoft Visual Studio para crear los siguientes tipos de implementaciones:

- Implementación dependiente de marco de trabajo
- Implementación dependiente de marco de trabajo con dependencias de terceros
- Implementación autocontenida
- Implementación autocontenida con dependencias de terceros

Para obtener información sobre el uso de Visual Studio para desarrollar aplicaciones de .NET Core, vea [Requisitos previos para .NET Core en Windows](../windows-prerequisites.md#prerequisites-with-visual-studio-2017).

## <a name="framework-dependent-deployment"></a>Implementación dependiente de marco de trabajo

La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso.  

1. Crear el proyecto.

   Seleccione **Archivo** > **Nuevo** > **Proyecto**. En el cuadro de diálogo **Nuevo proyecto**, seleccione **.NET Core** en el panel de tipos de proyecto **Instalados** y seleccione la plantilla **Aplicación de consola (.NET Core)** en el panel central. Escriba un nombre de proyecto, como "FDD", en el cuadro de texto **Nombre**. Seleccione el botón **Aceptar**.

1. Agregar el código fuente de la aplicación.

   Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente. Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Crear una versión de depuración de la aplicación.

   Seleccione **Compilar** > **Compilar solución**. También puede compilar y ejecutar la versión de depuración de la aplicación seleccionando **Depurar** > **Iniciar depuración**.

1. Implementar la aplicación.

   Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación. Para publicar desde Visual Studio, siga estos pasos:

      1. Cambie la configuración de la solución de **Depurar** a **Versión** en la barra de herramientas para compilar una compilación de versión (en lugar de depuración) de la aplicación.

      1. Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.

      1. En la pestaña **Publicar**, seleccione **Publicar**. Visual Studio escribe los archivos que componen la aplicación en el sistema de archivos local.

      1. La pestaña **Publicar** muestra ahora un solo perfil, **FolderProfile**. Los valores de configuración del perfil se muestran en la sección **Resumen** de la pestaña.

   Los archivos resultantes se colocan en un directorio llamado `PublishOutput` que se encuentra en un subdirectorio del subdirectorio *.\bin\release* del proyecto.

Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones. Puede decidir no empaquetarlo con los archivos de la aplicación. Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.

Implemente el conjunto completo de archivos de la aplicación del modo que quiera. Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.

Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.  La instalación del marco compartido requiere acceso raíz o de administrador dado que implica a toda la máquina.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Implementación dependiente de marco de trabajo con dependencias de terceros

La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que todas las dependencias estén disponibles para el proyecto. Se requieren los pasos adicionales siguientes antes de poder compilar la aplicación:

1. Use el **Administrador de paquetes NuGet** para agregar una referencia a un paquete de NuGet para el proyecto y, si el paquete todavía no está disponible en el sistema, instálelo. Para abrir el administrador de paquetes, seleccione **Herramientas** > **Administrador de paquetes NuGet** > **Administrar paquetes NuGet para la solución**.

1. Confirme que `Newtonsoft.Json` está instalado en el sistema y, si no es así, instálelo. La pestaña **Instalado** enumera los paquetes de NuGet instalados en el sistema. Si `Newtonsoft.Json` no aparece ahí, seleccione la pestaña **Examinar** y escriba "Newtonsoft.Json" en el cuadro de búsqueda. Seleccione `Newtonsoft.Json` y, en el panel derecho, seleccione el proyecto antes de hacer clic en **Instalar**.

1. Si `Newtonsoft.Json` ya está instalado en el sistema, agréguelo al proyecto seleccionando el proyecto en el panel derecho de la pestaña **Administrar paquetes para la solución**.

Tenga en cuenta que una implementación dependiente de la plataforma con dependencias de terceros solo será tan portátil como sus dependencias de terceros. Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows. Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo. Un buen ejemplo de esto es [el servidor Kestrel](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv). Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md) que admita la dependencia nativa (y que exista en su paquete de NuGet).

## <a name="simpleSelf"></a> Implementación independiente sin dependencias de terceros

La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso. 

1. Crear el proyecto.

   Seleccione **Archivo** > **Nuevo** > **Proyecto**. En el cuadro de diálogo **Agregar nuevo proyecto**, seleccione **.NET Core** en el panel de tipos de proyecto **Instalado** y seleccione la plantilla **Aplicación de consola (.NET Core)** en el panel central. Escriba un nombre de proyecto, como "SCD", en el cuadro de texto **Nombre** y pulse el botón **Aceptar**.

1. Agregar el código fuente de la aplicación.

   Abra el archivo *Program.cs* en el editor y reemplace el código generado automáticamente por el código siguiente. Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

   [!code-csharp[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. Definir las plataformas de destino de la aplicación.

   1. Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Editar SCD.csproj**.

   1. Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una. Tenga en cuenta que también debe agregar un punto y coma para separar los RID. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md). 

   Por ejemplo, el ejemplo siguiente indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```
   Tenga en cuenta que el elemento `<RuntimeIdentifiers>` puede ir en cualquier `<PropertyGroup>` que tenga en el archivo *csproj*. Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.

1. Crear una versión de depuración de la aplicación.

   Seleccione **Compilar** > **Compilar solución**. También puede compilar y ejecutar la versión de depuración de la aplicación seleccionando **Depurar** > **Iniciar depuración**.

1. Publique la aplicación.

   Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.

   Para publicar la aplicación desde Visual Studio, siga estos pasos:

      1. Cambie la configuración de la solución de **Depurar** a **Versión** en la barra de herramientas para compilar una compilación de versión (en lugar de depuración) de la aplicación.

      1. Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**. 

      1. En la pestaña **Publicar**, seleccione **Publicar**. Visual Studio escribe los archivos que componen la aplicación en el sistema de archivos local.

      1. La pestaña **Publicar** muestra ahora un solo perfil, **FolderProfile**. Los valores de configuración del perfil se muestran en la sección **Resumen** de la pestaña. **Tiempo de ejecución de destino** identifica qué tiempo de ejecución se ha publicado, y **Ubicación de destino** identifica dónde se escriben los archivos de la implementación independiente.

      1. De forma predeterminada, Visual Studio escribe todos los archivos publicados en un único directorio. Para mayor comodidad, es mejor crear perfiles distintos para cada tiempo de ejecución de destino y colocar los archivos publicados en un directorio específico de la plataforma. Esto implica la creación de un perfil de publicación independiente para cada plataforma de destino. Por tanto, vuelva a compilar la aplicación para cada plataforma siguiendo estos pasos:

         1. Seleccione **Crear nuevo perfil** en el cuadro de diálogo **Publicar**.

         1. En el cuadro de diálogo **Elegir un destino de publicación**, cambie la ubicación **Elegir una carpeta** a *bin\Release\PublishOutput\win10-x64*. Seleccione **Aceptar**.

         1. Seleccione el nuevo perfil (**FolderProfile1**) en la lista de perfiles y asegúrese de que el **Tiempo de ejecución de destino** es `win10-x64`. Si no lo es, seleccione **Configuración**. En el cuadro de diálogo **Configuración de perfil**, cambie **Tiempo de ejecución de destino** por `win10-x64` y haga clic en **Guardar**. En caso contrario, haga clic en **Cancelar**.

         1. Seleccione **Publicar** para publicar la aplicación para las plataformas de 64 bits de Windows 10.

         1. Siga los pasos anteriores de nuevo para crear un perfil para la plataforma `osx.10.11-x64`. La **Ubicación de destino** es *bin\Release\PublishOutput\osx.10.11-x64* y el **Tiempo de ejecución de destino** es `osx.10.11-x64`. El nombre que Visual Studio asigna a este perfil es **FolderProfile2**.

      Tenga en cuenta que cada ubicación de destino contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesarios para iniciar la aplicación.

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

Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias. Se requieren los pasos adicionales siguientes antes de poder compilar la aplicación:

1. Use el **Administrador de paquetes NuGet** para agregar una referencia a un paquete de NuGet para el proyecto y, si el paquete todavía no está disponible en el sistema, instálelo. Para abrir el administrador de paquetes, seleccione **Herramientas** > **Administrador de paquetes NuGet** > **Administrar paquetes NuGet para la solución**.

1. Confirme que `Newtonsoft.Json` está instalado en el sistema y, si no es así, instálelo. La pestaña **Instalado** enumera los paquetes de NuGet instalados en el sistema. Si `Newtonsoft.Json` no aparece ahí, seleccione la pestaña **Examinar** y escriba "Newtonsoft.Json" en el cuadro de búsqueda. Seleccione `Newtonsoft.Json` y, en el panel derecho, seleccione el proyecto antes de hacer clic en **Instalar**.

1. Si `Newtonsoft.Json` ya está instalado en el sistema, agréguelo al proyecto seleccionando el proyecto en el panel derecho de la pestaña **Administrar paquetes para la solución**.

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

Tenga en cuenta que solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca. Esto es similar a tener dependencias de terceros con dependencias nativas en la implementación dependiente de la plataforma, donde las dependencias nativas no existirán en la plataforma de destino a menos que se hayan instalado allí previamente.

# <a name="see-also"></a>Vea también
[Implementación de aplicaciones .NET Core](index.md)   
[Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)   
