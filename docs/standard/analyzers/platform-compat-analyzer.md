---
title: Analizador de compatibilidad de plataformas
description: Un analizador de Roslyn que puede ayudar a detectar problemas de compatibilidad de plataformas en aplicaciones y bibliotecas multiplataforma.
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406592"
---
# <a name="platform-compatibility-analyzer"></a>Analizador de compatibilidad de plataformas

Probablemente ha oído hablar del lema de "One .NET": una única plataforma unificada para crear cualquier tipo de aplicación. El SDK de .NET 5.0 incluye ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin y ML.NET, y agregará compatibilidad con más plataformas a lo largo del tiempo. .NET 5.0 se esfuerza por proporcionar una experiencia en la que no tenga que preocuparse de los distintos tipos de .NET, pero no intenta abstraer completamente el sistema operativo (SO) subyacente. Podrá seguir llamando a las API específicas de la plataforma, por ejemplo, P/Invokes, WinRT o los enlaces de Xamarin para iOS y Android.

Pero el uso de API específicas de la plataforma en un componente significa que el código deje de funcionar en todas las plataformas. Necesitábamos una manera de detectar esto en tiempo de diseño para que los desarrolladores obtuvieran diagnósticos al utilizar accidentalmente API específicas de la plataforma. Para lograr este objetivo, .NET 5.0 presenta el [analizador de compatibilidad de plataformas](/visualstudio/code-quality/ca1416) y API complementarias para ayudar a los desarrolladores a identificar y usar las API específicas de la plataforma cuando sea necesario.
Entre las nuevas API se incluyen:

