---
ms.openlocfilehash: 78faa5f4008b41bac75c94ce09a58c8227e5b485
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614668"
---
### <a name="currentculture-and-currentuiculture-flow-across-tasks"></a>CurrentCulture y CurrentUICulture fluyen entre tareas

#### <a name="details"></a>Detalles

A partir de la versión 4.6 de .NET Framework, <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> se almacenan en el <xref:System.Threading.ExecutionContext?displayProperty=fullName> del subproceso, que fluye entre las operaciones asincrónicas. Esto significa que los cambios en <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> se verán reflejados en las tareas que después se ejecutan de forma asincrónica. Esto difiere del comportamiento de las versiones anteriores de .NET Framework (en las que se restablecían <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> en todas las tareas asincrónicas).

#### <a name="suggestion"></a>Sugerencia

Las aplicaciones afectadas por este cambio pueden solucionar el problema si se establece explícitamente el valor <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> deseado como la primera operación de una tarea asincrónica. Como alternativa, el comportamiento anterior (de que <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName> no fluyan) se puede incluir si se establece el modificador de compatibilidad siguiente:

```csharp
AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);
```

WPF ha solucionado este problema en .NET Framework 4.6.2. También se ha corregido en .NET Framework 4.6, 4.6.1 a través de [KB 3139549](https://support.microsoft.com/kb/3139549). Las aplicaciones destinadas a .NET Framework 4.6 o una versión posterior obtendrán automáticamente el comportamiento correcto en las aplicaciones de WPF: <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=fullName>/<xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=fullName>) se conservará entre las operaciones del distribuidor.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentCulture?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.CurrentUICulture?displayProperty=nameWithType>
- <xref:System.Threading.Thread.CurrentUICulture?displayProperty=nameWithType>
