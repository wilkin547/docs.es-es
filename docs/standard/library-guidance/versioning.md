---
title: Control de versiones y bibliotecas de .NET
description: Procedimientos recomendados para el control de versiones de las bibliotecas de .NET.
ms.date: 12/10/2018
ms.openlocfilehash: ab15d56e40abedd842b681496b9e5ee737c8b1cd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290128"
---
# <a name="versioning"></a>Control de versiones

Una biblioteca de software rara vez se completa en la versión 1.0. Las buenas bibliotecas evolucionan con el tiempo, al agregar características, corregir errores y mejorar el rendimiento. Es importante que pueda lanzar nuevas versiones de una biblioteca de .NET, proporcionando valor adicional con cada versión, sin interrumpir a los usuarios existentes.

## <a name="breaking-changes"></a>Cambios importantes

Para información sobre el control de cambios importantes entre versiones, vea [cambios importantes](./breaking-changes.md).

## <a name="version-numbers"></a>Números de versión

Una biblioteca de .NET tiene muchas maneras de especificar una versión. Las versiones siguientes son las más importantes:

### <a name="nuget-package-version"></a>Versión del paquete NuGet

La [versión del paquete NuGet](/nuget/reference/package-versioning) se muestra en NuGet.org, el administrador de paquetes NuGet de Visual Studio, y se agrega al código fuente cuando se usa el paquete. La versión del paquete de NuGet es el número de versión que los usuarios suelen ver, y se referirán a ella cuando hablen sobre la versión de una biblioteca que están usando. La versión del paquete de NuGet la usa NuGet y no tiene ningún efecto sobre el comportamiento en tiempo de ejecución.

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

