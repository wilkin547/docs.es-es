---
title: Novedades de .NET Framework
ms.custom: updateeachrelease
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- what's new [.NET Framework]
ms.assetid: 1d971dd7-10fc-4692-8dac-30ca308fc0fa
ms.openlocfilehash: 82a2c1780c6e0e1d94a206b9b959d8e1944fd0a9
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802321"
---
# <a name="whats-new-in-the-net-framework"></a>Novedades de .NET Framework

En este artículo se resumen las nuevas características y mejoras en las siguientes versiones de .NET Framework:

- [.NET Framework 4.8](#v48)
- [.NET Framework 4.7.2](#v472)
- [.NET Framework 4.7.1](#v471)
- [.NET Framework 4.7](#v47)
- [.NET Framework 4.6.2](#v462)
- [.NET Framework 4.6.1](#v461)
- [.NET 2015 y .NET Framework 4.6](#v46)
- [.NET Framework 4.5.2](#v452)
- [.NET Framework 4.5.1](#v451)
- [.NET Framework 4.5](#v45)

Este artículo no proporciona información completa sobre cada una de las características nuevas y puede estar sujeto a cambios. Para obtener información general sobre .NET Framework, vea [Introducción](../get-started/index.md). Para conocer las plataformas compatibles, vea [Requisitos de sistema](../get-started/system-requirements.md). Para obtener vínculos de descarga e instrucciones de instalación, vea [Instalar](../install/guide-for-developers.md).

> [!NOTE]
> El equipo de .NET Framework también publica características fuera de banda con NuGet para expandir la compatibilidad con la plataforma e introducir nuevas funciones (como colecciones invariables y tipos de vector habilitados para SIMD). Para obtener más información, vea [Las API y las bibliotecas de clases adicionales](../additional-apis/index.md) y [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md).
> Vea una [lista completa de paquetes NuGet](https://www.nuget.org/profiles/dotnetframework) para .NET Framework.

<a name="v48" />

## <a name="introducing-net-framework-48"></a>Introducción a .NET Framework 4.8

.NET Framework 4.8 se basa en versiones anteriores de .NET Framework 4.x, ya que se han agregado muchas nuevas correcciones y varias características nuevas, sin dejar de ser un producto muy estable.

### <a name="downloading-and-installing-net-framework-48"></a>Descarga e instalación de .NET Framework 4.8

Puede descargar .NET Framework 4.8 de las ubicaciones siguientes:

- [Instalador web de .NET Framework 4.8](https://go.microsoft.com/fwlink/?LinkId=2085155)

- [Instalador sin conexión de .NET Framework 4.8](https://go.microsoft.com/fwlink/?linkid=2088631)

.NET Framework 4.8 se puede instalar en Windows 10, Windows 8.1, Windows 7 SP1 y las plataformas de servidor correspondientes a partir de Windows Server 2008 R2 SP1. Puede instalar .NET Framework 4.8 mediante el instalador web o el instalador sin conexión. La manera recomendada para la mayoría de los usuarios es usar el programa de instalación web.

Puede usar como destino .NET Framework 4.8 en Visual Studio 2012 o una versión posterior mediante la instalación del [Paquete de desarrollador de .NET Framework 4.8](https://go.microsoft.com/fwlink/?LinkId=2085167).

### <a name="whats-new-in-net-framework-48"></a>Novedades de .NET Framework 4.8

.NET Framework 4.8 incluye características nuevas en las áreas siguientes:

- [Clases base](#core48)
- [Windows Communication Foundation (WCF)](#wcf48)
- [Windows Presentation Foundation (WPF)](#wpf48)
- [Common Language Runtime](#clr48)

La accesibilidad mejorada, que permite que una aplicación proporcione una experiencia adecuada para los usuarios de tecnología de asistencia, sigue siendo uno de los principales aspectos en los que se centra .NET Framework 4.8. Para información sobre las mejoras de accesibilidad en .NET Framework 4.8, consulte [Novedades de accesibilidad en .NET Framework](whats-new-in-accessibility.md).

<a name="core48" />

#### <a name="base-classes"></a>Clases base

**Impacto de FIPS reducido sobre la criptografía**. En versiones anteriores de .NET Framework, las clases del proveedor de servicios criptográficos administrados, como <xref:System.Security.Cryptography.SHA256Managed>, producen una excepción <xref:System.Security.Cryptography.CryptographicException> cuando las bibliotecas criptográficas del sistema están configuradas en "modo FIPS". Estas excepciones se producen porque las versiones administradas de las clases de proveedor de servicios criptográficos, a diferencia de las bibliotecas criptográficas, no han pasado por la certificación 140-2 de FIPS (Estándar federal de procesamiento de información). Dado que pocos desarrolladores tienen sus máquinas de desarrollo en modo FIPS, las excepciones se producen normalmente en los sistemas de producción.

De forma predeterminada en las aplicaciones que tienen como destino .NET Framework 4.8, las siguientes clases de criptografía administrada ya no producen una excepción <xref:System.Security.Cryptography.CryptographicException> en este caso:

- <xref:System.Security.Cryptography.MD5Cng>
- <xref:System.Security.Cryptography.MD5CryptoServiceProvider>
- <xref:System.Security.Cryptography.RC2CryptoServiceProvider>
- <xref:System.Security.Cryptography.RijndaelManaged>
- <xref:System.Security.Cryptography.RIPEMD160Managed>
- <xref:System.Security.Cryptography.SHA256Managed>

En su lugar, estas clases redirigen las operaciones criptográficas a una biblioteca de criptografía del sistema. Este cambio elimina eficazmente una diferencia potencialmente confusa entre los entornos de desarrollo y los entornos de producción y permite que componentes nativos y componentes administrados funcionen bajo la misma directiva criptográfica. Las aplicaciones que dependen de estas excepciones pueden restaurar el comportamiento anterior mediante el establecimiento del modificador de AppContext `Switch.System.Security.Cryptography.UseLegacyFipsThrow` en `true`. Para más información, consulte [Applications that depend on these exceptions can restore the previous behavior by setting the AppContext switch](../migration-guide/retargeting/4.7.2-4.8.md#managed-cryptography-classes-do-not-throw-a-cryptographyexception-in-fips-mode) (Las aplicaciones que dependen de estas excepciones pueden restaurar el comportamiento anterior mediante el establecimiento del modificador AppContext).

**Uso de la versión actualizada de ZLib**

A partir de .NET Framework 4.5, el ensamblado clrcompression.dll usa [ZLib](https://www.zlib.net), una biblioteca externa nativa para la compresión de datos, con el fin de proporcionar una implementación del algoritmo deflate. En .NET Framework 4.8, clrcompression.dll se actualiza a ZLib, versión 1.2.11, que incluye varias mejoras y correcciones importantes.

<a name="wcf48" />

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

**Introducción de ServiceHealthBehavior**

Los puntos de conexión de mantenimiento se usan ampliamente en las herramientas de orquestación para administrar servicios en función de su estado de mantenimiento. Las comprobaciones de mantenimiento también se pueden usar en las herramientas de supervisión para realizar el seguimiento de la disponibilidad y rendimiento de un servicio y proporcionar notificaciones al respecto.

**ServiceHealthBehavior** es un comportamiento del servicio WCF que amplía <xref:System.ServiceModel.Description.IServiceBehavior>.  Cuando se agrega a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors?displayProperty=nameWithType>, un comportamiento de servicio hace lo siguiente:

- Devuelve el estado de mantenimiento del servicio con códigos de respuesta HTTP. Puede especificar en una cadena de consulta el código de estado HTTP para una solicitud de sondeo de estado HTTP/GET.

- Publica información sobre el mantenimiento del servicio. Se pueden mostrar detalles específicos del servicio, como estado del servicio, recuentos de aceleración y capacidad mediante una solicitud HTTP/GET con la cadena de consulta `?health`. La facilidad de acceso a dicha información es importante para solucionar los problemas de errores de comportamiento de un servicio WCF.

Hay dos maneras de exponer el punto de conexión de mantenimiento y publicar información de mantenimiento del servicio WCF:

- Mediante el código Por ejemplo:

  ```csharp
  ServiceHost host = new ServiceHost(typeof(Service1),
                     new Uri("http://contoso:81/Service1"));
  ServiceHealthBehavior healthBehavior =
      host.Description.Behaviors.Find<ServiceHealthBehavior>();
  healthBehavior ??= new ServiceHealthBehavior();
  host.Description.Behaviors.Add(healthBehavior);
  ```

  ```vb
  Dim host As New ServiceHost(GetType(Service1),
              New Uri("http://contoso:81/Service1"))
  Dim healthBehavior As ServiceHealthBehavior =
     host.Description.Behaviors.Find(Of ServiceHealthBehavior)()
  If healthBehavior Is Nothing Then
     healthBehavior = New ServiceHealthBehavior()
  End If
  host.Description.Behaviors.Add(healthBehavior)
  ```

- Por medio de un archivo de configuración Por ejemplo:

  ```xml
  <behaviors>
    <serviceBehaviors>
      <behavior name="DefaultBehavior">
        <serviceHealth httpsGetEnabled="true"/>
      </behavior>
    </serviceBehaviors>
  </behaviors>
  ```

Se puede consultar el estado de mantenimiento de un servicio mediante parámetros de consulta, como `OnServiceFailure`, `OnDispatcherFailure`, `OnListenerFailure`, `OnThrottlePercentExceeded`), y se puede especificar un código de respuesta HTTP para cada parámetro de consulta. Si se omite el código de respuesta HTTP para un parámetro de consulta, se usa de forma predeterminada un código de respuesta HTTP 503. Por ejemplo:

- OnServiceFailure: `https://contoso:81/Service1?health&OnServiceFailure=450`

  Se devuelve un código de estado de respuesta HTTP 450 cuando [ServiceHost.State](xref:System.ServiceModel.Channels.CommunicationObject.State) es mayor que <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.
Parámetros de consulta y ejemplos:

- OnDispatcherFailure: `https://contoso:81/Service1?health&OnDispatcherFailure=455`

  se devuelve un código de estado de respuesta HTTP 455 cuando el estado de cualquier distribuidor de canal es mayor que <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.

- OnListenerFailure: `https://contoso:81/Service1?health&OnListenerFailure=465`

  se devuelve un código de estado de respuesta HTTP 465 cuando el estado de cualquiera de las escuchas de canales es mayor que <xref:System.ServiceModel.CommunicationState.Opened?displayProperty=nameWithType>.

- OnThrottlePercentExceeded: `https://contoso:81/Service1?health&OnThrottlePercentExceeded= 70:350,95:500`

  especifica el porcentaje {1 a 100} que desencadena la respuesta y su código de respuesta HTTP {200 a 599}. En este ejemplo:

  - Si el porcentaje es mayor que 95, se devuelve un código de respuesta HTTP 500.

  - Si el porcentaje está entre 70 y 95, se devuelve 350.

  - En caso contrario, se devuelve 200.

El estado de mantenimiento del servicio se puede mostrar en HTML mediante la especificación de una cadena de consulta como `https://contoso:81/Service1?health` o en XML mediante la especificación de una cadena de consulta como `https://contoso:81/Service1?health&Xml`. Una cadena de consulta como `https://contoso:81/Service1?health&NoContent` devuelve una página HTML vacía.

<a name="wpf48" />

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

**Altas mejoras de PPP**

En .NET Framework 4.8, WPF proporciona compatibilidad con el reconocimiento de PPP por Monitor V2 y escala de PPP en modo mixto. Consulte [High DPI Desktop Application Development on Windows](/windows/win32/hidpi/high-dpi-desktop-application-development-on-windows) (Desarrollo de aplicaciones de escritorio de alto PPP en Windows).

.NET Framework 4.8 mejora la compatibilidad con la interoperación de HWND hospedado y Windows Forms en aplicaciones WPF de alto PPP en plataformas que admiten la escalabilidad de PPP en modo mixto (a partir de la actualización de abril de 2018 de Windows 10). Cuando se crean HWND hospedados o controles de Windows Forms como ventanas con escala PPP en modo mixto mediante la llamada a [SetThreadDpiHostingBehavior](/windows/desktop/api/winuser/nf-winuser-setthreaddpihostingbehavior) y [SetThreadDpiAwarenessContext](/windows/desktop/api/winuser/nf-winuser-setthreaddpiawarenesscontext), se pueden hospedar en una aplicación WPF por Monitor V2 y ajustar su tamaño y escalarse correctamente. Este contenido hospedado no se representa en el valor de PPP nativo, sino que el sistema operativo escala el contenido hospedado al tamaño adecuado. La compatibilidad con el modo de reconocimiento de PPP por Monitor v2 también permite hospedar los controles de WPF (es decir, convertir en elementos primarios) en una ventana nativa de una aplicación de alto PPP.

Para permitir la compatibilidad con la escalabilidad de alto PPP en modo mixto, puede establecer los siguientes modificadores [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) en el archivo de configuración de la aplicación:

```xml
<runtime>
   <AppContextSwitchOverrides value = "Switch.System.Windows.DoNotScaleForDpiChanges=false; Switch.System.Windows.DoNotUsePresentationDpiCapabilityTier2OrGreater=false"/>
</runtime>
```

<a name="clr48" />

#### <a name="common-language-runtime"></a>Common Language Runtime

El entorno de ejecución de .NET Framework 4.8 incluye los siguientes cambios y mejoras:

**Mejoras en el compilador JIT**. El compilador Just-in-time (JIT) de .NET Framework 4.8 se basa en el compilador JIT de .NET Core 2.1. Muchas de las optimizaciones y todas las correcciones de errores realizadas en el compilador JIT de .NET Core 2.1 se incluyen en el compilador JIT de .NET Framework 4.8.

**Mejoras de NGEN**. El entorno de ejecución ha mejorado la administración de memoria para las imágenes del [Generador de imágenes nativo](../tools/ngen-exe-native-image-generator.md) (NGEN) de forma que los datos asignados a partir de imágenes NGEN no son residentes en memoria. Esto reduce la superficie expuesta a ataques que intentan ejecutar código arbitrario mediante la modificación de la memoria que se va a ejecutar.

**Examen de todos los ensamblados con antimalware**. En versiones anteriores de .NET Framework, el entorno de ejecución examina todos los ensamblados cargados desde el disco mediante Windows Defender o software antimalware de terceros. Sin embargo, los ensamblados cargados desde otros orígenes, como con el método <xref:System.Reflection.Assembly.Load(System.Byte[])?displayProperty=nameWithType>, no se examinan y pueden contener posiblemente software malintencionado no detectado. A partir de .NET Framework 4.8 que se ejecuta en Windows 10, el entorno de ejecución desencadena un examen mediante soluciones antimalware que implementan la [Interfaz de detección de antimalware (AMSI)](/windows/desktop/AMSI/antimalware-scan-interface-portal).

<a name="v472" />

## <a name="whats-new-in-net-framework-472"></a>Novedades de .NET Framework 4.7.2

.NET Framework 4.7.2 incluye características nuevas en las áreas siguientes:

- [Clases base](#core-472)
- [ASP.NET](#asp-net472)
- [Redes](#net472)
- [SQL](#sql472)
- [WPF](#wpf472)
- [ClickOnce](#clickonce)

Uno de los aspectos en los que se centra .NET Framework 4.7.2 continuamente es la mejora de la accesibilidad, que permite que una aplicación proporcione una experiencia adecuada para los usuarios de tecnología de asistencia. Para información sobre las mejoras de accesibilidad en .NET Framework 4.7.2, consulte [Novedades de accesibilidad en .NET Framework](whats-new-in-accessibility.md).

<a name="core-472" />

#### <a name="base-classes"></a>Clases base

.NET Framework 4.7.2 presenta un gran número de mejoras criptográficas, mayor compatibilidad con descompresión de archivos ZIP y API de colección adicionales.

**Nuevas sobrecargas de RSA.Create y DSA.Create**

Los métodos <xref:System.Security.Cryptography.DSA.Create(System.Security.Cryptography.DSAParameters)?displayProperty=nameWithType> y <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> permiten especificar parámetros de clave cuando se crea una instancia de una clave <xref:System.Security.Cryptography.DSA> o <xref:System.Security.Cryptography.RSA>. Permiten reemplazar código similar al siguiente:

```csharp
// Before .NET Framework 4.7.2
using (RSA rsa = RSA.Create())
{
   rsa.ImportParameters(rsaParameters);
   // Other code to execute using the RSA instance.
}
```

```vb
' Before .NET Framework 4.7.2
Using rsa = RSA.Create()
   rsa.ImportParameters(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

con código como este:

```csharp
// Starting with .NET Framework 4.7.2
using (RSA rsa = RSA.Create(rsaParameters))
{
   // Other code to execute using the rsa instance.
}
```

```vb
' Starting with .NET Framework 4.7.2
Using rsa = RSA.Create(rsaParameters)
   ' Other code to execute using the rsa instance.
End Using
```

Los métodos <xref:System.Security.Cryptography.DSA.Create(System.Int32)?displayProperty=nameWithType> y <xref:System.Security.Cryptography.RSA.Create(System.Int32)?displayProperty=nameWithType> permiten generar claves <xref:System.Security.Cryptography.DSA> o <xref:System.Security.Cryptography.RSA> nuevas con un tamaño de clave específico. Por ejemplo:

```csharp
using (DSA dsa = DSA.Create(2048))
{
   // Other code to execute using the dsa instance.
}
```

```vb
Using dsa = DSA.Create(2048)
   ' Other code to execute using the dsa instance.
End Using
```

**Los constructores de Rfc2898DeriveBytes aceptan un nombre de algoritmo hash**

La clase <xref:System.Security.Cryptography.Rfc2898DeriveBytes> tiene tres constructores nuevos con un parámetro <xref:System.Security.Cryptography.HashAlgorithmName> que identifica el algoritmo HMAC que se va a usar en la derivación de las claves. En lugar de usar SHA-1, los programadores deben usar un algoritmo HMAC basado en SHA-2 como SHA-256, como se muestra en el ejemplo siguiente:

```csharp
private static byte[] DeriveKey(string password, out int iterations, out byte[] salt,
                                out HashAlgorithmName algorithm)
{
   iterations = 100000;
   algorithm = HashAlgorithmName.SHA256;

   const int SaltSize = 32;
   const int DerivedValueSize = 32;

   using (Rfc2898DeriveBytes pbkdf2 = new Rfc2898DeriveBytes(password, SaltSize,
                                                             iterations, algorithm))
   {
      salt = pbkdf2.Salt;
      return pbkdf2.GetBytes(DerivedValueSize);
   }
}
```

```vb
Private Shared Function DeriveKey(password As String, ByRef iterations As Integer,
                                  ByRef salt AS Byte(), ByRef algorithm As HashAlgorithmName) As Byte()
   iterations = 100000
   algorithm = HashAlgorithmName.SHA256

   Const SaltSize As Integer = 32
   Const  DerivedValueSize As Integer = 32

   Using pbkdf2 = New Rfc2898DeriveBytes(password, SaltSize, iterations, algorithm)
      salt = pbkdf2.Salt
      Return pbkdf2.GetBytes(DerivedValueSize)
   End Using
End Function
```

**Compatibilidad con claves efímeras**

La importación de PFX puede cargar de manera opcional las claves privadas directamente desde la memoria, omitiendo la unidad de disco duro. Cuando se especifica la marca <xref:System.Security.Cryptography.X509Certificates.X509KeyStorageFlags.EphemeralKeySet?displayProperty=nameWithType> nueva en un constructor de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> o una de las sobrecargas del método <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.Import%2A?displayProperty=nameWithType>, las claves privadas se cargarán como claves efímeras. Esto impide que las claves sean visibles en el disco. Pero:

- Como las claves no se conservan en el disco, los certificados que se cargan con esta marca no son buenos candidatos para agregar a un X509Store.

- Las claves que se cargan de esta manera casi siempre se cargan a través de CNG de Windows. Por tanto, los autores de la llamada deben tener acceso a la clave privada mediante la llamada a métodos de extensión, como [cert.GetRSAPrivateKey()](xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A). La propiedad <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> no funciona.

- Como la propiedad <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> heredada no funciona con los certificados, los desarrolladores deben realizar pruebas rigurosas antes de cambiar a las claves efímeras.

**Creación mediante programación de solicitudes de firma de certificación de PKCS#10 y certificados de clave pública X.509**

A partir de .NET Framework 4.7.2, las cargas de trabajo pueden generar solicitudes de firma de certificado (CSR), que permite que la generación de solicitudes de certificado se almacene provisionalmente en las herramientas existentes. Esto es útil en muchas ocasiones en escenarios de prueba.

Para obtener más información y ejemplos de código, vea "Programmatic creation of PKCS#10 certification signing requests and X.509 public key certificates" (Creación mediante programación de solicitudes de firma de certificación de PKCS#10 y certificados de clave pública X.509) en el [blog de .NET](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Nuevos miembros SignerInfo**

A partir de .NET Framework 4.7.2, la clase <xref:System.Security.Cryptography.Pkcs.SignerInfo> expone más información sobre la firma. Se puede recuperar el valor de la propiedad <xref:System.Security.Cryptography.Pkcs.SignerInfo.SignatureAlgorithm?displayProperty=fullName> para determinar el algoritmo de firma que usa el firmante. Se puede llamar a <xref:System.Security.Cryptography.Pkcs.SignerInfo.GetSignature%2A?displayProperty=nameWithType> para obtener una copia de la firma criptográfica para este firmante.

**Mantener abierta una secuencia ajustada después de eliminar CryptoStream**

A partir de .NET Framework 4.7.2, la clase <xref:System.Security.Cryptography.CryptoStream> tiene un constructor adicional que permite que <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no cierre la secuencia ajustada. Para dejar abierta la secuencia ajustada después de eliminar la instancia de <xref:System.Security.Cryptography.CryptoStream>, llame al nuevo constructor de <xref:System.Security.Cryptography.CryptoStream> como se indica a continuación:

```csharp
var cStream = new CryptoStream(stream, transform, mode, leaveOpen: true);
```

```vb
Dim cStream = New CryptoStream(stream, transform, mode, leaveOpen:=true)
```

**Cambios de descompresión en DeflateStream**

A partir de .NET Framework 4.7.2, la implementación de operaciones de descompresión en la clase <xref:System.IO.Compression.DeflateStream> ha cambiado para usar las API nativas de Windows de forma predeterminada. Normalmente, esto da como resultado una mejora considerable del rendimiento.

La compatibilidad para la descompresión mediante las API de Windows está habilitada de forma predeterminada para las aplicaciones que tienen como destino .NET Framework 4.7.2. Las aplicaciones que tienen como destino versiones anteriores de .NET Framework pero que se ejecutan en .NET Framework 4.7.2 pueden participar en este comportamiento mediante la adición del [modificador de AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente al archivo de configuración de la aplicación:

```xml
<AppContextSwitchOverrides value="Switch.System.IO.Compression.DoNotUseNativeZipLibraryForDecompression=false" />
```

**API de colección adicionales**

En .NET Framework 4.7.2 se agregan varias API nuevas a los tipos <xref:System.Collections.Generic.SortedSet%601> y <xref:System.Collections.Generic.HashSet%601>. Se incluyen los siguientes:

- Los métodos `TryGetValue`, que amplían el patrón de try que se usa en otros tipos de colección a estos dos tipos. Los métodos son:

  - [public bool HashSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)
  - [public bool SortedSet\<T>.TryGetValue(T equalValue, out T actualValue)](xref:System.Collections.Generic.SortedSet%601.TryGetValue%2A)

- Los métodos de extensión `Enumerable.To*`, que convierten una colección en un <xref:System.Collections.Generic.HashSet%601>:

  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source)](xref:System.Linq.Enumerable.ToHashSet%2A)
  - [public static HashSet\<TSource> ToHashSet\<TSource>(this IEnumerable\<TSource> source, IEqualityComparer\<TSource> comparer)](xref:System.Linq.Enumerable.ToHashSet%2A)

- Nuevos constructores de <xref:System.Collections.Generic.HashSet%601> que permiten establecer la capacidad de la colección, lo que da como resultado una mejora del rendimiento cuando se conoce el tamaño de <xref:System.Collections.Generic.HashSet%601> con antelación:

  - [public HashSet(int capacity)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32))
  - [public HashSet(int capacity, IEqualityComparer\<T> comparer)](xref:System.Collections.Generic.HashSet%601.%23ctor(System.Int32,System.Collections.Generic.IEqualityComparer%7B%600%7D))

La clase <xref:System.Collections.Concurrent.ConcurrentDictionary%602> incluye sobrecargas nuevas de los métodos <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> para recuperar un valor del diccionario o para agregarlo si no se encuentra, y para agregar un valor al diccionario o actualizarlo si ya existe.

```csharp
public TValue AddOrUpdate<TArg>(TKey key, Func<TKey, TArg, TValue> addValueFactory, Func<TKey, TValue, TArg, TValue> updateValueFactory, TArg factoryArgument)

public TValue GetOrAdd<TArg>(TKey key, Func<TKey, TArg, TValue> valueFactory, TArg factoryArgument)
```

```vb
Public AddOrUpdate(Of TArg)(key As TKey, addValueFactory As Func(Of TKey, TArg, TValue), updateValueFactory As Func(Of TKey, TValue, TArg, TValue), factoryArgument As TArg) As TValue

Public GetOrAdd(Of TArg)(key As TKey, valueFactory As Func(Of TKey, TArg, TValue), factoryArgument As TArg) As TValue
```

<a name="asp-net472" />

#### <a name="aspnet"></a>ASP.NET

**Compatibilidad con la inserción de dependencias en formularios Web Forms**

La [inserción de dependencias (DI)](/aspnet/core/fundamentals/dependency-injection#overview-of-dependency-injection) desacopla los objetos y sus dependencias para que ya no sea necesario cambiar el código de un objeto solo porque haya cambiado una dependencia. Al desarrollar aplicaciones de ASP.NET que tienen como destino .NET Framework 4.7.2, puede:

- Usar la inserción basada en establecedores, interfaces y constructores en [controladores y módulos](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [instancias de Page](xref:System.Web.UI.Page) y [controles de usuario](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) de proyectos de aplicación web ASP.NET.

- Usar la inserción basada en establecedores, e interfaces en [controladores y módulos](https://docs.microsoft.com/previous-versions/aspnet/bb398986(v=vs.100)), [instancias de Page](xref:System.Web.UI.Page) y [controles de usuario](https://docs.microsoft.com/previous-versions/aspnet/y6wb1a0e(v=vs.100)) de proyectos de sitio web ASP.NET.

- Conectar otros marcos de inserción de dependencias.

**Compatibilidad con cookies de SameSite**

[SameSite](https://tools.ietf.org/html/draft-west-first-party-cookies-07) impide que un explorador envíe una cookie junto con una solicitud entre sitios. .NET Framework 4.7.2 agrega una propiedad <xref:System.Web.HttpCookie.SameSite?displayProperty=nameWithType> cuyo valor es un miembro de la enumeración <xref:System.Web.SameSiteMode?displayProperty=nameWithType>. Si su valor es <xref:System.Web.SameSiteMode.Strict?displayProperty=nameWithType> o <xref:System.Web.SameSiteMode.Lax?displayProperty=nameWithType>, ASP.NET agrega el atributo `SameSite` al encabezado set-cookie. La compatibilidad con SameSite se aplica a los objetos <xref:System.Web.HttpCookie>, y también a las cookies <xref:System.Web.Security.FormsAuthentication> y <xref:System.Web.SessionState>.

Puede establecer SameSite para un objeto <xref:System.Web.HttpCookie> de esta forma:

```csharp
var c = new HttpCookie("secureCookie", "same origin");
c.SameSite = SameSiteMode.Lax;
```

```vb
Dim c As New HttpCookie("secureCookie", "same origin")
c.SameSite = SameSiteMode.Lax
```

También se pueden configurar cookies de SameSite en el nivel de aplicación si se modifica el archivo web.config:

```xml
<system.web>
   <httpCookies sameSite="Strict" />
</system.web>
```

Se puede agregar SameSite para las cookies <xref:System.Web.Security.FormsAuthentication> y <xref:System.Web.SessionState> si se modifica el archivo de configuración web:

```xml
<system.web>
   <authentication mode="Forms">
      <forms cookieSameSite="Lax">
         <!-- ...   -->
      </forms>
   <authentication />
   <sessionState cookieSameSite="Lax"></sessionState>
</system.web>
```

<a name="net472" />

#### <a name="networking"></a>Redes

**Implementación de propiedades de HttpClientHandler**

En .NET Framework 4.7.1 se agregaron ocho propiedades a la clase <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType>. Pero dos de ellas iniciaban una excepción <xref:System.PlatformNotSupportedException>. En .NET Framework 4.7.2 ahora se proporciona una implementación para estas propiedades. Las propiedades son las siguientes:

- <xref:System.Net.Http.HttpClientHandler.CheckCertificateRevocationList>
- <xref:System.Net.Http.HttpClientHandler.SslProtocols>

<a name="sql472" />

#### <a name="sqlclient"></a>SQLClient

**Compatibilidad con la autenticación universal y Multi-Factor Authentication de Azure Active Directory**

Las necesidades crecientes de seguridad y cumplimiento requieren que muchos clientes usen Multi-Factor Authentication (MFA). Además, los procedimientos recomendados actuales desaconsejan incluir las contraseñas de usuario directamente en las cadenas de conexión. Para admitir estos cambios, en .NET Framework 4.7.2 se extienden las [cadenas de conexión de SQLClient](xref:System.Data.SqlClient.SqlConnection.ConnectionString) mediante la adición de un nuevo valor, "Active Directory Interactive", para la palabra clave "Authentication" existente para admitir MFA, y [Autenticación de Azure AD](/azure/sql-database/sql-database-aad-authentication-configure). El nuevo método interactivo admite los usuarios nativos y federados de Azure AD, así como los usuarios invitados de Azure AD. Cuando se usa este método, se admite la autenticación MFA impuesta por Azure AD para las bases de datos SQL. Además, el proceso de autenticación solicita una contraseña de usuario para cumplir con los procedimientos recomendados de seguridad.

En versiones anteriores de .NET Framework, la conectividad SQL solo admitía las opciones <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryPassword?displayProperty=nameWithType> y <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryIntegrated?displayProperty=nameWithType>. Ambas forman parte del [protocolo ADAL](/azure/active-directory/develop/active-directory-authentication-libraries) no interactivo, que no admite MFA. Con la nueva opción <xref:System.Data.SqlClient.SqlAuthenticationMethod.ActiveDirectoryInteractive?displayProperty=nameWithType>, la conectividad SQL es compatible con MFA, así como los métodos de autenticación existentes (contraseña y autenticación integrada), lo que permite a los usuarios escribir las contraseñas de usuario de manera interactiva sin guardarlas en la cadena de conexión.

Para obtener más información y un ejemplo, vea "SQL -- Azure AD Universal and Multi-factor Authentication Support" (SQL: Compatibilidad con la autenticación universal y Multi-Factor Authentication de Azure AD) en el [blog de .NET](https://devblogs.microsoft.com/dotnet/net-framework-4-7-2-developer-pack-early-access-build-3056-is-available/).

**Compatibilidad con la versión 2 de Always Encrypted**

En .NET Framework 4.7.2 se agrega compatibilidad con Always Encrypted basada en enclave. La versión original de Always Encrypted es una tecnología de cifrado del lado cliente en la que las claves de cifrado nunca salen del cliente. En Always Encrypted basada en enclave, el cliente puede enviar opcionalmente las claves de cifrado a un enclave seguro, que es una entidad de cálculo segura que se puede considerar parte de SQL Server pero que el código de SQL Server no puede alterar. Para admitir Always Encrypted basado en enclave, en .NET Framework 4.7.2 se agregan los tipos y miembros siguientes al espacio de nombres <xref:System.Data.SqlClient>:

- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.EnclaveAttestationUrl?displayProperty=nameWithType>, que especifica el URI para Always Encrypted basada en enclave.

- <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider>, que es una clase abstracta de la que se derivan todos los proveedores de enclaves.

- <xref:System.Data.SqlClient.SqlEnclaveSession>, que encapsula el estado de una sesión de enclave determinada.

- <xref:System.Data.SqlClient.SqlEnclaveAttestationParameters>, que proporciona los parámetros de atestación que usa SQL Server para obtener la información necesaria para ejecutar un protocolo de atestación específico.

Después, el archivo de configuración de la aplicación especifica una implementación concreta de la clase abstracta <xref:System.Data.SqlClient.SqlColumnEncryptionEnclaveProvider?displayProperty=nameWithType> en la que se proporciona la funcionalidad para el proveedor de enclaves. Por ejemplo:

```xml
<configuration>
  <configSections>
    <section name="SqlColumnEncryptionEnclaveProviders" type="System.Data.SqlClient.SqlColumnEncryptionEnclaveProviderConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/> 
  </configSections>
  <SqlColumnEncryptionEnclaveProviders>
    <providers>
      <add name="Azure" type="Microsoft.SqlServer.Management.AlwaysEncrypted.AzureEnclaveProvider,MyApp"/>
      <add name="HGS" type="Microsoft.SqlServer.Management.AlwaysEncrypted.HGSEnclaveProvider,MyApp" />
    </providers>
  </SqlColumnEncryptionEnclaveProviders >
</configuration>
```

El flujo básico de Always Encrypted basada en enclave es el siguiente:

1. El usuario crea una conexión de AlwaysEncrypted a SQL Server que admita Always Encrypted basada en enclave. El controlador se pone en contacto con el servicio de atestación para asegurarse de que se está conectando al enclave correcto.

1. Una vez comprobado al enclave, el controlador establece un canal seguro con el enclave seguro alojado en SQL Server.

1. El controlador comparte las claves de cifrado autorizadas por el cliente con el enclave seguro para la duración de la conexión SQL.

<a name="wpf472" />

#### <a name="windows-presentation-foundation"></a>Windows Presentation Foundation

**Búsqueda de objetos ResourceDictionary por origen**

A partir de .NET Framework 4.7.2, un asistente de diagnóstico puede localizar los objetos  <xref:System.Windows.Xps.Packaging.IXpsFixedPageReader.ResourceDictionaries> que se han creado desde un URI de origen determinado. (Esta característica es para uso por parte de los asistentes de diagnóstico, no por las aplicaciones de producción). Un asistente de diagnóstico, como la opción "Editar y continuar" de Visual Studio, permite al usuario editar un objeto ResourceDictionary con la intención de que los cambios se puedan aplicar a la aplicación en ejecución. Un paso para lograr esto consiste en buscar todos los objetos ResourceDictionary que la aplicación en ejecución ha creado a partir del diccionario que se está editando. Por ejemplo, una aplicación puede declarar un objeto ResourceDictionary cuyo contenido se copia desde un URI de origen determinado:

```xml
<ResourceDictionary Source="MyRD.xaml">
```

Un asistente de diagnóstico que edite el marcado original en *MyRD.xaml*  puede usar la característica nueva para buscar el diccionario. La característica se implementa mediante un método estático nuevo, <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetResourceDictionariesForSource%2A?displayProperty=nameWithType>. El asistente de diagnóstico llama al método nuevo mediante un URI absoluto que identifica el marcado original, como se muestra en el código siguiente:

```csharp
IEnumerable<ResourceDictionary> dictionaries = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(new Uri("pack://application:,,,/MyApp;component/MyRD.xaml"));
```

```vb
Dim dictionaries As IEnumerable(Of ResourceDictionary) = ResourceDictionaryDiagnostics.GetResourceDictionariesForSource(New Uri("pack://application:,,,/MyApp;component/MyRD.xaml"))
```

El método devuelve un enumerable vacío a menos que se habilite  <xref:System.Windows.Diagnostics.VisualDiagnostics> y se establezca la variable de entorno [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) .

**Buscar los propietarios de ResourceDictionary**

A partir de .NET Framework 4.7.2, un asistente de diagnóstico puede localizar los propietarios de un objeto <xref:Windows.UI.Xaml.ResourceDictionary> determinado. (La característica está pensada para que la usen los asistentes de diagnóstico, no las aplicaciones de producción). Siempre que se realice un cambio en un <xref:Windows.UI.Xaml.ResourceDictionary>, WPF busca automáticamente todas las referencias [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md) que es posible que se vean afectadas por el cambio.

Un asistente de diagnóstico como la opción "Editar y continuar" de Visual Studio puede extender esta opción para controlar las referencias [StaticResource](../wpf/advanced/staticresource-markup-extension.md). El primer paso de este proceso consiste en encontrar los propietarios del diccionario; es decir, buscar todos los objetos cuya propiedad `Resources` hace referencia al diccionario (ya sea directa o indirectamente a través de la propiedad <xref:System.Windows.ResourceDictionary.MergedDictionaries?displayProperty=nameWithType>). Tres métodos estáticos nuevos implementadas en la clase <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics?displayProperty=nameWithType>, uno para cada uno de los tipos base que tengan una propiedad `Resources`, admiten este paso:

- [`public static IEnumerable<FrameworkElement> GetFrameworkElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkElementOwners%2A)

- [`public static IEnumerable<FrameworkContentElement> GetFrameworkContentElementOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetFrameworkContentElementOwners%2A)

- [`public static IEnumerable<Application> GetApplicationOwners(ResourceDictionary dictionary);`](xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.GetApplicationOwners%2A)

Estos métodos devuelven un enumerable vacío a menos que se habilite  <xref:System.Windows.Diagnostics.VisualDiagnostics> y se establezca la variable de entorno [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) .

**Buscar referencias StaticResource**

Ahora un asistente de diagnóstico puede recibir una notificación cada vez que se resuelva una referencia [StaticResource](../wpf/advanced/staticresource-markup-extension.md). (La característica está pensada para que la usen los asistentes de diagnóstico, no las aplicaciones de producción). Es posible que un asistente de diagnóstico, como la opción "Editar y continuar" de Visual Studio, quiera actualizar todos los usos de un recurso cuando cambie su valor en un objeto <xref:Windows.UI.Xaml.ResourceDictionary>. WPF hace esto automáticamente para las referencias [DynamicResource](../wpf/advanced/dynamicresource-markup-extension.md), pero no deliberadamente para las referencias [StaticResource](../wpf/advanced/staticresource-markup-extension.md). A partir de .NET Framework 4.7.2, el asistente de diagnóstico puede usar estas notificaciones para buscar esos usos del recurso estático.

La notificación se implementa mediante el nuevo evento <xref:System.Windows.Diagnostics.ResourceDictionaryDiagnostics.StaticResourceResolved?displayProperty=nameWithType>:

```csharp
public static event EventHandler<StaticResourceResolvedEventArgs> StaticResourceResolved;
```

```vb
Public Shared Event StaticResourceResolved As EventHandler(Of StaticResourceResolvedEventArgs)
```

Este evento se desencadena cuando el tiempo de ejecución resuelve una referencia [StaticResource](../wpf/advanced/staticresource-markup-extension.md). Los argumentos de <xref:System.Windows.Diagnostics.StaticResourceResolvedEventArgs> describen la resolución e indican el objeto y la propiedad que hospedan la referencia [StaticResource](../wpf/advanced/staticresource-markup-extension.md) y el objeto  <xref:Windows.UI.Xaml.ResourceDictionary> y la clave que se usan para la resolución:

```csharp
public class StaticResourceResolvedEventArgs : EventArgs
{
   public Object TargetObject { get; }

   public Object TargetProperty { get; }

   public ResourceDictionary ResourceDictionary { get; }

   public object ResourceKey { get; }
}
```

```vb
Public Class StaticResourceResolvedEventArgs : Inherits EventArgs
   Public ReadOnly Property TargetObject As Object
   Public ReadOnly Property TargetProperty As Object
   Public ReadOnly Property ResourceDictionary As ResourceDictionary
   Public ReadOnly Property ResourceKey As Object
End Class
```

El evento no se desencadena y su descriptor de acceso `add` se ignora, a menos que se habilite  <xref:System.Windows.Diagnostics.VisualDiagnostics> y se establezca la variable de entorno [`ENABLE_XAML_DIAGNOSTICS_SOURCE_INFO`](xref:System.Windows.Diagnostics.VisualDiagnostics.GetXamlSourceInfo%2A) .

#### <a name="clickonce"></a>ClickOnce

Las aplicaciones compatibles con HDPI para Windows Forms, Windows Presentation Foundation (WPF) y Visual Studio Tools para Office (VSTO) se pueden implementar mediante ClickOnce. Si la entrada siguiente se encuentra en el manifiesto de aplicación, se podrá completar correctamente la implementación en .NET Framework 4.7.2:

```xml
<windowsSettings>
   <dpiAware xmlns="http://schemas.microsoft.com/SMI/2005/WindowsSettings">true</dpiAware>
</windowsSettings>
```

Para la aplicación de Windows Forms, la solución anterior de establecer el reconocimiento de PPP en el archivo de configuración de la aplicación en lugar de en el manifiesto de aplicación ya no es necesaria para que la implementación de ClickOnce sea correcta.

<a name="v471" />

## <a name="whats-new-in-net-framework-471"></a>Novedades de .NET Framework 4.7.1

.NET Framework 4.7.1 incluye características nuevas en las áreas siguientes:

- [Clases base](#core471)
- [Common Language Runtime (CLR)](#clr)
- [Redes](#net471)
- [ASP.NET](#asp-net471)

Además, uno de los principales aspectos en los que se centra .NET Framework 4.7.1 es en la mejora de accesibilidad, que permite que una aplicación proporcione una experiencia adecuada para los usuarios de tecnología de asistencia. Para información sobre las mejoras de la accesibilidad en .NET Framework 4.7.1, consulte [Novedades de accesibilidad en .NET Framework](whats-new-in-accessibility.md).

<a name="core471" />

#### <a name="base-classes"></a>Clases base

**Compatibilidad con .NET Standard 2.0**

[.NET Standard](../../standard/net-standard.md) define un conjunto de API que debe estar disponible en cada implementación de .NET que cumple con esa versión de Standard. .NET Framework 4.7.1 es totalmente compatible con .NET Standard 2.0 y agrega [unas 200 API](https://github.com/dotnet/standard/blob/master/netstandard/src/ApiCompatBaseline.net461.txt) definidas en .NET Standard 2.0 que no se encuentran en .NET Framework 4.6.1, 4.6.2 y 4.7. (Tenga en cuenta que estas versiones de .NET Framework son compatibles con .NET Standard 2.0 solo si también se implementan los archivos de compatibilidad adicionales de .NET Standard en el sistema de destino). Para más información, vea "BCL - .NET Standard 2.0 Support" (BCL: compatibilidad con .NET Standard 2.0) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Características del compilador y del tiempo de ejecución de NET Framework 4.7.1).

**Compatibilidad con los generadores de configuración**

Los generadores de configuración permiten a los desarrolladores insertar y crear valores de configuración de forma dinámica para aplicaciones en tiempo de ejecución. Se pueden usar generadores de configuración personalizados para modificar datos existentes de una sección de configuración o para crear una sección de configuración totalmente desde cero. Sin los generadores de configuración, los archivos .config son estáticos y sus valores se definen algún tiempo antes de que se inicie la aplicación.

Para crear un generador de configuración personalizado, derive el generador de la clase <xref:System.Configuration.ConfigurationBuilder> abstracta y reemplace sus métodos <xref:System.Configuration.ConfigurationBuilder.ProcessConfigurationSection%2A?displayProperty=nameWithType> y <xref:System.Configuration.ConfigurationBuilder.ProcessRawXml%2A?displayProperty=nameWithType>. También debe definir los generadores en el archivo .config. Para más información, vea la sección "Configuration Builders" (Generadores de configuración) en la entrada de blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Características de configuración y ASP.NET en .NET Framework 4.7.1).

**Detección de características en tiempo de ejecución**

La clase <xref:System.Runtime.CompilerServices.RuntimeFeature?displayProperty=nameWithType> proporciona un mecanismo para determinar si se admite una característica predefinida en una determinada implementación de .NET en tiempo de compilación o en tiempo de ejecución. En tiempo de compilación, un compilador puede comprobar si existe un campo especificado para determinar si se admite la característica; si es así, puede emitir código que aprovecha las ventajas de la característica. En tiempo de ejecución, una aplicación puede llamar al método <xref:System.Runtime.CompilerServices.RuntimeFeature.IsSupported%2A?displayProperty=nameWithType> antes de emitir el código en tiempo de ejecución. Para obtener más información, vea [Add helper method to describe features supported by the runtime](https://github.com/dotnet/corefx/issues/17116) (Adición de un método del asistente para describir características admitidas en tiempo de ejecución).

**Los tipos value tuple son serializables**

A partir de .NET Framework 4.7.1, <xref:System.ValueTuple?displayProperty=nameWithType> y sus tipos genéricos asociados se marcan como [serializables](xref:System.SerializableAttribute), lo que permite la serialización binaria. Esto facilita la migración de tipos tuple, como <xref:System.Tuple%603> y <xref:System.Tuple%604>, a tipos value tuple. Para más información, vea "Compiler -- ValueTuple is Serializable" (Compilador: ValueTuple serializable) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Características del compilador y del tiempo de ejecución de .NET Framework 4.7.1).

**Compatibilidad con referencias de solo lectura**

.NET Framework 4.7.1 agrega <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute?displayProperty=nameWithType>. Los compiladores de lenguaje utilizan este atributo para marcar los miembros que tienen parámetros o tipos de valor devuelto con referencias de solo lectura. Para más información, vea "Compiler -- Support for ReadOnlyReferences" (Compilador: compatibilidad con referencias de solo lectura) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Características del compilador y del tiempo de ejecución de NET Framework 4.7.1). Para obtener información sobre los valores devueltos de referencia, vea [Ref return values and ref locals (C# Guide)](../../csharp/programming-guide/classes-and-structs/ref-returns.md) [Valores devueltos y variables locales de tipo ref (Guía de C#)] y [Ref return values (Visual Basic)](../../visual-basic/programming-guide/language-features/procedures/ref-return-values.md) [Valores devueltos tipo ref (Visual Basic)].

<a name="clr" />

#### <a name="common-language-runtime-clr"></a>Common Language Runtime (CLR)

**Mejoras de rendimiento de la recolección de elementos no utilizados**

Los cambios en la recolección de elementos no utilizados en .NET Framework 4.7.1 mejoran el rendimiento general, sobre todo para las asignaciones del montón de objetos grandes. En .NET Framework 4.7.1, se usan bloqueos independientes para las asignaciones de montón de objetos pequeños y de montón de objetos grandes, lo que permite que se realicen asignaciones de montón de objetos grandes cuando la operación de recolección de elementos no utilizados en segundo plano barre el montón de objetos pequeños. Como resultado, las aplicaciones que realizan un número elevado de asignaciones de montón de objetos grandes deben observar una reducción de la contención del bloqueo de asignación y un rendimiento mejorado. Para más información, vea la sección "Runtime - GC Performance Improvements" (Tiempo de ejecución: mejoras de rendimiento de GC) en la entrada de blog [.NET Framework 4.7.1 Runtime and Compiler Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-runtime-and-compiler-features/) (Características del compilador y del tiempo de ejecución de NET Framework 4.7.1).

<a name="net471"/>

#### <a name="networking"></a>Redes

**Compatibilidad de SHA-2 con Message.HashAlgorithm**

En .NET Framework 4.7 y versiones anteriores, la propiedad <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType> solo admitía los valores <xref:System.Messaging.HashAlgorithm.Md5?displayProperty=nameWithType> y <xref:System.Messaging.HashAlgorithm.Sha?displayProperty=nameWithType>. A partir de .NET Framework 4.7.1, también se admiten <xref:System.Messaging.HashAlgorithm.Sha256?displayProperty=nameWithType>, <xref:System.Messaging.HashAlgorithm.Sha384?displayProperty=nameWithType> y <xref:System.Messaging.HashAlgorithm.Sha512?displayProperty=nameWithType>. Si este valor se usa realmente, depende de MSMQ, ya que la propia instancia <xref:System.Messaging.Message> no tiene ninguna función hash, sino que solo pasa los valores a MSMQ. Para más información, vea la sección "SHA-2 support for Message.HashAlgorithm" (Compatibilidad de SHA-2 con Message.HashAlgorithm) en la entrada de blog [.NET Framework 2 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Características de configuración y ASP.NET en .NET Framework 4.7.1).

<a name="asp-net471" />

#### <a name="aspnet"></a>ASP.NET

**Pasos de ejecución en aplicaciones ASP.NET**

ASP.NET procesa las solicitudes en una canalización predefinida que incluye veintitrés eventos. ASP.NET ejecuta cada controlador de eventos como un paso de ejecución. En las versiones de ASP.NET hasta .NET Framework 4.7, ASP.NET no puede permitir el flujo del contexto de ejecución debido al cambio entre subprocesos nativos y administrados. En su lugar, ASP.NET solo crea un flujo selectivo de <xref:System.Web.HttpContext>. A partir de .NET Framework 4.7.1, el método <xref:System.Web.HttpApplication.OnExecuteRequestStep(System.Action{System.Web.HttpContextBase,System.Action})?displayProperty=nameWithType> también permite que los módulos restauren los datos de ambiente. Esta característica está orientada a las bibliotecas que tratan sobre el seguimiento, la generación de perfiles, el diagnóstico o las transacciones, que, por ejemplo, abordan el flujo de ejecución de la aplicación. Para más información, vea la sección "ASP.NET Execution Step Feature" (Característica de pasos de ejecución de ASP.NET) en la entrada de blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Características de configuración y ASP.NET en .NET Framework 4.7.1).

**Análisis HttpCookie de ASP.NET**

.NET Framework 4.7.1 incluye un nuevo método, <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType>, que ofrece una forma estandarizada de crear un objeto <xref:System.Web.HttpCookie> a partir de una cadena y asignar con precisión valores de cookie, como la fecha de expiración y la ruta de acceso. Para más información, vea la sección "ASP.NET HttpCookie parsing" (Análisis HttpCookie de ASP.NET) en la entrada de blog [.NET Framework 4.7.1 ASP.NET and Configuration Features](https://devblogs.microsoft.com/dotnet/net-framework-4-7-1-asp-net-and-configuration-features/) (Características de configuración y ASP.NET en .NET Framework 4.7.1).

**Compatibilidad con opciones hash SHA-2 para las credenciales de autenticación de formularios de ASP.NET**

En .NET Framework 4.7 y versiones anteriores, ASP.NET permitía a los desarrolladores almacenar credenciales de usuario con contraseña a las que se les había aplicado el algoritmo hash en archivos de configuración que usan MD5 o SHA1. A partir de .NET Framework 4.7.1, ASP.NET también admite nuevas opciones hash SHA-2 seguras, como SHA256, SHA384 y SHA512. SHA1 sigue siendo la opción predeterminada, aunque se puede definir un algoritmo hash no predeterminado en el archivo de configuración web. Por ejemplo:

```xml
<system.web>
    <authentication mode="Forms">
        <forms loginUrl="~/login.aspx">
          <credentials passwordFormat="SHA512">
            <user name="jdoe" password="6D003E98EA1C7F04ABF8FCB375388907B7F3EE06F278DB966BE960E7CBBD103DF30CA6D61F7E7FD981B2E4E3A64D43C836A4BEDCA165C33B163E6BCDC538A664" />
          </credentials>
        </forms>
    </authentication>
</system.web>
```

<a name="v47" />

## <a name="whats-new-in-net-framework-47"></a>Novedades de .NET Framework 4.7

.NET Framework 4.7 incluye características nuevas en las áreas siguientes:

- [Clases base](#Core47)
- [Redes](#net47)
- [ASP.NET](#ASP-NET47)
- [Windows Communication Foundation (WCF)](#wcf47)
- [Windows Forms](#wf47)
- [Windows Presentation Foundation (WPF)](#WPF47)

Para ver una lista de las nuevas API agregadas a .NET Framework 4.7, consulte [.NET Framework 4.7 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-api-changes.md) (Cambios de API de .NET Framework 4.7) en GitHub. Para ver una lista de las mejoras de características y correcciones de errores en .NET Framework 4.7, consulte [.NET Framework 4.7 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net47/dotnet47-changes.md) (Lista de cambios de .NET Framework 4.7) en GitHub.  Para más información, vea [Announcing .NET Framework 4.7](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-7/) (Anuncio de .NET Framework 4.7) en el blog de .NET.

<a name="Core47" />

#### <a name="base-classes"></a>Clases base

.NET Framework 4.7 mejora la serialización con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>:

**Funcionalidad mejorada con criptografía de curva elíptica (ECC)** *

En .NET Framework 4.7, los métodos `ImportParameters(ECParameters)` se han agregado a las clases <xref:System.Security.Cryptography.ECDsa> y <xref:System.Security.Cryptography.ECDiffieHellman> para permitir que un objeto represente una clave establecida previamente. También se agregó un método `ExportParameters(Boolean)` para exportar la clave mediante parámetros de curva explícitos.

.NET Framework 4.7 también admite curvas adicionales, como el conjunto de curvas Brainpool, y se han agregado definiciones predefinidas para facilitar la creación mediante los nuevos patrones de diseño Factory Method <xref:System.Security.Cryptography.ECDsa.Create%2A> y <xref:System.Security.Cryptography.ECDiffieHellman.Create%2A>.

Puede ver un [ejemplo de las mejoras de criptografía de .NET Framework 4.7](https://gist.github.com/richlander/5a182899895a87a296c21ada97f7a54e) en GitHub.

**Mayor compatibilidad para caracteres de control mediante DataContractJsonSerializer**

En .NET Framework 4.7, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serializa los caracteres de control en conformidad con el estándar ECMAScript 6. Este comportamiento está habilitado de manera predeterminada para aplicaciones que tienen .NET Framework 4.7 como destino y es una característica opcional para las aplicaciones que se ejecutan en .NET Framework 4.7 pero tienen como destino una versión anterior de .NET Framework. Para más información, consulte [Cambios de redestinación en .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="net47" />

#### <a name="networking"></a>Redes

.NET Framework 4.7 agrega la siguiente característica relacionada con la red:

**Compatibilidad predeterminada del sistema operativo con protocolos TLS***

La pila TLS, que la usan <xref:System.Net.Security.SslStream?displayProperty=nameWithType> y los componentes que se encuentran por encima de la pila, como HTTP, FTP y SMTP, permite a los desarrolladores usar los protocolos TLS predeterminados compatibles con el sistema operativo. Ya no es necesario que los desarrolladores codifiquen una versión de TLS de forma rígida.

<a name="ASP-NET47" />

#### <a name="aspnet"></a>ASP.NET

En .NET Framework 4.7, ASP.NET incluye las siguientes características nuevas:

**Extensibilidad de caché de objetos**

A partir de .NET Framework 4.7, ASP.NET agrega un nuevo conjunto de API que permiten que los desarrolladores reemplacen las implementaciones predeterminadas de ASP.NET por la supervisión de memoria y el almacenamiento en caché de objetos en memoria. Ahora los desarrolladores pueden reemplazar cualquiera de los siguientes tres componentes si la implementación de ASP.NET no es adecuada:

- **Almacén de caché de objetos**. En la nueva sección de configuración de proveedores de caché, los desarrolladores pueden insertar implementaciones nuevas de una caché de objetos para una aplicación de ASP.NET mediante la nueva interfaz **ICacheStoreProvider**.

- **Supervisión de memoria**. El monitor de memoria predeterminado de ASP.NET notifica a las aplicaciones cuando se ejecutan cerca del límite de bytes privado configurado para el proceso o cuando queda poca RAM física total disponible en la máquina. Las notificaciones se activan cuando se está cerca de estos límites. En el caso de algunas aplicaciones, las notificaciones se activan demasiado cerca de los límites configurados como para permitir reacciones que sean útiles. Los desarrolladores ahora pueden usar la propiedad <xref:System.Web.Hosting.ApplicationMonitors.MemoryMonitor%2A?displayProperty=nameWithType> para escribir sus propios monitores de memoria y, así, reemplazar el predeterminado.

- **Reacciones por límite de memoria**. De forma predeterminada, ASP.NET intenta recortar la caché de objetos y llama periódicamente a <xref:System.GC.Collect%2A?displayProperty=nameWithType> cuando se está cerca del límite de proceso de bytes privados. En algunas aplicaciones, la frecuencia de llamadas a <xref:System.GC.Collect%2A?displayProperty=nameWithType> o la cantidad de caché que se recorta no son suficientes. Ahora los desarrolladores puede reemplazar o complementar el comportamiento predeterminado si suscriben las implementaciones de **IObserver** al monitor de memoria de la aplicación.

<a name="wcf47" />

#### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

Windows Communication Foundation (WCF) agrega las siguientes características y cambios:

**Capacidad de configurar las opciones de seguridad de mensaje predeterminadas en TLS 1.1 o TLS 1.2**

A partir de .NET Framework 4.7, WCF le permite configurar TSL 1.1 o TLS 1.2 además de SSL 3.0 y TSL 1.0 como protocolo de seguridad de mensajes predeterminado. Esta es una configuración opcional; para habilitarla, debe agregar la entrada siguiente al archivo de configuración de la aplicación:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

**Confiabilidad mejorada de las aplicaciones WFC y la serialización WCF**

WCF incluye varios cambios de código que eliminan condiciones de carrera, por lo que se mejora el rendimiento y la confiabilidad de las opciones de serialización. Se incluyen los siguientes:

- Mayor compatibilidad para combinar código asincrónico y sincrónico en las llamadas a **SocketConnection.BeginRead** y **SocketConnection.Read**.
- Confiabilidad mejorada cuando se anula una conexión con **SharedConnectionListener** y **DuplexChannelBinder**.
- Confiabilidad mejorada de las operaciones de serialización al llamar al método <xref:System.Runtime.Serialization.FormatterServices.GetSerializableMembers%28System.Type%29?displayProperty=nameWithType>.
- Confiabilidad mejorada cuando se elimina un objeto waiter mediante una llamada al método **ChannelSynchronizer.RemoveWaiter**.

<a name="wf47" />

#### <a name="windows-forms"></a>Windows Forms

En .NET Framework 4.7, Windows Forms mejora la compatibilidad con monitores con valores altos de PPP.

**Compatibilidad con valores altos de PPP**

A partir de las aplicaciones que tienen .NET Framework 4.7 como destino, .NET Framework cuenta con compatibilidad con valores altos de PPP y PPP dinámicos en aplicaciones de Windows Forms. La compatibilidad con valores altos de PPP mejora el diseño y la apariencia de los formularios y controles en monitores con valores altos de PPP. PPP dinámicos cambia el diseño y la apariencia de los formularios y controles cuando el usuario cambia los PPP o el factor de escala de visualización de una aplicación en ejecución.

Compatibilidad con valores altos de PPP es una característica opcional que se configura definiendo una sección [\<System.Windows.Forms.ConfigurationSection>](../configure-apps/file-schema/winforms/index.md) en el archivo de configuración de la aplicación. Para más información sobre cómo agregar compatibilidad con valores altos de PPP y PPP dinámicos a la aplicación de Windows Forms, consulte [Compatibilidad con valores altos de PPP en Windows Forms](../winforms/high-dpi-support-in-windows-forms.md).

<a name="WPF47" />

#### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

En .NET Framework 4.7, WPF incluye las siguientes mejoras:

**Compatibilidad con una pila de entrada táctil o de lápiz basada en mensajes WM_POINTER de Windows**

Ahora tiene la opción de usar una pila de entrada táctil o de lápiz basada en [mensajes WM_POINTER](https://docs.microsoft.com/previous-versions/windows/desktop/InputMsg/messages) en lugar de Windows Ink Services Platform (WISP). Se trata de una característica opcional de .NET Framework. Para más información, consulte [Cambios de redestinación en .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

**Nueva implementación para API de impresión de WPF**

Las API de impresión de WPF de la clase <xref:System.Printing.PrintQueue?displayProperty=nameWithType> llaman a la [API Print Document Package](/windows/desktop/printdocs/tailored-app-printing-api) de Windows en lugar de a la [API XPS Print](/windows/desktop/printdocs/xps-printing), que está en desuso. Para ver el impacto que este cambio tiene en la compatibilidad de aplicaciones, consulte [Cambios de redestinación en .NET Framework 4.7](../migration-guide/retargeting-changes-in-the-net-framework-4-7.md).

<a name="v462" />

## <a name="whats-new-in-net-framework-462"></a>Novedades de .NET Framework 4.6.2

.NET Framework 4.6.2 incluye nuevas características en las áreas siguientes:

- [ASP.NET](#ASPNET462)

- [Categorías de caracteres](#Strings)

- [Criptografía](#Crypto462)

- [SqlClient](#SQLClient)

- [Windows Communication Foundation](#WCF)

- [Windows Presentation Foundation (WPF)](#WPF462)

- [Windows Workflow Foundation (WF)](#WF462)

- [ClickOnce](#clickonce-1)

- [Conversión de aplicaciones de Windows Forms y WPF a aplicaciones de UWP](#UWPConvert)

- [Mejoras en la depuración](#Debug462)

Para ver una lista de las nuevas API agregadas a .NET Framework 4.6.2, consulte [.NET Framework 4.6.2 API Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-api-changes.md) (Cambios de API de .NET Framework 4.6.2) en GitHub. Para ver una lista de las mejoras de características y correcciones de errores en .NET Framework 4.6.2, consulte [.NET Framework 4.6.2 List of Changes](https://github.com/Microsoft/dotnet/blob/master/releases/net462/dotnet462-changes.md) (Lista de cambios de .NET Framework 4.6.2) en GitHub. Para obtener más información, vea [Announcing .NET Framework 4.6.2](https://devblogs.microsoft.com/dotnet/announcing-net-framework-4-6-2/) (Anuncio de .NET Framework 4.6.2) en el blog de .NET.

<a name="ASPNET462" />

### <a name="aspnet"></a>ASP.NET

En .NET Framework 4.6.2, ASP.NET incluye las siguientes mejoras:

**Compatibilidad mejorada para los mensajes de error localizado de validadores de anotación de datos**

Los validadores de anotación de datos permiten realizar la validación agregando uno o varios atributos a una propiedad de clase. El elemento <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> del atributo define el texto del mensaje de error si se produce un error de validación. A partir de .NET Framework 4.6.2, ASP.NET facilita la tarea de localizar mensajes de error. Los mensajes de error se localizarán si:

1. Se proporciona <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> en el atributo de validación.

2. El archivo de recursos está almacenado en la carpeta App_LocalResources.

3. El nombre del archivo de recursos localizados tiene la forma `DataAnnotation.Localization.{`*nombre*`}.resx`, donde *nombre* es un nombre de referencia cultural en el formato *códigoDeIdioma*`-`*códigoDePaís/Región* o *códigoDeIdioma*.

4. El nombre de clave del recurso es la cadena asignada al atributo <xref:System.ComponentModel.DataAnnotations.ValidationAttribute.ErrorMessage%2A?displayProperty=nameWithType> y su valor es el mensaje de error localizado.

Por ejemplo, el siguiente atributo de anotación de datos define el mensaje de error de la referencia cultural predeterminada para una clasificación no válida.

```csharp
public class RatingInfo
{
   [Required(ErrorMessage = "The rating must be between 1 and 10.")]
   [Display(Name = "Your Rating")]
   public int Rating { get; set; }
}
```

```vb
Public Class RatingInfo
   <Required(ErrorMessage = "The rating must be between 1 and 10.")>
   <Display(Name = "Your Rating")>
   Public Property Rating As Integer = 1
End Class
```

A continuación, puede crear un archivo de recursos DataAnnotation.Localization.fr.resx cuya clave sea la cadena del mensaje de error y cuyo valor sea el mensaje de error localizado. El archivo debe encontrarse en la carpeta `App.LocalResources`. Por ejemplo, a continuación se muestra la clave y su valor en un mensaje de error localizado en idioma francés (fr):

| Name                                 | Valor                                     |
| ------------------------------------ | ----------------------------------------- |
| La clasificación debe estar entre 1 y 10. | La note doit être comprise entre 1 et 10. |

 Además, la localización de anotaciones de datos es extensible. Los desarrolladores pueden conectar su propio proveedor de localizador de cadenas mediante la implementación de la interfaz <xref:System.Web.Globalization.IStringLocalizerProvider> para almacenar la cadena de localización en un lugar distinto de un archivo de recursos.

 **Compatibilidad asincrónica con proveedores de almacenes de estados de sesión**

 Actualmente, ASP.NET permite el uso de métodos de devolución de tareas con proveedores de almacenes de estados de sesión, lo que permite que las aplicaciones ASP.NET aprovechen las ventajas de escalabilidad de la asincronía. Para admitir operaciones asincrónicas con proveedores de almacenes de estados de sesión, ASP.NET incluye una nueva interfaz, <xref:System.Web.SessionState.ISessionStateModule?displayProperty=nameWithType>, que se hereda de <xref:System.Web.IHttpModule> y permite a los desarrolladores implementar sus propios módulos de estados de sesión y proveedores de almacenes de sesión asincrónica. La interfaz se define de la siguiente manera:

```csharp
public interface ISessionStateModule : IHttpModule {
    void ReleaseSessionState(HttpContext context);
    Task ReleaseSessionStateAsync(HttpContext context);
}
```

```vb
Public Interface ISessionStateModule : Inherits IHttpModule
   Sub ReleaseSessionState(context As HttpContext)
   Function ReleaseSessionStateAsync(context As HttpContext) As Task
End Interface
```

 Además, la clase <xref:System.Web.SessionState.SessionStateUtility> incluye dos nuevos métodos, <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateReadOnly%2A> y <xref:System.Web.SessionState.SessionStateUtility.IsSessionStateRequired%2A>, que se pueden usar para admitir operaciones asincrónicas.

 **Compatibilidad asincrónica con proveedores de caché de resultados**

 A partir de .NET Framework 4.6.2, pueden usarse métodos de devolución de tarea con proveedores de caché de resultados para proporcionar las ventajas de escalabilidad de la asincronía.  Los proveedores que implementan estos métodos reducen el bloqueo de subprocesos en un servidor web y mejoran la escalabilidad de un servicio de ASP.NET.

 Se han agregado las API siguientes para ofrecer compatibilidad con proveedores de caché de resultados asincrónicos:

- La clase <xref:System.Web.Caching.OutputCacheProviderAsync?displayProperty=nameWithType>, que se hereda de <xref:System.Web.Caching.OutputCacheProvider?displayProperty=nameWithType> y permite a los desarrolladores implementar un proveedor de caché de resultados asincrónicos.

- La clase <xref:System.Web.Caching.OutputCacheUtility>, que proporciona métodos del asistente para configurar la caché de resultados.

- 18 métodos nuevos en la clase <xref:System.Web.HttpCachePolicy?displayProperty=nameWithType>. Entre estos se incluyen <xref:System.Web.HttpCachePolicy.GetCacheability%2A>, <xref:System.Web.HttpCachePolicy.GetCacheExtensions%2A>, <xref:System.Web.HttpCachePolicy.GetETag%2A>, <xref:System.Web.HttpCachePolicy.GetETagFromFileDependencies%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetNoStore%2A>, <xref:System.Web.HttpCachePolicy.GetNoTransforms%2A>, <xref:System.Web.HttpCachePolicy.GetOmitVaryStar%2A>, <xref:System.Web.HttpCachePolicy.GetProxyMaxAge%2A>, <xref:System.Web.HttpCachePolicy.GetRevalidation%2A>, <xref:System.Web.HttpCachePolicy.GetUtcLastModified%2A>, <xref:System.Web.HttpCachePolicy.GetVaryByCustom%2A>, <xref:System.Web.HttpCachePolicy.HasSlidingExpiration%2A> y <xref:System.Web.HttpCachePolicy.IsValidUntilExpires%2A>.

- 2 métodos nuevos en la clase <xref:System.Web.HttpCacheVaryByContentEncodings?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByContentEncodings.GetContentEncodings%2A> y <xref:System.Web.HttpCacheVaryByContentEncodings.SetContentEncodings%2A>.

- 2 métodos nuevos en la clase <xref:System.Web.HttpCacheVaryByHeaders?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByHeaders.GetHeaders%2A> y <xref:System.Web.HttpCacheVaryByHeaders.SetHeaders%2A>.

- 2 métodos nuevos en la clase <xref:System.Web.HttpCacheVaryByParams?displayProperty=nameWithType>: <xref:System.Web.HttpCacheVaryByParams.GetParams%2A> y <xref:System.Web.HttpCacheVaryByParams.SetParams%2A>.

- En la clase <xref:System.Web.Caching.AggregateCacheDependency?displayProperty=nameWithType>, el método <xref:System.Web.Caching.AggregateCacheDependency.GetFileDependencies%2A>.

- En la clase <xref:System.Web.Caching.CacheDependency>, el método <xref:System.Web.Caching.CacheDependency.GetFileDependencies%2A>.

<a name="Strings" />

### <a name="character-categories"></a>Categorías de caracteres

Los caracteres de .NET Framework 4.6.2 se clasifican según el [estándar Unicode, versión 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/). En .NET Framework 4.6 y .NET Framework 4.6.1, los caracteres están clasificados según las categorías de caracteres Unicode 6.3.

La compatibilidad con Unicode 8.0 está limitada a la clasificación de caracteres mediante la clase <xref:System.Globalization.CharUnicodeInfo> y a los tipos y los métodos que se basan en ella. Entre ellos se incluyen la clase <xref:System.Globalization.StringInfo>, el método sobrecargado <xref:System.Char.GetUnicodeCategory%2A?displayProperty=nameWithType> y las [clases de caracteres](../../standard/base-types/character-classes-in-regular-expressions.md) reconocidas por el motor de expresiones regulares de .NET Framework.  La comparación y la ordenación de caracteres y cadenas no se ven afectadas por este cambio y siguen dependiendo del sistema operativo subyacente o, en el caso de los sistemas Windows 7, de los datos de caracteres proporcionados por .NET Framework.

Para realizar cambios en las categorías de caracteres de Unicode 6.0 a Unicode 7.0, consulte la página sobre [el estándar Unicode, versión 7.0.0](https://www.unicode.org/versions/Unicode7.0.0/) en el sitio web de The Unicode Consortium. Para realizar cambios de caracteres de Unicode 7.0 a Unicode 8.0, consulte la página sobre [el estándar Unicode, versión 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/) en el sitio web de The Unicode Consortium.

<a name="Crypto462" />

### <a name="cryptography"></a>Criptografía

**Compatibilidad con certificados X509 que contienen DSA de FIPS 186-3**

.NET Framework 4.6.2 agrega compatibilidad con certificados X509 de DSA (algoritmo de firma digital) cuyas claves superan el límite de 1024 bits de FIPS 186-2.

Además de admitir los tamaños de clave más grandes de FIPS 186-3, .NET Framework 4.6.2 permite calcular firmas con la familia SHA-2 de algoritmos hash (SHA256, SHA384 y SHA512). La compatibilidad con FIPS 186-3 se proporciona mediante la nueva clase <xref:System.Security.Cryptography.DSACng?displayProperty=nameWithType>.

Para conservar los cambios recientes en la clase <xref:System.Security.Cryptography.RSA> de .NET Framework 4.6 y la clase <xref:System.Security.Cryptography.ECDsa> de .NET Framework 4.6.1, la clase base abstracta <xref:System.Security.Cryptography.DSA> de .NET Framework 4.6.2 tiene métodos adicionales que permiten que los autores de llamada usen esta funcionalidad sin conversión. Puede llamar al método de extensión <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPrivateKey%2A?displayProperty=nameWithType> para firmar los datos, como se muestra en el ejemplo siguiente.

```csharp
public static byte[] SignDataDsaSha384(byte[] data, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPrivateKey())
    {
        return dsa.SignData(data, HashAlgorithmName.SHA384);
    }
}
```

```vb
Public Shared Function SignDataDsaSha384(data As Byte(), cert As X509Certificate2) As Byte()
    Using DSA As DSA = cert.GetDSAPrivateKey()
        Return DSA.SignData(data, HashAlgorithmName.SHA384)
    End Using
End Function
```

También puede llamar al método de extensión <xref:System.Security.Cryptography.X509Certificates.DSACertificateExtensions.GetDSAPublicKey%2A?displayProperty=nameWithType> para comprobar los datos firmados, como se muestra en el ejemplo siguiente.

```csharp
public static bool VerifyDataDsaSha384(byte[] data, byte[] signature, X509Certificate2 cert)
{
    using (DSA dsa = cert.GetDSAPublicKey())
    {
        return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384);
    }
}
```

```vb
 Public Shared Function VerifyDataDsaSha384(data As Byte(), signature As Byte(), cert As X509Certificate2) As Boolean
    Using dsa As DSA = cert.GetDSAPublicKey()
        Return dsa.VerifyData(data, signature, HashAlgorithmName.SHA384)
    End Using
End Function
```

**Mayor claridad para las entradas en rutinas de derivación de claves ECDiffieHellman**

.NET Framework 3.5 incluía compatibilidad con el acuerdo de claves Diffie-Hellman de curva elíptica con tres rutinas diferentes de función de derivación de claves (KDF). Las entradas en las rutinas y las propias rutinas se configuraban mediante propiedades en el objeto <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Pero como no todas las rutinas leían todas las propiedades de entrada, esto podía provocar confusión al desarrollador.

Para solucionarlo en .NET Framework 4.6.2, se han agregado los tres métodos siguientes a la clase base <xref:System.Security.Cryptography.ECDiffieHellman> para manifestar con mayor claridad estas rutinas KDF y sus entradas:

|Método ECDiffieHellman|DESCRIPCIÓN|
|----------------------------|-----------------|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHash%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante la fórmula<br /><br /> HASH(secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HASH(secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado calculado del algoritmo de Diffie-Hellman de curva elíptica.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyFromHmac%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Security.Cryptography.HashAlgorithmName%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante la fórmula<br /><br /> HMAC(hmacKey, secretPrepend &#124;&#124; *x* &#124;&#124; secretAppend)<br /><br /> HMAC(hmacKey, secretPrepend OrElse *x* OrElse secretAppend)<br /><br /> donde *x* es el resultado calculado del algoritmo de Diffie-Hellman de curva elíptica.|
|<xref:System.Security.Cryptography.ECDiffieHellman.DeriveKeyTls%28System.Security.Cryptography.ECDiffieHellmanPublicKey%2CSystem.Byte%5B%5D%2CSystem.Byte%5B%5D%29>|Deriva el material de clave mediante el algoritmo de derivación de función pseudoaleatoria (PRF) de TLS.|

**Compatibilidad con el cifrado simétrico de clave persistente**

La biblioteca de criptografía (CNG) de Windows agrega compatibilidad para almacenar claves simétricas persistentes y para usar claves simétricas almacenadas en el hardware, y .NET Framework 4.6.2 hace posible que los desarrolladores usen esta característica.  Como el concepto de nombres de clave y proveedores de clave depende de la implementación, el uso de esta característica obliga a emplear el constructor de los tipos de la implementación concreta, en lugar del enfoque de fábrica preferido (por ejemplo, llamar a `Aes.Create`).

Existe compatibilidad con el cifrado simétrico de clave persistente para los algoritmos AES (<xref:System.Security.Cryptography.AesCng>) y 3DES (<xref:System.Security.Cryptography.TripleDESCng>). Por ejemplo:

```csharp
public static byte[] EncryptDataWithPersistedKey(byte[] data, byte[] iv)
{
    using (Aes aes = new AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider))
    {
        aes.IV = iv;

        // Using the zero-argument overload is required to make use of the persisted key
        using (ICryptoTransform encryptor = aes.CreateEncryptor())
        {
            if (!encryptor.CanTransformMultipleBlocks)
            {
                throw new InvalidOperationException("This is a sample, this case wasn’t handled...");
            }

            return encryptor.TransformFinalBlock(data, 0, data.Length);
        }
    }
}
```

```vb
Public Shared Function EncryptDataWithPersistedKey(data As Byte(), iv As Byte()) As Byte()
    Using Aes As Aes = New AesCng("AesDemoKey", CngProvider.MicrosoftSoftwareKeyStorageProvider)
        Aes.IV = iv

        ' Using the zero-argument overload Is required to make use of the persisted key
        Using encryptor As ICryptoTransform = Aes.CreateEncryptor()
            If Not encryptor.CanTransformMultipleBlocks Then
                Throw New InvalidOperationException("This is a sample, this case wasn’t handled...")
            End If
            Return encryptor.TransformFinalBlock(data, 0, data.Length)
        End Using
    End Using
End Function
```

**Compatibilidad con SignedXml para hash SHA-2**

.NET Framework 4.6.2 agrega compatibilidad con la clase <xref:System.Security.Cryptography.Xml.SignedXml> para los métodos de firma PKCS#1 RSA-SHA256, RSA-SHA384 y RSA-SHA512, y para los algoritmos de resumen de referencia SHA256, SHA384 y SHA512.

Todas las constantes URI se exponen en <xref:System.Security.Cryptography.Xml.SignedXml>:

|Campo SignedXml|Constante|
|---------------------|--------------|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA256Url>|"http://www.w3.org/2001/04/xmlenc#sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA256Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha256"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA384Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha384"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigSHA512Url>|"http://www.w3.org/2001/04/xmlenc#sha512"|
|<xref:System.Security.Cryptography.Xml.SignedXml.XmlDsigRSASHA512Url>|"http://www.w3.org/2001/04/xmldsig-more#rsa-sha512"|

 Todos los programas que hayan registrado un controlador <xref:System.Security.Cryptography.SignatureDescription> personalizado en <xref:System.Security.Cryptography.CryptoConfig> para agregar compatibilidad para estos algoritmos seguirán funcionando como antes, pero como ahora hay valores predeterminados de la plataforma, ya no es necesario el registro de <xref:System.Security.Cryptography.CryptoConfig>.

<a name="SQLClient" />

### <a name="sqlclient"></a>SqlClient

El proveedor de datos .NET Framework para SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>) incluye las siguientes características nuevas en .NET Framework 4.6.2:

**Agrupación de conexiones y tiempos de espera con bases de datos SQL de Azure**

Cuando se habilita la agrupación de conexiones y se produce un error de tiempo de espera u otro tipo de error de inicio de sesión, se almacena en caché una excepción que se produce en todos los intentos de conexión posteriores que se realicen en un plazo de entre 5 segundos y 1 minuto.  Para obtener más información, vea [Agrupación de conexiones en SQL Server (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).

Este comportamiento no es el deseable al conectarse a bases de datos SQL de Azure, ya que en los intentos de conexión se pueden producir errores transitorios que normalmente se recuperan rápidamente. Para optimizar la experiencia de reintento de conexión, se elimina el comportamiento del período de bloqueo del grupo de conexiones cuando se produce un error en las conexiones a bases de datos SQL de Azure.

La adición de la nueva palabra clave `PoolBlockingPeriod` permite seleccionar el período de bloqueo más adecuado para la aplicación. Estos valores incluyen:

<xref:System.Data.SqlClient.PoolBlockingPeriod.Auto>

El período de bloqueo del grupo de conexiones para una aplicación que se conecta a una base de datos SQL de Azure está deshabilitado, mientras que el período de bloqueo del grupo de conexiones para una aplicación que se conecta a cualquier otra instancia de SQL Server está habilitado. Este es el valor predeterminado. Si el nombre del punto de conexión del servidor termina de alguna de las siguientes maneras, se considera que se trata de bases de datos SQL de Azure:

- .database.windows.net

- .database.chinacloudapi.cn

- .database.usgovcloudapi.net

- .database.cloudapi.de

<xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>

El período de bloqueo del grupo de conexión siempre está habilitado.

<xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock>

El período de bloqueo del grupo de conexión siempre está deshabilitado.

**Mejoras para Always Encrypted**

SQLClient presenta dos mejoras para Always Encrypted:

- Para mejorar el rendimiento de las consultas con parámetros en las columnas de una base de datos cifrada, ahora se almacenan en caché los metadatos de cifrado de los parámetros de consulta. Con la propiedad <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionQueryMetadataCacheEnabled%2A?displayProperty=nameWithType> establecida en `true` (que es el valor predeterminado), si se llama varias veces a la misma consulta, el cliente recupera los metadatos de parámetros del servidor una sola vez.

- Ahora, las entradas de clave de cifrado de columna incluidas en la caché de claves se expulsan después de un intervalo de tiempo configurable, que se establece mediante la propiedad <xref:System.Data.SqlClient.SqlConnection.ColumnEncryptionKeyCacheTtl%2A?displayProperty=nameWithType>.

<a name="WCF" />

### <a name="windows-communication-foundation"></a>Windows Communication Foundation

En .NET Framework 4.6.2, Windows Communication Foundation se ha mejorado en las áreas siguientes:

**Compatibilidad con la seguridad de transporte de WCF para los certificados almacenados con CNG**

La seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows. En .NET Framework 4.6.2, esta compatibilidad está limitada al uso de certificados con una clave pública que tenga un exponente con una longitud no superior a 32 bits. Cuando una aplicación tiene .NET Framework 4.6.2 como destino, esta característica está activada de forma predeterminada.

En el caso de las aplicaciones que tengan como destino .NET Framework 4.6.1 y versiones anteriores, pero se ejecuten en .NET Framework 4.6.2, esta característica se puede activar agregando la siguiente línea a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config o web.config.

```xml
<AppContextSwitchOverrides
    value="Switch.System.ServiceModel.DisableCngCertificates=false"
/>
```

Esto también se puede hacer mediante programación con código similar al siguiente:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificates";
AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

**Mejor compatibilidad para varias reglas de ajuste al horario de verano mediante la clase DataContractJsonSerializer**

Los clientes pueden usar una opción de configuración de la aplicación para determinar si la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> admite varias reglas de ajuste para una sola zona horaria. Esta característica es opcional. Para habilitarla, agregue la siguiente opción de configuración al archivo app.config:

```xml
<runtime>
     <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseTimeZoneInfo=false" />
</runtime>
```

Cuando se habilita esta característica, un objeto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> usa el tipo <xref:System.TimeZoneInfo> en lugar del tipo <xref:System.TimeZone> para deserializar los datos de fecha y hora. <xref:System.TimeZoneInfo> admite varias reglas de ajuste, lo que permite trabajar con datos históricos de zona horaria, mientras que <xref:System.TimeZone> no las admite.

Para obtener más información sobre la estructura <xref:System.TimeZoneInfo> y los ajustes de zona horaria, consulte [Información general sobre zonas horarias](../../standard/datetime/time-zone-overview.md).

**Mejor coincidencia de NetNamedPipeBinding**

WCF tiene una nueva opción de la aplicación que se puede establecer en las aplicaciones cliente para garantizar que siempre se conecten al servicio que escucha en el URI que mejor coincida con el que solicitan. Con esta opción de la aplicación establecida en `false` (valor predeterminado), es posible que los clientes que usan <xref:System.ServiceModel.NetNamedPipeBinding> intenten conectarse a un servicio que escucha en un URI que es una subcadena del URI solicitado.

Por ejemplo, un cliente intenta conectarse a un servicio que escucha en `net.pipe://localhost/Service1`, pero un servicio diferente en ese equipo que se ejecuta con privilegios de administrador escucha en `net.pipe://localhost`. Con esta opción de la aplicación establecida en `false`, el cliente intentará conectarse al servicio incorrecto. Después de establecer la opción de la aplicación en `true`, el cliente siempre se conectará al mejor servicio.

> [!NOTE]
> Los clientes que usan <xref:System.ServiceModel.NetNamedPipeBinding> encuentran servicios basados en la dirección base del servicio (si existe) en lugar de la dirección del punto de conexión completo. Para garantizar que esta opción siempre funcione, el servicio debe usar una dirección base única.

Para habilitar este cambio, agregue la siguiente opción de la aplicación al archivo App.config o Web.config de la aplicación cliente:

```xml
<configuration>
    <appSettings>
        <add key="wcf:useBestMatchNamedPipeUri" value="true" />
    </appSettings>
</configuration>
```

**SSL 3.0 no es el protocolo predeterminado**

Al usar NetTcp con seguridad de transporte y un tipo de credencial de certificado, SSL 3.0 ya no es el protocolo predeterminado para negociar una conexión segura. En la mayoría de los casos, esto no debería afectar a las aplicaciones existentes, porque TLS 1.0 está incluido en la lista de protocolos para NetTcp. Todos los clientes deberían poder negociar una conexión usando como mínimo TLS 1.0. Si se requiere Ssl3, use uno de los siguientes mecanismos de configuración para agregarlo a la lista de protocolos negociados.

- La propiedad <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=nameWithType>

- La propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType>

- La sección [\<transport>](../configure-apps/file-schema/wcf/transport-of-nettcpbinding.md) de la sección [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)

- La sección [\<sslStreamSecurity>](../configure-apps/file-schema/wcf/sslstreamsecurity.md) de la sección [\<customBinding>](../configure-apps/file-schema/wcf/custombinding.md)

<a name="WPF462" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

En .NET Framework 4.6.2, Windows Presentation Foundation se ha mejorado en las áreas siguientes:

**Ordenación de grupos**

Ahora, una aplicación que use un objeto <xref:System.Windows.Data.CollectionView> para agrupar los datos puede declarar explícitamente cómo ordenar los grupos. La ordenación explícita resuelve el problema de la ordenación no intuitiva que se produce cuando una aplicación agrega o elimina grupos dinámicamente, o cuando cambia el valor de las propiedades de elementos implicadas en la agrupación. También puede mejorar el rendimiento del proceso de creación de grupos, ya que mueve las comparaciones de las propiedades de agrupación de la ordenación de la colección completa a la ordenación de los grupos.

Para admitir la ordenación de grupos, las nuevas propiedades <xref:System.ComponentModel.GroupDescription.SortDescriptions%2A?displayProperty=nameWithType> y <xref:System.ComponentModel.GroupDescription.CustomSort%2A?displayProperty=nameWithType> describen cómo ordenar la colección de grupos generada por el objeto <xref:System.ComponentModel.GroupDescription>. Esto es análogo a la forma en que las propiedades <xref:System.Windows.Data.ListCollectionView> con el mismo nombre describen cómo se ordenan los elementos de datos.

Dos nuevas propiedades estáticas de la clase <xref:System.Windows.Data.PropertyGroupDescription>, <xref:System.Windows.Data.PropertyGroupDescription.CompareNameAscending%2A> y <xref:System.Windows.Data.PropertyGroupDescription.CompareNameDescending%2A>, se pueden usar para los casos más comunes.

Por ejemplo, el siguiente código XAML agrupa los datos por edad, ordena los grupos de edad en orden ascendente y agrupa los elementos de cada grupo de edad por apellido.

```xaml
<GroupDescriptions>
     <PropertyGroupDescription
         PropertyName="Age"
         CustomSort=
              "{x:Static PropertyGroupDescription.CompareNamesAscending}"/>
     </PropertyGroupDescription>
</GroupDescriptions>

<SortDescriptions>
     <SortDescription PropertyName="LastName"/>
</SortDescriptions>
```

**Compatibilidad con teclado en pantalla**

La compatibilidad con teclado en pantalla permite el seguimiento del foco en aplicaciones WPF, ya que invoca y descarta automáticamente el nuevo teclado en pantalla de Windows 10 cuando un control que acepta entrada de texto recibe la entrada táctil.

En versiones anteriores de .NET Framework, las aplicaciones WPF no pueden optar por el seguimiento del foco sin deshabilitar la compatibilidad con lápiz o movimiento táctil en WPF.  Como resultado, las aplicaciones WPF deben elegir entre compatibilidad táctil completa en WPF o basarse en la promoción del mouse de Windows.

**PPP por monitor**

Para admitir la reciente proliferación de entornos con valores altos o híbridos de PPP para las aplicaciones WPF, WPF en .NET Framework 4.6.2 habilita el reconocimiento de monitor. Consulte [los ejemplos y la guía para desarrolladores](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI) en GitHub para obtener más información sobre cómo activar el reconocimiento de PPP por monitor en la aplicación WPF.

En versiones anteriores de .NET Framework, las aplicaciones WPF tienen habilitado el reconocimiento de PPP del sistema. En otras palabras, el sistema operativo escala la interfaz de usuario de la aplicación según corresponda, en función del valor de PPP del monitor en el que se representa la aplicación.

Para aplicaciones que se ejecutan en .NET Framework 4.6.2, puede deshabilitar los cambios de PPP por monitor en las aplicaciones WPF. Para ello, agregue una instrucción de configuración en la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación de la siguiente manera:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Windows.DoNotScaleForDpiChanges=false"/>
</runtime>
```

<a name="WF462" />

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

En .NET Framework 4.6.2, Windows Workflow Foundation se ha mejorado en las áreas siguientes:

**Compatibilidad con expresiones de C# e IntelliSense en el Diseñador de WF rehospedado**

A partir de .NET Framework 4.5, WF admite expresiones de C# en el diseñador de Visual Studio y en los flujos de trabajo de código. El Diseñador de flujo de trabajo rehospedado es una característica clave de WF que permite que el Diseñador de flujo de trabajo esté en una aplicación fuera de Visual Studio (por ejemplo, en WPF).  Windows Workflow Foundation permite admitir expresiones de C# e IntelliSense en el Diseñador de flujo de trabajo rehospedado. Para obtener más información, consulte el [blog de Windows Workflow Foundation](https://blogs.msdn.microsoft.com/workflowteam/2016/07/20/building-c-expressions-support-and-intellisense-in-the-rehosted-workflow-designer/).

`Availability of IntelliSense when a customer rebuilds a workflow project from Visual Studio` En las versiones de .NET Framework anteriores a .NET Framework 4.6.2, IntelliSense del Diseñador de WF se interrumpe cuando un cliente vuelve a compilar un proyecto de flujo de trabajo desde Visual Studio. Aunque la compilación del proyecto es correcta, los tipos de flujo de trabajo no se encuentran en el diseñador y en la ventana **Lista de errores** aparecen advertencias de IntelliSense que indican los tipos de flujo de trabajo que faltan. .NET Framework 4.6.2 soluciona este problema y hace que IntelliSense esté disponible.

**Las aplicaciones V1 de flujo de trabajo con seguimiento del flujo de trabajo ahora se ejecutan en modo FIPS**

Los equipos que tienen habilitado el modo de cumplimiento de FIPS ahora pueden ejecutar correctamente una aplicación de versión 1 de flujo de trabajo con el seguimiento del flujo de trabajo habilitado. Para habilitar este escenario, debe realizar el cambio siguiente en el archivo app.config:

```xml
<add key="microsoft:WorkflowRuntime:FIPSRequired" value="true" />
```

Si este escenario no está habilitado, al ejecutar la aplicación se sigue generando una excepción con el mensaje "Esta implementación no forma parte de los algoritmos criptográficos validados por Windows Platform FIPS".

**Mejoras en el flujo de trabajo al usar la actualización dinámica con el Diseñador de flujo de trabajo de Visual Studio**

El Diseñador de flujo de trabajo, el Diseñador de actividad de diagrama de flujo y otros diseñadores de actividad de flujo de trabajo ahora cargan y muestran correctamente los flujos de trabajo que se han guardado después de llamar al método <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>. En versiones de .NET Framework anteriores a .NET Framework 4.6.2, la carga de un archivo XAML en Visual Studio para un flujo de trabajo guardado después de llamar a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> puede producir los problemas siguientes:

- El Diseñador de flujo de trabajo no se puede cargar el archivo XAML correctamente (cuando <xref:System.Activities.Presentation.ViewState.ViewStateData.Id%2A?displayProperty=nameWithType> se encuentra al final de la línea).

- El Diseñador de actividad de diagrama de flujo u otros diseñadores de actividad de flujo de trabajo pueden mostrar todos los objetos en sus ubicaciones predeterminadas en lugar de los valores de la propiedad adjunta.

<a name="clickonce-1" />

### <a name="clickonce"></a>ClickOnce

Se ha actualizado ClickOnce para que admita TLS 1.1 y TLS 1.2 además del protocolo 1.0, que ya se admite. ClickOnce detecta automáticamente qué protocolo se requiere; no es necesario realizar ningún paso adicional en la aplicación ClickOnce para habilitar la compatibilidad con TLS 1.1 y 1.2.

<a name="UWPConvert" />

### <a name="converting-windows-forms-and-wpf-apps-to--uwp-apps"></a>Conversión de aplicaciones de Windows Forms y WPF a aplicaciones de UWP

Windows ahora ofrece funciones para llevar aplicaciones existentes de escritorio de Windows, incluidas aplicaciones de Windows Forms y WPF, a la Plataforma universal de Windows (UWP). Esta tecnología actúa como un puente, ya que permite migrar gradualmente su base de código existente a UWP, lo que lleva su aplicación a todos los dispositivos Windows 10.

Las aplicaciones de escritorio convertidas obtienen una identidad de aplicación similar a la identidad de aplicación de las aplicaciones de UWP, lo que hace que las API de UWP sean accesibles para habilitar características como iconos dinámicos y notificaciones. La aplicación sigue comportándose como antes y se ejecuta como una aplicación de plena confianza. Una vez convertida la aplicación, se puede agregar un proceso de contenedor de la aplicación al proceso de plena confianza existente para agregar una interfaz de usuario adaptable. Cuando todas las funciones se hayan movido al proceso de contenedor de la aplicación, se puede quitar el proceso de plena confianza y la nueva aplicación de UWP estará disponible para todos los dispositivos Windows 10.

<a name="Debug462" />

### <a name="debugging-improvements"></a>Mejoras en la depuración

La *API de depuración no administrada* se ha mejorado en .NET Framework 4.6.2 para que realice análisis adicionales cuando se produzca una excepción <xref:System.NullReferenceException>, de modo que sea posible determinar qué variable de una sola línea de código fuente es `null`.   Para admitir este escenario, se han agregado las API siguientes a la API de depuración no administrada.

- Las interfaces [ICorDebugCode4](../unmanaged-api/debugging/icordebugcode4-interface.md), [ICorDebugVariableHome](../unmanaged-api/debugging/icordebugvariablehome-interface.md) e [ICorDebugVariableHomeEnum](../unmanaged-api/debugging/icordebugvariablehomeenum-interface.md), que exponen las ubicaciones nativas de las variables administradas. Esto permite a los depuradores realizar un análisis de flujo de código cuando se produce una excepción <xref:System.NullReferenceException> y trabajar hacia atrás para determinar la variable administrada que se corresponde con la ubicación nativa que era `null`.

- El método [ICorDebugType2::GetTypeID](../unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) proporciona una asignación para ICorDebugType a [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md), lo que permite al depurador obtener un valor [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) sin una instancia de ICorDebugType. Después, las API existentes en [COR_TYPEID](../unmanaged-api/debugging/cor-typeid-structure.md) pueden usarse para determinar el diseño de clase del tipo.

<a name="v461" />

## <a name="whats-new-in-net-framework-461"></a>Novedades de .NET Framework 4.6.1

.NET Framework 4.6.1 incluye nuevas características en las áreas siguientes:

- [Criptografía](#Crypto)

- [ADO.NET](#ADO.NET461)

- [Windows Presentation Foundation (WPF)](#WPF461)

- [Windows Workflow Foundation](#WWF461)

- [Generación de perfiles](#Profile461)

- [NGen](#NGEN461)

Para más información sobre .NET Framework 4.6.1, consulte los temas siguientes:

- [Lista de cambios de .NET Framework 4.6.1](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-changes.md)

- [Compatibilidad de aplicaciones en 4.6.1](../migration-guide/application-compatibility.md)

- [Diferencia de la API de .NET Framework](https://github.com/Microsoft/dotnet/blob/master/releases/net461/dotnet461-api-changes.md) (en GitHub)

<a name="Crypto" />

### <a name="cryptography-support-for-x509-certificates-containing-ecdsa"></a>Criptografía: Compatibilidad con certificados X509 que contienen ECDSA

.NET Framework 4.6 agregó compatibilidad con RSACng para certificados X509. .NET Framework 4.6.1 agrega compatibilidad para certificados X509 ECDSA (Elliptic Curve Digital Signature Algorithm).

ECDSA ofrece un mejor rendimiento y es un algoritmo de cifrado más seguro que RSA, lo que lo convierte en una excelente elección cuando están en juego la escalabilidad y el rendimiento de la seguridad de capa de transporte (TLS). La implementación de .NET Framework encapsula las llamadas en funciones de Windows existentes.

El ejemplo de código siguiente muestra lo fácil que es generar una firma para una secuencia de bytes mediante la nueva compatibilidad para certificados X509 de ECDSA incluidos en .NET Framework 4.6.1.

[!code-csharp[whatsnew.461.crypto#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#1)]
[!code-vb[whatsnew.461.crypto#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code461.vb#1)]

Esto ofrece un marcado contraste con el código necesario para generar una firma en .NET Framework 4.6.

[!code-csharp[whatsnew.461.crypto#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.461.crypto/cs/Code46.cs#2)]
[!code-vb[whatsnew.461.crypto#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.461.crypto/vb/Code46.vb#2)]

<a name="ADO.NET461" />

### <a name="adonet"></a>ADO.NET

Se agregó lo siguiente a ADO.NET:

**Compatibilidad con Always Encrypted para claves protegidas por hardware**

ADO.NET ahora permite almacenar claves maestras de la columna Always Encrypted de forma nativa en módulos de seguridad de hardware (HSM). Con esta compatibilidad, los clientes pueden aprovechar las claves asimétricas almacenadas en HSM sin tener que escribir proveedores de almacenes de clave maestra de la columna personalizada ni registrarlos en las aplicaciones.

Los clientes necesitan instalar el proveedor CSP proporcionado por el fabricante HSM o los proveedores de almacén de claves de CNG en los servidores de aplicación o en los equipos cliente para tener acceso a los datos que Always Encrypted ha protegido con las claves maestras de columna almacenadas en un HSM.

**Comportamiento de la conexión de <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> mejorado para AlwaysOn**

Ahora SqlClient proporciona de forma automática conexiones más rápidas a un grupo de disponibilidad AlwaysOn (AG). Detecta de forma transparente si la aplicación se conecta a un grupo de disponibilidad AlwaysOn (AG) en una subred diferente y detecta rápidamente el servidor activo actual y proporciona una conexión al servidor. Antes de esta versión, una aplicación tenía que establecer la cadena de conexión para incluir `"MultisubnetFailover=true"` e indicar que se conecta a un grupo de disponibilidad AlwaysOn. Sin establecer la palabra clave de conexión en `true`, una aplicación podría experimentar un tiempo de espera mientras se conecta a un grupo de disponibilidad AlwaysOn. Con esta versión, la aplicación ya *no* necesita establecer <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A> en `true`. Para obtener más información sobre la compatibilidad de SqlClient con grupos de disponibilidad AlwaysOn, vea [Compatibilidad de SqlClient para alta disponibilidad y recuperación ante desastres](../data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md).

<a name="WPF461" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

Windows Presentation Foundation incluye una serie de mejoras y cambios.

**Rendimiento mejorado**

Se corrigió el retraso de activación de eventos de función táctil en .NET Framework 4.6.1. Además, al escribir un control <xref:System.Windows.Controls.RichTextBox> ya no se bloquea el subproceso de representación durante la entrada rápida.

**Mejoras en el corrector ortográfico**

El corrector ortográfico en WPF se ha actualizado en Windows 8.1 y en versiones posteriores para aprovechar la compatibilidad del sistema operativo con la corrección ortográfica de idiomas adicionales.  No hay ningún cambio en la funcionalidad en las versiones de Windows anteriores a Windows 8.1.

Como en versiones anteriores de .NET Framework, el idioma de un control <xref:System.Windows.Controls.TextBox> o un bloque <xref:System.Windows.Controls.RichTextBox> se detecta mediante la búsqueda de información en el orden siguiente:

- `xml:lang`, si está presente.

- Idioma de entrada actual.

- Referencia cultural del subproceso actual.

Para obtener más información sobre la compatibilidad de idioma en WPF, vea la [entrada de blog de WPF sobre las características de .NET Framework 4.6.1](https://devblogs.microsoft.com/wpf/wpf-in-net-4-6-1/).

**Compatibilidad adicional con diccionarios personalizados por el usuario**

En .NET Framework 4.6.1, WPF reconoce los diccionarios personalizados que se registran de forma global. Esta funcionalidad está disponible además de la posibilidad de registrarlos por control.

En versiones anteriores de WPF, los diccionarios personalizados no reconocían palabras excluidas ni listas de autocorrección. Ahora se admiten en Windows 8.1 y Windows 10 mediante el uso de archivos que se pueden colocar en el directorio `%AppData%\Microsoft\Spelling\<language tag>`.  Las reglas siguientes se aplican a estos archivos:

- Los archivos deben tener las extensiones .dic (para palabras agregadas), .exc (para las palabras excluidas) o .acl (para la autocorrección).

- Los archivos deben ser texto sin formato UTF-16 LE que comienza con la marca BOM (Byte Order Mark).

- Cada línea debe constar de una palabra (en las listas de palabras agregadas y excluidas) o un par de autocorrección con las palabras separadas por una barra vertical ("&#124;") (en la lista de palabras de Autocorrección).

- Estos archivos se consideran de solo lectura y el sistema no los modifica.

> [!NOTE]
> Estos nuevos formatos de archivos no son compatibles directamente con las API de corrección ortográfica de WPF, y los diccionarios personalizados proporcionados a WPF en las aplicaciones deben continuar usando los archivos .lex.

**Muestras**

En el repositorio de GitHub [Microsoft/WPF-Samples](https://github.com/Microsoft/WPF-Samples) encontrará una serie de muestras de WPF. Ayúdenos a mejorar nuestros ejemplos enviando una solicitud de extracción o abriendo un [problema de GitHub](https://github.com/Microsoft/WPF-Samples/issues).

**Extensiones de DirectX**

WPF incluye un [paquete NuGet](https://www.nuget.org/packages/Microsoft.Wpf.Interop.DirectX-x86/) en el que se proporcionan nuevas implementaciones de <xref:System.Windows.Interop.D3DImage> que facilitan la tarea de interoperar con contenido DX10 y Dx11. El código para este paquete se ha abierto y está disponible [en GitHub](https://github.com/Microsoft/WPFDXInterop).

<a name="WWF461" />

### <a name="windows-workflow-foundation-transactions"></a>Windows Workflow Foundation: Transacciones

El método <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> ahora puede usar un administrador de transacciones distribuidas que no sea MSDTC para promocionar la transacción. Para ello, especifique un identificador GUID de promoción de transacción a la nueva sobrecarga <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType>. Si esta operación se realiza correctamente, hay limitaciones de las capacidades de la transacción. Una vez que se activa un promotor de transacciones que no sea MSDTC, los métodos siguientes inician una <xref:System.Transactions.TransactionPromotionException> porque estos métodos requieren promoción a MSDTC:

- <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetDtcTransaction%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetExportCookie%2A?displayProperty=nameWithType>

- <xref:System.Transactions.TransactionInterop.GetTransmitterPropagationToken%2A?displayProperty=nameWithType>

Una vez que se activa un promotor de transacciones que no sea MSDTC, debe usarse para futuras inscripciones duraderas a través de los protocolos que define. El <xref:System.Guid> del promotor de transacción puede obtenerse con la propiedad <xref:System.Transactions.Transaction.PromoterType%2A>. Cuando se promueve la transacción, el promotor de transacciones proporciona una matriz <xref:System.Byte> que representa el token promocionado. Una aplicación puede obtener el token promocionado de una transacción promocionada que no sea de MSDTC con el método <xref:System.Transactions.Transaction.GetPromotedToken%2A>.

Los usuarios de la nueva sobrecarga <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%28System.Transactions.IPromotableSinglePhaseNotification%2CSystem.Guid%29?displayProperty=nameWithType> deben seguir una secuencia de llamadas específica para completar correctamente la operación de promoción. Estas reglas están registradas en la documentación del método.

<a name="Profile461" />

### <a name="profiling"></a>Generación de perfiles

La API de generación de perfiles no administrada se ha mejorado de la siguiente forma:

- Se ha mejorado la compatibilidad para acceder a archivos PDB en la interfaz [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md).

  En ASP.NET Core, cada vez es más común que los ensamblados se compilen en memoria mediante Roslyn. Para desarrolladores que crean herramientas de generación de perfiles, esto significa que los PDB serializados históricamente en disco ya no estén presentes. Las herramientas del generador de perfiles suelen usar archivos PDB para asignar código a las líneas de código fuente para tareas como el análisis de rendimiento de línea por línea o de cobertura de código. La interfaz [ICorProfilerInfo7](../unmanaged-api/profiling/icorprofilerinfo7-interface.md) ahora incluye dos nuevos métodos, [ICorProfilerInfo7::GetInMemorySymbolsLength](../unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md) e [ICorProfilerInfo7::ReadInMemorySymbols](../unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md), para proporcionar estas herramientas del generador de perfiles con acceso a los datos de PDB en memoria. Usando las nuevas API, un generador de perfiles puede obtener el contenido de un PDB en memoria como una matriz de bytes y luego procesarlo o serializarlo en el disco.

- Se ha mejorado la instrumentación con la interfaz ICorProfiler.

  Los generadores de perfiles que utilizan la funcionalidad ReJit de la API `ICorProfiler` para la instrumentación dinámica ahora pueden modificar algunos metadatos. Anteriormente dichas herramientas podían instrumentar IL en cualquier momento, pero los metadatos solo se podían modificar en tiempo de carga del módulo. Dado que IL hace referencia a los metadatos, esto limita los tipos de instrumentación que se podían hacer. Hemos solucionado algunos de esos límites agregando el método [ICorProfilerInfo7::ApplyMetaData](../unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md) para admitir un subconjunto de ediciones de metadatos después de que el módulo se cargue, en particular agregando nuevos registros `AssemblyRef`, `TypeRef`, `TypeSpec`, `MemberRef`, `MemberSpec` y `UserString`. Este cambio permite una mayor variedad de instrumentación sobre la marcha.

<a name="NGEN461" />

### <a name="native-image-generator-ngen-pdbs"></a>PDB del generador de imágenes nativas (NGEN)

El seguimiento de eventos de varios equipos permite a los clientes generar perfiles de un programa en la máquina A y mirar los datos de generación de perfiles con la asignación de la línea de origen en la máquina B. Al usar versiones anteriores de .NET Framework, el usuario copiaría todos los módulos y las imágenes nativas de la máquina con generación de perfiles a la máquina de análisis que contiene el archivo PDB de IL para crear la asignación de código fuente a nativo. Aunque este proceso puede funcionar bien cuando los archivos son relativamente pequeños, como en aplicaciones de teléfono, los archivos pueden ser muy grandes en sistemas de escritorio y requieren mucho tiempo para copiarse.

Con los archivos PDB de NGen, NGen puede crear un archivo PDB que contenga la asignación de IL a nativo sin una dependencia del archivo PDB de IL. En nuestro escenario de seguimiento de eventos de varias máquinas, todo lo que se necesita es copiar la imagen nativa PDB generada por la máquina A a la máquina B y utilizar [Depurar API de acceso de interfaz](/visualstudio/debugger/debug-interface-access/debug-interface-access-sdk-reference) para leer la asignación de origen al IL del archivo PDB de IL y la asignación del IL a nativo del archivo PDB de imágenes nativas. La combinación de ambas asignaciones permite asignar código fuente a nativo. Dado que el PDB de imagen nativa es mucho menor que todos los módulos y las imágenes nativas, el proceso de copiar de la máquina A a la máquina B es mucho más rápido.

<a name="v46" />

## <a name="whats-new-in-net-2015"></a>Novedades de .NET 2015

.NET 2015 presenta .NET Framework 4.6 y .NET Core. Algunas características nuevas se aplican a ambos, y otras son específicas de .NET Framework 4.6 o .NET Core.

- **ASP.NET Core**

  .NET Framework 2015 incluye ASP.NET Core, que es una implementación .NET eficiente para la compilación de aplicaciones modernas basadas en la nube. ASP.NET Core es modular, por lo que puede incluir solo aquellas características que se necesitan en la aplicación. Puede hospedarse en IIS o autohospedarse en un proceso personalizado y se pueden ejecutar aplicaciones con diferentes versiones de .NET Framework en el mismo servidor. Incluye un nuevo sistema de configuración de entorno que está diseñado para la implementación de la nube.

  MVC, Web API y Web Pages están unificados en un marco único llamado MVC 6. Las aplicaciones de ASP.NET Core se compilan con las herramientas de Visual Studio 2015 o versiones posteriores. Las aplicaciones existentes funcionarán en la nueva versión de .NET Framework; sin embargo, para compilar una aplicación que use MVC 6 o SignalR 3, debe usar el sistema de proyectos de Visual Studio 2015 o versiones posteriores.

  Para obtener información, vea [ASP.NET Core](/aspnet/core/).

- **Actualizaciones de ASP.NET**

  - **API basada en tareas para el vaciado de respuestas asincrónicas**

    Ahora, ASP.NET proporciona una API sencilla basada en tareas para el vaciado de respuestas asincrónicas, <xref:System.Web.HttpResponse.FlushAsync%2A?displayProperty=nameWithType>, que permite vaciar las respuestas de forma asincrónica con el soporte `async/await` de su lenguaje.

  - **El enlace de modelos admite los métodos de devolución de tareas**

    ASP.NET agregó en .NET Framework 4.5 la característica Enlace de modelos, que habilita un enfoque extensible y centrado en el código en las operaciones de datos basadas en CRUD de las páginas de formularios Web Forms y los controles de usuario. Ahora el sistema Enlace de modelos es compatible con los métodos de enlace de modelos que devuelven <xref:System.Threading.Tasks.Task>. Esta característica permite que los desarrolladores de formularios Web Forms aprovechen las ventajas que presenta la escalabilidad de la asincronía con la facilidad del sistema de enlace de datos al usar las versiones más recientes de ORM, incluido Entity Framework.

    El enlace de modelos asincrónicos se controla con la opción de configuración `aspnet:EnableAsyncModelBinding`.

    ```xml
    <appSettings>
        <add key=" aspnet:EnableAsyncModelBinding" value="true|false" />
    </appSettings>
    ```

    En las aplicaciones que tienen como destino .NET Framework 4.6, el valor predeterminado es `true`. En las aplicaciones que se ejecutan en .NET Framework 4.6 y que tienen como destino una versión anterior de .NET Framework, el valor predeterminado es `false`. Se puede habilitar estableciendo la opción de configuración en `true`.

  - **Compatibilidad con HTTP/2 (Windows 10)**

    [HTTP/2](https://www.wikipedia.org/wiki/HTTP/2) es una nueva versión del protocolo HTTP que proporciona un uso mucho mejor de la conexión (menos recorridos de ida y vuelta entre el cliente y el servidor), lo que permite una latencia más baja para los usuarios al cargar páginas web.  Las páginas web (no de servicios) aprovechan HTTP/2 al máximo, porque el protocolo se optimizó para la solicitud de varios artefactos como parte de una sola experiencia. La compatibilidad con HTTP/2 se agregó a ASP.NET en .NET Framework 4.6. Como la funcionalidad de red existe en varios niveles, se necesitaban nuevas características en Windows, IIS y ASP.NET para habilitar HTTP/2. Debe ejecutar Windows 10 para usar HTTP/2 con ASP.NET.

    También se admite HTTP/2, y está activado de forma predeterminada en las aplicaciones de la Plataforma universal de Windows (UWP) de Windows 10 que usan la API <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>.

    Para proporcionar una forma de usar la característica [PUSH_PROMISE](https://http2.github.io/http2-spec/#PUSH_PROMISE) en aplicaciones de ASP.NET, se ha agregado un método nuevo con dos sobrecargas, <xref:System.Web.HttpResponse.PushPromise%28System.String%29> y <xref:System.Web.HttpResponse.PushPromise%28System.String%2CSystem.String%2CSystem.Collections.Specialized.NameValueCollection%29>, a la clase <xref:System.Web.HttpResponse>.

    > [!NOTE]
    > Mientras que ASP.NET Core admite HTTP/2, la compatibilidad con la característica PUSH PROMISE aún no se ha agregado.

    El explorador y el servidor web (IIS en Windows) hacen todo el trabajo. No tiene que hacer el trabajo más farragoso para los usuarios.

    La mayoría de [los principales navegadores admiten HTTP/2](https://www.wikipedia.org/wiki/HTTP/2), por lo que probablemente los usuarios se beneficiarán de la compatibilidad con HTTP/2 si el servidor lo admite.

  - **Compatibilidad con el Protocolo de enlace de tokens**

    Google y Microsoft colaboraron en un nuevo sistema de autenticación llamado [Protocolo de enlace de tokens](https://github.com/TokenBinding/Internet-Drafts). La premisa es que los tokens de autenticación (en la memoria caché del navegador) pueden ser robados y usados por delincuentes para acceder a recursos seguros (por ejemplo, su cuenta bancaria) sin necesidad de contraseña ni de otra información privilegiada. El nuevo protocolo tiene como objetivo mitigar este problema.

    El Protocolo de enlace de tokens se implementará en Windows 10 como una característica del explorador. Las aplicaciones de ASP.NET participarán en el protocolo para validar la legitimidad de los tokens de autenticación. Las implementaciones de cliente y de servidor establecen la protección de extremo a extremo especificada por el protocolo.

  - **Algoritmos hash de cadena aleatoria**

    En .NET Framework 4.5, se introdujo un [algoritmo hash de cadena aleatorio](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md). pero no era compatible con ASP.NET porque algunas características de ASP.NET dependían de un código hash estable. En .NET Framework 4.6 ya se admiten los algoritmos hash de cadena aleatoria. Para habilitar esta característica, use la opción de configuración `aspnet:UseRandomizedStringHashAlgorithm`.

    ```xml
    <appSettings>
        <add key="aspnet:UseRandomizedStringHashAlgorithm" value="true|false" />
    </appSettings>
    ```

- **ADO.NET**

  ADO .NET ahora es compatible con la característica Always Encrypted disponible en SQL Server 2016 Community Technology Preview 2 (CTP2). Con Always Encrypted, SQL Server puede realizar operaciones en los datos cifrados y, lo mejor de todo, es que la clave de cifrado reside, junto con la aplicación, en el entorno de confianza del cliente y no en el servidor. Always Encrypted protege los datos del cliente para que los administradores de bases de datos no tengan acceso a los datos de texto sin formato. El cifrado y descifrado de datos ocurre de forma transparente en el nivel de controlador, lo que minimiza los cambios que deben realizarse en las aplicaciones existentes. Para obtener más información, vea [Always Encrypted (motor de base de datos)](/sql/relational-databases/security/encryption/always-encrypted-database-engine) y [Always Encrypted (desarrollo de cliente)](/sql/relational-databases/security/encryption/always-encrypted-client-development).

- **Compilador JIT de 64 bits para código administrado**

  .NET Framework 4.6 incluye una nueva versión del compilador JIT de 64 bits (llamado originalmente RyuJIT). El nuevo compilador de 64 bits proporciona importantes mejoras de rendimiento con respecto al antiguo compilador JIT de 64 bits. El nuevo compilador de 64 bits está habilitado para los procesos de 64 bits que se ejecutan en .NET Framework 4.6. La aplicación se ejecutará en un proceso de 64 bits si se ha compilado como aplicación de 64 bits o AnyCPU y se está ejecutando en un sistema operativo de 64 bits. Aunque se hayan tomado precauciones para efectuar la transición al nuevo compilador de la manera más transparente posible, es posible que se produzcan cambios en el comportamiento. Nos gustaría que se pusiera en contacto con nosotros si encuentra algún problema al usar el nuevo compilador JIT. Póngase en contacto con nosotros a través de [Microsoft Connect](https://connect.microsoft.com/) si detecta algún problema que pueda estar relacionado con el nuevo compilador JIT de 64 bits.

  El nuevo compilador JIT de 64 bits también incluye características de aceleración SIMD de hardware al acoplarse con tipos SIMD habilitados para SIMD en el espacio de nombres <xref:System.Numerics>, que puede producir notables mejoras en el rendimiento.

- **Mejoras en el cargador de ensamblados**

  Ahora el cargador de ensamblados usa la memoria de un modo más eficaz al descargar ensamblados de IL después de cargar una imagen NGEN correspondiente. Este cambio reduce la memoria virtual, que es bastante útil en las aplicaciones de 32 bits de gran tamaño (por ejemplo, Visual Studio), y también guarda la memoria física.

- **Cambios en la biblioteca de clases base**

  Se agregaron muchas nuevas API a .NET Framework 4.6 para habilitar escenarios clave. Incluyen los siguientes cambios y adiciones:

  - **Implementaciones de IReadOnlyCollection\<T>**

    Las colecciones adicionales implementan <xref:System.Collections.Generic.IReadOnlyCollection%601>, como <xref:System.Collections.Generic.Queue%601> y <xref:System.Collections.Generic.Stack%601>.

  - **CultureInfo.CurrentCulture y CultureInfo.CurrentUICulture**

    Las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType> ahora son de lectura y escritura, en lugar de solo lectura. Si asigna un nuevo objeto <xref:System.Globalization.CultureInfo> a estas propiedades, también cambian la referencia cultural del subproceso actual definida por la propiedad `Thread.CurrentThread.CurrentCulture` y la referencia cultural del subproceso de la interfaz usuario actual definida por las propiedades `Thread.CurrentThread.CurrentUICulture`.

  - **Mejoras en la recolección de elementos no utilizados (GC)**

    La clase <xref:System.GC> ahora incluye los métodos <xref:System.GC.TryStartNoGCRegion%2A> y <xref:System.GC.EndNoGCRegion%2A> que permiten impedir la recolección de elementos no usados durante la ejecución de una ruta crítica.

    Una nueva sobrecarga del método <xref:System.GC.Collect%28System.Int32%2CSystem.GCCollectionMode%2CSystem.Boolean%2CSystem.Boolean%29?displayProperty=nameWithType> permite controlar si el montón del objeto pequeño y el montón del objeto grande se exploran y compactan o si solo se exploran.

  - **Tipos habilitados para SIMD**

    El espacio de nombres <xref:System.Numerics> incluye ahora varios tipos habilitados para SIMD, como <xref:System.Numerics.Matrix3x2>, <xref:System.Numerics.Matrix4x4>, <xref:System.Numerics.Plane>, <xref:System.Numerics.Quaternion>, <xref:System.Numerics.Vector2>, <xref:System.Numerics.Vector3> y <xref:System.Numerics.Vector4>.

    Como el nuevo compilador JIT de 64 bits también incluye características de aceleración de hardware SIMD, hay mejoras de rendimiento considerablemente importantes al usar los tipos habilitados para SIMD con el nuevo compilador JIT de 64 bits.

  - **Actualizaciones de criptografía**

    La API <xref:System.Security.Cryptography?displayProperty=nameWithType> se está actualizando para que sea compatible con las [API de criptografía CNG de Windows](/windows/desktop/SecCNG/cng-reference). Las versiones anteriores de .NET Framework dependían totalmente de una [versión anterior de las API de criptografía de Windows](/windows/desktop/SecCrypto/cryptography-portal) como base para la implementación de <xref:System.Security.Cryptography?displayProperty=nameWithType>. Recibimos solicitudes para admitir la API de CNG, ya que admite [algoritmos de criptografía modernos](/windows/desktop/SecCNG/cng-features#suite-b-support), que son importantes para determinadas categorías de aplicaciones.

    .NET Framework 4.6 incluye las siguientes nuevas mejoras para admitir las API de criptografía de CNG de Windows:

    - Un conjunto de métodos de extensión para los certificados X509, `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey(System.Security.Cryptography.X509Certificates.X509Certificate2)` y `System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey(System.Security.Cryptography.X509Certificates.X509Certificate2)`, que devuelven, siempre que sea posible, una implementación basada en CNG en lugar de una implementación basada en CAPI (algunas tarjetas inteligentes, entre otros, siguen necesitando CAPI, mientras que las API controlan la reserva).

    - La clase <xref:System.Security.Cryptography.RSACng?displayProperty=nameWithType>, que proporciona una implementación de CNG del algoritmo RSA.

    - Mejoras en la API de RSA, de modo que las acciones habituales ya no necesitan ninguna conversión. Por ejemplo, el cifrado de datos con un objeto <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> necesita un código similar al siguiente en las versiones anteriores de .NET Framework.

      [!code-csharp[WhatsNew.Casting#1](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#1)]
      [!code-vb[WhatsNew.Casting#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#1)]

      El código que usa las nuevas API de criptografía de .NET Framework 4.6 se puede reescribir del siguiente modo para evitar la conversión.

      [!code-csharp[WhatsNew.Casting#2](~/samples/snippets/csharp/VS_Snippets_CLR/whatsnew.casting/cs/program.cs#2)]
      [!code-vb[WhatsNew.Casting#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/whatsnew.casting/vb/module1.vb#2)]

  - **Compatibilidad con la conversión de fechas y horas a o desde la hora de Unix**

    Se han agregado los siguientes métodos nuevos a la estructura <xref:System.DateTimeOffset> para admitir la conversión de valores de fecha y hora a o desde la hora de Unix:

    - <xref:System.DateTimeOffset.FromUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.FromUnixTimeMilliseconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeSeconds%2A?displayProperty=nameWithType>

    - <xref:System.DateTimeOffset.ToUnixTimeMilliseconds%2A?displayProperty=nameWithType>

  - **Modificadores de compatibilidad**

    La nueva clase <xref:System.AppContext> agrega una nueva característica de compatibilidad que permite a los autores de bibliotecas proporcionar a sus usuarios un mecanismo uniforme para cancelar la participación de la nueva funcionalidad. Establece un contrato flexible entre los componentes para poder comunicar una solicitud de cancelación de la participación. Esta capacidad normalmente es importante cuando se realiza un cambio en la funcionalidad existente. Por el contrario, la nueva funcionalidad participa de forma implícita.

    Con <xref:System.AppContext>, las bibliotecas definen y exponen modificadores de compatibilidad, mientras que el código que depende de ellas puede configurar dichos modificadores para que afecten al comportamiento de la biblioteca. De forma predeterminada, las bibliotecas proporcionan la nueva funcionalidad y solo la modifican (es decir, ofrecen la funcionalidad anterior) si el modificador está establecido.

    Una aplicación (o una biblioteca) puede declarar el valor de un modificador (que es siempre un valor <xref:System.Boolean>) que define una biblioteca dependiente. El modificador siempre es implícitamente `false`. Cuando el modificador se establece en `true`, se habilita. Cuando el modificador se establece explícitamente en `false`, proporciona el nuevo comportamiento.

    ```csharp
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", true);
    ```

    ```vb
    AppContext.SetSwitch("Switch.AmazingLib.ThrowOnException", True)
    ```

    La biblioteca debe comprobar si un consumidor declaró el valor del conmutador y, después, actuar en consecuencia.

    ```csharp
    if (!AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", out shouldThrow))
    {
        // This is the case where the switch value was not set by the application.
        // The library can choose to get the value of shouldThrow by other means.
        // If no overrides nor default values are specified, the value should be 'false'.
        // A false value implies the latest behavior.
    }

    // The library can use the value of shouldThrow to throw exceptions or not.
    if (shouldThrow)
    {
        // old code
    }
    else
    {
        // new code
    }
    ```

    ```vb
    If Not AppContext.TryGetSwitch("Switch.AmazingLib.ThrowOnException", shouldThrow) Then
        ' This is the case where the switch value was not set by the application.
        ' The library can choose to get the value of shouldThrow by other means.
        ' If no overrides nor default values are specified, the value should be 'false'.
        ' A false value implies the latest behavior.
    End If

    ' The library can use the value of shouldThrow to throw exceptions or not.
    If shouldThrow Then
        ' old code
    Else
        ' new code
    End If
    ```

    Es conveniente usar un formato coherente para los modificadores porque son un contrato formal que expone una biblioteca. Las siguientes son dos formatos obvios.

    - *Modificador*.*espacio de nombres*.*nombre del modificador*

    - *Modificador*.*biblioteca*.*nombre del modificador*

  - **Cambios en el modelo asincrónico basado en tareas (TAP)**

    Para las aplicaciones que tienen como destino .NET Framework 4.6, los objetos <xref:System.Threading.Tasks.Task> y <xref:System.Threading.Tasks.Task%601> heredan la referencia cultural y la referencia cultural de interfaz de usuario del subproceso que realiza la llamada. No se ve afectado el comportamiento de las aplicaciones que tienen como destino las versiones anteriores de .NET Framework o que no especifican una versión concreta de .NET Framework. Para obtener más información, vea la sección "Referencia cultural y operaciones asincrónicas basadas en tareas" del tema sobre la clase <xref:System.Globalization.CultureInfo>.

    La clase <xref:System.Threading.AsyncLocal%601?displayProperty=nameWithType> le permite representar datos de ambiente locales de un flujo de control asincrónico determinado, por ejemplo, un método `async`. Se puede usar para conservar los datos en todos los subprocesos. También puede definir un método de devolución de llamada que se le notifique al cambiar los datos de ambiente, ya sea porque se ha cambiado la propiedad <xref:System.Threading.AsyncLocal%601.Value%2A?displayProperty=nameWithType> de forma explícita o porque el subproceso ha encontrado una transición de contexto.

    Se han agregado tres prácticos métodos, <xref:System.Threading.Tasks.Task.CompletedTask%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Task.FromCanceled%2A?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Task.FromException%2A?displayProperty=nameWithType>, al patrón asincrónico basado en tareas (TAP) para que devuelva las tareas completadas en un estado determinado.

    La clase <xref:System.IO.Pipes.NamedPipeClientStream> ahora admite la comunicación asincrónica con su nuevo método <xref:System.IO.Pipes.NamedPipeClientStream.ConnectAsync%2A>. .

  - **EventSource ahora permite escribir en el Registro de eventos**

    Ahora puede usar la clase <xref:System.Diagnostics.Tracing.EventSource> para registrar mensajes administrativos u operativos en el registro de eventos, además de cualquier sesión ETW existente que se haya creado en el equipo. Anteriormente, tenía que usar el paquete de NuGet Microsoft.Diagnostics.Tracing.EventSource para poder aprovechar esta funcionalidad, que ahora está integrada en .NET Framework 4.6.

    El paquete NuGet y .NET Framework 4.6 se han actualizado con las siguientes características:

    - **Eventos dinámicos**

      Permite eventos definidos "sobre la marcha" sin crear métodos de eventos.

    - **Cargas enriquecidas**

      Permite que las matrices y clases con atributos especiales, así como los tipos primitivos, se pasen como carga

    - **Seguimiento de actividad**

      Hace que los eventos de inicio y de detención etiqueten eventos entre ellos con un identificador que representa todas las actividades actualmente activas.

    Para admitir estas características, se ha agregado el método <xref:System.Diagnostics.Tracing.EventSource.Write%2A> sobrecargado a la clase <xref:System.Diagnostics.Tracing.EventSource>.

- **Windows Presentation Foundation (WPF)**

  - **Mejoras en el HDPI**

    Se mejoró la compatibilidad con HDPI en WPF en .NET Framework 4.6. Se han hecho cambios en el redondeo del diseño para reducir las instancias de recorte en los controles que contienen bordes. De forma predeterminada, esta característica solo está habilitada si se establece <xref:System.Runtime.Versioning.TargetFrameworkAttribute> en .NET 4.6.  Las aplicaciones que tienen como destino versiones anteriores de .NET Framework y que se ejecutan en .NET Framework 4.6 pueden participar en el nuevo comportamiento agregando la siguiente línea a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo app.config:

    ```xml
    <AppContextSwitchOverrides
    value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false"
    />
    ```

    Actualmente, las ventanas de WPF que ocupan varios monitores con diferentes valores de PPP (configuración de varios PPP) se representan completamente sin regiones oscurecidas. Puede deshabilitar este comportamiento agregando la siguiente línea a la sección `<appSettings>` del archivo app.config:

    ```xml
    <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    ```

    Se ha agregado a <xref:System.Windows.Input.Cursor?displayProperty=nameWithType> compatibilidad para cargar automáticamente el cursor derecho según la configuración de PPP.

  - **Mejor si es táctil**

    Los informes de los clientes en [Connect](https://connect.microsoft.com/VisualStudio/feedback/details/903760/) acerca del comportamiento impredecible de la función táctil se han tratado en .NET Framework 4.6. Ahora, el umbral de doble punteo de las aplicaciones de WPF y de la Tienda Windows es el mismo en Windows 8.1 y versiones superiores.

  - **Compatibilidad con las ventanas secundarias transparentes**

    En .NET Framework 4.6, WPF admite las ventanas secundarias transparentes en Windows 8.1 y versiones superiores, de manera que puede crear ventanas secundarias transparentes y no rectangulares en las ventanas de nivel superior. Puede habilitar esta característica estableciendo la propiedad <xref:System.Windows.Interop.HwndSourceParameters.UsesPerPixelTransparency%2A?displayProperty=nameWithType> en `true`.

- **Windows Communication Foundation (WCF)**

  - **Compatibilidad con SSL**

    WCF ahora admite la versión con SSL TLS 1.1 y TLS 1.2, además de SSL 3.0 y TLS 1.0, al usar NetTcp con la autenticación de cliente y la seguridad de transporte. Ahora se puede seleccionar el protocolo que se quiere usar o bien deshabilitar protocolos antiguos menos seguros; para ello, establezca la propiedad <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A> o agregue lo siguiente a un archivo de configuración.

    ```xml
    <netTcpBinding>
        <binding>
          <security mode= "None|Transport|Message|TransportWithMessageCredential" >
              <transport clientCredentialType="None|Windows|Certificate"
                        protectionLevel="None|Sign|EncryptAndSign"
                        sslProtocols="Ssl3|Tls1|Tls11|Tls12">
                </transport>
          </security>
        </binding>
    </netTcpBinding>
    ```

  - **Enviar mensajes con diferentes conexiones HTTP**

    Ahora WCF permite que los usuarios se aseguren de que se han enviado determinados mensajes con diferentes conexiones HTTP subyacentes. Existen dos modos para hacer esto:

    - **Usar un prefijo de nombre de grupo de conexión**

      Los usuarios pueden especificar una cadena que WCF usará como prefijo del nombre del grupo de conexión. Se envían dos mensajes con prefijos diferentes por distintas conexiones HTTP subyacentes. Establezca el prefijo agregando un par clave-valor a la propiedad <xref:System.ServiceModel.Channels.Message.Properties%2A?displayProperty=nameWithType> del mensaje. La clave es "httpTransporteConexiónGrupoNombrePrefijo"; el valor es el prefijo deseado.

    - **Usar distintos generadores de canales**

      Los usuarios también pueden habilitar una característica que garantiza que los mensajes enviados por canales creados por distintos generadores de canales usen diferentes conexiones HTTP subyacentes. Para habilitar esta característica, los usuarios deben establecer el siguiente valor `appSetting` en `true`:

      ```xml
      <appSettings>
          <add key="wcf:httpTransportBinding:useUniqueConnectionPoolPerFactory" value="true" />
      </appSettings>
      ```

- **Windows Workflow Foundation (WWF)**

  Ahora puede especificar los segundos durante los que un servicio de flujo de trabajo retendrá una solicitud de operación fuera de servicio cuando haya un marcador que no sea de protocolo pendiente antes de que expire la solicitud. Un marcador "no de protocolo" es un marcador que no está relacionado con las actividades de recepción pendientes. Algunas actividades crean marcadores no de protocolo dentro de su implementación, por lo que es posible que no sea obvio que exista un marcador no de protocolo. Entre ellas se encuentran Estado y Selección. Si tiene un servicio de flujo de trabajo implementado con un equipo de estado o que contiene una actividad de selección, lo más probable es que tenga marcadores no de protocolo. Especifique el intervalo agregando una línea como la siguiente a la sección `appSettings` del archivo app.config:

  ```xml
  <add key="microsoft:WorkflowServices:FilterResumeTimeoutInSeconds" value="60"/>
  ```

  El valor predeterminado es de 60 segundos. Si `value` se establece en 0, las solicitudes fuera de servicio se rechazan inmediatamente con un error que contiene un texto similar a este:

  ```console
  Operation 'Request3|{http://tempuri.org/}IService' on service instance with identifier '2b0667b6-09c8-4093-9d02-f6c67d534292' cannot be performed at this time. Please ensure that the operations are performed in the correct order and that the binding in use provides ordered delivery guarantees.
  ```

  Este es el mismo mensaje que aparece si recibe un mensaje de operación fuera de servicio y no hay ningún marcador que no sea de protocolo.

  Si el valor del elemento `FilterResumeTimeoutInSeconds` es distinto de cero, hay marcadores no de protocolo y el intervalo de tiempo de espera expira, se produce un error en la operación con un mensaje de tiempo de espera.

- **Transacciones**

  Ahora puede incluir el identificador de transacción distribuida para la transacción que provocó que se produjera una excepción derivada de <xref:System.Transactions.TransactionException>. Para ello, agregue la siguiente clave a la sección `appSettings` del archivo app.config:

  ```xml
  <add key="Transactions:IncludeDistributedTransactionIdInExceptionMessage" value="true"/>
  ```

  El valor predeterminado es `false`.

- **Redes**

  - **Reutilización del socket**

    Windows 10 incluye un nuevo algoritmo de red de alta escalabilidad que optimiza los recursos del equipo con la reutilización de los puertos locales para las conexiones TCP salientes. .NET Framework 4.6 admite este algoritmo, lo que permite que las aplicaciones .NET aprovechen el nuevo comportamiento. En versiones anteriores de Windows había un límite de conexiones simultáneas artificial (normalmente de 16.384, el tamaño predeterminado del intervalo de puertos dinámicos) y esto podía limitar la escalabilidad de un servicio provocando el agotamiento de puertos durante la carga.

    Se agregaron dos API nuevas a .NET Framework 4.6 para permitir la reutilización de puertos, lo que elimina de forma eficaz el límite de 64 K de las conexiones simultáneas:

    - El valor de enumeración <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType>.

    - Propiedad <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType>

    De forma predeterminada, la propiedad <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> es `false`, a menos que el valor `HWRPortReuseOnSocketBind` de la clave del Registro `HKLM\SOFTWARE\Microsoft\.NETFramework\v4.0.30319` se establezca en 0x1. Para habilitar la reutilización del puerto local en las conexiones HTTP, establezca la propiedad <xref:System.Net.ServicePointManager.ReusePort%2A?displayProperty=nameWithType> en `true`. Esto hace que todas las conexiones de socket TCP salientes de <xref:System.Net.Http.HttpClient> y <xref:System.Net.HttpWebRequest> usen una nueva opción de socket de Windows 10, [SO_REUSE_UNICASTPORT](/windows/desktop/WinSock/sol-socket-socket-options), que permite la reutilización del puerto local.

    Los desarrolladores que crean una aplicación solo de sockets pueden especificar la opción <xref:System.Net.Sockets.SocketOptionName?displayProperty=nameWithType> al llamar a un método (como <xref:System.Net.Sockets.Socket.SetSocketOption%2A?displayProperty=nameWithType>) para que los sockets de salida reutilicen los puertos locales durante el enlace.

  - **Compatibilidad con nombres de dominio internacionales y PunyCode**

    Se ha agregado una nueva propiedad, <xref:System.Uri.IdnHost%2A>, a la clase <xref:System.Uri> para ofrecer una mejor compatibilidad con los nombres de dominio internacionales y PunyCode.

- **Cambio de tamaño en controles de Windows Forms**

  Esta característica se amplió en .NET Framework 4.6 para incluir los tipos <xref:System.Windows.Forms.DomainUpDown>, <xref:System.Windows.Forms.NumericUpDown>, <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.ToolStripSplitButton> y el rectángulo especificado por la propiedad <xref:System.Drawing.Design.PaintValueEventArgs.Bounds%2A> que se usa al dibujar un <xref:System.Drawing.Design.UITypeEditor>.

  Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Compatibilidad para codificaciones de páginas de códigos**

  .NET Core admite principalmente las codificaciones Unicode y, de forma predeterminada, proporciona compatibilidad limitada para las codificaciones de páginas de códigos. Puede agregar compatibilidad con codificaciones de páginas de códigos disponibles en .NET Framework pero que no se admiten en .NET Core mediante el registro de las codificaciones de páginas de códigos con el método <xref:System.Text.Encoding.RegisterProvider%2A?displayProperty=nameWithType>. Para más información, consulte <xref:System.Text.CodePagesEncodingProvider?displayProperty=nameWithType>.

- **.NET Native**

  Las aplicaciones de Windows para Windows 10 que tienen como destino .NET Core y están escritas en C# o Visual Basic pueden aprovechar una nueva tecnología que compila las aplicaciones en código nativo en lugar de IL. Generan aplicaciones que se caracterizan por un inicio y tiempos de ejecución más rápidos. Para obtener más información, consulte [Compilar aplicaciones con .NET Native](../net-native/index.md). Para obtener información general sobre .NET Native en la que se examina cómo difiere de la compilación JIT y de NGEN, y lo que eso conlleva para el código, vea [.NET Native y compilación](../net-native/net-native-and-compilation.md).

  Las aplicaciones se compilan en código nativo de forma predeterminada cuando se compilan con Visual Studio 2015 o versiones posteriores. Para obtener más información, vea [Introducción a .NET Native](../net-native/getting-started-with-net-native.md).

  Para admitir la depuración de aplicaciones .NET Native, se agregó una serie de interfaces y enumeraciones nuevas a la API de depuración no administrada. Para obtener más información, consulte el tema [Depuración (Referencia de la API no administrada)](../unmanaged-api/debugging/index.md).

- **Paquetes de .NET Framework de código abierto**

  Los paquetes de .NET Core como las colecciones inmutables, las [API de SIMD](https://www.nuget.org/packages/Microsoft.Bcl.Simd) y las API de red, como las que se encuentran en el espacio de nombres <xref:System.Net.Http>, ahora están disponibles como paquetes de código abierto en [GitHub](https://github.com/). Para tener acceso al código, vea [CoreFx en GitHub](https://github.com/dotnet/corefx). Para obtener más información y saber cómo contribuir a estos paquetes, vea [.NET Core y código abierto](../get-started/net-core-and-open-source.md) y la [página principal de .NET en GitHub](https://github.com/dotnet/home).

<a name="v452" />

## <a name="whats-new-in-net-framework-452"></a>Novedades de .NET Framework 4.5.2

- **Nuevas API para aplicaciones de ASP.NET.** Los nuevos métodos <xref:System.Web.HttpResponse.AddOnSendingHeaders%2A?displayProperty=nameWithType> y <xref:System.Web.HttpResponseBase.AddOnSendingHeaders%2A?displayProperty=nameWithType> le permiten inspeccionar y modificar encabezados y códigos de estado cuando se vuelca la respuesta de la aplicación cliente. Puede usar estos métodos en lugar de los eventos <xref:System.Web.HttpApplication.PreSendRequestHeaders> y <xref:System.Web.HttpApplication.PreSendRequestContent>, ya que son más eficientes y fiables.

  El método <xref:System.Web.Hosting.HostingEnvironment.QueueBackgroundWorkItem%2A?displayProperty=nameWithType> permite programar pequeños elementos de trabajo en segundo plano. ASP.NET realiza un seguimiento de estos elementos y evita que IIS termine el proceso de trabajo de manera abrupta hasta que se completen todos los elementos de trabajo en segundo plano. Este método no se puede invocar desde fuera del dominio de una aplicación administrada de ASP.NET.

  Las nuevas propiedades <xref:System.Web.HttpResponse.HeadersWritten?displayProperty=nameWithType> y <xref:System.Web.HttpResponseBase.HeadersWritten?displayProperty=nameWithType> devuelven valores booleanos que indican si los encabezados de respuesta se han escrito. Puede usar estas propiedades para comprobar si se realizan correctamente las llamadas a las API como <xref:System.Web.HttpResponse.StatusCode%2A?displayProperty=nameWithType> (que producen excepciones si se han escrito los encabezados).

- **Cambio de tamaño en controles de Windows Forms** Esta característica se ha ampliado. Ahora se puede usar el valor de PPP del sistema para cambiar el tamaño de componentes de los siguientes controles adicionales (por ejemplo, la flecha desplegable en cuadros combinados):

  - <xref:System.Windows.Forms.ComboBox>
  - <xref:System.Windows.Forms.ToolStripComboBox>
  - <xref:System.Windows.Forms.ToolStripMenuItem>
  - <xref:System.Windows.Forms.Cursor>
  - <xref:System.Windows.Forms.DataGridView>
  - <xref:System.Windows.Forms.DataGridViewComboBoxColumn>

  Esta característica es opcional. Para habilitarla, establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true` en el archivo de configuración de la aplicación (app.config):

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

- **Nueva característica de flujo de trabajo.** Un administrador de recursos que usa el método <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> (y, por lo tanto, implementa la interfaz <xref:System.Transactions.IPromotableSinglePhaseNotification>) puede usar el nuevo método <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> para pedir lo siguiente:

  - Promocionar la transacción a una transacción de MSDTC (Coordinador de transacciones distribuidas de Microsoft).

  - Reemplace <xref:System.Transactions.IPromotableSinglePhaseNotification> con una <xref:System.Transactions.ISinglePhaseNotification>, que es una inscripción duradera que admite confirmaciones de fase única.

  Esto puede realizarse en el mismo dominio de la aplicación y no requiere que ningún código sin administrar adicional interactúe con MSDTC para realizar la promoción. Solo se puede llamar al nuevo método cuando existe una llamada pendiente de <xref:System.Transactions?displayProperty=nameWithType> al método <xref:System.Transactions.IPromotableSinglePhaseNotification>`Promote` que está implementado por una inscripción que puede promocionarse.

- **Mejoras de generación de perfiles.** Las siguientes API de generación de perfiles no administradas proporcionan una generación de perfiles más sólida:

  - [COR_PRF_ASSEMBLY_REFERENCE_INFO (estructura)](../unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)
  - [COR_PRF_HIGH_MONITOR (enumeración)](../unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)
  - [GetAssemblyReferences (método)](../unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
  - [GetEventMask2 (método)](../unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
  - [SetEventMask2 (método)](../unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
  - [Método AddAssemblyReference](../unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)

  Las implementaciones de `ICorProfiler` anteriores eran compatibles con la carga diferida de ensamblados dependientes. Las nuevas API de generación de perfiles requieren que los ensamblados dependientes insertados por el generador de perfiles se carguen inmediatamente, en lugar de cargarse cuando la aplicación se haya inicializado por completo. Este cambio no afecta a los usuarios de las API de `ICorProfiler` existentes.

- **Mejoras en la depuración.** Las API de depuración no administradas proporcionan una mejor integración con un generador de perfiles. Ahora se puede acceder a metadatos insertados por el generador de perfiles, así como a variables locales y código producidos por solicitudes de ReJIT del compilador en la depuración de volcados.

  - [SetWriteableMetadataUpdateMode (método)](../unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
  - [EnumerateLocalVariablesEx (método)](../unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md)
  - [GetLocalVariableEx (método)](../unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md)
  - [GetCodeEx (método)](../unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md)
  - [GetActiveReJitRequestILCode (método)](../unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)
  - [Método GetInstrumentedILMap](../unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)

- **Cambios en el seguimiento de eventos.** .NET Framework 4.5.2 permite realizar el seguimiento de actividades fuera del proceso, basado en el Seguimiento de eventos para Windows (ETW), para una mayor área expuesta. Esto permite a los proveedores de Administración avanzada de energía (APM) proporcionar herramientas sencillas que realicen un seguimiento preciso de solicitudes y actividades individuales en distintos subprocesos.  Estos eventos solo se desencadenan cuando son habilitados por los controladores de ETW; por lo tanto, los cambios no afectan a código de ETW escrito anteriormente o a código que se ejecute cuando ETW esté deshabilitado.

- **Promover una transacción y convertirla en una inscripción duradera**

  <xref:System.Transactions.Transaction.PromoteAndEnlistDurable%2A?displayProperty=nameWithType> es una API nueva que se ha agregado a .NET Framework 4.5.2 y 4.6:

  ```csharp
  [System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]
  public Enlistment PromoteAndEnlistDurable(Guid resourceManagerIdentifier,
                                            IPromotableSinglePhaseNotification promotableNotification,
                                            ISinglePhaseNotification enlistmentNotification,
                                            EnlistmentOptions enlistmentOptions)
  ```

  ```vb
  <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")>
  public Function PromoteAndEnlistDurable(resourceManagerIdentifier As Guid,
                                          promotableNotification As IPromotableSinglePhaseNotification,
                                          enlistmentNotification As ISinglePhaseNotification,
                                          enlistmentOptions As EnlistmentOptions) As Enlistment
  ```

  El método se puede usar con una inscripción creada previamente por <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A?displayProperty=nameWithType> en respuesta al método <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Pide a `System.Transactions` que promueva la transacción a una transacción MSDTC y que "convierta" la inscripción que se puede promover en una inscripción duradera. Cuando este método finalice correctamente, `System.Transactions` ya no hará referencia a la interfaz <xref:System.Transactions.IPromotableSinglePhaseNotification> y todas las notificaciones futuras llegarán a la interfaz <xref:System.Transactions.ISinglePhaseNotification> proporcionada. La inscripción en cuestión debe actuar como inscripción duradera y admitir el registro y la recuperación de transacciones. Vea <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType> para obtener más información. Además, la inscripción debe admitir <xref:System.Transactions.ISinglePhaseNotification>.  *Solo* se puede llamar a este método al procesar una llamada de <xref:System.Transactions.ITransactionPromoter.Promote%2A?displayProperty=nameWithType>. Si no es el caso, se produce una excepción <xref:System.Transactions.TransactionException>.

<a name="v451" />

## <a name="whats-new-in-net-framework-451"></a>Novedades de .NET Framework 4.5.1

**Actualizaciones de abril de 2014**:

- [Visual Studio 2013 Update 2](https://go.microsoft.com/fwlink/p/?LinkId=393658) incluye actualizaciones para las plantillas de la Biblioteca de clases portable para garantizar la compatibilidad en los escenarios siguientes:

  - Puede usar las API de Windows en tiempo de ejecución en bibliotecas portables cuyo destino sea Windows 8.1, Windows Phone 8.1 y Windows Phone Silverlight 8.1.

  - Puede incluir XAML (tipos de Windows.UI.XAML) en las bibliotecas portables cuyo destino es Windows 8.1 o Windows Phone 8.1. Se admiten las siguientes plantillas de XAML:  Página en blanco, Diccionario de recursos, Control basado en modelo y Control de usuario.

  - Se puede crear un componente de Windows en tiempo de ejecución portable (archivo .winmd) para usarlo en aplicaciones de la Tienda que tengan como destino Windows 8.1 y Windows Phone 8.1.

  - Puede cambiar el destino de una biblioteca de clases de la Tienda Windows o la Tienda de Windows Phone como biblioteca de clases portable.

  Para obtener más información sobre estos cambios, vea [Biblioteca de clases portable](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

- El conjunto de contenido de .NET Framework ahora incluye documentación para .NET Native, que es una tecnología de precompilación para crear e implementar aplicaciones de Windows. .NET Native compila aplicaciones directamente en código nativo, en lugar de hacerlo en un lenguaje intermedio (IL), lo que mejora el rendimiento. Para obtener información detallada, vea [Compilar aplicaciones con .NET Native](../net-native/index.md).

- [.NET Framework Reference Source](https://referencesource.microsoft.com/) proporciona una nueva experiencia de navegación y mejores funciones. Ahora puede navegar en línea por el código fuente de .NET Framework, [descargar la referencia](https://referencesource.microsoft.com/download.html) para visualizarlo sin conexión y examinar los orígenes (incluidas revisiones y actualizaciones) durante la depuración. Para obtener más información, vea la entrada de blog [A new look for .NET Reference Source](https://devblogs.microsoft.com/dotnet/a-new-look-for-net-reference-source/) (Un nuevo aspecto para el origen de referencia de .NET).

Las nuevas características y mejoras realizadas en las clases base en .NET Framework 4.5.1 son:

- Redirección automática de enlace de ensamblados. A partir de Visual Studio 2013, cuando se compila una aplicación cuyo destino es .NET Framework 4.5.1, se pueden agregar al archivo de configuración de la aplicación redirecciones de enlace si la aplicación o sus componentes hacen referencia a varias versiones del mismo ensamblado. Esta característica también se puede habilitar en proyectos que tienen como destino versiones anteriores de .NET Framework. Para obtener más información, vea [Cómo: Habilitar y deshabilitar redireccionamiento de enlaces automático](../configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).

- Capacidad de recopilar información de diagnóstico para ayudar a los desarrolladores a mejorar el rendimiento de las aplicaciones de servidor y en la nube. Para obtener más información, vea los métodos <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityId%2A> y <xref:System.Diagnostics.Tracing.EventSource.WriteEventWithRelatedActivityIdCore%2A> de la clase <xref:System.Diagnostics.Tracing.EventSource>.

- Capacidad de compactar explícitamente el montón de objetos grandes (LOH) durante la recolección de elementos no utilizados. Para obtener más información, vea la propiedad <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode%2A?displayProperty=nameWithType>.

- Mejoras adicionales de rendimiento como, por ejemplo, la suspensión de la aplicación ASP.NET, mejoras de JIT con varios núcleos o reducción del tiempo de inicio de la aplicación tras una actualización de .NET Framework. Para obtener información detallada, vea las entradas de blog relativas al [anuncio de .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/) y la [suspensión de aplicaciones ASP.NET](https://devblogs.microsoft.com/dotnet/asp-net-app-suspend-responsive-shared-net-web-hosting/).

Las mejoras en Windows Forms son las siguientes:

- Cambio de tamaño en controles de Windows Forms. Puede usar el valor de PPP del sistema para cambiar el tamaño de los componentes de controles (por ejemplo, los iconos que aparecen en una cuadrícula de propiedades); para ello, active esta opción con una entrada en el archivo de configuración de la aplicación (app.config). Actualmente, esta característica es compatible con los siguientes controles de Windows Forms:

  - <xref:System.Windows.Forms.PropertyGrid>
  - <xref:System.Windows.Forms.TreeView>
  - Algunos aspectos de <xref:System.Windows.Forms.DataGridView> (vea las [nuevas características de la versión 4.5.2](#v452) para conocer los controles adicionales admitidos)

  Para activar esta característica, agregue un nuevo elemento \<appSettings> al archivo de configuración (app.config) y establezca el elemento `EnableWindowsFormsHighDpiAutoResizing` en `true`:

  ```xml
  <appSettings>
      <add key="EnableWindowsFormsHighDpiAutoResizing" value="true" />
  </appSettings>
  ```

Algunas de las mejoras realizadas durante la depuración de las aplicaciones de .NET Framework en Visual Studio 2013 son:

- Valores devueltos en el depurador de Visual Studio. Al depurar una aplicación administrada en Visual Studio 2013, en la ventana Automático se muestran los valores y tipos devueltos de los métodos. Esta información está disponible para el escritorio, la Tienda Windows y las aplicaciones Windows Phone. Para más información, vea [Examinar los valores devueltos de llamadas a métodos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/dn323257(v=vs.120)).

- Editar y continuar en aplicaciones de 64 bits. Visual Studio 2013 admite la característica Editar y continuar en aplicaciones administradas de 64 bits para el escritorio, la Tienda Windows y Windows Phone. Las limitaciones existentes siguen en vigor para las aplicaciones de 32 bits y 64 bits (vea la última sección del artículo [Cambios admitidos en el código (C#)](/visualstudio/debugger/supported-code-changes-csharp)).

- Depuración asincrónica. Para facilitar la depuración de aplicaciones asincrónicas en Visual Studio 2013, la pila de llamadas oculta el código de infraestructura proporcionado por los compiladores para permitir la programación asincrónica y, además, encadena los principales marcos lógicos para que pueda seguir la ejecución lógica del programa con mayor claridad. La ventana Tareas reemplaza a la ventana Tareas paralelas, donde se muestran las tareas relacionadas con un punto de interrupción determinado, así como las demás tareas que actualmente están activas o programadas en la aplicación. Puede obtener más información sobre esta característica en la sección "Async-aware debugging" (Depuración asincrónica) de la publicación sobre [el anuncio de .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

- Mayor compatibilidad con las excepciones de los componentes de Windows en tiempo de ejecución. En Windows 8.1, las excepciones que se inician en aplicaciones de la Tienda Windows conservan información sobre el error que provocó la excepción, incluso entre diferentes lenguajes. Puede obtener más información sobre esta característica en la sección "Windows Store app development" (Desarrollo de aplicaciones de la Tienda Windows) de la publicación del [anuncio de .NET Framework 4.5.1](https://devblogs.microsoft.com/dotnet/announcing-the-net-framework-4-5-1-preview/).

A partir de Visual Studio 2013, puede usar la [herramienta de optimización guiada por perfiles administrados (Mpgo.exe)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) para optimizar las aplicaciones de Tienda Windows 8.x, así como las aplicaciones de escritorio.

Para descubrir las nuevas características de ASP.NET 4.5.1, vea [ASP.NET and Web Tools for Visual Studio 2013 Release Notes](/aspnet/visual-studio/overview/2013/release-notes) (Notas de la versión de ASP.NET y herramientas web para Visual Studio 2013).

<a name="v45" />

## <a name="whats-new-in-net-framework-45"></a>Novedades de .NET Framework 4.5

### <a name="base-classes"></a>Clases base

- Capacidad para reducir los reinicios del sistema mediante la detección y cierre de las aplicaciones de .NET Framework 4 durante la implementación. Vea [Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](../deployment/reducing-system-restarts.md).

- Compatibilidad con matrices mayores de 2 gigabytes (GB) en plataformas de 64 bits. Esta característica se puede habilitar en el archivo de configuración de la aplicación. Consulte el elemento [\<gcAllowVeryLargeObjects>](../configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md), donde también se indican otras restricciones de tamaño de objeto y de tamaño de matriz.

- Mayor rendimiento a través de la recolección de elementos no utilizados en segundo plano en el caso de los servidores. Cuando se usa la recolección de elementos no utilizados de los servidores en .NET Framework 4.5, se habilita automáticamente la recolección de elementos no utilizados en segundo plano. Vea la sección sobre la recolección de elementos no utilizados en segundo plano de los servidores del tema [Fundamentals of Garbage Collection](../../standard/garbage-collection/fundamentals.md) (Fundamentos de la recolección de elementos no utilizados).

- Compilación Just-in-time (JIT) en segundo plano, que se encuentra disponible opcionalmente en los procesadores de varios núcleos para mejorar el rendimiento de la aplicación. Vea <xref:System.Runtime.ProfileOptimization>.

- Capacidad para limitar el tiempo durante el cual el motor de expresiones regulares intentará resolver una expresión regular antes de agotar el tiempo de espera. Vea la propiedad <xref:System.Text.RegularExpressions.Regex.MatchTimeout%2A?displayProperty=nameWithType>.

- Capacidad para definir la referencia cultural predeterminada de un dominio de aplicación. Vea la descripción de la clase <xref:System.Globalization.CultureInfo>.

- Compatibilidad de la consola con la codificación Unicode (UTF-16). Vea la descripción de la clase <xref:System.Console>.

- Compatibilidad con el control de versiones de ordenación cultural de cadenas y datos de comparación. Vea la descripción de la clase <xref:System.Globalization.SortVersion>.

- Mayor rendimiento al recuperar recursos. Vea [Empaquetar e implementar recursos](../resources/packaging-and-deploying-resources-in-desktop-apps.md).

- Mejoras en la compresión Zip para reducir el tamaño de un archivo comprimido. Vea el espacio de nombres <xref:System.IO.Compression?displayProperty=nameWithType>.

- Capacidad de personalizar un contexto de reflexión para invalidar el comportamiento predeterminado de reflexión a través de la clase <xref:System.Reflection.Context.CustomReflectionContext>.

- Compatibilidad con la versión 2008 del estándar de internacionalización de nombres de dominio de las aplicaciones (IDNA) cuando se utiliza la clase <xref:System.Globalization.IdnMapping?displayProperty=nameWithType> en Windows 8.

- Delegación de comparación de cadenas en el sistema operativo, que implementa Unicode 6.0, cuando se usa .NET Framework en Windows 8. Al ejecutarse en otras plataformas, .NET Framework incluye sus propios datos de comparación de cadenas, que implementan Unicode 5.x. Vea la clase <xref:System.String> y la sección Comentarios de la clase <xref:System.Globalization.SortVersion>.

- Capacidad para calcular los códigos hash de cadenas en cada dominio de aplicación. Vea el elemento [\<UseRandomizedStringHashAlgorithm>](../configure-apps/file-schema/runtime/userandomizedstringhashalgorithm-element.md).

- Compatibilidad con la reflexión de tipos dividida entre las clases <xref:System.Type> y <xref:System.Reflection.TypeInfo>. Vea [Reflection in the .NET Framework for Windows Store Apps](../reflection-and-codedom/reflection-for-windows-store-apps.md) (Reflexión en .NET Framework para aplicaciones de la Tienda Windows).

### <a name="managed-extensibility-framework-mef"></a>Managed Extensibility Framework (MEF)

En .NET Framework 4.5, Managed Extensibility Framework (MEF) cuenta con las siguientes características nuevas:

- Compatibilidad con los tipos genéricos.

- Modelo de programación basado en convenciones que permite crear elementos basándose en convenciones de nomenclatura en lugar de en atributos.

- Ámbitos múltiples.

- Un subconjunto de MEF que puede usar cuando cree aplicaciones de la Tienda Windows 8.x. Este subconjunto está disponible como un [paquete descargable](https://www.nuget.org/packages/Microsoft.Composition) en la galería de NuGet. Para instalar el paquete, abra el proyecto en Visual Studio, elija **Administrar paquetes de NuGet** en el menú **Proyecto** y busque en línea el paquete `Microsoft.Composition`.

Para obtener más información, vea [Managed Extensibility Framework (MEF)](../mef/index.md).

### <a name="asynchronous-file-operations"></a>Operaciones de archivo asincrónicas

En .NET Framework 4.5, se agregaron nuevas características asincrónicas a los lenguajes C# y Visual Basic. Estas características agregan un modelo basado en tareas para realizar operaciones asincrónicas. Para utilizar este nuevo modelo, use los métodos asincrónicos de las clases de E/S. Vea [E/S de archivos asincrónica](../../standard/io/asynchronous-file-i-o.md).

<a name="tools" />

### <a name="tools"></a>Herramientas

En .NET Framework 4.5, el generador de archivos de recursos (Resgen.exe) permite crear un archivo .resw para su uso en aplicaciones de la Tienda Windows 8.x desde un archivo .resources incrustado en un ensamblado de .NET Framework. Para obtener más información, vea [Resgen.exe (Resource File Generator)](../tools/resgen-exe-resource-file-generator.md) (Resgen.exe [generador de archivos de recursos]).

La optimización guiada por perfiles administrados (Mpgo.exe) permite mejorar el tiempo de inicio de la aplicación, la utilización de la memoria (el tamaño del espacio de trabajo) y el rendimiento mediante la optimización de los ensamblados de imagen nativos. La herramienta de línea de comandos genera datos de perfil para los ensamblados nativos de aplicación de la imagen. Vean [Mpgo.exe (Managed Profile Guided Optimization Tool)](../tools/mpgo-exe-managed-profile-guided-optimization-tool.md) (Mpgo.exe [herramienta de optimización guiada por perfiles administrados]). A partir de Visual Studio 2013, puede usar la Mpgo.exe para optimizar las aplicaciones de Tienda Windows 8.x, así como las aplicaciones de escritorio.

<a name="parallel" />

### <a name="parallel-computing"></a>Informática en paralelo

.NET Framework 4.5 cuenta con varias características y mejoras nuevas para el procesamiento informático en paralelo. Entre estas se incluyen un rendimiento mejorado, mayor control, mejor compatibilidad con la programación asincrónica, una nueva biblioteca de flujo de datos y mejor compatibilidad para la depuración y el análisis de rendimiento en paralelo. Vea la entrada [What’s New for Parallelism in .NET 4.5](https://devblogs.microsoft.com/pfxteam/whats-new-for-parallelism-in-net-4-5/) (Novedades de paralelismo en .NET 4.5) de la sección sobre Programación en paralelo del blog sobre .NET.

<a name="web" />

### <a name="web"></a>Web

ASP.NET 4.5 y 4.5.1 incorporan el enlace de modelos de formularios Web Forms, compatibilidad con WebSocket, controladores asincrónicos, mejoras de rendimiento y muchas otras características. Para obtener más información, vea los siguientes recursos:

- [ASP.NET 4.5 y Visual Studio 2012](https://docs.microsoft.com/previous-versions/aspnet/hh420390(v=vs.110))

- [Notas de la versión de ASP.NET and Web Tools para Visual Studio 2013](/aspnet/visual-studio/overview/2013/release-notes)

### <a name="networking-a-namenetworking-"></a>Redes <a name="networking" />

.NET Framework 4.5 proporciona una nueva interfaz de programación para aplicaciones HTTP. Para obtener más información, vea los nuevos espacios de nombres <xref:System.Net.Http?displayProperty=nameWithType> y <xref:System.Net.Http.Headers?displayProperty=nameWithType>.

También se incluye compatibilidad con una nueva interfaz de programación para aceptar e interactuar con una conexión WebSocket mediante el objeto <xref:System.Net.HttpListener> existente y las clases relacionadas. Para obtener más información, vea el nuevo espacio de nombres <xref:System.Net.WebSockets> y la clase <xref:System.Net.HttpListener>.

Además, .NET Framework 4.5 incluye las siguientes mejoras de red:

- Compatibilidad de URI conforme a RFC. Para obtener más información, vea <xref:System.Uri> y las clases relacionadas.

- Compatibilidad con el análisis de nombres de dominio internacionalizados (IDN). Para obtener más información, vea <xref:System.Uri> y las clases relacionadas.

- Compatibilidad con la internacionalización de direcciones de correo electrónico (EAI). Para obtener más información, vea el espacio de nombres <xref:System.Net.Mail>.

- Compatibilidad mejorada de IPv6. Para obtener más información, vea el espacio de nombres <xref:System.Net.NetworkInformation>.

- Compatibilidad con el socket de modo dual. Para obtener más información, vea las clases <xref:System.Net.Sockets.Socket> y <xref:System.Net.Sockets.TcpListener>.

<a name="client" />

### <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)

En .NET Framework 4.5, Windows Presentation Foundation (WPF) contiene cambios y mejoras en las áreas siguientes:

- El nuevo control <xref:System.Windows.Controls.Ribbon.Ribbon>, que permite implementar una interfaz de usuario en forma de cinta que incluye una barra de herramientas de acceso rápido, un menú de aplicación y pestañas.

- La nueva interfaz <xref:System.ComponentModel.INotifyDataErrorInfo>, que admite la validación de datos sincrónica y asincrónica.

- Nuevas características para las clases <xref:System.Windows.Controls.VirtualizingPanel> y <xref:System.Windows.Threading.Dispatcher>.

- Rendimiento mejorado al mostrar conjuntos grandes de datos agrupados y al acceder a colecciones en subprocesos que no son de interfaz de usuario.

- Enlace de datos a propiedades estáticas, enlace de datos a tipos personalizados que implementan la interfaz <xref:System.Reflection.ICustomTypeProvider> y recuperación de información de enlace de datos desde una expresión de enlace.

- Reposición de los datos a medida que cambian los valores (modelado dinámico).

- Capacidad de comprobar si el contexto de datos de un contenedor de elementos está desconectado.

- Capacidad de establecer la cantidad de tiempo que debe transcurrir entre los cambios de propiedad y las actualizaciones del origen de datos.

- Compatibilidad mejorada para implementar patrones de eventos débiles. Además, los eventos ahora pueden aceptar extensiones de marcado.

<a name="windows_communication_foundation" />

### <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)

En .NET Framework 4.5, se han agregado las características siguientes para facilitar la creación y el mantenimiento de aplicaciones de Windows Communication Foundation (WCF):

- Simplificación de los archivos de configuración generados.

- Compatibilidad con el desarrollo del contrato en primer lugar.

- Capacidad de configurar el modo de compatibilidad de ASP.NET más fácilmente.

- Cambios en los valores de propiedad de transporte predeterminados para reducir las probabilidades de tener que establecerlos.

- Actualizaciones de la clase <xref:System.Xml.XmlDictionaryReaderQuotas> que reducen las probabilidades de tener que configurar manualmente cuotas para los lectores de diccionarios XML.

- Validación de los archivos de configuración de WCF por parte de Visual Studio dentro del proceso de compilación, para que se puedan detectar errores de configuración antes de ejecutar la aplicación.

- Nueva compatibilidad con streaming asincrónico.

- Nueva asignación del protocolo HTTPS para facilitar la exposición de un extremo a través de HTTPS con Internet Information Services (IIS).

- Capacidad de generar metadatos en un solo documento WSDL anexando `?singleWSDL` a la dirección URL del servicio.

- Compatibilidad con Websockets para permitir una comunicación bidireccional verdadera a través de los puertos 80 y 443 con características de rendimiento similares a las del transporte TCP.

- Compatibilidad para configurar servicios en el código.

- Información sobre herramientas del editor XML.

- Compatibilidad con el almacenamiento en caché de <xref:System.ServiceModel.ChannelFactory>.

- Compatibilidad con la compresión de codificadores binarios.

- Compatibilidad con un transporte UDP que permite a los desarrolladores escribir servicios que utilizan mensajería de tipo "desencadenar y omitir”. Un cliente envía un mensaje a un servicio y no espera ninguna respuesta de él.

- Capacidad de admitir varios modos de autenticación en un único extremo de WCF mediante el uso de transporte HTTP y seguridad de transporte.

- Compatibilidad con los servicios WCF que utilizan nombres de dominio internacionalizados (IDN).

Para obtener más información, vea [Novedades de Windows Communication Foundation](../wcf/whats-new.md).

<a name="windows_workflow_foundation" />

### <a name="windows-workflow-foundation-wf"></a>Windows Workflow Foundation (WF)

Se agregaron varias características nuevas a Windows Workflow Foundation (WF) en .NET Framework 4.5, incluidas las siguientes:

- Flujos de trabajo de máquina de estados, que se incluyeron por primera vez como parte de .NET Framework 4.0.1 ([.NET Framework 4 Platform Update 1](https://blogs.msdn.microsoft.com/endpoint/2011/04/18/microsoft-net-framework-4-platform-update-1/)). Esta actualización incluía varias clases y actividades nuevas que permitían a los desarrolladores crear flujos de trabajo de máquina de estados. Estas clases y actividades se actualizaron para .NET Framework 4.5 con el objeto de incluir:

  - Capacidad de establecer puntos de interrupción en estados

  - Capacidad de copiar y pegar transiciones en el Diseñador de flujo de trabajo

  - Compatibilidad del diseñador para la creación de transiciones de desencadenador compartidas

  - Actividades para crear flujos de trabajo de máquina de estados, incluidas: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> y <xref:System.Activities.Statements.Transition>

- Características mejoradas del Diseñador de flujo de trabajo, como las siguientes:

  - Funcionalidades de búsqueda de flujo de trabajo mejoradas en Visual Studio, incluidas **Búsqueda rápida** y **Buscar en archivos**.

  - Capacidad de crear automáticamente una actividad Secuencia cuando una segunda actividad secundaria se agrega a una actividad del contenedor y para incluir ambas actividades en la actividad Secuencia.

  - Compatibilidad con el movimiento panorámico, que permite cambiar la parte visible de un flujo de trabajo sin usar las barras de desplazamiento.

  - Una nueva vista **Esquema del documento**, en la que se muestran los componentes de un flujo de trabajo en una vista de esquema con forma de árbol y que le permite seleccionar un componente en la vista **Esquema del documento**.

  - Capacidad de agregar anotaciones a las actividades.

  - Capacidad de definir y consumir delegados de actividad mediante el Diseñador de flujo de trabajo.

  - Conexión e inserción automáticas para actividades y transiciones en los flujos de trabajo de máquina de estados y diagrama de flujo.

- Almacenamiento de la información de estado de vista de un flujo de trabajo en un único elemento del archivo XAML, para poder encontrar y editar fácilmente la información de estado de vista.

- Una actividad de contenedor NoPersistScope para evitar que se conserven las actividades secundarias.

- Compatibilidad con expresiones de C#:

  - Los proyectos de flujo de trabajo que usan Visual Basic utilizarán las expresiones de Visual Basic, y los proyectos de flujo de trabajo de C# utilizarán las expresiones de C#.

  - Los proyectos de flujo de trabajo de C# creados en Visual Studio 2010 y que tengan expresiones de Visual Basic son compatibles con los proyectos de flujo de trabajo de C# que usan expresiones de C#.

- Mejoras del control de versiones:

  - La nueva clase <xref:System.Activities.WorkflowIdentity>, que proporciona una asignación entre una instancia de flujo de trabajo guardada y su definición de flujo de trabajo.

  - Ejecución en paralelo de varias versiones de flujo de trabajo en el mismo host, incluido <xref:System.ServiceModel.Activities.WorkflowServiceHost>.

  - En la actualización dinámica, la capacidad de modificar la definición de una instancia de flujo de trabajo guardada.

- Desarrollo de servicios de flujo de trabajo de contrato en primer lugar, que proporciona compatibilidad para generar automáticamente actividades que busquen coincidencias en un contrato de servicio existente.

Para obtener más información, vea [Novedades de Windows Workflow Foundation](../windows-workflow-foundation/whats-new-in-wf-in-dotnet.md).

<a name="tailored" />

### <a name="net-for-windows-8x-store-apps"></a>.NET para aplicaciones de la Tienda Windows 8.x

Las aplicaciones de la Tienda Windows 8.x están diseñadas para factores de forma específicos y aprovechan la eficacia del sistema operativo Windows. Un subconjunto de .NET Framework 4.5 o 4.5.1 está disponible para compilar aplicaciones de la Tienda Windows 8.x para Windows mediante C# o Visual Basic. Este subconjunto se denomina .NET para aplicaciones de la Tienda Windows 8.x y se explica en una [introducción](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

### <a name="portable-class-libraries-a-nameportable-"></a>Bibliotecas de clases portables <a name="portable" />

El proyecto de Biblioteca de clases portable de Visual Studio 2012 (y versiones posteriores) permite escribir y compilar ensamblados administrados capaces de funcionar en múltiples plataformas de .NET Framework. Mediante el uso de Biblioteca de clases portable, puede elegir las plataformas de destino, como Windows Phone y .NET para aplicaciones de la Tienda Windows 8.x. Los tipos y miembros disponibles en el proyecto se restringen automáticamente a los tipos y miembros comunes de estas plataformas. Para obtener más información, consulte [Biblioteca de clases portable](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md).

## <a name="see-also"></a>Vea también

- [.NET Framework y versiones fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md)
- [Novedades de accesibilidad en .NET Framework](whats-new-in-accessibility.md)
- [Novedades de Visual Studio 2017](/visualstudio/ide/whats-new-visual-studio-2017)
- [Novedades de Visual Studio 2019](/visualstudio/ide/whats-new-visual-studio-2019)
- [ASP.NET](/aspnet)
- [Novedades de C++ en Visual Studio](/cpp/what-s-new-for-visual-cpp-in-visual-studio)
