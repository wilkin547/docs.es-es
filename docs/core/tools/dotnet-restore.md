---
title: Comando dotnet restore
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
ms.date: 02/27/2020
ms.openlocfilehash: 276fad896a6a8a647ed05a9de8c582d463d9ab8f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005327"
---
# <a name="dotnet-restore"></a>dotnet restore

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet restore [<ROOT>] [--configfile <FILE>] [--disable-parallel]
    [-f|--force] [--force-evaluate] [--ignore-failed-sources]
    [--interactive] [--lock-file-path <LOCK_FILE_PATH>] [--locked-mode]
    [--no-cache] [--no-dependencies] [--packages <PACKAGES_DIRECTORY>]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [-s|--source <SOURCE>]
    [--use-lock-file] [-v|--verbosity <LEVEL>]

dotnet restore -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json.  En la mayoría de los casos, no es necesario usar explícitamente el comando `dotnet restore`, ya que una restauración de NuGet se ejecuta implícitamente si es necesario al ejecutar los siguientes comandos:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

A veces, puede que no sea conveniente ejecutar la restauración de NuGet implícita con estos comandos. Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red. Para evitar la restauración de NuGet implícita, puede usar la marca `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.

### <a name="specify-feeds"></a>Especificación de fuentes

Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes. Las fuente se proporcionan normalmente mediante el archivo de configuración *nuget.config*. Cuando se instala el SDK de .NET Core, se proporciona un archivo de configuración predeterminado. Para especificar fuentes adicionales, realice una de las acciones siguientes:

- Cree su propio archivo *nuget.config* en el directorio del proyecto. Para obtener más información, vea [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior) y [Diferencias de nuget.config](#nugetconfig-differences) más adelante en este artículo.
- Use comandos de `dotnet nuget` como [`dotnet nuget add source`](dotnet-nuget-add-source.md).

Puede invalidar las fuentes *nuget.config* con la opción `-s`.

Para obtener información sobre cómo usar las fuentes autenticadas, vea [Consumir paquetes desde fuentes autenticadas](/nuget/consume-packages/consuming-packages-authenticated-feeds).

### <a name="global-packages-folder"></a>Carpeta de paquetes globales

Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`. Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` del directorio de inicio del usuario en todos los sistemas operativos. Por ejemplo, */home/usuario1* en Linux o *C:\Usuarios\usuario1* en Windows.

### <a name="project-specific-tooling"></a>Herramientas específicas del proyecto

Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.

### <a name="nugetconfig-differences"></a>Diferencias de nuget.config

El comportamiento del comando `dotnet restore` depende de las opciones de configuración del archivo *nuget.config*, si existe. Por ejemplo, establecer `globalPackagesFolder` en *nuget.config* coloca los paquetes NuGet restaurados en la carpeta especificada. Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`. Para más información, consulte la [referencia de nuget.config](/nuget/schema/nuget-config-file).

Hay tres configuraciones específicas que `dotnet restore` omite:

- [bindingRedirects](/nuget/schema/nuget-config-file#bindingredirects-section)

  Los redireccionamientos de enlace no funcionan con elementos de `<PackageReference>` y .NET Core solo admite elementos de `<PackageReference>` para los paquetes NuGet.

- [solution](/nuget/schema/nuget-config-file#solution-section)

  Esta configuración es específica para Visual Studio y no se aplica a .NET Core. .NET Core no usa un archivo `packages.config` y, en su lugar, usa elementos de `<PackageReference>` para los paquetes NuGet.

- [trustedSigners](/nuget/schema/nuget-config-file#trustedsigners-section)

  Esta configuración no es aplicable porque [NuGet ya no admite la comprobación multiplataforma](https://github.com/NuGet/Home/issues/7939) de los paquetes de confianza.

## <a name="arguments"></a>Argumentos

- **`ROOT`**

  Ruta de acceso opcional del archivo de proyecto para restaurar.

## <a name="options"></a>Opciones

- **`--configfile <FILE>`**

  El archivo de configuración de NuGet (*nuget.config*) que se usa para la operación de restauración.

- **`--disable-parallel`**

  Deshabilita la restauración de varios proyectos en paralelo.

- **`--force`**

  Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.

- **`--force-evaluate`**

  Fuerza la restauración para volver a evaluar todas las dependencias aunque ya exista un archivo de bloqueo.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--ignore-failed-sources`**

  Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación). Desde .NET Core 2.1.400.

- **`--lock-file-path <LOCK_FILE_PATH>`**

  Ubicación de salida donde se escribe el archivo de bloqueo del proyecto. De forma predeterminada es *PROJECT_ROOT\packages.lock.json*.

- **`--locked-mode`**

  No permite actualizar el archivo de bloqueo del proyecto.

- **`--no-cache`**

  Especifica que no se almacenen en caché las solicitudes HTTP.

- **`--no-dependencies`**

  Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.

- **`--packages <PACKAGES_DIRECTORY>`**

  Especifica el directorio de los paquetes restaurados.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Especifica un tiempo de ejecución para la restauración del paquete. Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). Para proporcionar varios RID; especifique esta opción varias veces.

- **`-s|--source <SOURCE>`**

  Especifica el URI del origen del paquete NuGet que se usará durante la operación de restauración. Este valor invalida todos los orígenes especificados en los archivos *nuget.config*. Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.

- **`--use-lock-file`**

  Habilita la generación del archivo de bloqueo del proyecto y su uso con la restauración.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `minimal`.

## <a name="examples"></a>Ejemplos

- Restauración de dependencias y herramientas para el proyecto en el directorio actual:

  ```dotnetcli
  dotnet restore
  ```

- Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:

  ```dotnetcli
  dotnet restore ~/projects/app1/app1.csproj
  ```

- Restauración de dependencias y herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages
  ```

- Restauración de dependencias y herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:

  ```dotnetcli
  dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages
  ```

- Restauración de dependencias y herramientas para el proyecto en el directorio actual que muestra una salida detallada:

  ```dotnetcli
  dotnet restore --verbosity detailed
  ```