El identificador del paquete NuGet combinado con la versión de dicho paquete se usa para identificar un paquete en NuGet. Por ejemplo, `Newtonsoft.Json` + `11.0.2`. Un paquete con un sufijo es un paquete de versión preliminar y tiene un comportamiento especial que lo hace ideal para las pruebas. Para más información, consulte [Paquetes de versión preliminar](./nuget.md#pre-release-packages).

Dado que la versión del paquete NuGet es la versión más visible para los desarrolladores, es una buena idea actualizarla mediante [Versionamiento Semántico (SemVer)](https://semver.org/). SemVer indica la importancia de los cambios entre versiones y ayuda a los desarrolladores a tomar una decisión informada a la hora de elegir qué versión se debe usar. Por ejemplo, pasar de `1.0` a `2.0` indica que hay cambios potencialmente importantes.

✔️ ES RECOMENDABLE usar [SemVer 2.0.0](https://semver.org/) para crear versiones del paquete NuGet.

✔️ NO use la versión del paquete NuGet en la documentación pública, ya que es el número de versión que normalmente ven los usuarios.

✔️ INCLUYA un sufijo de versión preliminar cuando publique un paquete que no sea estable.

> Los usuarios deben optar por obtener paquetes de versión preliminar, de forma que comprendan que el paquete no está completo.

### <a name="assembly-version"></a>Versión de ensamblado

La versión del ensamblado es lo que CLR usa en tiempo de ejecución para seleccionar qué versión de un ensamblado se debe cargar. La selección de un ensamblado mediante el control de versiones solo se aplica a los ensamblados con un nombre seguro.

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

CLR de .NET Framework exige una coincidencia exacta para cargar un ensamblado con nombre seguro. Por ejemplo, `Libary1, Version=1.0.0.0` se compiló con una referencia a `Newtonsoft.Json, Version=11.0.0.0`. .NET Framework solo cargará esa versión exacta: la `11.0.0.0`. Para cargar otra versión en tiempo de ejecución, se debe agregar una redirección de enlace al archivo de configuración de la aplicación de .NET.

La asignación de nombres seguros junto con la versión de ensamblado permite la [carga de la versión de ensamblado estricta](../assembly/versioning.md). Aunque la asignación de nombres seguros a una biblioteca tiene una serie de ventajas, suele dar lugar a excepciones en tiempo de ejecución que indican que no se puede encontrar un ensamblado y [requiere que se corrijan las redirecciones de enlace](../../framework/configure-apps/redirect-assembly-versions.md) de `app.config` o `web.config`. En .NET Core, la carga de ensamblados no es tan estricta. El entorno de ejecución de .NET Core carga automáticamente ensamblados con una versión posterior en tiempo de ejecución.

✔️ ES RECOMENDABLE que solo incluya una versión principal en AssemblyVersion.

> Por ejemplo, tanto Library 1.0 como Library 1.0.1 tienen una AssemblyVersion de `1.0.0.0`, mientras que Library 2.0 tiene una AssemblyVersion de `2.0.0.0`. Cuando la versión del ensamblado cambia con menos frecuencia, reduce las redirecciones de enlace.

✔️ ES RECOMENDABLE mantener sincronizados el número de versión principal de AssemblyVersion y la versión del paquete NuGet.

> AssemblyVersion se incluye en algunos mensajes informativos que se muestran al usuario, por ejemplo, el nombre del ensamblado y los nombres de tipo completos del ensamblado en los mensajes de excepción. Mantener una relación entre las versiones proporciona más información a los desarrolladores sobre qué versión están usando.

❌ NO tenga una AssemblyVersion fija.

> Aunque una AssemblyVersion invariable evita la necesidad de redirecciones de enlace, significa que se puede instalar solo una única versión del ensamblado en la memoria caché de ensamblados global (GAC). Además, las aplicaciones que hacen referencia al ensamblado en la memoria caché de ensamblados global se interrumpirán si otra aplicación actualiza el ensamblado de dicha memoria con cambios importantes.

### <a name="assembly-file-version"></a>Versión del archivo de ensamblado

La versión del archivo de ensamblado se usa para mostrar una versión de archivo en Windows y no tiene ningún efecto sobre el comportamiento en tiempo de ejecución. La configuración de esta versión es opcional. Está visible en el cuadro de diálogo Propiedades del archivo en el Explorador de Windows:

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

![Explorador de Windows](./media/versioning/win-properties.png "Explorador de Windows")

✔️ ES RECOMENDABLE incluir un número de compilación de integración continua como la revisión AssemblyFileVersion.

> Por ejemplo, si va a compilar la versión 1.0.0 del proyecto y el número de compilación de integración continua es 99, su AssemblyFileVersion es 1.0.0.99.

✔️ USE el formato `Major.Minor.Build.Revision` para la versión de archivo.

> Aunque en .NET nunca se usa la versión de archivo, [Windows espera que la versión de archivo](/windows/desktop/menurc/versioninfo-resource) tenga el formato `Major.Minor.Build.Revision`. Se genera una advertencia si la versión no sigue este formato.

### <a name="assembly-informational-version"></a>Versión informativa del ensamblado

La versión informativa de ensamblado se usa para registrar información de versión adicional y no tiene ningún efecto sobre el comportamiento en tiempo de ejecución. La configuración de esta versión es opcional. Si usa SourceLink, esta versión se establecerá en la compilación con la versión del paquete NuGet más una versión de control de código fuente. Por ejemplo, `1.0.0-beta1+204ff0a` incluye el hash de confirmación del código fuente a partir del que se compiló el ensamblado. Para obtener más información, consulte [SourceLink](./sourcelink.md).

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

> [!NOTE]
> Las versiones anteriores de Visual Studio generan una advertencia de compilación si esta versión no sigue el formato `Major.Minor.Build.Revision`. La advertencia se puede omitir sin ningún problema.

❌ EVITE establecer usted mismo la versión informativa del ensamblado.

> Permita que SourceLink genere automáticamente la versión que contiene los metadatos de control de código fuente y NuGet.

>[!div class="step-by-step"]
>[Anterior](publish-nuget-package.md)
>[Siguiente](breaking-changes.md)
