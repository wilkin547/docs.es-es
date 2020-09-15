---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065184"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a>CA2014: No usar stackalloc en los bucles

La regla [CA2014](/visualstudio/code-quality/ca2014) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para cualquier código de C# donde se usa una expresión [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) dentro de un bucle.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2014](/visualstudio/code-quality/ca2014). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2014 busca código de C# en el que se usa una [expresión stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) dentro de un bucle. [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) asigna memoria del marco de pila actual. La memoria no se libera hasta que se devuelve la llamada al método actual, lo que puede provocar desbordamientos de pila. Como las excepciones de desbordamiento de pila no se pueden detectar, la aplicación finalizará en caso de desbordamiento de pila.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="recommended-action"></a>Acción recomendada

- Evite usar [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) dentro de bucles. Asigne el bloque de memoria fuera de un bucle y vuelva a usarlo dentro del bucle. Para obtener más información, vea [CA2014](/visualstudio/code-quality/ca2014).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Categoría

Análisis de código

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
