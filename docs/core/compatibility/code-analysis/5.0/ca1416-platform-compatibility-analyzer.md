---
title: 'Cambio importante: CA1416: Compatibilidad de plataformas'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA1416.
ms.date: 09/29/2020
ms.openlocfilehash: b1d8c9115d5ad0bc97b6ba68cc058de195d01584
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874360"
---
# <a name="warning-ca1416-platform-compatibility"></a>Advertencia CA1416: Compatibilidad de plataformas

La regla [CA1416](/visualstudio/code-quality/ca1416) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para las llamadas a API específicas de la plataforma desde sitios de llamada que no comprueban el sistema operativo.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA1416](/visualstudio/code-quality/ca1416). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación. La regla CA1416 le notifica cuando está usando API específicas de la plataforma desde lugares donde no se comprueba el contexto de la plataforma.

La regla [CA1416](/visualstudio/code-quality/ca1416), el analizador de compatibilidad de la plataforma, funciona conjuntamente con otras características que son nuevas en .NET 5.0. .NET 5 presenta <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, que permiten especificar las plataformas en las que una API *se admite* o *no se admite*. En ausencia de estos atributos, se supone que se admite una API en todas las plataformas. Estos atributos se han aplicado a muchas API específicas de la plataforma en las bibliotecas principales de .NET.

En los proyectos que tienen como destino las plataformas para las que no están disponibles las API que usan, la regla [CA1416](/visualstudio/code-quality/ca1416) marca cualquier llamada API específica de la plataforma en la que no se comprueba el contexto de la plataforma. La mayoría de las API que ahora están representadas con los atributos <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> producen excepciones <xref:System.PlatformNotSupportedException> cuando se invocan en un sistema operativo no compatible. Ahora que estas API están marcadas como específicas de la plataforma, la regla [CA1416](/visualstudio/code-quality/ca1416) ayuda a evitar excepciones <xref:System.PlatformNotSupportedException> en tiempo de ejecución mediante la adición de comprobaciones del sistema operativo a los sitios de llamada.

## <a name="examples"></a>Ejemplos

- El método <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> solo se admite en Windows y está decorado con el atributo `[SupportedOSPlatform("windows")]`. El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto [tiene como destino](../../../../standard/frameworks.md) `net5.0` (pero no `net5.0-windows`). Para ver las acciones que puede realizar para evitar la advertencia, consulte la sección [Acción recomendada](#recommended-action).

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- El método <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> no se admite en el explorador y está decorado con el atributo `[UnsupportedOSPlatform("browser")]`. El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto admite la plataforma del explorador.

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

  > [!TIP]
  >
  > - Los proyectos de Blazor WebAssembly y los de la biblioteca de clases de Razor incluyen compatibilidad con los exploradores automáticamente.
  > - Para agregar de forma manual el explorador como una plataforma compatible para el proyecto, agregue la entrada siguiente al archivo de proyecto:
  >
  >  ```xml
  >  <ItemGroup>
  >    <SupportedPlatform Include="browser" />
  >  </ItemGroup>
  >  ```

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Asegúrese de que solo se llama a las API específicas de la plataforma cuando el código se ejecuta en la plataforma adecuada. Puede comprobar el sistema operativo actual mediante uno de los métodos `Is<Platform>` de la clase <xref:System.OperatingSystem?displayProperty=nameWithType> (por ejemplo, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType>) antes de llamar a una API específica de la plataforma.

Puede usar uno de los métodos `Is<Platform>` en la condición de una instrucción `if`:

```csharp
public void PlayCMajor()
{
    if (OperatingSystem.IsWindows())
    {
        Console.Beep(261, 1000);
    }
}
```

O bien, si no quiere sobrecargar una instrucción `if` adicional en tiempo de ejecución, llame a <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> en su lugar:

```csharp
public void PlayCMajor()
{
    Debug.Assert(OperatingSystem.IsWindows());
    Console.Beep(261, 1000);
}
```

Si va a crear una biblioteca, puede marcar la API como específica de la plataforma. En este caso, la carga de los requisitos de comprobación recae en los autores de las llamadas. Puede marcar métodos o tipos específicos, o un ensamblado completo.

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

Si no quiere corregir todos los sitios de llamada, puede elegir una de las siguientes opciones para suprimir la advertencia:

- Para suprimir la regla CA1416, puede usar `#pragma` o la marca del compilador [**DisabledWarnings**](../../../../csharp/language-reference/compiler-options/errors-warnings.md#disabledwarnings), o bien [establecer la gravedad de la regla](../../../../fundamentals/code-analysis/configuration-options.md#severity-level) en `none` en un archivo .editorconfig.

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>API afectadas

Para la plataforma Windows:

- Todas las API que se enumeran en <https://github.com/dotnet/designs/blob/main/accepted/2020/windows-specific-apis/windows-specific-apis.md>.
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

Para la plataforma de WebAssembly de Blazor:

- Todas las API que se enumeran en <https://github.com/dotnet/runtime/issues/41087>.

<!--

### Affected APIs

- ``

### Category

- Code analysis
- Core .NET libraries

-->

## <a name="see-also"></a>Consulte también

- [CA1416: Validación de la compatibilidad con las plataformas](/visualstudio/code-quality/ca1416)
- [Analizador de API en .NET](../../../../standard/analyzers/api-analyzer.md)
