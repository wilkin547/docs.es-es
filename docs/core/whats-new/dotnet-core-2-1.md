---
title: Novedades de .NET Core 2.1
description: Obtenga información sobre las características nuevas de .NET Core 2.1.
dev_langs:
- csharp
- vb
ms.date: 10/10/2018
ms.openlocfilehash: 603e7ae4ffb9e6a4bb477af9597d6948bd63f55e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100748"
---
# <a name="whats-new-in-net-core-21"></a>Novedades de .NET Core 2.1

.NET Core 2.1 incluye mejoras y características nuevas en las áreas siguientes:

- [Herramientas](#tooling)
- [Puesta al día](#roll-forward)
- [Implementación](#deployment)
- [Paquete de compatibilidad de Windows](#windows-compatibility-pack)
- [Mejoras de la compilación JIT](#jit-compiler-improvements)
- [Cambios en la API](#api-changes)

## <a name="tooling"></a>Tooling

El SDK de .NET Core 2.1 (v 2.1.300), el conjunto de herramientas incluidas con .NET Core 2.1, incluye los siguientes cambios y mejoras:

### <a name="build-performance-improvements"></a>Mejoras en el rendimiento de la compilación

Un aspecto fundamental de .NET Core 2.1 es mejorar el rendimiento del tiempo de compilación, especialmente para compilaciones incrementales. Estas mejoras de rendimiento se aplican a las compilaciones de línea de comandos mediante `dotnet build` y a las compilaciones de Visual Studio. Algunas áreas individuales de mejora incluyen:

- Para la resolución de activos del paquete, solo se resuelven los activos utilizados por una compilación en lugar de todos los activos.

- Almacenamiento en caché de referencias de ensamblado.

- Uso de servidores de compilación de SDK de larga ejecución, que son procesos que se extienden a través de invocaciones `dotnet build` individuales. Eliminan la necesidad de compilar mediante JIT grandes bloques de código cada vez que se ejecuta `dotnet build`. Los procesos del servidor de compilación se pueden terminar automáticamente con el siguiente comando:

   ```dotnetcli
   dotnet buildserver shutdown
   ```

### <a name="new-cli-commands"></a>Nuevos comandos de la CLI

Una serie de herramientas que estaban disponibles solo en función del proyecto mediante [`DotnetCliToolReference`](../tools/extensibility.md) ahora están disponibles como parte del SDK de .NET Core. Estas herramientas incluyen:

- `dotnet watch` proporciona un monitor del sistema de archivos que espera que un archivo cambie antes de ejecutar un conjunto designado de comandos. Por ejemplo, el siguiente comando vuelve a generar automáticamente el proyecto actual y genera un resultado detallado cada vez que cambie un archivo en él:

   ```dotnetcli
   dotnet watch -- --verbose build
   ```

   Tenga en cuenta que la opción `--` precede a la opción `--verbose`. Delimita las opciones pasadas directamente al comando `dotnet watch` de los argumentos que se pasan al proceso `dotnet` secundario. Sin él, la opción `--verbose` se aplica al comando `dotnet watch`, no al comando `dotnet build`.
  
   Para más información, consulte [Desarrollar aplicaciones ASP.NET Core con un monitor de archivos](/aspnet/core/tutorials/dotnet-watch).

- `dotnet dev-certs` genera y administra los certificados que se usan durante el desarrollo de aplicaciones de ASP.NET Core.

- `dotnet user-secrets` administra los secretos en un almacén de secretos de usuario en aplicaciones de ASP.NET Core.

- `dotnet sql-cache` crea una tabla e índices en una base de datos de Microsoft SQL Server que se usará para el almacenamiento en caché distribuido.

- `dotnet ef` es una herramienta para administrar bases de datos, objetos <xref:Microsoft.EntityFrameworkCore.DbContext> y migraciones en las aplicaciones de Entity Framework Core. Para obtener más información, vea [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet) (Herramienta de la línea de comandos de .NET de EF Core).

### <a name="global-tools"></a>Herramientas globales

.NET core 2.1 es compatible con *Herramientas globales*: es decir, las herramientas personalizadas que están disponibles globalmente desde la línea de comandos. El modelo de extensibilidad en versiones previas de .NET Core permitió que las herramientas personalizadas estuvieran disponibles para cada proyecto solo utilizando [`DotnetCliToolReference`](../tools/extensibility.md#consuming-per-project-tools).

Para instalar una herramienta global, use el comando [dotnet tool install](../tools/dotnet-tool-install.md). Por ejemplo:

```dotnetcli
dotnet tool install -g dotnetsay
```

Una vez instalada, la herramienta se puede ejecutar desde la línea de comandos especificando el nombre de la herramienta. Para más información, vea [Información general sobre las herramientas globales de .NET Core](../tools/global-tools.md).

### <a name="tool-management-with-the-dotnet-tool-command"></a>Administración de herramientas con el comando `dotnet tool`

En el SDK de .NET Core 2.1, todas las operaciones de herramientas utilizan el comando `dotnet tool`. Están disponibles las siguientes opciones:

- [`dotnet tool install`](../tools/dotnet-tool-install.md) para instalar una herramienta.

- [`dotnet tool update`](../tools/dotnet-tool-update.md) para desinstalar y reinstalar una herramienta, lo cual la actualiza eficazmente.

- [`dotnet tool list`](../tools/dotnet-tool-list.md) para enumerar las herramientas instaladas actualmente.

- [`dotnet tool uninstall`](../tools/dotnet-tool-uninstall.md) para desinstalar las herramientas instaladas actualmente.

## <a name="roll-forward"></a>Puesta al día

Todas las aplicaciones de .NET Core a partir de .NET Core 2.0 se ponen al día automáticamente a la *versión secundaria* más reciente instalada en un sistema.

A partir de .NET Core 2.0, si la versión de .NET Core que se creó una aplicación no está presente en tiempo de ejecución, la aplicación se ejecuta automáticamente en la *versión secundaria* instalada más reciente de .NET Core. En otras palabras, si una aplicación se compila con .NET Core 2.0, y .NET Core 2.0 no está presente en el sistema host pero sí lo está .NET Core 2.1, la aplicación se ejecuta con .NET Core 2.1.

> [!IMPORTANT]
> Este comportamiento de puesta al día no se aplica para versiones preliminares. De forma predeterminada, tampoco se aplica a las versiones principales, pero se puede cambiar con las opciones siguientes.

Este comportamiento se puede modificar si se cambia la configuración para la puesta al día en los marcos de trabajo compartidos que no sean candidatos. Los valores disponibles son los siguientes:

- `0`: se deshabilita el comportamiento de puesta al día de las versiones secundarias. Con este valor, una aplicación compilada para .NET Core 2.0.0 se pondrá al día a .NET Core 2.0.1, pero no a .NET Core 2.2.0 ni .NET Core 3.0.0.
- `1`: se habilita el comportamiento de puesta al día de las versiones secundarias. Este es el valor predeterminado de la opción. Con este valor, una aplicación compilada para .NET Core 2.0.0 se pondrá al día a .NET Core 2.0.1 o .NET Core 2.2.0, en función de la versión instalada, pero no a .NET Core 3.0.0.
- `2`: se habilita el comportamiento de puesta al día de las versiones principales y secundarias. Si se establece, se tienen en cuenta incluso versiones principales diferentes, por lo que una aplicación compilada para .NET Core 2.0.0 se pondrá al día a .NET Core 3.0.0.

Esta configuración se puede modificar de estas tres maneras:

- Si se establece la variable de entorno `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` en el valor deseado.

- Agregue la línea siguiente con el valor deseado al archivo *.runtimeconfig.json*:

   ```json
   "rollForwardOnNoCandidateFx" : 0
   ```

- Cuando se usan [herramientas de la CLI de .NET Core](../tools/index.md), si se agrega la opción siguiente con el valor deseado a un comando de .NET Core como `run`:

   ```dotnetcli
   dotnet run --rollForwardOnNoCandidateFx=0
   ```

La puesta al día de versiones de revisión es independiente de esta configuración y se realiza después de aplicar la puesta al día de cualquier versión principal o secundaria posible.

## <a name="deployment"></a>Implementación

### <a name="self-contained-application-servicing"></a>Mantenimiento de aplicaciones independientes

`dotnet publish` ahora publica aplicaciones independientes con una versión en tiempo de ejecución con mantenimiento. Cuando publica una aplicación independiente con el SDK 2.1 de .NET Core (v. 2.1.300), su aplicación incluye la última versión de tiempo de ejecución con mantenimiento conocida por ese SDK. Cuando actualice a la versión más reciente del SDK, publicará con la versión más reciente del tiempo de ejecución de .NET Core. Esto se aplica para tiempos de ejecución de .NET Core 1.0 y versiones posteriores.

La publicación independiente se basa en las versiones del tiempo de ejecución en NuGet.org. No necesita tener el tiempo de ejecución con mantenimiento en su máquina.

Con el SDK de .NET Core 2.0, las aplicaciones independientes se publican con el tiempo de ejecución de .NET Core 2.0.0 a menos que se especifique una versión diferente a través de la propiedad `RuntimeFrameworkVersion`. Con este nuevo comportamiento, ya no será necesario configurar esta propiedad para seleccionar una versión de tiempo de ejecución más alta para una aplicación independiente. El enfoque más sencillo a partir de ahora es publicar siempre con el SDK de .NET Core 2.1 (v. 2.1.300).

Para obtener más información, vea [Puesta al día del runtime de implementación autocontenida](../deploying/runtime-patch-selection.md).
## <a name="windows-compatibility-pack"></a>Paquete de compatibilidad de Windows

Al trasladar el código existente de .NET Framework a .NET Core, puede usar el [paquete de compatibilidad de Windows](https://www.nuget.org/packages/Microsoft.Windows.Compatibility). Esto proporciona acceso a 20 000 API más de las que están disponibles en .NET Core. Estas API incluyen tipos en el espacio de nombres <xref:System.Drawing?displayProperty=nameWithType>, la clase <xref:System.Diagnostics.EventLog>, WMI, contadores de rendimiento, servicios de Windows y los tipos y miembros de Registro de Windows.

## <a name="jit-compiler-improvements"></a>Mejoras del compilador JIT

.NET Core incorpora una nueva tecnología de compilador JIT denominada *compilación por niveles* (también conocida como *optimización adaptable*) que puede mejorar significativamente el rendimiento. La compilación por niveles es una configuración opcional.

Una de las tareas importantes realizadas por el compilador JIT es optimizar la ejecución de código. Sin embargo, para las rutas de código poco utilizadas, el compilador puede dedicar más tiempo a la optimización del código del que dedica el tiempo de ejecución a ejecutar el código no optimizado. La compilación por niveles incluye dos fases en la compilación JIT:

- Un **primer nivel**, que genera código tan pronto como sea posible.

- Un **segundo nivel**, que genera código optimizado para los métodos que se ejecutan con frecuencia. El segundo nivel de la compilación se realiza en paralelo para mejorar el rendimiento.

Puede participar en la compilación en niveles de cualquiera de estas dos maneras.

- Para utilizar la compilación en capas en todos los proyectos que utilizan el SDK de .NET Core 2.1, establezca la variable de entorno siguiente:

  ```console
  COMPlus_TieredCompilation="1"
  ```

- Para utilizar la compilación por niveles por proyecto, agregue la propiedad `<TieredCompilation>` a la sección `<PropertyGroup>` del archivo de proyecto de MSBuild, como se muestra en el ejemplo siguiente:

   ```xml
   <PropertyGroup>
      <!-- other property definitions -->

      <TieredCompilation>true</TieredCompilation>
   </PropertyGroup>
   ```

## <a name="api-changes"></a>Cambios en la API

### <a name="spant-and-memoryt"></a>`Span<T>` y `Memory<T>`

.NET Core 2.1 incluye algunos tipos nuevos que hacen que trabajar con matrices y otros tipos de memoria sea mucho más eficiente. Estos nuevos tipos incluyen:

- <xref:System.Span%601?displayProperty=nameWithType> y <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>.

- <xref:System.Memory%601?displayProperty=nameWithType> y <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>.

Sin estos tipos, al pasar tales elementos como una porción de una matriz o una sección de un búfer de memoria, debe hacer una copia de una parte de los datos antes de pasarlo a un método. Estos tipos proporcionan una vista virtual de los datos que elimina la necesidad de ejecutar operaciones adicionales de copia y asignación de memoria.

En el ejemplo siguiente se usa una instancia de <xref:System.Span%601> y <xref:System.Memory%601> para proporcionar una vista virtual de 10 elementos de una matriz.

[!code-csharp[Span\<T>](~/samples/core/whats-new/whats-new-in-21/cs/program.cs)]

[!code-vb[Memory\<T>](~/samples/core/whats-new/whats-new-in-21/vb/program.vb)]

### <a name="brotli-compression"></a>Compresión de Brotli

.NET Core 2.1 agrega compatibilidad con la compresión y descompresión de Brotli. Brotli es un algoritmo de compresión sin pérdida de datos de uso general que se define en [RFC 7932](https://www.ietf.org/rfc/rfc7932.txt) y es compatible con la mayoría de los exploradores web y servidores web principales. Puede usar la clase <xref:System.IO.Compression.BrotliStream?displayProperty=nameWithType> basada en secuencias o las clases <xref:System.IO.Compression.BrotliEncoder?displayProperty=nameWithType> y <xref:System.IO.Compression.BrotliDecoder?displayProperty=nameWithType> basadas en intervalos de alto rendimiento. En el ejemplo siguiente se muestra la compresión con la clase <xref:System.IO.Compression.BrotliStream>:

[!code-csharp[Brotli compression](~/samples/core/whats-new/whats-new-in-21/cs/brotli.cs#1)]

[!code-vb[Brotli compression](~/samples/core/whats-new/whats-new-in-21/vb/brotli.vb#1)]

El comportamiento de <xref:System.IO.Compression.BrotliStream> es el mismo que <xref:System.IO.Compression.DeflateStream> y <xref:System.IO.Compression.GZipStream>, lo que facilita la conversión de código que llama a estas API a <xref:System.IO.Compression.BrotliStream>.

### <a name="new-cryptography-apis-and-cryptography-improvements"></a>Nuevas API de criptografía y mejoras de criptografía

.NET Core 2.1 incluye numerosas mejoras para las API de criptografía:

- <xref:System.Security.Cryptography.Pkcs.SignedCms?displayProperty=nameWithType> está disponible en el paquete System.Security.Cryptography.Pkcs. La implementación es la misma que la clase <xref:System.Security.Cryptography.Pkcs.SignedCms> en .NET Framework.

- Las nuevas sobrecargas de los métodos <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHash%2A?displayProperty=nameWithType> y <xref:System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString%2A?displayProperty=nameWithType> aceptan un identificador de algoritmo hash para permitir que los autores de la llamada obtengan valores de huella digital de certificado utilizando algoritmos distintos de SHA-1.

- Las nuevas API de criptografía basadas en <xref:System.Span%601> están disponibles para crear valores hash, HMAC, generación de números aleatorios criptográficos, generación de firmas asimétricas, procesamiento de firmas asimétricas y cifrado RSA.

- El rendimiento de <xref:System.Security.Cryptography.Rfc2898DeriveBytes?displayProperty=nameWithType> mejoró aproximadamente un 15 % mediante el uso de una implementación basada en <xref:System.Span%601>.

- La nueva clase <xref:System.Security.Cryptography.CryptographicOperations?displayProperty=nameWithType> incluye dos nuevos métodos:

  - <xref:System.Security.Cryptography.CryptographicOperations.FixedTimeEquals%2A> tarda una cantidad fija de tiempo en devolver dos entradas cualesquiera de la misma longitud, siendo así adecuada para su uso en la comprobación criptográfica para evitar contribuir al control de tiempo de la información en el canal.

  - <xref:System.Security.Cryptography.CryptographicOperations.ZeroMemory%2A> es una rutina de borrado de memoria que no se puede optimizar.

- El método estático <xref:System.Security.Cryptography.RandomNumberGenerator.Fill%2A?displayProperty=nameWithType> rellena un <xref:System.Span%601> con valores aleatorios.

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms?displayProperty=nameWithType> ahora es compatible con Linux y macOS.

- La curva elíptica Diffie-Hellman (ECDH) ahora está disponible en la familia de clases <xref:System.Security.Cryptography.ECDiffieHellman?displayProperty=nameWithType>. El área expuesta es la misma que en .NET Framework.

- La instancia devuelta por <xref:System.Security.Cryptography.RSA.Create%2A?displayProperty=nameWithType> puede cifrar o descifrar con OAEP con un resumen de SHA-2, así como generar o validar firmas mediante RSA-PSS.

### <a name="sockets-improvements"></a>Mejoras en los sockets

.NET Core incluye un nuevo tipo, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> y una reescritura <xref:System.Net.Http.HttpMessageHandler?displayProperty=nameWithType>, que forman la base de las API de red de nivel superior.  <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>, por ejemplo, es la base de la implementación <xref:System.Net.Http.HttpClient>. En versiones anteriores de .NET Core, las API de nivel superior se basaban en implementaciones de redes nativas.

La implementación de sockets introducida en .NET Core 2.1 presenta una serie de ventajas:

- Una mejora significativa del rendimiento en comparación con la implementación anterior.

- Eliminación de las dependencias de plataforma, lo que simplifica la implementación y el mantenimiento.

- Comportamiento coherente en todas las plataformas de .NET Core.

<xref:System.Net.Http.SocketsHttpHandler> es la implementación predeterminada en .NET Core 2.1. Sin embargo, puede configurar su aplicación para usar la clase anterior <xref:System.Net.Http.HttpClientHandler> llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>:

```csharp
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", false);
```

```vb
AppContext.SetSwitch("System.Net.Http.UseSocketsHttpHandler", False)
```

También puede usar una variable de entorno para optar por no usar implementaciones de sockets basadas en <xref:System.Net.Http.SocketsHttpHandler>. Para ello, configure `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` en `false` o en 0.

En Windows, también puede optar por usar <xref:System.Net.Http.WinHttpHandler?displayProperty=nameWithType>, que se basa en una implementación nativa, o la clase <xref:System.Net.Http.SocketsHttpHandler> pasando una instancia de la clase al constructor <xref:System.Net.Http.HttpClient>.

En Linux y macOS, solo se puede configurar <xref:System.Net.Http.HttpClient> para cada proceso. En Linux, deberá implementar [libcurl](https://curl.haxx.se/libcurl/) si desea usar la antigua implementación de <xref:System.Net.Http.HttpClient>. (Se instala con .NET Core 2.0).

## <a name="see-also"></a>Vea también

- [Novedades de .NET Core](index.md)
- [Novedades de EF Core 2.1](/ef/core/what-is-new/ef-core-2.1)
- [Novedades de ASP.NET Core 2.1](/aspnet/core/aspnetcore-2.1)
