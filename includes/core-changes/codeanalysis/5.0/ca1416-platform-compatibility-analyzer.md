---
ms.openlocfilehash: cd7860a5dfff1eb595625665382689733cffc94a
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90721279"
---
### <a name="ca1416-platform-compatibility"></a>CA1416: Compatibilidad de plataformas

La regla [CA1416](/visualstudio/code-quality/ca1416) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para las llamadas a API específicas de la plataforma desde sitios de llamada que no comprueban el sistema operativo.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA1416](/visualstudio/code-quality/ca1416). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación. La regla CA1416 le notifica cuando está usando API específicas de la plataforma desde lugares donde no se comprueba el contexto de la plataforma.

La regla [CA1416](/visualstudio/code-quality/ca1416), el analizador de compatibilidad de la plataforma, funciona conjuntamente con otras características que son nuevas en .NET 5.0. .NET 5.0 presenta <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, que permiten especificar las plataformas en las que una API *se admite* o *no se admite*. En ausencia de estos atributos, se supone que se admite una API en todas las plataformas. Estos atributos se han aplicado a muchas API específicas de la plataforma en las bibliotecas principales de .NET.

En los proyectos que tienen como destino las plataformas para las que no están disponibles las API que usan, la regla [CA1416](/visualstudio/code-quality/ca1416) marca cualquier llamada API específica de la plataforma en la que no se comprueba el contexto de la plataforma. La mayoría de las API que ahora están representadas con los atributos <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> y <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> producen excepciones <xref:System.PlatformNotSupportedException> cuando se invocan en un sistema operativo no compatible. Ahora que estas API están marcadas como específicas de la plataforma, la regla [CA1416](/visualstudio/code-quality/ca1416) ayuda a evitar excepciones <xref:System.PlatformNotSupportedException> en tiempo de ejecución mediante la adición de comprobaciones del sistema operativo a los sitios de llamada.

#### <a name="examples"></a>Ejemplos

- El método <xref:System.Console.Beep(System.Int32,System.Int32)?displayProperty=nameWithType> solo se admite en Windows (está decorado con el atributo `[SupportedOSPlatform("windows")]`). El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto [tiene como destino](../../../../docs/standard/frameworks.md) `net5.0` (pero no `net5.0-windows`). Para ver las acciones que puede realizar para evitar la advertencia, consulte la sección [Acción recomendada](#recommended-action).

  ```csharp
  public void PlayCMajor()
  {
      Console.Beep(261, 1000);
  }
  ```

- El método <xref:System.Drawing.Image.FromFile(System.String)?displayProperty=nameWithType> no se admite en el explorador (está decorado con el atributo `[UnsupportedOSPlatform("browser")]`). El código siguiente generará una advertencia CA1416 en tiempo de compilación si el proyecto usa el SDK de WebAssembly de Blazor (`<Project Sdk="Microsoft.NET.Sdk.BlazorWebAssembly">`) o si incluye `browser` como plataforma compatible (`<SupportedPlatform Include="browser" />`) en el archivo del proyecto.

  ```csharp
  public void CreateImage()
  {
      Image newImage = Image.FromFile("SampImag.jpg");
  }
  ```

#### <a name="version-introduced"></a>Versión introducida

5.0 RC1

#### <a name="recommended-action"></a>Acción recomendada

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

También puede marcar la API como específica de la plataforma, en cuyo caso la tarea de comprobar los requisitos corresponde a los autores de las llamadas. Puede marcar métodos o tipos específicos, o un ensamblado completo.

```csharp
[SupportedOSPlatform("windows")]
public void PlayCMajor()
{
    Console.Beep(261, 1000);
}
```

Si no quiere corregir todos los sitios de llamada, puede elegir una de las siguientes opciones para suprimir la advertencia:

- Para suprimir la regla CA1416, puede usar `#pragma` o la marca del compilador [-nowarn](../../../../docs/csharp/language-reference/compiler-options/nowarn-compiler-option.md), o bien puede [establecer la gravedad de la regla](../../../../docs/fundamentals/productivity/configure-code-analysis-rules.md#suppress-violations) en `none` en un archivo .editorconfig.

  ```csharp
  public void PlayCMajor()
  {
  #pragma warning disable CA1416
      Console.Beep(261, 1000);
  #pragma warning restore CA1416
  }
  ```

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Categoría

- Análisis de código
- Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

Para la plataforma Windows:

- Todas las API que se enumeran en <https://github.com/dotnet/designs/blob/master/accepted/2020/windows-specific-apis/windows-specific-apis.md>.
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>

Para la plataforma de WebAssembly de Blazor:

- Todas las API que se enumeran en <https://github.com/dotnet/runtime/issues/41087>.

<!--

#### Affected APIs

- ``

-->

#### <a name="see-also"></a>Consulte también

- [CA1416: Validación de la compatibilidad con las plataformas](/visualstudio/code-quality/ca1416)
- [Analizador de API en .NET](../../../../docs/standard/analyzers/api-analyzer.md)