- <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> para anotar las API como específicas de la plataforma y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> para anotar las API como no compatibles en un sistema operativo determinado. Estos atributos pueden incluir opcionalmente el número de versión y ya se han aplicado a algunas API específicas de la plataforma en las bibliotecas .NET básicas.
- Los métodos estáticos `Is<Platform>()` y `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` en la clase <xref:System.OperatingSystem?displayProperty=nameWithType> para llamar a API específicas de la plataforma de forma segura. Por ejemplo, se puede usar <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> para proteger una llamada a una API específica de Windows y se puede usar <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() para proteger una llamada API específica de Windows con control de versiones. Consulte estos [ejemplos](#guard-platform-specific-apis-with-guard-methods) sobre cómo se pueden usar estos métodos como protecciones de las referencias de API específicas de la plataforma.

> [!TIP]
> El analizador de compatibilidad de plataformas actualiza y reemplaza la característica de [detección de problemas multiplataforma](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) del [analizador de API de .NET](../../standard/analyzers/api-analyzer.md).

## <a name="prerequisites"></a>Requisitos previos

El analizador de compatibilidad de plataformas es uno de los analizadores de calidad de código de Roslyn. A partir de .NET 5.0, estos analizadores se [incluyen con el SDK de .NET](../../fundamentals/productivity/code-analysis.md). El analizador de compatibilidad de plataformas está habilitado de forma predeterminada solo para los proyectos que tienen como destino `net5.0` o una versión posterior. Sin embargo, puede [habilitar](/visualstudio/code-quality/ca1416.md#configurability) para los proyectos que tienen como destino otras plataformas.

## <a name="how-the-analyzer-determines-platform-dependency"></a>Cómo determina el analizador la dependencia de plataformas

- Una **API sin atributos** se considera que funciona en **todas las plataformas de sistema operativo**.
- Una API marcada con `[SupportedOSPlatform("platform")]` solo se considera portable a la `platform` del sistema operativo especificado.
  - El atributo se puede aplicar varias veces para indicar la **compatibilidad con varias plataformas** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).
  - El analizador generará una **advertencia** si se hace referencia a las API específicas de la plataforma sin un **contexto de plataforma** adecuado:
    - **Produce una advertencia** si el proyecto no tiene como destino la plataforma compatible (por ejemplo, una llamada de API específica de Windows y los destinos del proyecto `<TargetFramework>net5.0-ios14.0</TargetFramework>`).
    - **Advierte** si el proyecto tiene varios destinos (`<TargetFramework>net5.0</TargetFramework>`).
    - **No advierte** si se hace referencia a la API específica de la plataforma dentro de un proyecto destinado a cualquiera de las **plataformas especificadas** (por ejemplo, para una llamada de API específica de Windows y el proyecto tiene como destino `<TargetFramework>net5.0-windows</TargetFramework>`).
    - **No advierte** si la llamada API específica de la plataforma está protegida por los métodos de comprobación de plataforma correspondientes (por ejemplo, `if(OperatingSystem.IsWindows())`).
    - **No advierte** si se hace referencia a la API específica de la plataforma desde el mismo contexto específico de la plataforma (**el sitio de llamada también tiene un atributo** con `[SupportedOSPlatform("platform")`).
- Una API marcada con `[UnsupportedOSPlatform("platform")]` se considera no compatible solo en la `platform` del sistema operativo especificado, pero se admite para todas las demás plataformas.
  - El atributo se puede aplicar varias veces con diferentes plataformas, por ejemplo, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.
  - El analizador genera una **advertencia** solo si la `platform` es efectiva para el sitio de llamada:
    - **Advierte** si el proyecto tiene como destino la plataforma que se atribuye como no compatible (por ejemplo, si la API tiene el atributo `[UnsupportedOSPlatform("windows")]` y el sitio de llamada tiene como destino `<TargetFramework>net5.0-windows</TargetFramework>`).
    - **Advierte** si el proyecto tiene varios destinos y el `platform` está incluido en el grupo de elementos predeterminado de [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props), o la `platform` se incluye manualmente en el grupo de elementos `MSBuild` \<SupportedPlatform>:

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - **No advierte** si está creando una aplicación que no tiene como destino la plataforma no compatible o que tiene varios destinos, y la plataforma no se incluye en el grupo de elementos predeterminados de [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props).
- Se puede crear una instancia de ambos atributos con o sin números de versión como parte del nombre de la plataforma.
  - Los números de versión están en el formato de `major.minor[.build[.revision]]`; `major.minor` es obligatorio y las partes `build` y `revision` son opcionales. Por ejemplo, "Windows 7.0" indica la versión 7.0 de Windows, pero "Windows" se interpreta como Windows 0.0.

Para más información, consulte los [ejemplos de cómo funcionan los atributos y qué diagnósticos causan](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).

### <a name="advanced-scenarios-for-combining-attributes"></a>Escenarios avanzados para combinar atributos

- Si hay una combinación de los atributos `[SupportedOSPlatform]` y `[UnsupportedOSPlatform]`, todos los atributos se agrupan por identificador de plataforma de sistema operativo:
  - **Lista Solo compatibles**. Si la versión más antigua de cada plataforma de sistema operativo es un atributo `[SupportedOSPlatform]`, se considera que la API solo es compatible con las plataformas de la lista y no es compatible con todas las demás plataformas. Los atributos de `[UnsupportedOSPlatform]` opcionales para cada plataforma solo pueden tener una versión más alta de la versión mínima admitida, lo que indica que la API se ha quitado a partir de la versión especificada.

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - **Lista Solo no compatibles** Si la versión más antigua de cada plataforma de sistema operativo es un atributo `[UnsupportedOSPlatform]`, se considera que la API no es compatible solo con las plataformas de la lista y es compatible con todas las demás plataformas. La lista podría tener el atributo `[SupportedOSPlatform]` con la misma plataforma pero con una versión superior, lo que indica que la API se admite a partir de esa versión.
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - **Lista de incoherentes**: Si la versión más antigua de algunas plataformas es `[SupportedOSPlatform]` mientras es `[UnsupportedOSPlatform]` para otras plataformas, se considera incoherente, lo que no se admite para el analizador.
  - Si las versiones más bajas de los atributos `[SupportedOSPlatform]` y `[UnsupportedOSPlatform]` son iguales, el analizador considera la plataforma como parte de la **lista Solo compatibles**.
- Los atributos de plataforma se pueden aplicar a tipos, miembros (métodos, campos, propiedades y eventos) y ensamblados con un nombre de plataforma o versión diferentes.
  - Los atributos aplicados en el `target` de nivel superior afectan a todos sus miembros y tipos.
  - Solo se aplican los atributos de nivel secundario si se adhieren a la regla de "las anotaciones secundarias pueden limitar la compatibilidad de plataformas, pero no pueden ampliarla".
    - Cuando el elemento primario tiene la lista **Solo compatibles**, los atributos de los miembros secundarios no podían agregar una nueva compatibilidad con la plataforma, ya que podría extenderse el soporte primario; una nueva compatibilidad con la plataforma solo se puede agregar al propio elemento primario. Pero puede tener el atributo `Supported` para la misma plataforma con versiones posteriores, ya que esto limitará la compatibilidad. También puede tener el atributo `Unsupported` con la misma plataforma, lo que también limitará la compatibilidad con los elementos primarios.
    - Cuando el elemento primario tiene una lista **Solo no compatibles**, los atributos de miembro secundario podrían agregar una nueva compatibilidad con la plataforma, ya que sería la compatibilidad con el elemento primario de restricción, pero no puede tener el atributo `Supported` para la misma plataforma que en el elemento primario, lo que ampliaría el soporte primario. La compatibilidad con la misma plataforma solo se puede agregar al nivel primario en el que se aplicó el atributo `Unsupported` original.
  - Si se aplica `[SupportedOSPlatform("platformVersion")]` más de una vez para una API con el mismo nombre de `platform`, el analizador solo tiene en cuenta la que tiene la versión mínima.
  - Si se aplica `[UnsupportedOSPlatform("platformVersion")]` más de dos veces para una API con el mismo nombre de `platform`, el analizador solo tiene en cuenta las dos con las versiones mínimas.
  
  > [!NOTE]
  > No se espera que una API admitida inicialmente pero no admitida (retirada) en una versión posterior pueda volver a admitirse en una versión incluso posterior.

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a>Ejemplos de cómo funcionan los atributos y qué diagnóstico producen

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a>Control de advertencias detectadas

La manera recomendada de tratar estos diagnósticos es asegurarse de que solo se llama a las API específicas de la plataforma cuando se ejecuta en una plataforma adecuada. A continuación se muestran las opciones que puede usar para solucionar las advertencias; elija lo que sea más adecuado para su situación:

- **Proteja la llamada**. Para ello, puede llamar condicionalmente al código en tiempo de ejecución. Compruebe si se está ejecutando en una `Platform` deseada mediante el uso de uno de los métodos de comprobación de plataforma, por ejemplo, `OperatingSystem.Is<Platform>()` o `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.

- **Marque el sitio de llamada como específico de la plataforma**. También puede elegir marcar sus propias API como específicas de la plataforma y, por tanto, reenviar los requisitos a los autores de llamadas de forma eficaz. Marque el método o tipo contenedor o todo el ensamblado con los mismos atributos que la llamada dependiente de la plataforma a la que se hace referencia. [Ejemplos](#mark-call-site-as-platform-specific).

- **Aserción del sitio de llamada con comprobación de la plataforma**. O bien, si no quiere sobrecargar una instrucción `if` adicional en tiempo de ejecución, llame a <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> en su lugar: [Ejemplo](#assert-the-call-site-with-platform-check).

- **Elimine el código**. Por lo general, no lo que desea porque significa que perderá fidelidad cuando los usuarios de Windows usen el código. En los casos en los que existe una alternativa multiplataforma, es probable que sea mejor usarlo en las API específicas de la plataforma.

- **Suprima la advertencia**. También puede suprimir la advertencia, ya sea mediante editor.config o `#pragma warning disable ca1416`. Sin embargo, esta opción debe ser el último recurso cuando se usan API específicas de la plataforma.

### <a name="guard-platform-specific-apis-with-guard-methods"></a>Restricción de API específicas de la plataforma con métodos de restricción

El nombre de la plataforma del método de restricción debe coincidir con el nombre de la plataforma de API dependiente de la plataforma que llama. Si la cadena de la plataforma de la API de llamada incluye la versión:

- En el caso del atributo `[SupportedOSPlatform("platformVersion")]`, la `version` de la plataforma del método de restricción debe ser mayor o igual que la `Version` de la plataforma que realiza la llamada.
- En el caso del atributo `[UnsupportedOSPlatform("platformVersion")]`, la `version` de la plataforma del método de restricción debe ser menor o igual que la `Version` de la plataforma que realiza la llamada.

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- Si necesita restringir un código destinado a netstandard o netcoreapp, donde las nuevas API de <xref:System.OperatingSystem> no están disponibles, se puede usar la API de <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> y el analizador respetará su cumplimiento. Pero no es tan optimizado como las nuevas API agregadas en <xref:System.OperatingSystem>. En caso de que la plataforma no se admita en la estructura <xref:System.Runtime.InteropServices.OSPlatform>, puede usar <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType> ("plataforma"), que también respeta el analizador.

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a>Marcado del sitio de llamada como específico de la plataforma

Los nombres de la plataforma deben coincidir con la API dependiente de la plataforma que realiza la llamada. Si la cadena de la plataforma incluye una versión:

- En el caso del atributo `[SupportedOSPlatform("platformVersion")]`, la `version` de la plataforma del sitio de llamada debe ser mayor o igual que la `Version` de la plataforma que realiza la llamada.
- En el caso del atributo `[UnsupportedOSPlatform("platformVersion")]`, la `version` de la plataforma del sitio de llamada debe ser menor o igual que la `Version` de la plataforma que realiza la llamada.

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a>Aserción del sitio de llamada con comprobación de la plataforma

Todas las comprobaciones condicionales que se usan en los [ejemplos de restricción de la plataforma](#guard-platform-specific-apis-with-guard-methods) también se pueden usar como condición para <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a>Consulte también

- [Nombres de plataformas de destino en .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [Anotación de API específicas de la plataforma y detección de su uso](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [Anotación de las API como no compatibles en plataformas específicas](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [Analizador de compatibilidad de plataformas CA1416](/visualstudio/code-quality/ca1416)
- [Analizador de API en .NET](../../standard/analyzers/api-analyzer.md)
