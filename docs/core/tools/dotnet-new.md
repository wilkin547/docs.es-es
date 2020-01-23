---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 05/06/2019
ms.openlocfilehash: c9529e135f48c80f445c91038294a3e7266486f1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420473"
---
# <a name="dotnet-new"></a>dotnet new

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.

## <a name="synopsis"></a>Sinopsis

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.

El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.

## <a name="arguments"></a>Argumentos

`TEMPLATE`

La plantilla de la que se va a crear una instancia cuando se invoca el comando. Cada plantilla puede tener opciones específicas que puede pasar. Para obtener más información, vea [Opciones de plantilla](#template-options).

Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto**, se realiza una coincidencia de subcadena con esas dos columnas.

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -l` para obtener una lista de las plantillas disponibles. En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core 2.2.100. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

| Plantillas                                    | Nombre corto        | Lenguaje     | Etiquetas                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| Aplicación de consola                          | `console`         | [C#], F#, VB | Común/Consola                        |
| Biblioteca de clases                                | `classlib`        | [C#], F#, VB | Común/Biblioteca                        |
| Proyecto de prueba unitaria                            | `mstest`          | [C#], F#, VB | Prueba/MSTest                           |
| Proyecto de prueba de NUnit 3                         | `nunit`           | [C#], F#, VB | Prueba/NUnit                            |
| Elemento de prueba de NUnit 3                            | `nunit-test`      | [C#], F#, VB | Prueba/NUnit                            |
| Proyecto de prueba de xUnit                           | `xunit`           | [C#], F#, VB | Prueba/xUnit                            |
| Página de Razor                                   | `page`            | [C#]         | Web/ASP.NET                           |
| MVC ViewImports                              | `viewimports`     | [C#]         | Web/ASP.NET                           |
| MVC ViewStart                                | `viewstart`       | [C#]         | Web/ASP.NET                           |
| Vacío de ASP.NET Core                           | `web`             | [C#], F#     | Web/Vacío                             |
| Aplicación web de ASP.NET Core (Model-View-Controller) | `mvc`             | [C#], F#     | Web/MVC                               |
| Aplicación web de ASP.NET Core                         | `webapp`, `razor` | [C#]         | Web/MVC/Razor Pages                   |
| ASP.NET Core con Angular                    | `angular`         | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js                   | `react`           | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js y Redux         | `reactredux`      | [C#]         | Web/MVC/SPA                           |
| Biblioteca de clases de Razor                          | `razorclasslib`   | [C#]         | Web/Razor/Biblioteca/Biblioteca de clases de Razor |
| API web de ASP.NET Core                         | `webapi`          | [C#], F#     | Web/WebAPI                            |
| archivo global.json                             | `globaljson`      |              | Configuración                                |
| Configuración de NuGet                                 | `nugetconfig`     |              | Configuración                                |
| Configuración web                                   | `webconfig`       |              | Configuración                                |
| Archivo de solución                                | `sln`             |              | Soluciones                              |

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -l` para obtener una lista de las plantillas disponibles. En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

| Plantillas                                    | Nombre corto      | Lenguaje     | Etiquetas                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| Aplicación de consola                          | `console`       | [C#], F#, VB | Común/Consola                        |
| Biblioteca de clases                                | `classlib`      | [C#], F#, VB | Común/Biblioteca                        |
| Proyecto de prueba unitaria                            | `mstest`        | [C#], F#, VB | Prueba/MSTest                           |
| Proyecto de prueba de xUnit                           | `xunit`         | [C#], F#, VB | Prueba/xUnit                            |
| Página de Razor                                   | `page`          | [C#]         | Web/ASP.NET                           |
| MVC ViewImports                              | `viewimports`   | [C#]         | Web/ASP.NET                           |
| MVC ViewStart                                | `viewstart`     | [C#]         | Web/ASP.NET                           |
| Vacío de ASP.NET Core                           | `web`           | [C#], F#     | Web/Vacío                             |
| Aplicación web de ASP.NET Core (Model-View-Controller) | `mvc`           | [C#], F#     | Web/MVC                               |
| Aplicación web de ASP.NET Core                         | `razor`         | [C#]         | Web/MVC/Razor Pages                   |
| ASP.NET Core con Angular                    | `angular`       | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js                   | `react`         | [C#]         | Web/MVC/SPA                           |
| ASP.NET Core con React.js y Redux         | `reactredux`    | [C#]         | Web/MVC/SPA                           | 
| Biblioteca de clases de Razor                          | `razorclasslib` | [C#]         | Web/Razor/Biblioteca/Biblioteca de clases de Razor |
| API web de ASP.NET Core                         | `webapi`        | [C#], F#     | Web/WebAPI                            |
| archivo global.json                             | `globaljson`    |              | Configuración                                |
| Configuración de NuGet                                 | `nugetconfig`   |              | Configuración                                |
| Configuración web                                   | `webconfig`     |              | Configuración                                |
| Archivo de solución                                | `sln`           |              | Soluciones                              |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -l` para obtener una lista de las plantillas disponibles. En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core 2.0.0. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

| Plantillas                                    | Nombre corto    | Lenguaje     | Etiquetas                |
|----------------------------------------------|---------------|--------------|---------------------|
| Aplicación de consola                          | `console`     | [C#], F#, VB | Común/Consola      |
| Biblioteca de clases                                | `classlib`    | [C#], F#, VB | Común/Biblioteca      |
| Proyecto de prueba unitaria                            | `mstest`      | [C#], F#, VB | Prueba/MSTest         |
| Proyecto de prueba de xUnit                           | `xunit`       | [C#], F#, VB | Prueba/xUnit          |
| Vacío de ASP.NET Core                           | `web`         | [C#], F#     | Web/Vacío           |
| Aplicación web de ASP.NET Core (Model-View-Controller) | `mvc`         | [C#], F#     | Web/MVC             |
| Aplicación web de ASP.NET Core                         | `razor`       | [C#]         | Web/MVC/Razor Pages |
| ASP.NET Core con Angular                    | `angular`     | [C#]         | Web/MVC/SPA         |
| ASP.NET Core con React.js                   | `react`       | [C#]         | Web/MVC/SPA         |
| ASP.NET Core con React.js y Redux         | `reactredux`  | [C#]         | Web/MVC/SPA         |
| API web de ASP.NET Core                         | `webapi`      | [C#], F#     | Web/WebAPI          |
| archivo global.json                             | `globaljson`  |              | Configuración              |
| Configuración de NuGet                                 | `nugetconfig` |              | Configuración              |
| Configuración web                                   | `webconfig`   |              | Configuración              |
| Archivo de solución                                | `sln`         |              | Soluciones            |
| Página de Razor                                   | `page`        |              | Web/ASP.NET         |
| MVC ViewImports                              | `viewimports` |              | Web/ASP.NET         |
| MVC ViewStart                                | `viewstart`   |              | Web/ASP.NET         |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -all` para obtener una lista de las plantillas disponibles. En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core 1.0.1. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

| Plantillas            | Nombre corto    | Lenguaje | Etiquetas           |
|----------------------|---------------|----------|----------------|
| Aplicación de consola  | `console`     | [C#], F# | Común/Consola |
| Biblioteca de clases        | `classlib`    | [C#], F# | Común/Biblioteca |
| Proyecto de prueba unitaria    | `mstest`      | [C#], F# | Prueba/MSTest    |
| Proyecto de prueba de xUnit   | `xunit`       | [C#], F# | Prueba/xUnit     |
| Vacío de ASP.NET Core   | `web`         | [C#]     | Web/Vacío      |
| Aplicación web de ASP.NET Core | `mvc`         | [C#], F# | Web/MVC        |
| API web de ASP.NET Core | `webapi`      | [C#]     | Web/WebAPI     |
| Configuración de NuGet         | `nugetconfig` |          | Configuración         |
| Configuración web           | `webconfig`   |          | Configuración         |
| Archivo de solución        | `sln`         |          | Soluciones       |

---

## <a name="options"></a>Opciones

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

`--dry-run`

Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.

`--force`

Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados. Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`. De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete. Vea un ejemplo en la sección [Ejemplos](#examples).

Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#|VB}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

> [!NOTE]
> Algunos shells interpretan `#` como un carácter especial. En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`--nuget-source`

Especifica un origen de NuGet para usarlo durante la instalación.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

`--type`

Filtra plantillas en función de los tipos disponibles. Los valores predefinidos son "project", "item" u "other".

`-u|--uninstall <PATH|NUGET_ID>`

Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados. Al excluir el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.

> [!NOTE]
> Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso. Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.
> Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--force`

Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados. Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`. De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete. Vea un ejemplo en la sección [Ejemplos](#examples).

Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#|VB}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

> [!NOTE]
> Algunos shells interpretan `#` como un carácter especial. En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`--nuget-source`

Especifica un origen de NuGet para usarlo durante la instalación.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

`--type`

Filtra plantillas en función de los tipos disponibles. Los valores predefinidos son “project”, “item” y “other”.

`-u|--uninstall <PATH|NUGET_ID>`

Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.

> [!NOTE]
> Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso. Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.
> Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--force`

Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados. Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`. De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete. Vea un ejemplo en la sección [Ejemplos](#examples).

Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#|VB}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

> [!NOTE]
> Algunos shells interpretan `#` como un carácter especial. En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

`--type`

Filtra plantillas en función de los tipos disponibles. Los valores predefinidos son “project”, “item” y “other”.

`-u|--uninstall <PATH|NUGET_ID>`

Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.

> [!NOTE]
> Para desinstalar una plantilla mediante un origen `PATH`, debe usar el nombre completo de la ruta de acceso. Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará. Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.
> 
> Si no puede determinar el argumento `PATH` o `NUGET_ID` necesario para desinstalar una plantilla, la ejecución de `dotnet new --uninstall` sin un argumento enumerará todas las plantillas instaladas y el argumento requerido para desinstalarlas.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-all|--show-all`

Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo. Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

> [!NOTE]
> Algunos shells interpretan `#` como un carácter especial. En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

---

## <a name="template-options"></a>Opciones de plantilla

Cada plantilla de proyecto puede tener opciones adicionales disponibles. Las plantillas principales tienen las siguientes opciones adicionales:

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

**console**

`--langVersion <VERSION_NUMBER>`: establece la propiedad `LangVersion` en el archivo de proyecto creado. Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3. No es compatible con F#.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**angular, react, reactredux**

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

`--no-https`: el proyecto no requiere HTTPS. Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.

**razorclasslib**

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**classlib**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp2.2` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard. El valor predeterminado es `netstandard2.0`.

`--langVersion <VERSION_NUMBER>`: establece la propiedad `LangVersion` en el archivo de proyecto creado. Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3. No es compatible con F#.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**mstest, xunit**

`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**nunit**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. El valor predeterminado es `netcoreapp2.1`.

`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**page**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado. El valor predeterminado es `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la página sin PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado. El valor predeterminado es `MyApp.Namespace`.

**web**

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

`--no-https`: el proyecto no requiere HTTPS. Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.

**mvc, webapp**

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Los valores posibles son:

- `None`: sin autenticación (valor predeterminado).
- `Individual`: autenticación individual.
- `IndividualB2C`: autenticación individual con Azure AD B2C.
- `SingleOrg`: autenticación organizativa para un solo inquilino.
- `MultiOrg`: autenticación organizativa para varios inquilinos.
- `Windows`: autenticación de Windows.

`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto. Úsela con la autenticación `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto. Úsela con la autenticación `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto. Úsela con la autenticación `IndividualB2C`.

`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión. Úsela con las autenticaciones `SingleOrg` o `MultiOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

`--client-id <ID>`: el id. de cliente para este proyecto. Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: el dominio para el inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `/signin-oidc`.

`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`--no-https`: el proyecto no requiere HTTPS. `app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`. Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.

`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Los valores posibles son:

- `None`: sin autenticación (valor predeterminado).
- `IndividualB2C`: autenticación individual con Azure AD B2C.
- `SingleOrg`: autenticación organizativa para un solo inquilino.
- `Windows`: autenticación de Windows.

`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto. Úsela con la autenticación `IndividualB2C`.

`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

`--client-id <ID>`: el id. de cliente para este proyecto. Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: el dominio para el inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`--no-https`: el proyecto no requiere HTTPS. `app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`. Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.

`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

**console, angular, react, reactredux, razorclasslib**

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**classlib**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp2.1` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard. El valor predeterminado es `netstandard2.0`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**mstest, xunit**

`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.

**web**

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

`--no-https`: el proyecto no requiere HTTPS. Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Los valores posibles son:

- `None`: sin autenticación (valor predeterminado).
- `IndividualB2C`: autenticación individual con Azure AD B2C.
- `SingleOrg`: autenticación organizativa para un solo inquilino.
- `Windows`: autenticación de Windows.

`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto. Úsela con la autenticación `IndividualB2C`.

`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

`--client-id <ID>`: el id. de cliente para este proyecto. Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: el dominio para el inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

`--no-https`: el proyecto no requiere HTTPS. `app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`. Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Los valores posibles son:

- `None`: sin autenticación (valor predeterminado).
- `Individual`: autenticación individual.
- `IndividualB2C`: autenticación individual con Azure AD B2C.
- `SingleOrg`: autenticación organizativa para un solo inquilino.
- `MultiOrg`: autenticación organizativa para varios inquilinos.
- `Windows`: autenticación de Windows.

`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto. Úsela con la autenticación `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto. Úsela con la autenticación `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto. Úsela con la autenticación `IndividualB2C`.

`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión. Úsela con las autenticaciones `SingleOrg` o `MultiOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

`--client-id <ID>`: el id. de cliente para este proyecto. Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: el dominio para el inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `/signin-oidc`.

`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.

`--use-browserlink`: incluye BrowserLink en el proyecto.

`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

`--no-https`: el proyecto no requiere HTTPS. `app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`. Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.

**page**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado. El valor predeterminado es `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la página sin PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado. El valor predeterminado es `MyApp.Namespace`.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

**console, angular, react, reactredux**

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**classlib**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard. El valor predeterminado es `netstandard2.0`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**mstest, xunit**

`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.

**web**

`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**webapi**

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Los valores posibles son:

- `None`: sin autenticación (valor predeterminado).
- `IndividualB2C`: autenticación individual con Azure AD B2C.
- `SingleOrg`: autenticación organizativa para un solo inquilino.
- `Windows`: autenticación de Windows.

`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto. Úsela con la autenticación `IndividualB2C`.

`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

`--client-id <ID>`: el id. de cliente para este proyecto. Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: el dominio para el inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.

`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**mvc, razor**

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Los valores posibles son:

- `None`: sin autenticación (valor predeterminado).
- `Individual`: autenticación individual.
- `IndividualB2C`: autenticación individual con Azure AD B2C.
- `SingleOrg`: autenticación organizativa para un solo inquilino.
- `MultiOrg`: autenticación organizativa para varios inquilinos.
- `Windows`: autenticación de Windows.

`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto. Úsela con la autenticación `IndividualB2C`.

`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto. Úsela con la autenticación `IndividualB2C`.

`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto. Úsela con la autenticación `IndividualB2C`.

`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión. Úsela con las autenticaciones `SingleOrg` o `MultiOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

`--client-id <ID>`: el id. de cliente para este proyecto. Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

`--domain <DOMAIN>`: el dominio para el inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `/signin-oidc`.

`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.

`--use-browserlink`: incluye BrowserLink en el proyecto.

`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.

**page**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado. El valor predeterminado es `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la página sin PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado. El valor predeterminado es `MyApp.Namespace`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**console, xunit, mstest, web, webapi**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0` o `netcoreapp1.1`. El valor predeterminado es `netcoreapp1.0`.

**classlib**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`. El valor predeterminado es `netstandard1.4`.

**mvc**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0` o `netcoreapp1.1`. El valor predeterminado es `netcoreapp1.0`.

`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar. Valores: `None` o `Individual`. El valor predeterminado es `None`.

`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite. Valores: `true` o `false`. El valor predeterminado es `false`.

---

## <a name="examples"></a>Ejemplos

Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:

`dotnet new "Console Application"`

Creación de un proyecto de aplicación de consola con F# en el directorio actual:

`dotnet new console -lang F#`

Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):

`dotnet new classlib -lang VB -o MyLibrary`

Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:

`dotnet new mvc -au None`

Creación de un proyecto de xUnit:

`dotnet new xunit`

Enumere todas las plantillas disponibles para MVC:

`dotnet new mvc -l`

Enumeración de todas las plantillas que coinciden con la subcadena *we*. No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.

`dotnet new we -l`

Intento de invocar a la plantilla que coincide con *ng*. Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.

`dotnet new ng`

Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a>Vea también

- [Plantillas personalizadas para dotnet new](custom-templates.md)
- [Creación de una plantilla personalizada para dotnet new](../tutorials/cli-templates-create-item-template.md)
- [Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)
