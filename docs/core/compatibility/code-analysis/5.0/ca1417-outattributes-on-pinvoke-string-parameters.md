---
title: 'Cambio importante: CA1417: OutAttribute en parámetros de cadena para P/Invoke'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA1417.
ms.date: 09/29/2020
ms.openlocfilehash: 74aa6dc867bc1eb62e32dd086dd6b43f62e7f01f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257835"
---
# <a name="warning-ca1417-outattribute-on-string-parameter-for-pinvoke"></a>Advertencia CA1417: OutAttribute en parámetros de cadena para P/Invoke

La regla [CA1417](/visualstudio/code-quality/ca1417) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para cualquier definición del método de [invocación de plataforma (P/Invoke)](../../../../standard/native-interop/pinvoke.md) donde se pasa un parámetro <xref:System.String> por valor y se marca con <xref:System.Runtime.InteropServices.OutAttribute>.

## <a name="change-description"></a>Descripción del cambio

A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA1417](/visualstudio/code-quality/ca1417). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA1417 marca las definiciones del método [P/Invoke](../../../../standard/native-interop/pinvoke.md) en las que un parámetro <xref:System.String> está marcado con el atributo <xref:System.Runtime.InteropServices.OutAttribute> y se pasa por valor. Por ejemplo:

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

El entorno de ejecución de .NET mantiene una tabla, denominada grupo de internos, que contiene una sola referencia a cada cadena literal única en un programa. Si una cadena internalizada marcada con <xref:System.Runtime.InteropServices.OutAttribute> se pasa por valor a un método P/Invoke, el entorno de ejecución se puede desestabilizar. Para obtener más información sobre la asignación al grupo interno de cadenas, vea los comentarios sobre <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

- Si necesita serializar los datos modificados de la cadena de vuelta al autor de la llamada, pase la cadena por referencia en su lugar.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- Si no necesita serializar los datos modificados de la cadena de vuelta al autor de la llamada, simplemente quite el elemento <xref:System.Runtime.InteropServices.OutAttribute>.

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  Para obtener más información, vea [CA1417](/visualstudio/code-quality/ca1417).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).

## <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
