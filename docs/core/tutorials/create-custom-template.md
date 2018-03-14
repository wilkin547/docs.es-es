---
title: "Creación de una plantilla personalizada para dotnet new"
description: "Obtenga información sobre cómo crear una plantilla personalizada para el comando dotnet new en este ameno tutorial."
keywords: ".NET, .NET Core, plantilla, creación de plantillas, tutorial, dotnet new"
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 519b910a-6efe-4394-9b81-0546aa3e7462
ms.workload:
- dotnetcore
ms.openlocfilehash: bf523ead40d0e3cc9148b48d5c7a4a84d3d5cb81
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="create-a-custom-template-for-dotnet-new"></a>Creación de una plantilla personalizada para dotnet new

En este tutorial se le enseñará a hacer lo siguiente:

- Crear una plantilla básica a partir de un proyecto existente o un nuevo proyecto de aplicación de consola.
- Empaquetar la plantilla para su distribución en nuget.org o a partir de un archivo *nupkg* local.
- Instalar la plantilla desde nuget.org, un archivo *nupkg* local o el sistema de archivos local.
- Desinstalar la plantilla.

Si prefiere hacer uso del tutorial con una muestra completa, descargue la [plantilla de proyecto de muestra](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package). La plantilla de muestra está configurada para la distribución de NuGet.

Si quiere usar el ejemplo descargado con la distribución del sistema de archivos, haga lo siguiente:

- Suba un nivel el contenido de la carpeta *content* de la muestra a la carpeta *GarciaSoftware.ConsoleTemplate.CSharp*.
- Elimine la carpeta *content* vacía.
- Elimine el archivo *nuspec*.

## <a name="prerequisites"></a>Requisitos previos

