---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538934"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a>CA2200: Reiniciar para mantener los detalles de la pila

La regla [CA2200](/visualstudio/code-quality/ca2200) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0. Genera una advertencia de compilación para cualquier bloque `catch` que vuelva a iniciar una excepción y la excepción se especifica de forma explícita en la instrucción `throw`.

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md). Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2200](/visualstudio/code-quality/ca2200). Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.

La regla CA2200 marca el código donde se vuelven a iniciar las excepciones y la variable de excepción se especifica en la instrucción `throw`. Cuando se inicia una excepción, parte de la información que contiene es el seguimiento de la pila. El seguimiento de la pila es una lista de la jerarquía de llamadas de método que comienza con el método que inicia la excepción y termina con el que la captura. Si se especifica una excepción en la instrucción `throw` y la excepción se vuelve a iniciar, el seguimiento de la pila se reinicia en el método actual y se pierde la lista de llamadas de método entre el método original que ha iniciado la excepción y el método actual. Para mantener la información de seguimiento de la pila original con la excepción, use la instrucción `throw` sin especificar la excepción.

El fragmento de código siguiente no genera una advertencia para la regla CA2200. Pero la línea comentada *desencadenaría* una infracción.

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a>Versión introducida

5.0 RC1

#### <a name="recommended-action"></a>Acción recomendada

- Vuelva a iniciar las excepciones sin especificar la excepción de forma explícita. Para obtener más información, vea [CA2200](/visualstudio/code-quality/ca2200).

- Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto. Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).

#### <a name="category"></a>Categoría

Análisis de código

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
