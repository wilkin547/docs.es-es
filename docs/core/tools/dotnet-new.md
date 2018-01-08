---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
keywords: dotnet-new, CLI, comando de CLI, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.workload: dotnetcore
ms.openlocfilehash: f5815e1ad2a36a8ef3279f6ff83465dba9ec5d50
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-new"></a>dotnet new

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a>Description

El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido. 

El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.

## <a name="arguments"></a>Argumentos

`TEMPLATE`

La plantilla de la que se va a crear una instancia cuando se invoca el comando. Cada plantilla puede tener opciones específicas que puede pasar. Para obtener más información, vea [Opciones de plantilla](#template-options).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -l` para obtener una lista de las plantillas disponibles. En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

|Descripción de plantilla                          | Nombre de plantilla  | Lenguajes     |
|----------------------------------------------|----------------|---------------|
| Aplicación de consola                          | consola        | [C#], F#, VB  |
| Biblioteca de clases                                | classlib       | [C#], F#, VB  |
| Proyecto de prueba unitaria                            | mstest         | [C#], F#, VB  |
| Proyecto de prueba xUnit                           | xunit          | [C#], F#, VB  |
| Vacío de ASP.NET Core                           | web            | [C#], F#      |
| Aplicación web de ASP.NET Core (Model-View-Controller) | mvc            | [C#], F#      |
| Aplicación web de ASP.NET Core                         | razor          | [C#]          |
| ASP.NET Core con Angular                    | angular        | [C#]          |
| ASP.NET Core con React.js                   | react          | [C#]          |
| ASP.NET Core con React.js y Redux         | reactredux     | [C#]          |
| API web de ASP.NET Core                         | webapi         | [C#], F#      |
| archivo global.json                             | globaljson     |               |
| Configuración de NuGet                                 | nugetconfig    |               |
| Configuración de la Web                                   | webconfig      |               |
| Archivo de solución                                | sln            |               |
| Página de Razor                                   | página           |               |
| MVC/ViewImports                              | viewimports    |               |
| MVC ViewStart                                | viewstart      |               |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

El comando contiene una lista predeterminada de plantillas. Use `dotnet new -all` para obtener una lista de las plantillas disponibles. En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 1.x. El lenguaje predeterminado de la plantilla se muestra entre corchetes.

|Descripción de plantilla  | Nombre de plantilla  | Lenguajes |
|----------------------|----------------|-----------|
| Aplicación de consola  | consola        | [C#], F#  |
| Biblioteca de clases        | classlib       | [C#], F#  |
| Proyecto de prueba unitaria    | mstest         | [C#], F#  |
| Proyecto de prueba xUnit   | xunit          | [C#], F#  |
| Vacío de ASP.NET Core   | web            | [C#]      |
| Aplicación web de ASP.NET Core | mvc            | [C#], F#  |
| API web de ASP.NET Core | webapi         | [C#]      |
| Configuración de NuGet         | nugetconfig    |           |
| Configuración de la Web           | webconfig      |           |
| Archivo de solución        | sln            |           |

---

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--force`

Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-i|--install <PATH|NUGET_ID>`

Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados. Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#|VB}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

`--type`

Filtra plantillas en función de los tipos disponibles. Los valores predefinidos son “project”, “item” y “other”.

`-u|--uninstall <PATH|NUGET_ID>`

Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.

> [!NOTE]
> Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso. Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.
> Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-all|--show-all`

Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo. Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación. Esto es necesario cuando el directorio de salida ya contiene un proyecto.

`-h|--help`

Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.

`-l|--list`

Muestra las plantillas que contienen el nombre especificado. Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado. Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.

`-lang|--language {C#|F#}`

El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

`-n|--name <OUTPUT_NAME>`

El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

`-o|--output <OUTPUT_DIRECTORY>`

La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

---

## <a name="template-options"></a>Opciones de plantilla

Cada plantilla de proyecto puede tener opciones adicionales disponibles. Las plantillas principales tienen las siguientes opciones adicionales:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**console, angular, react, reactredux**

`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.

**classlib**

`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard. El valor predeterminado es `netstandard2.0`.

`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.

**mstest, xunit**

`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).

`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.

**globaljson**

`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.

**web**

`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.

`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.

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

`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.

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

`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.

**page**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado. El valor predeterminado es `MyApp.Namespace`.

`-np|--no-pagemodel`: crea la página sin PageModel.

**viewimports**

`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado. El valor predeterminado es `MyApp.Namespace`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**console, xunit, mstest, web, webapi**

`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0` o `netcoreapp1.1`. El valor predeterminado es `netcoreapp1.0`.

**classlib**

`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`. El valor predeterminado es `netstandard1.4`.

**mvc**

`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino. Valores: `netcoreapp1.0` o `netcoreapp1.1`. El valor predeterminado es `netcoreapp1.0`.

`-au|--auth`: el tipo de autenticación que se va a usar. Valores: `None` o `Individual`. El valor predeterminado es `None`.

`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite. Valores: `true` o `false`. El valor predeterminado es `false`.

---

## <a name="examples"></a>Ejemplos

Creación de un proyecto de aplicación de consola con F# en el directorio actual:

`dotnet new console -lang f#`

Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):

`dotnet new classlib -lang VB -o MyLibrary`

Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 2.0:

`dotnet new mvc -au None -f netcoreapp2.0`

Creación de una aplicación de xUnit que tenga como destino .NET Core 2.0:

`dotnet new xunit --framework netcoreapp2.0`

Enumere todas las plantillas disponibles para MVC:

`dotnet new mvc -l`

## <a name="see-also"></a>Vea también

[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)  
[Creación de una plantilla personalizada para dotnet new](~/docs/core/tutorials/create-custom-template.md)  
[Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)  
[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)