- Instalar el [SDK de .NET Core 2.0](https://www.microsoft.com/net/core) o una versión posterior.
- Leer el tema de referencia [Custom templates for dotnet new](../tools/custom-templates.md) (Plantillas personalizadas para dotnet new).

## <a name="create-a-template-from-a-project"></a>Creación de una plantilla a partir de un proyecto

Use un proyecto existente que se haya confirmado que se compila y se ejecuta, o cree un nuevo proyecto de aplicación de consola en una carpeta del disco duro. En este tutorial se da por hecho que el nombre de la carpeta de proyecto es *GarciaSoftware.ConsoleTemplate.CSharp* y que está almacenada en *Documentos\Plantillas* en el perfil del usuario. El nombre de la plantilla de proyecto del tutorial tiene el formato *\<nombre de la compañía>.\<tipo de plantilla>.\<lenguaje de programación>*, pero puede asignar el nombre que quiera al proyecto y a la plantilla.

1. Agregue una carpeta a la raíz del proyecto denominada *.template.config*.
1. Dentro de la carpeta *.template.config*, cree un archivo *template.json* para configurar la plantilla. Para obtener más información y definiciones de miembros para el archivo *template.json*, vea el tema [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) (Plantillas personalizadas para dotnet new) y el esquema [*template.json* en el almacenamiento del esquema JSON](http://json.schemastore.org/template).

```json
{
    "$schema": "http://json.schemastore.org/template",
    "author": "Catalina Garcia",
    "classifications": [ "Common", "Console" ],
    "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
    "name": "Garcia Software Console Application",
    "shortName": "garciaconsole"
}
```

Ha terminado la plantilla. Una vez hecho esto, tiene dos opciones para la distribución de la plantilla. Para continuar con este tutorial, elija uno de los dos pasos siguientes:

1. [Distribución de NuGet](#use-nuget-distribution): instalación de la plantilla de NuGet o del paquete *nupkg* local y uso de la plantilla instalada.
2. [Distribución del sistema de archivos](#use-file-system-distribution).

## <a name="use-nuget-distribution"></a>Uso de la distribución de NuGet

### <a name="pack-the-template-into-a-nuget-package"></a>Empaquetar la plantilla en un paquete de NuGet

1. Cree una carpeta para el paquete de NuGet. Para el tutorial, se usa el nombre de carpeta *GarciaSoftware.ConsoleTemplate.CSharp*, y esta se crea dentro de una carpeta *Documentos\NuGetTemplates* del perfil del usuario. Cree una carpeta denominada *content* dentro de la nueva carpeta de plantillas que contendrá los archivos del proyecto.
1. Copie el contenido de la carpeta del proyecto, junto con el archivo *.template.config/template.json*, en la carpeta *content* que ha creado.
1. Junto a la carpeta *content*, agregue un [archivo *nuspec*](/nuget/create-packages/creating-a-package). El archivo nuspec es un archivo de manifiesto XML en el que se describe el contenido de un paquete y que controla el proceso de creación del paquete de NuGet.
   
   ![Estructura de directorios en la que se muestra el diseño del paquete de NuGet](./media/create-custom-template/nugetdirectorylayout.png)

1. Dentro de un elemento **\<packageTypes>** en el archivo *nuspec*, incluya un elemento **\<packageType>** con un valor de atributo `name` de `Template`. Tanto la carpeta *content* como el archivo *nuspec* deben estar en el mismo directorio. En la tabla se muestran los elementos de archivo *nuspec* mínimos necesarios para generar una plantilla como un paquete NuGet.

   | Elemento            | Tipo   | Description |
   | ------------------ | ------ | ----------- |
   | **\<authors>**     | cadena | Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores. |
   | **\<description>** | cadena | Una descripción larga del paquete para su visualización en la interfaz de usuario. |
   | **\<id>**          | cadena | El identificador del paquete que no distingue entre mayúsculas y minúsculas, que debe ser único en nuget.org o en la galería en la que se mantendrá el paquete. Los id. no pueden contener espacios ni caracteres no válidos para una URL y normalmente seguirán las reglas de espacios de nombres de .NET. Vea [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) (Elección de un identificador de paquete único y establecimiento del número de versión) para obtener instrucciones. |
   | **\<packageType>** | cadena | Coloque este elemento dentro de un elemento **\<packageTypes>** entre los elementos **\<metadata>**. Establezca el atributo `name` del elemento **\<packageType>** en `Template`. |
   | **\<version>**     | cadena | La versión del paquete, siguiendo el patrón de mayor.menor.revisión. Los números de versión pueden incluir un sufijo de versión preliminar, tal y como se describe en [Versiones preliminares](/nuget/create-packages/prerelease-packages#semantic-versioning). |

   Consulte [.nuspec reference](/nuget/schema/nuspec) (Referencia de .nuspec) para ver el esquema de archivo de *nuspec* completo.

   El archivo *nuspec* para el tutorial se denomina *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* e incluye el siguiente contenido:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. [Cree el paquete](/nuget/create-packages/creating-a-package#creating-the-package) mediante el comando `nuget pack <PATH_TO_NUSPEC_FILE>`. En el comando siguiente se da por supuesto que la carpeta que contiene los recursos de NuGet está en *C:\Users\\\<USUARIO>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp\*. En cambio, no importa dónde ponga la carpeta en el sistema, el comando `nuget pack` acepta la ruta de acceso al archivo *nuspec*:

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a>Publicación del paquete en nuget.org

Para publicar un paquete de NuGet, siga las instrucciones del tema [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) (Crear y publicar un paquete). En cambio, se recomienda que no publique la plantilla de tutorial en NuGet, ya que no se puede eliminar una vez publicada, solo se puede eliminar de la lista. Ahora que tiene el paquete de NuGet en forma de un archivo *nupkg*, le recomendamos que siga estas instrucciones para instalar la plantilla directamente a partir del archivo *nupkg* local.

### <a name="install-the-template-from-a-nuget-package"></a>Instalación de la plantilla a partir de un paquete de NuGet

#### <a name="install-the-template-from-the-local-nupkg-file"></a>Instalación de la plantilla a partir del archivo *nupkg* local

Para instalar la plantilla a partir del archivo *nupkg* que ha creado, use el comando `dotnet new` con la opción `-i|--install` y proporcione la ruta de acceso al archivo *nupkg*:

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a>Instalación de la plantilla a partir de un paquete de NuGet almacenado en nuget.org

Si quiere volver a instalar una plantilla a partir de un paquete de NuGet almacenado en nuget.org, use el comando `dotnet new` con la opción `-i|--install` y proporcione el nombre del paquete de NuGet:

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> El ejemplo solamente sirve de demostración. No hay ningún paquete de NuGet denominado `GarciaSoftware.ConsoleTemplate.CSharp` en nuget.org y no se recomienda que publique y consuma las plantillas de prueba de NuGet. Si ejecuta el comando, no se instala ninguna plantilla. En cambio, puede instalar una plantilla que no se haya publicado en nuget.org si hace referencia al archivo *nupkg* directamente en el sistema de archivos local, tal y como se muestra en la sección anterior [Instalación de la plantilla a partir de un archivo nupkg local](#install-the-template-from-the-local-nupkg-file).

Si quiere ver un ejemplo de cómo instalar una plantilla de un paquete en nuget.org, puede usar la [plantilla de NUnit 3 para dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/). Esta plantilla configura un proyecto para usar las pruebas unitarias de NUnit. Use el comando siguiente para instalarla:

```console
dotnet new -i NUnit3.DotNetNew.Template
```

Al enumerar las plantillas con `dotnet new -l`, verá el *proyecto de prueba de NUnit 3* con el breve nombre de *nunit* en la lista de plantillas. Está listo para usar la plantilla en la sección siguiente.

![Ventana de consola en la que muestra la plantilla de NUnit junto a otras plantillas instaladas](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a>Creación de un proyecto a partir de la plantilla

Después de instalar la plantilla desde NuGet, ejecute el comando `dotnet new <TEMPLATE>` desde el directorio donde quiera que se coloque la salida del motor de plantillas (a menos que esté usando la opción `-o|--output` para especificar un directorio específico) para usarla. Para obtener más información, consulte las [Opciones de `dotnet new`](~/docs/core/tools/dotnet-new.md#options). Proporcione el nombre breve de la plantilla directamente junto al comando `dotnet new`. Para crear un proyecto a partir de la plantilla de NUnit, ejecute el siguiente comando:

```console
dotnet new nunit
```

En la consola se muestra que se crea el proyecto y que se restauran los paquetes de este. Después de ejecutar el comando, el proyecto estará listo para usarse.

![Ventana de consola en la que se muestra la salida del comando dotnet new en el proceso de creación del proyecto de NUnit y de restauración de las dependencias del proyecto](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Desinstalación de una plantilla de un paquete de NuGet almacenado en nuget.org

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> El ejemplo solamente sirve de demostración. No hay ningún paquete de NuGet denominado `GarciaSoftware.ConsoleTemplate.CSharp` en nuget.org ni instalado con el SDK de .NET Core. Si ejecuta el comando, no se desinstalará ninguna plantilla ni paquete y se mostrará la siguiente excepción:
> 
> > Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp' (No se ha encontrado nada denominado “GarciaSoftware.ConsoleTemplate.CSharp” para desinstalarlo).

Si ha instalado la [plantilla de NUnit 3 para dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) y quiere desinstalarla, use el comando siguiente:

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a>Desinstalación de la plantilla de un paquete de nupkg local

Si quiere desinstalar la plantilla, no intente usar la ruta de acceso al archivo *nupkg*. *Si intenta desinstalar una plantilla mediante `dotnet new -u <PATH_TO_NUPKG_FILE>`, se produce un error.* Haga referencia al paquete por su `id`:

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a>Uso de la distribución del sistema de archivos

Para distribuir la plantilla, coloque la carpeta de plantillas de proyecto en una ubicación accesible para los usuarios de la red. Use el comando `dotnet new` con la opción `-i|--install` y especifique la ruta de acceso a la carpeta de plantillas (la carpeta del proyecto que contiene el proyecto y la carpeta *.template.config*).

En este tutorial se da por supuesto que la plantilla de proyecto se almacena en la carpeta *Documents/Templates* del perfil de usuario. Desde esa ubicación, instale la plantilla con el comando siguiente, pero reemplazando \<USER> con el nombre del perfil de usuario:

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a>Creación de un proyecto a partir de la plantilla

Después de instalar la plantilla a partir del sistema de archivos, ejecute el comando `dotnet new <TEMPLATE>` desde el directorio donde quiera que se coloque la salida del motor de plantillas (a menos que esté usando la opción `-o|--output` para especificar un directorio específico) para usarla. Para obtener más información, consulte las [Opciones de `dotnet new`](~/docs/core/tools/dotnet-new.md#options). Proporcione el nombre breve de la plantilla directamente junto al comando `dotnet new`.

Desde una nueva carpeta de proyecto creada en *C:\Users\\\<USUARIO>\Documentos\Proyectos\MyConsoleApp*, cree un proyecto a partir de la plantilla `garciaconsole`:

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a>Desinstalación de la plantilla

Si ha creado la plantilla en el sistema de archivos local en*C:\Users\\\<USUARIO>\Documentos\Plantillas\GarciaSoftware.ConsoleTemplate.CSharp*, desinstálela con el modificador `-u|--uninstall` e indicando la ruta de acceso a la carpeta de la plantilla:

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Para desinstalar la plantilla del sistema de archivos local, debe usar el nombre completo de la ruta de acceso. Por ejemplo, *C:\Users\\\<USUARIO>\Documentos\Plantillas\GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.
> Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.

## <a name="see-also"></a>Vea también

[Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki)  
[Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)  
[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) (Cómo crear sus propias plantillas para dotnet new)  
[Esquema *template.json* en el Almacenamiento del esquema JSON](http://json.schemastore.org/template)  
