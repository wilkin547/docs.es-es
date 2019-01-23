---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 26fb7cb25b9bf7f00f87059fbe1848763f7f175d
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415551"
---
# <a name="whats-new-in-net-core-30-preview-1"></a>Novedades de .NET Core 3.0 (versión preliminar 1)

En este artículo se describen las novedades de .NET Core 3.0 (versión preliminar 1). Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows). Mediante el uso de un componente de .NET Core 3.0 denominado "Escritorio de Windows", puede trasladar sus aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms. Para ser más precisos, el componente Escritorio de Windows solo se admite en Windows. Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) de más adelante.

.NET Core 3.0 agrega compatibilidad con C# 8.0.

[Descargue .NET Core 3 (versión preliminar 1) y empiece a usarlo](https://aka.ms/netcore3download) ahora mismo en Windows, Mac y Linux. Puede ver los detalles completos de la versión en las [notas de la versión preliminar 1 de .NET Core 3](https://aka.ms/netcore3releasenotes).

Para obtener más información, consulte el [anuncio sobre la versión preliminar 1 de .NET Core 3.0](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 también implementa .NET Standard 2.1.

## <a name="default-executables"></a>Archivos ejecutables predeterminados

.NET Core compilará ahora los [archivos ejecutables dependientes de marco de trabajo](../deploying/index.md#framework-dependent-executables-fde) de forma predeterminada. Se trata de una novedad en las aplicaciones que usan una versión de .NET Core instalada de forma global. Hasta ahora, solo las [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) producirían un archivo ejecutable.

Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable siempre que coincida con el entorno y la plataforma del SDK que usa. Estos ejecutables funcionan de la misma forma que los ejecutables nativos:

* Haga doble clic en el archivo ejecutable.
* También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.

## <a name="build-copies-dependencies"></a>Compilación de dependencias de copias

`dotnet build` ahora copia las dependencias de NuGet de la aplicación desde la caché de NuGet en la carpeta de salida de compilación. Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`. 

Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.


## <a name="local-dotnet-tools"></a>Herramientas de dotnet locales

Aunque .NET Core 2.1 admitía herramientas globales, .NET Core 3.0 ahora cuenta con herramientas locales. Las herramientas locales son similares a las globales, pero están asociadas a una ubicación concreta del disco. De este modo, se pueden usar herramientas por proyecto y por repositorio. Las herramientas instaladas de forma local no están disponibles de manera global.

Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual. Este archivo de manifiesto define las herramientas que estarán disponibles. Al crear este archivo de manifiesto en la raíz del repositorio, asegúrese de que cualquier usuario que clone el código pueda restaurar y usar las herramientas que se necesitan para trabajar correctamente con el código.

Cuando el archivo de manifiesto de herramientas locales está disponible, use el comando siguiente para descargar e instalar automáticamente estas herramientas de manera local:

```console
dotnet tool restore
```

Ejecute una herramienta local con el comando siguiente:

```console
dotnet tool run <tool-command-name>
```

Cuando se llama a una herramienta local, dotnet busca un manifiesto en la estructura de directorios. Cuando se encuentra un archivo de manifiesto de herramientas, se busca la herramienta solicitada. Si se encuentra la herramienta, incluirá la información necesaria para encontrar la herramienta en la ubicación de paquetes globales NuGet. 

Si la herramienta se encuentra en el manifiesto, pero no en la caché, el usuario recibe un error. Se mejorará el mensaje después de la versión preliminar 1 para pedir al usuario que ejecute `dotnet tool restore`.

Para agregar herramientas locales a un directorio, deberá crear primero el archivo de manifiesto de herramientas. Después de la versión preliminar 1, ofreceremos un mecanismo para crear los archivos de manifiesto de herramientas, por ejemplo, una nueva plantilla de dotnet. Para la versión preliminar 1, debe crear un archivo denominado "`dotnet-tools.json`" con el siguiente contenido:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Una vez que se crea el manifiesto, podrá agregarle herramientas locales mediante lo siguiente:

```console
dotnet tool install <toolPackageId>
```

Este comando instala la versión más reciente de la herramienta, a menos que se especifique otra.  Aunque eligiera automáticamente la más reciente, la versión de la herramienta se escribe en el archivo de manifiesto de herramientas para permitir que se pueda restaurar o ejecutar la versión correcta de la herramienta.

El archivo de manifiesto de herramientas está diseñado para poder modificarse manualmente (podría hacerlo para actualizar la versión necesaria para trabajar con el repositorio).

A continuación, se muestra un archivo `dotnet-tools.json` de ejemplo:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

Para quitar una herramienta del archivo de manifiesto de herramientas, ejecute el siguiente comando:

```console
dotnet tool uninstall <toolPackageId>
```

Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución. Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1. Para instalarlas de forma global o local, aún es necesario instalar el [entorno de ejecución de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

Para obtener más información, consulte [Local Tools Early Preview Documentation](https://github.com/dotnet/cli/issues/10288) (Documentación de la versión preliminar anticipada de las herramientas locales).

## <a name="windows-desktop"></a>Escritorio de Windows

A partir de la versión preliminar 1 de .NET Core 3.0, puede compilar aplicaciones de Escritorio de Windows con WPF y Windows Forms. Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).

El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.

Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:

```console
dotnet new wpf
dotnet new winforms
```

También puede abrir, iniciar y depurar proyectos de Windows Forms y WPF de .NET Core 3.0 en la versión preliminar 1 de Visual Studio 2019. Actualmente se pueden abrir estos proyectos en Visual Studio 2017 15.9; sin embargo, no se trata de un escenario compatible (y debe [habilitar las versiones preliminares](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).

Los nuevos proyectos son los mismos que los existentes de .NET Core, con algunas adiciones. Esta es la comparación del proyecto de consola de .NET Core básico y un proyecto básico de Windows Forms y WPF.

En un proyecto de consola de .NET Core, se usa el SDK `Microsoft.NET.Sdk` y se declara una dependencia en .NET Core 3.0 a través del marco de destino `netcoreapp3.0`. Para crear una aplicación de Escritorio de Windows, use el SDK `Microsoft.NET.Sdk.WindowsDesktop` y elija qué marco de interfaz de usuario usará:

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

Para elegir Windows Forms en WPF, establezca `UseWindowsForms` en lugar de `UseWPF`:

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

`UseWPF` y `UseWindowsForms` se puede establecer en `true` si la aplicación usa ambos marcos, por ejemplo, cuando un cuadro de diálogo de Windows Forms hospeda un control de WPF.

Comparta sus comentarios en los repositorios [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) y [dotnet/core](https://github.com/dotnet/core/issues).

## <a name="fast-built-in-json-support"></a>Compatibilidad con JSON integrada con rápido rendimiento

`System.Text.Json.Utf8JsonReader` es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`. `Utf8JsonReader` es un tipo fundamental de bajo nivel que puede utilizarse para crear analizadores y deserializadores personalizados. La lectura a través de una carga JSON con el nuevo lector `Utf8JsonReader` es el doble de rápido que con el lector de [Json.NET](https://www.newtonsoft.com/json). No se realiza la asignación hasta que se necesite actualizar los tokens JSON como cadenas (UTF-16).

Esta nueva API incluirá los siguientes componentes:

* En la versión preliminar 1: lector JSON (acceso secuencial)
* Próximamente: escritor JSON, DOM (acceso aleatorio), y serializador y deserializador poco

Este es el bucle de lectura básico para el lector `Utf8JsonReader` que puede utilizarse como punto inicial:

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

El ecosistema .NET depende de [Json.NET](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones. JSON.NET utiliza cadenas .NET como su tipo de datos base, que son UTF-16 en segundo plano. 

En .NET Core 2.1 y 3.0, hemos agregado nuevas API que permiten escribir las API de JSON (como `Utf8JsonReader`) que requieren mucho menos memoria, en función del uso de cadenas UTF-8 y `Span<T>`, y satisfacen mejor las necesidades de aplicaciones de alto rendimiento, como Kestrel, el servidor web de ASP.NET Core.

## <a name="ranges-and-indices"></a>Rangos e índices

El nuevo tipo `Index` se puede utilizar para la indización. Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

También hay un tipo `Range`, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de rango `x..y` (C#). A continuación, puede crear un índice con un rango `Range` con el fin de generar un segmento:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

> [!NOTE]
> Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) admite la sintaxis de `Range` y `Index`.

## <a name="async-streams"></a>Flujos asincrónicos

El tipo `IAsyncEnumerable<T>` es una nueva versión asincrónica de `IEnumerable<T>`. El lenguaje permite ejecutar la instrucción `await foreach` en los flujos para consumir sus elementos, y ejecutar la instrucción `yield return` en ellos para generar los elementos.

En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos. La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores. Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

> [!WARNING]
> Actualmente, en la versión preliminar 1 de .NET Core 3.0 hay un error con `await foreach`. En su lugar, use `GetEnumerator` y `MoveNext` en procesar los elementos. Para obtener más información, consulte [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).

Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`. Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.

> [!NOTE]
> Solo [C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) admite la sintaxis de `await foreach`.

## <a name="type-sequencereader"></a>Tipo: SequenceReader

En .NET Core 3.0, se ha agregado `System.Buffers.SequenceReader`, que se puede usar como lector de `ReadOnlySequence<T>`. De este modo, se puede realizar un análisis de alto rendimiento y de asignación baja de los datos `System.IO.Pipelines` que pueden atravesar varios búferes de respaldo. 

En el ejemplo siguiente, se interrumpe una entrada `Sequence` en las líneas delimitadas `CR/LF` válidas:

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>Tipo: MetadataLoadContext

Se ha agregado el tipo `MetadataLoadContext` que permite leer los metadatos de ensamblado sin que afecte al dominio de aplicación del llamador. Los ensamblados se leen como datos, incluidos los ensamblados compilados para arquitecturas y plataformas distintas al entorno en tiempo de ejecución actual. `MetadataLoadContext` se superpone con <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, que solo está disponible en .NET Framework.

`MetdataLoadContext` está disponible en el paquete [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext). Se trata de un paquete de .NET Standard 2.0.

`MetadataLoadContext`expone las API similares al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, pero no se basa en ese tipo. De forma similar a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` habilita la carga de ensamblados dentro del universo de carga de ensamblados aislados. Las API de `MetdataLoadContext` devuelven objetos <xref:System.Reflection.Assembly>, lo que permite el uso de API de reflexión conocidas. Las API orientadas a la ejecución, como [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), no se permiten y generan la excepción InvalidOperationException.

El ejemplo siguiente muestra cómo buscar tipos concretos en un ensamblado que implementa una interfaz determinada:

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

Los escenarios para `MetadataLoadContext` incluyen características de tiempo de diseño, herramientas de tiempo de compilación y características de alumbrado en tiempo de ejecución que necesitan inspeccionar un conjunto de ensamblados como datos y que tienen todos los bloqueos de archivo y la memoria liberada después de la inspección.

`MetadataLoadContext` tiene una clase de resolución que se transmite a su constructor. El trabajo de la resolución consiste en cargar un ensamblado `Assembly` dado su `AssemblyName`. La clase de la resolución se deriva de la clase abstracta `MetadataAssemblyResolver`. Se proporciona una implementación de la resolución para escenarios basados en rutas de acceso con `PathAssemblyResolver`.

[MetadataLoadContext pruebas](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) muestra muchos casos de uso. Las [pruebas de ensamblado](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) son un buen punto inicial.

## <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 y OpenSSL 1.1.1 en Linux

.NET Core ahora usará la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/) cuando esté disponible en un entorno determinado. TLS 1.3 aporta varias ventajas, según el [equipo de OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):

* Mejora de los tiempos de conexión gracias a una reducción del número de recorridos de ida y vuelta necesario entre el cliente y servidor.

* Mejora de la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros y al mayor cifrado del protocolo de enlace de la conexión.

La versión preliminar 1 de .NET Core 3.0 puede usar **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (la mejor versión que se encuentre en un sistema Linux).  Cuando **OpenSSL 1.1.1** está disponible, los tipos SslStream y HttpClient usarán **TLS 1.3** al usar `SslProtocols.None` (protocolos predeterminados del sistema), dando por sentado que el cliente y el servidor admiten **TLS 1.3**.

En el siguiente ejemplo se muestra la versión preliminar 1 de .NET Core 3.0 en Ubuntu 18.10 con conexión a <https://www.cloudflare.com>:

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows y macOS aún no admiten **TLS 1.3**. .NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.

## <a name="cryptography"></a>Criptografía

Se ha agregado compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan a través de `System.Security.Cryptography.AesGcm` y `System.Security.Cryptography.AesCcm`. Estos algoritmos son el [cifrado autenticado con algoritmos de datos de asociación (AEAD)](https://en.wikipedia.org/wiki/Authenticated_encryption) y los primeros algoritmos de cifrado autenticado (AE) agregados a .NET Core.

En el código siguiente se muestra cómo utilizar el cifrado **AesGcm** para cifrar y descifrar datos aleatorios.

El código de **AesCcm** sería casi idéntico (solo los nombres de variables de clase serían diferentes).

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>Importación y exportación de claves criptográfica

La versión preliminar 1 de .NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas de los formatos estándar, sin necesidad de usar un certificado X.509.

Todos los tipos de clave (RSA, DSA, ECDsa y ECDiffieHellman) son compatibles con el formato **X.509 SubjectPublicKeyInfo** de las claves públicas, y con los formatos **PKCS #8 PrivateKeyInfo** y **EncryptedPrivateKeyInfo de PKCS #8**  de las claves privadas. Además, RSA admite **PKCS #1 RSAPublicKey** y **PKCS #1 RSAPrivateKey**. Todos los métodos de exportación e importación generan datos binarios con codificación DER. Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

Los archivos PKCS#8 pueden inspeccionarse con la clase `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.

Los archivos PFX/PKCS#12 se pueden inspeccionar y manipular con `System.Security.Cryptography.Pkcs.Pkcs12Info` y `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectivamente.

## <a name="serialport-for-linux"></a>SerialPort para Linux

.NET Core 3.0 ahora admite <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.

Anteriormente, .NET Core solo admite el uso del tipo `SerialPort` en Windows.

## <a name="more-bcl-improvements"></a>Más mejoras de BCL

`Span<T>`, `Memory<T>` y los tipos relacionados que se introdujeron en .NET Core 2.1 se han optimizado en .NET Core 3.0. Operaciones comunes, como la construcción de intervalos, la segmentación, el análisis y la aplicación de formato funcionan mejor ahora. 

Además, los tipos como `String` se han mejorado para que sean más eficaces cuando se utilizan como claves con `Dictionary<TKey, TValue>` y otras colecciones. No se requiere ningún cambio de código para aprovechar estas mejoras.

Las mejoras siguientes también son nuevas en la versión preliminar 1 de .NET Core 3:

* Compatibilidad con Brotli integrada en HttpClient
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)
* Unsafe.Unbox
* CancellationToken.Unregister
* Operadores aritméticos complejos
* API de socket para TCP persistente
* StringBuilder.GetChunks
* Análisis de IPEndPoint
* RandomNumberGenerator.GetInt32

## <a name="tiered-compilation"></a>Compilación en niveles

La [compilación en niveles](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) está activada de forma predeterminada con .NET Core 3.0. Se trata de una característica que permite que el entorno de ejecución use de forma más adaptable el compilador Just-In-Time (JIT) para obtener un mejor rendimiento, tanto en el inicio como al maximizar el rendimiento.

Se agregó como una característica opcional en [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) y, más tarde, se habilitó de forma predeterminada en la [versión preliminar 2 de .NET Core 2.2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/). Posteriormente, se revirtió a opcional con .NET Core 2.2.

## <a name="arm64-linux-support"></a>Compatibilidad con ARM64 para Linux

Vamos a agregar compatibilidad con ARM64 para Linux en esta versión. Para poner en contexto, hemos agregado compatibilidad con ARM32 para Linux con .NET Core 2.1 y Windows con .NET Core 2.2. El principal caso de uso de ARM64 son escenarios de IoT.

Las [imágenes de Docker de Alpine, Debian y Ubuntu están disponibles en .NET Core para ARM64](https://hub.docker.com/r/microsoft/dotnet/).

Consulte la página sobre el [estado de ARM64 para .NET Core](https://github.com/dotnet/announcements/issues/82) si desea obtener más información.

>[!NOTE]
> Windows aún no ofrece soporte técnico para **ARM64**.
