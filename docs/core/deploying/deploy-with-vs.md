---
title: Implementación de aplicaciones de .NET Core con Visual Studio
description: Aprenda a implementar una aplicación de .NET Core con Visual Studio.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 1c9aba10e27609bdf8e95d844ead60fd0ec0bd2c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538728"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a>Implementación de aplicaciones de .NET Core con Visual Studio

Puede implementar una aplicación de .NET Core como una *implementación dependiente de la plataforma*, que incluye los archivos binarios de la aplicación pero depende de la presencia de .NET Core en el sistema de destino, o como una *implementación independiente*, que incluye la aplicación y los archivos binarios de .NET Core. Para obtener información general sobre la implementación de aplicaciones de NET Core, vea [Implementación de aplicaciones .NET Core](index.md).

En las secciones siguientes se muestra cómo usar Microsoft Visual Studio para crear los siguientes tipos de implementaciones:

- Implementación dependiente de marco de trabajo
- Implementación dependiente de marco de trabajo con dependencias de terceros
- Implementación autocontenida
- Implementación autocontenida con dependencias de terceros

Para obtener información sobre el uso de Visual Studio para desarrollar aplicaciones de .NET Core, vea [Dependencias y requisitos de .NET Core](../install/windows.md) .

## <a name="framework-dependent-deployment"></a>Implementación dependiente de marco de trabajo

La implementación de una implementación dependiente del marco sin dependencias de terceros implica simplemente la compilación, la prueba y la publicación de la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso.

