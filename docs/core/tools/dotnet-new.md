---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442246"
---
# <a name="dotnet-new"></a>dotnet new

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.

El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.

### <a name="implicit-restore"></a>Restauración implícita

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Argumentos

- **`TEMPLATE`**

  La plantilla de la que se va a crear una instancia cuando se invoca el comando. Cada plantilla puede tener opciones específicas que puede pasar. Para obtener más información, vea [Opciones de plantilla](#template-options).

  Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas. Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.

  A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:

  - Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.
  - Si hay disponible una versión más reciente de la plantilla. En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.

  En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core. El lenguaje predeterminado de la plantilla se muestra entre corchetes. Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.

| Plantillas                                    | Nombre corto                      | Lenguaje     | Etiquetas                                  | Inclusión |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| Aplicación de consola                          | [console](#console)             | [C#], F#, VB | Común/Consola                        | 1.0        |
| Biblioteca de clases                                | [classlib](#classlib)           | [C#], F#, VB | Común/Biblioteca                        | 1.0        |
| Aplicación WPF                              | [wpf](#wpf)                     | [C#]         | Común/WPF                            | 3.0        |
| Biblioteca de clases de WPF                            | [wpflib](#wpf)                  | [C#]         | Común/WPF                            | 3.0        |
| Biblioteca de controles personalizados WPF                   | [wpfcustomcontrollib](#wpf)     | [C#]         | Común/WPF                            | 3.0        |
| Biblioteca de controles de usuario de WPF                     | [wpfusercontrollib](#wpf)       | [C#]         | Común/WPF                            | 3.0        |
| Aplicación de Windows Forms (WinForms)         | [winforms](#winforms)           | [C#]         | Común/WinForms                       | 3.0        |
| Biblioteca de clases de Windows Forms (WinForms)       | [winformslib](#winforms)        | [C#]         | Común/WinForms                       | 3.0        |
| Servicio Worker                               | [worker](#web-others)           | [C#]         | Común/Worker/Web                     | 3.0        |
| Proyecto de prueba unitaria                            | [mstest](#test)                 | [C#], F#, VB | Prueba/MSTest                           | 1.0        |
| Proyecto de prueba de NUnit 3                         | [nunit](#nunit)                  | [C#], F#, VB | Prueba/NUnit                            | 2.1.400    |
| Elemento de prueba de NUnit 3                            | `nunit-test`                    | [C#], F#, VB | Prueba/NUnit                            | 2.2        |
| Proyecto de prueba de xUnit                           | [xunit](#test)                  | [C#], F#, VB | Prueba/xUnit                            | 1.0        |
| Componente Razor                              | `razorcomponent`                | [C#]         | Web/ASP.NET                           | 3.0        |
| Página de Razor                                   | [page](#page)                   | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewImports                              | [viewimports](#namespace)       | [C#]         | Web/ASP.NET                           | 2.0        |
| MVC ViewStart                                | `viewstart`                     | [C#]         | Web/ASP.NET                           | 2.0        |
| Aplicación de servidor Blazor                            | [blazorserver](#blazorserver)   | [C#]         | Web/Blazor                            | 3.0        |
| Vacío de ASP.NET Core                           | [web](#web)                     | [C#], F#     | Web/Vacío                             | 1.0        |
| Aplicación web de ASP.NET Core (Model-View-Controller) | [mvc](#web-options)             | [C#], F#     | Web/MVC                               | 1.0        |
| Aplicación web de ASP.NET Core                         | [webapp, razor](#web-options)   | [C#]         | Web/MVC/Razor Pages                   | 2.2, 2.0   |
| ASP.NET Core con Angular                    | [angular](#spa)                 | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core con React.js                   | [react](#spa)                   | [C#]         | Web/MVC/SPA                           | 2.0        |
| ASP.NET Core con React.js y Redux         | [reactredux](#reactredux)       | [C#]         | Web/MVC/SPA                           | 2.0        |
| Biblioteca de clases de Razor                          | [razorclasslib](#razorclasslib) | [C#]         | Web/Razor/Biblioteca/Biblioteca de clases de Razor | 2.1        |
| API web de ASP.NET Core                         | [webapi](#webapi)               | [C#], F#     | Web/WebAPI                            | 1.0        |
| Servicio gRPC de ASP.NET Core                    | [grpc](#web-others)             | [C#]         | Web/gRPC                              | 3.0        |
| Archivo dotnet gitignore                        | `gitignore`                     |              | Configuración                                | 3.0        |
| archivo global.json                             | [globaljson](#globaljson)       |              | Configuración                                | 2.0        |
| Configuración de NuGet                                 | `nugetconfig`                   |              | Configuración                                | 1.0        |
| Archivo de manifiesto de la herramienta local dotnet              | `tool-manifest`                 |              | Configuración                                | 3.0        |
| Configuración web                                   | `webconfig`                     |              | Configuración                                | 1.0        |
| Archivo de solución                                | `sln`                           |              | Soluciones                              | 1.0        |
| Archivo de búfer de protocolo                         | [proto](#namespace)             |              | Web/gRPC                              | 3.0        |

## <a name="options"></a>Opciones

- **`--dry-run`**

  Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla. Disponible a partir del SDK de .NET Core 2.2.

- **`--force`**

  Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes. Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.

- **`-h|--help`**

  Imprime la ayuda para el comando. Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla. Por ejemplo: `dotnet new mvc --help`.

- **`-i|--install <PATH|NUGET_ID>`**

  Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados. Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`. De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete. Vea un ejemplo en la sección [Ejemplos](#examples).
  
  Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.

  Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).

- **`-l|--list`**

  Muestra las plantillas que contienen el nombre especificado. Si no se especifica ningún nombre, enumera todas las plantillas.

- **`-lang|--language {C#|F#|VB}`**

  El lenguaje de la plantilla que se va a crear. El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)). No es válido para algunas plantillas.

  > [!NOTE]
  > Algunos shells interpretan `#` como un carácter especial. En esos casos, incluya el valor del parámetro de lenguaje entre comillas. Por ejemplo: `dotnet new console -lang "F#"`.

- **`-n|--name <OUTPUT_NAME>`**

  El nombre de la salida creada. Si no se especifica ningún nombre, se usa el nombre del directorio actual.

- **`--nuget-source <SOURCE>`**

  Especifica un origen de NuGet para usarlo durante la instalación. Disponible a partir del SDK de .NET Core 2.1.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  La ubicación para colocar la salida generada. El valor predeterminado es el directorio actual.

- **`--type <TYPE>`**

  Filtra plantillas en función de los tipos disponibles. Los valores predefinidos son `project`, `item` y `other`.

- **`-u|--uninstall [PATH|NUGET_ID]`**

  Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados. Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas. Al especificar `NUGET_ID`, no incluya el número de versión.

  Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.

  > [!NOTE]
  > Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso. Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.
  > No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.

- **`--update-apply`**

  Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala. Disponible desde el SDK de .NET Core 3.0.

- **`--update-check`**

  Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente. Disponible desde el SDK de .NET Core 3.0.

## <a name="template-options"></a>Opciones de plantilla

Cada plantilla de proyecto puede tener opciones adicionales disponibles. Las plantillas principales tienen las siguientes opciones adicionales:

### <a name="console"></a>consola

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Disponible desde el SDK de .NET Core 3.0.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  Establece la propiedad `LangVersion` en el archivo del proyecto creado. Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3. No es compatible con F#. Disponible a partir del SDK de .NET Core 2.2.

  Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto. Disponible a partir del SDK de .NET Core 2.2.

***

### <a name="classlib"></a>classlib

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard. El valor predeterminado es `netstandard2.0`.

- **`--langVersion <VERSION_NUMBER>`**

  Establece la propiedad `LangVersion` en el archivo del proyecto creado. Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3. No es compatible con F#. Disponible a partir del SDK de .NET Core 2.2.

  Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. El valor predeterminado es `netcoreapp3.1`. Disponible a partir del SDK de .NET Core 3.1.

- **`--langVersion <VERSION_NUMBER>`**

  Establece la propiedad `LangVersion` en el archivo del proyecto creado. Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.

  Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> winforms, winformslib

- **`--langVersion <VERSION_NUMBER>`**

  Establece la propiedad `LangVersion` en el archivo del proyecto creado. Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.

  Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="worker-grpc"></a><a name="web-others"></a> worker, grpc

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. El valor predeterminado es `netcoreapp3.1`. Disponible a partir del SDK de .NET Core 3.1.

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="mstest-xunit"></a><a name="test"></a> mstest, xunit

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Opción disponible a partir del SDK de .NET Core 3.0.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="nunit"></a>nunit

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.2         | `netcoreapp2.2` |
  | 2.1         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="page"></a>página

- **`-na|--namespace <NAMESPACE_NAME>`**

  Espacio de nombres del código generado. El valor predeterminado es `MyApp.Namespace`.

- **`-np|--no-pagemodel`**

  Crea la página sin PageModel.

***

### <a name="viewimports-proto"></a><a name="namespace"></a> viewimports, proto

- **`-na|--namespace <NAMESPACE_NAME>`**

  Espacio de nombres del código generado. El valor predeterminado es `MyApp.Namespace`.

***

### <a name="blazorserver"></a>blazorserver

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo de autenticación que se va a usar. Los valores posibles son:

  - `None`: sin autenticación (valor predeterminado).
  - `Individual`: autenticación individual.
  - `IndividualB2C`: autenticación individual con Azure AD B2C.
  - `SingleOrg`: autenticación organizativa para un solo inquilino.
  - `MultiOrg`: autenticación organizativa para varios inquilinos.
  - `Windows`: autenticación de Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  Identificador de la directiva de registro e inicio de sesión de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`-rp|--reset-password-policy-id <ID>`**

  Identificador de la directiva de restablecimiento de contraseñas de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`-ep|--edit-profile-policy-id <ID>`**

  Identificador de la directiva de edición de perfiles de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Instancia de Azure Active Directory con la que se realiza la conexión. Úsela con las autenticaciones `SingleOrg` o `MultiOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Identificador de cliente de este proyecto. Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio del inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

- **`--tenant-id <ID>`**

  Identificador de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `/signin-oidc`.

- **`-r|--org-read-access`**

  Concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`--no-https`**

  Desactiva HTTPS. Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.

- **`-uld|--use-local-db`**

  Especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="web"></a>web

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Opción no disponible en el SDK de .NET Core 2.2.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.1` |

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

- **`--no-https`**

  Desactiva HTTPS.

***

### <a name="mvc-webapp"></a><a name="web-options"></a> mvc, webapp

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo de autenticación que se va a usar. Los valores posibles son:

  - `None`: sin autenticación (valor predeterminado).
  - `Individual`: autenticación individual.
  - `IndividualB2C`: autenticación individual con Azure AD B2C.
  - `SingleOrg`: autenticación organizativa para un solo inquilino.
  - `MultiOrg`: autenticación organizativa para varios inquilinos.
  - `Windows`: autenticación de Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  Identificador de la directiva de registro e inicio de sesión de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`-rp|--reset-password-policy-id <ID>`**

  Identificador de la directiva de restablecimiento de contraseñas de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`-ep|--edit-profile-policy-id <ID>`**

  Identificador de la directiva de edición de perfiles de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Instancia de Azure Active Directory con la que se realiza la conexión. Úsela con las autenticaciones `SingleOrg` o `MultiOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Identificador de cliente de este proyecto. Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio del inquilino del directorio. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `qualified.domain.name`.

- **`--tenant-id <ID>`**

  Identificador de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

- **`--callback-path <PATH>`**

  Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección. Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`. El valor predeterminado es `/signin-oidc`.

- **`-r|--org-read-access`**

  Concede a esta aplicación acceso de lectura al directorio. Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`--no-https`**

  Desactiva HTTPS. Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.

- **`-uld|--use-local-db`**

  Especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Opción disponible a partir del SDK de .NET Core 3.0.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

- **`--use-browserlink`**

  Incluye BrowserLink en el proyecto. Opción no disponible en el SDK de .NET Core 2.2 y 3.1.

- **`-rrc|--razor-runtime-compilation`**

  Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración. Opción disponible a partir del SDK de .NET Core 3.1.201.

***

### <a name="angular-react"></a><a name="spa"></a> angular, react

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo de autenticación que se va a usar. Disponible desde el SDK de .NET Core 3.0.
  
  Los valores posibles son:

  - `None`: sin autenticación (valor predeterminado).
  - `Individual`: autenticación individual.

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

- **`--no-https`**

  Desactiva HTTPS. Esta opción solo se aplica si la autenticación es `None`.

- **`-uld|--use-local-db`**

  Especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`. Disponible desde el SDK de .NET Core 3.0.

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Opción no disponible en el SDK de .NET Core 2.2.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

***

### <a name="reactredux"></a>reactredux

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Opción no disponible en el SDK de .NET Core 2.2.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.0` |

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

- **`--no-https`**

  Desactiva HTTPS.

***

### <a name="razorclasslib"></a>razorclasslib

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

- **`-s|--support-pages-and-views`**

  Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca. Disponible desde el SDK de .NET Core 3.0.

***
  
### <a name="webapi"></a>webapi

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  Tipo de autenticación que se va a usar. Los valores posibles son:

  - `None`: sin autenticación (valor predeterminado).
  - `IndividualB2C`: autenticación individual con Azure AD B2C.
  - `SingleOrg`: autenticación organizativa para un solo inquilino.
  - `Windows`: autenticación de Windows.

- **`--aad-b2c-instance <INSTANCE>`**

  Instancia de Azure Active Directory B2C con la que se realiza la conexión. Úsela con la autenticación `IndividualB2C`. El valor predeterminado es `https://login.microsoftonline.com/tfp/`.

- **`-ssp|--susi-policy-id <ID>`**

  Identificador de la directiva de registro e inicio de sesión de este proyecto. Úsela con la autenticación `IndividualB2C`.

- **`--aad-instance <INSTANCE>`**

  Instancia de Azure Active Directory con la que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `https://login.microsoftonline.com/`.

- **`--client-id <ID>`**

  Identificador de cliente de este proyecto. Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`. El valor predeterminado es `11111111-1111-1111-11111111111111111`.

- **`--domain <DOMAIN>`**

  Dominio del inquilino del directorio. Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`. El valor predeterminado es `qualified.domain.name`.

- **`--tenant-id <ID>`**

  Identificador de inquilino del directorio con el que se realiza la conexión. Úsela con la autenticación `SingleOrg`. El valor predeterminado es `22222222-2222-2222-2222-222222222222`.

- **`-r|--org-read-access`**

  Concede a esta aplicación acceso de lectura al directorio. Solo se aplica a la autenticación `SingleOrg`.

- **`--exclude-launch-settings`**

  Excluye *launchSettings.json* de la plantilla generada.

- **`--no-https`**

  Desactiva HTTPS. `app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`. Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.

- **`-uld|--use-local-db`**

  Especifica que se debería usar LocalDB en vez de SQLite. Solo se aplica a la autenticación `IndividualB2C`.

- **`-f|--framework <FRAMEWORK>`**

  Especifica el [marco](../../standard/frameworks.md) de destino. Opción no disponible en el SDK de .NET Core 2.2.

  En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:

  | Versión del SDK | Valor predeterminado   |
  |-------------|-----------------|
  | 3.1         | `netcoreapp3.1` |
  | 3.0         | `netcoreapp3.0` |
  | 2.1         | `netcoreapp2.1` |

- **`--no-restore`**

  No se ejecuta ninguna restauración implícita durante la creación del proyecto.

***

### <a name="globaljson"></a>globaljson

- **`--sdk-version <VERSION_NUMBER>`**

  Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json*.

***

## <a name="examples"></a>Ejemplos

- Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:

  ```dotnetcli
  dotnet new "Console Application"
  ```

- Creación de un proyecto de aplicación de consola con F# en el directorio actual:

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:

  ```dotnetcli
  dotnet new mvc -au None
  ```

- Creación de un proyecto de xUnit:

  ```dotnetcli
  dotnet new xunit
  ```

- Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):

  ```dotnetcli
  dotnet new spa -l
  ```

- Enumeración de todas las plantillas que coinciden con la subcadena *we*. No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.

  ```dotnetcli
  dotnet new we -l
  ```

- Intento de invocar a la plantilla que coincide con *ng*. Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.

  ```dotnetcli
  dotnet new ng
  ```

- Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:

  ```dotnetcli
  dotnet new -u
  ```

- Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a>Vea también

- [Plantillas personalizadas para dotnet new](custom-templates.md)
- [Creación de una plantilla personalizada para dotnet new](../tutorials/cli-templates-create-item-template.md)
- [Repositorio de GitHub dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples)
- [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)
