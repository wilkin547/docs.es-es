---
title: 'Cambio importante: Cambio de valor de TextInfo.ListSeparator'
description: Obtenga información sobre el cambio importante de .NET 5.0 en el que el valor predeterminado de TextInfo.ListSeparator se ha cambiado entre las versiones 5.0 y 5.0.1.
ms.date: 12/10/2020
ms.openlocfilehash: 720d46c1908bcd70812f575a90f580470dbc7f32
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596422"
---
# <a name="textinfolistseparator-values-changed"></a>Cambio de los valores de TextInfo.ListSeparator

Los valores predeterminados de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para las distintas referencias culturales han cambiado en todos los sistemas operativos.

## <a name="change-description"></a>Descripción del cambio

En .NET 5.0.0, como parte del [cambio de NLS a bibliotecas de ICU](icu-globalization-api.md), se cambiaron los valores predeterminados de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para las distintas referencias culturales en Windows. Los valores de separador decimal, obtenidos de los componentes internacionales para Unicode (ICU), se usaban como valores de <xref:System.Globalization.TextInfo.ListSeparator>. En Linux y macOS, no se produjo ningún cambio en los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>, es decir, se siguieron usando valores de separador decimal.

Para todos los sistemas operativos en .NET 5.0.1 y versiones posteriores, los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> son equivalentes a los valores que se obtendrían de NLS. En Windows, esto significa que los valores son equivalentes a los de .NET Framework y .NET Core 1.0 a 3.1. Para Linux y macOS, los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> coinciden ahora coinciden con los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para Windows.

En la tabla siguiente se resumen los cambios en los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>.

| | .NET Framework<br/>.NET Core 1.0 a 3.1 | .NET 5.0 | .NET 5.0.1 |
-|-|-|-
| **Windows** | Obtenidos de NLS | Separador decimal de ICU<br/>(Se puede volver a NLS) | Equivalentes a NLS |
| **Linux y macOS** | Separador decimal de ICU | Separador decimal de ICU | Equivalentes a NLS |

## <a name="version-introduced"></a>Versión introducida

5.0.1

## <a name="reason-for-change"></a>Motivo del cambio

Los desarrolladores informaron de que, al usar la propiedad <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> para analizar archivos de valores separados por comas (CSV), los nuevos valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> interrumpían ese análisis.

## <a name="recommended-action"></a>Acción recomendada

Si su código se basa en los valores de separador decimal anteriores, puede codificar los valores de <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> deseados.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