1. Crear el proyecto.

   Seleccione **Archivo** > **Nuevo** > **Proyecto**. En el cuadro de diálogo **Nuevo proyecto**, expanda las categorías de proyecto del lenguaje (C# o Visual Basic) en el panel de tipos de proyecto **instalados**, elija **.NET Core** y luego seleccione la plantilla **Aplicación de consola (.NET Core)** en el panel central. Escriba un nombre de proyecto, como "FDD", en el cuadro de texto **Nombre**. Seleccione el botón **Aceptar**.

1. Agregar el código fuente de la aplicación.

   Abra el archivo *Program.cs* o *Program.vb* en el editor y reemplace el código generado automáticamente por el siguiente. Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

   [!code-csharp[deployment#1](./snippets/deploy-with-vs/csharp/deployment-example.cs)]
   [!code-vb[deployment#1](./snippets/deploy-with-vs/vb/deployment-example.vb)]

1. Crear una versión de depuración de la aplicación.

   Seleccione **Compilar** > **Compilar solución**. También puede compilar y ejecutar la versión de depuración de la aplicación seleccionando **Depurar** > **Iniciar depuración**.

1. Implementar la aplicación.

   Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación. Para publicar desde Visual Studio, siga estos pasos:

      1. Cambie la configuración de la solución de **Depurar** a **Versión** en la barra de herramientas para compilar una compilación de versión (en lugar de depuración) de la aplicación.

      1. Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.

      1. En la pestaña **Publicar**, seleccione **Publicar**. Visual Studio escribe los archivos que componen la aplicación en el sistema de archivos local.

      1. La pestaña **Publicar** muestra ahora un solo perfil, **FolderProfile**. Los valores de configuración del perfil se muestran en la sección **Resumen** de la pestaña.

   Los archivos resultantes se colocan en un directorio denominado `Publish` en Windows y `publish` en sistemas Unix que está en un subdirectorio del subdirectorio *.\bin\release\netcoreapp2.1* del proyecto.

Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones. Puede decidir no empaquetarlo con los archivos de la aplicación. Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.

Implemente el conjunto completo de archivos de la aplicación del modo que quiera. Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera. Una vez instalados, los usuarios pueden ejecutar la aplicación mediante el comando `dotnet` y proporcionando el nombre de archivo, como `dotnet fdd.dll`.

Además de los archivos binarios de la aplicación, el instalador también debe empaquetar el instalador de marco compartido o buscarlo como requisito previo como parte de la instalación de la aplicación.  La instalación del marco compartido requiere acceso raíz o de administrador dado que implica a toda la máquina.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>Implementación dependiente de marco de trabajo con dependencias de terceros

La implementación de una implementación dependiente de la plataforma con una o más dependencias de terceros requiere que todas las dependencias estén disponibles para el proyecto. Se requieren los pasos adicionales siguientes antes de poder compilar la aplicación:

1. Use el **Administrador de paquetes NuGet** para agregar una referencia a un paquete de NuGet para el proyecto y, si el paquete todavía no está disponible en el sistema, instálelo. Para abrir el administrador de paquetes, seleccione **Herramientas** > **Administrador de paquetes NuGet** > **Administrar paquetes NuGet para la solución**.

1. Confirme que las dependencias de terceros (por ejemplo, `Newtonsoft.Json`) están instaladas en el sistema y, si no es así, instálelas. La pestaña **Instalado** enumera los paquetes de NuGet instalados en el sistema. Si `Newtonsoft.Json` no aparece ahí, seleccione la pestaña **Examinar** y escriba "Newtonsoft.Json" en el cuadro de búsqueda. Seleccione `Newtonsoft.Json` y, en el panel derecho, seleccione el proyecto antes de hacer clic en **Instalar**.

1. Si `Newtonsoft.Json` ya está instalado en el sistema, agréguelo al proyecto seleccionando el proyecto en el panel derecho de la pestaña **Administrar paquetes para la solución**.

Una implementación dependiente del marco con dependencias de terceros solo es tan portátil como sus dependencias de terceros. Por ejemplo, si una biblioteca de terceros solo admite macOS, la aplicación no se puede portar a sistemas Windows. Esto ocurre si la dependencia de terceros propiamente dicha depende del código nativo. Un buen ejemplo de esto es [el servidor Kestrel](/aspnet/core/fundamentals/servers/kestrel), que requiere una dependencia nativa de [libuv](https://github.com/libuv/libuv). Cuando se crea una FDD para una aplicación con esta clase de dependencia de terceros, el resultado publicado contiene una carpeta para cada [identificador en tiempo de ejecución (RID)](../rid-catalog.md) que admita la dependencia nativa (y que exista en su paquete de NuGet).

## <a name="self-contained-deployment-without-third-party-dependencies"></a><a name="simpleSelf"></a> Implementación independiente sin dependencias de terceros

La implementación de una implementación independiente sin dependencias de terceros implica crear el proyecto, modificar el archivo *csproj* y compilar, probar y publicar la aplicación. Un sencillo ejemplo escrito en C# ilustra el proceso. Empiece por crear, codificar y probar el proyecto, como haría en el caso de una implementación dependiente del marco de trabajo:

1. Crear el proyecto.

   Seleccione **Archivo** > **Nuevo** > **Proyecto**. En el cuadro de diálogo **Nuevo proyecto**, expanda las categorías de proyecto del lenguaje (C# o Visual Basic) en el panel de tipos de proyecto **instalados**, elija **.NET Core** y luego seleccione la plantilla **Aplicación de consola (.NET Core)** en el panel central. Escriba un nombre de proyecto, como "SCD", en el cuadro de texto **Nombre** y pulse el botón **Aceptar**.

1. Agregar el código fuente de la aplicación.

   Abra el archivo *Program.cs* o *Program.vb* en el editor y reemplace el código generado automáticamente por el siguiente. Pide al usuario que escriba texto y muestra las palabras individuales escritas por el usuario. Se usa la expresión regular `\w+` para separar las palabras en el texto de entrada.

   [!code-csharp[deployment#1](./snippets/deploy-with-vs/csharp/deployment-example.cs)]
   [!code-vb[deployment#1](./snippets/deploy-with-vs/vb/deployment-example.vb)]

1. Determine si quiere usar el modo de globalización invariable.

   Especialmente si la aplicación es para Linux, puede reducir el tamaño total de la implementación si aprovecha las ventajas del [modo de globalización invariable](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md). El modo de globalización invariable es útil para aquellas aplicaciones que no son globales y que pueden usar las convenciones de formato, las convenciones de mayúsculas y minúsculas y el criterio de ordenación y la comparación de cadenas de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture).

   Para habilitar el modo invariable, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Editar SCD.csproj** o **Editar SCD.vbproj**. Luego agregue las siguientes líneas resaltadas al archivo:

   [!code-xml[globalization-invariant-mode](./snippets/deploy-with-vs/xml/invariant.csproj?highlight=7-9)]

1. Cree una compilación de depuración de la aplicación.

   Seleccione **Compilar** > **Compilar solución**. También puede compilar y ejecutar la versión de depuración de la aplicación seleccionando **Depurar** > **Iniciar depuración**. Este paso de depuración permite identificar problemas con la aplicación cuando se ejecuta en la plataforma de host. Pero, aun así, tiene que probarla en cada una de las plataformas de destino.

   Si ha habilitado el modo de globalización invariable, asegúrese especialmente de probar si la ausencia de datos dependientes de la referencia cultural es adecuada para la aplicación.

Una vez que haya terminado de depurar, puede publicar la implementación independiente:

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earlier"></a>[Visual Studio 15.6 y anterior](#tab/vs156)

Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino.

Para publicar la aplicación desde Visual Studio, siga estos pasos:

1. Definir las plataformas de destino de la aplicación.

   1. Haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Editar SCD.csproj**.

   1. Cree una etiqueta `<RuntimeIdentifiers>` en la sección `<PropertyGroup>` del archivo *csproj* que defina las plataformas a las que se destina la aplicación y especifique el identificador en tiempo de ejecución (RID) de cada una. También debe agregar un punto y coma para separar los RID. Para ver una lista de identificadores de tiempo de ejecución, consulte el [catálogo de identificadores de tiempo de ejecución](../rid-catalog.md).

   Por ejemplo, el ejemplo siguiente indica que la aplicación se ejecuta en sistemas operativos Windows 10 de 64 bits y OS X versión 10.11 de 64 bits.

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   El elemento `<RuntimeIdentifiers>` puede ir en cualquier `<PropertyGroup>` que tenga en el archivo *csproj*. Más adelante en esta sección aparece un ejemplo completo del archivo *csproj*.

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

      Cada ubicación de destino contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesarios para iniciar la aplicación.

Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones. Puede decidir no empaquetarlo con los archivos de la aplicación. Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.

Implemente los archivos publicados de la forma que quiera. Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.

A continuación se muestra el archivo *csproj* completo para este proyecto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[Visual Studio 15.7 y posterior](#tab/vs157)

Después de depurar y probar el programa, cree los archivos que se implementarán con la aplicación para cada una de las plataformas de destino. Esto implica la creación de un perfil independiente para cada plataforma de destino.

Haga lo siguiente para cada plataforma que sea destino de la aplicación:

1. Cree un perfil para la plataforma de destino.

   Si este es el primer perfil que ha creado, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.

   Si ya ha creado un perfil, haga clic con el botón derecho en el proyecto para abrir el cuadro de diálogo **Publicar**, si aún no está abierto. Luego seleccione **Nuevo perfil**.

   Se abre el cuadro de diálogo **Elegir un destino de publicación**.

1. Seleccione la ubicación en la que Visual Studio publica la aplicación.

   Si solo se va a publicar en una plataforma, se puede aceptar el valor predeterminado del cuadro de texto **Elegir una carpeta**; así, se publica la implementación dependiente del marco de la aplicación en el directorio *\<project-directory>\bin\Release\netcoreapp2.1\publish*.

   Si va a publicar en más de una plataforma, anexe una cadena que identifique a la plataforma de destino. Por ejemplo, si anexa la cadena "linux" a la ruta de acceso de archivo, Visual Studio publica la implementación dependiente del marco de la aplicación en el directorio *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux*.

1. Para crear el perfil, seleccione el icono de lista desplegable situado junto al botón **Publicar** y luego **Crear perfil**. Después, seleccione el botón **Crear perfil** para crear el perfil.

1. Indique que va a publicar una implementación independiente y defina una plataforma como destino de la aplicación.

   1. En el cuadro de diálogo **Publicar**, seleccione el vínculo **Configurar** para abrir el cuadro de diálogo **Configuración del perfil**.

   1. Seleccione **Independiente** en el cuadro de lista **Modo de implementación**.

   1. En el cuadro de lista **Tiempo de ejecución de destino**, seleccione una de las plataformas de destino de la aplicación.

   1. Seleccione **Guardar** para aceptar los cambios y cerrar el cuadro de diálogo.

1. Asigne un nombre al perfil.

   1. Seleccione **Acciones** > **Cambiar nombre de perfil** apara asignar el nombre al perfil.

   2. Asigne al perfil un nombre que identifique a la plataforma de destino y luego seleccione **Guardar*.

Repita estos pasos para definir las plataformas de destino adicionales de la aplicación.

Ha configurado los perfiles y ahora está listo para publicar la aplicación. Para hacerlo:

   1. Si la ventana **Publicar** no está abierta, haga clic con el botón derecho en el proyecto (no en la solución) en el **Explorador de soluciones** y seleccione **Publicar**.

   2. Seleccione el perfil que quiere publicar y luego **Publicar**. Realice este procedimiento para cada perfil que se vaya a publicar.

   Cada ubicación de destino (en el caso de nuestro ejemplo, bin\release\netcoreapp2.1\publish\\*profile-name* contiene el conjunto completo de archivos (los archivos de aplicación y todos los archivos de .NET Core) necesarios para iniciar la aplicación.

Junto con los archivos de la aplicación, el proceso de publicación emite un archivo de base de datos de programa (.pdb) que contiene información de depuración sobre la aplicación. El archivo es útil principalmente para depurar excepciones. Puede decidir no empaquetarlo con los archivos de la aplicación. Pero se debe guardar en caso de que se quiera depurar la compilación de versión de la aplicación.

Implemente los archivos publicados de la forma que quiera. Por ejemplo, puede empaquetarlos en un archivo ZIP, usar un simple comando `copy` o implementarlos con el paquete de instalación que prefiera.

A continuación se muestra el archivo *csproj* completo para este proyecto.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Además, Visual Studio crea un perfil de publicación independiente (\*.pubxml) para cada plataforma de destino. Por ejemplo, el archivo para nuestro perfil de Linux (linux.pubxml) aparece así:

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a>Implementación autocontenida con dependencias de terceros

Implementar una implementación independiente con una o varias dependencias de terceros implica agregar las dependencias. Se requieren los pasos adicionales siguientes antes de poder compilar la aplicación:

1. Use el **Administrador de paquetes NuGet** para agregar una referencia a un paquete de NuGet para el proyecto y, si el paquete todavía no está disponible en el sistema, instálelo. Para abrir el administrador de paquetes, seleccione **Herramientas** > **Administrador de paquetes NuGet** > **Administrar paquetes NuGet para la solución**.

1. Confirme que las dependencias de terceros (por ejemplo, `Newtonsoft.Json`) están instaladas en el sistema y, si no es así, instálelas. La pestaña **Instalado** enumera los paquetes de NuGet instalados en el sistema. Si `Newtonsoft.Json` no aparece ahí, seleccione la pestaña **Examinar** y escriba "Newtonsoft.Json" en el cuadro de búsqueda. Seleccione `Newtonsoft.Json` y, en el panel derecho, seleccione el proyecto antes de hacer clic en **Instalar**.

1. Si `Newtonsoft.Json` ya está instalado en el sistema, agréguelo al proyecto seleccionando el proyecto en el panel derecho de la pestaña **Administrar paquetes para la solución**.

A continuación se muestra el archivo *csproj* completo de este proyecto:

# <a name="visual-studio-156-and-earlier"></a>[Visual Studio 15.6 y anterior](#tab/vs156)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[Visual Studio 15.7 y posterior](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

Al implementar la aplicación, los archivos de aplicación también contienen las dependencias de terceros usadas en la aplicación. No se requieren las bibliotecas de terceros en el sistema en el que se ejecuta la aplicación.

Solo puede implementar una implementación autocontenida con una biblioteca de terceros en plataformas compatibles con esa biblioteca. Esto es similar a tener dependencias de terceros con dependencias nativas en la implementación dependiente de la plataforma, donde las dependencias nativas no existirán en la plataforma de destino a menos que se hayan instalado allí previamente.

## <a name="see-also"></a>Vea también

- [Implementación de aplicaciones .NET Core](index.md)
- [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)
