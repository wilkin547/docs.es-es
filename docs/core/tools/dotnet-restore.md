---
title: Comando dotnet restore
description: Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore.
ms.date: 02/27/2020
ms.openlocfilehash: e74027ba70ddf6905a12f9691caeb0a406428ad6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157029"
---
# <a name="dotnet-restore"></a>dotnet restore

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet restore`: restaura las dependencias y las herramientas de un proyecto.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet restore [<ROOT>] [--configfile] [--disable-parallel]
    [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime]
    [-s|--source] [-v|--verbosity] [--interactive]

dotnet restore [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json. De forma predeterminada, la restauración de dependencias y herramientas se ejecuta en paralelo.

Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes. Las fuente se proporcionan normalmente mediante el archivo de configuración *nuget.config*. Cuando se instala el SDK de .NET Core, se proporciona un archivo de configuración predeterminado. Puede especificar más fuentes creando su propio archivo *nuget.config* en el directorio del proyecto. Puede invalidar las fuentes *nuget.config* con la opción - `-s`.

Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`. Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` del directorio de inicio del usuario en todos los sistemas operativos. Por ejemplo, */home/usuario1* en Linux o *C:\Usuarios\usuario1* en Windows.

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

## <a name="implicit-restore"></a>Restauración implícita

El comando `dotnet restore` se ejecuta de forma implícita si es necesario al ejecutar los comandos siguientes:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

En la mayoría de los casos, no es necesario usar el comando `dotnet restore` de forma explícita.

En ocasiones, es posible que no sea conveniente ejecutar `dotnet restore` de forma implícita. Por ejemplo, algunos sistemas automatizados, como los sistemas de compilación, deben llamar a `dotnet restore` explícitamente para controlar cuándo se produce la restauración a fin de controlar el uso de la red. Para evitar que `dotnet restore` se ejecute de forma implícita, se puede usar la marca `--no-restore` con cualquiera de estos comandos para deshabilitar la restauración implícita.

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

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--ignore-failed-sources`**

  Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.

- **`--no-cache`**

  Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.

- **`--no-dependencies`**

  Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.

- **`--packages <PACKAGES_DIRECTORY>`**

  Especifica el directorio de los paquetes restaurados.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Especifica un tiempo de ejecución para la restauración del paquete. Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). Para proporcionar varios RID; especifique esta opción varias veces.

- **`-s|--source <SOURCE>`**

  Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración. Este valor invalida todos los orígenes especificados en los archivos *nuget.config*. Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.

- **`--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `minimal`.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación). Desde .NET Core 2.1.400.

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
