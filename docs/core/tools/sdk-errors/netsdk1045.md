---
title: 'NETSDK1045: El SDK de .NET actual no es compatible con "versión más reciente" como destino.'
description: Obtenga información sobre el error NETSDK1045 del SDK de .NET, que se produce cuando las herramientas de compilación no pueden encontrar la versión solicitada del SDK de .NET.
ms.topic: error-reference
ms.date: 02/12/2021
f1_keywords:
- NETSDK1045
ms.openlocfilehash: 7f21270fdc7c2db862a49302a302bf8121fc86a5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104107"
---
# <a name="netsdk1045-the-current-net-sdk-does-not-support-newer-version-as-a-target"></a>NETSDK1045: El SDK de .NET actual no es compatible con "versión más reciente" como destino.

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

Este error se produce cuando las herramientas de compilación no pueden encontrar la versión del SDK de .NET necesaria para compilar un proyecto. Esto se suele deber a un problema de instalación o configuración del SDK de .NET Core. El mensaje de error es similar al ejemplo siguiente:

> NETSDK1045: El SDK de .NET actual no es compatible con "versión más reciente" como destino. Seleccione "versión anterior" u otra inferior como destino, o bien use una versión del SDK de .NET que admita "versión más reciente".

En las secciones siguientes se describen algunas de las posibles razones de este error. Compruebe cada una de ellas y vea cuál es la correspondiente. Tenga en cuenta que, al realizar cambios en el entorno o en los archivos de configuración, es posible que tenga que reiniciar ventanas de comandos, Visual Studio o la máquina para que los cambios surtan efecto.

## <a name="net-sdk-version"></a>Versión de SDK de .NET

Abra el archivo del proyecto (.csproj, .vbproj o .fsproj) y compruebe la plataforma de destino. Esta es la versión de la plataforma que la aplicación intenta usar.

```xml
<TargetFramework>netcoreapp3.0</TargetFramework>
```

Asegúrese de que la versión de .NET que aparece en la lista está instalada en la máquina. Puede enumerar las versiones instaladas con el comando siguiente (abra un Símbolo del sistema para desarrolladores y ejecútelo):

```dotnetcli
dotnet --list-sdks
```

### <a name="x86-or-x64-architecture"></a>Arquitectura x86 o x64

Cada versión del SDK de .NET está disponible en la arquitectura x86 y x64. Es posible que el proyecto intente encontrar el SDK de .NET para la arquitectura equivocada, o bien que no esté instalado el SDK de .NET para la arquitectura que necesita el proyecto. Busque en las carpetas de instalación la arquitectura que necesita. Por ejemplo, en Windows, la versión x86 del SDK de .NET se instala en *C:\Archivos de programa (x86)\dotnet*, y la versión x64, en *C:\Archivos de programa\dotnet*. Vea [Cómo comprobar que .NET Core ya está instalado](../../install/how-to-detect-installed-versions.md) y elija el sistema operativo para averiguar cómo detectar lo que está instalado en la máquina.

Si la versión que necesita no está instalada, búsquela en la página [Descargas de .NET](https://dotnet.microsoft.com/download/dotnet).

## <a name="preview-not-enabled"></a>Versión preliminar no habilitada

Si tiene instalada una versión preliminar de la versión del SDK de .NET solicitada, también debe establecer la opción para habilitar las versiones preliminares en Visual Studio. Vaya a **Herramientas** > **Opciones** > **Entorno** > **Características en versión preliminar** y asegúrese de que la opción **Usar versiones preliminares del SDK de .NET Core** está activada.

## <a name="visual-studio-version"></a>Versión de Visual Studio

Por ejemplo, en .NET Core 3.0 y versiones posteriores se necesita Visual Studio 2019. Actualice su versión a [Visual Studio 2019, versión 16.3](https://visualstudio.microsoft.com/downloads) o posterior para compilar el proyecto.

## <a name="path-environment-variable"></a>Variable de entorno PATH

Las herramientas de compilación usan la variable de entorno PATH para encontrar la versión correcta de las herramientas de compilación de .NET. Si la variable de entorno PATH contiene rutas de acceso directas a herramientas de compilación más antiguas, podría aparecer este mensaje de error. Asegúrese de que la única ruta de acceso a las herramientas de .NET en la variable de entorno PATH es a la carpeta *dotnet* de nivel superior, por ejemplo, *C:\Archivos de programa\dotnet*. Un ejemplo de una ruta de acceso incorrecta sería similar a *C:\Archivos de programa\dotnet\2.1.0\sdks*.

## <a name="msbuildsdkpath-environment-variable"></a>Variable de entorno MSBuildSDKPath

Compruebe la variable de entorno MSBuildSDKPath. MSBuild reconoce esta variable de entorno opcional y, si se establece, invalida el valor predeterminado. Es posible que esté establecida en una versión anterior específica del SDK de .NET. Si está establecida, intente eliminarla y vuelva a compilar el proyecto.

## <a name="globaljson-file"></a>archivo global.json

Busque un archivo *global.json* en la carpeta raíz del proyecto y en la cadena de directorios de la raíz del volumen, ya que puede estar en cualquier parte de la estructura de carpetas. Si contiene una versión del SDK, elimine el nodo `sdk` y todos sus elementos secundarios, o bien actualícelo a la versión más reciente de .NET Core deseada.

```json
{
  "sdk": {
    "version": "2.1.0"
  }
}
```

El archivo *global.json* no es necesario, por lo que, si no contiene nada que no sea el nodo `sdk`, puede eliminarlo por completo.

## <a name="directorybuildprops-file"></a>Archivo Directory.build.props

*Directory.build.props* es un archivo de MSBuild opcional que puede establecer propiedades globales. Busque estos archivos en la carpeta de la solución y en la cadena de directorios de la raíz del volumen, ya que pueden estar en cualquier parte de la estructura de carpetas. Busque elementos `TargetFramework` o la configuración de `MSBuildSDKPath` que puede invalidar la configuración deseada.

## <a name="see-also"></a>Vea también

- [El SDK de .NET actual no admite seleccionar como destino .NET Core 3.0: corrección](https://www.ryadel.com/current-net-sdk-not-support-net-core-3-0-fix/)
