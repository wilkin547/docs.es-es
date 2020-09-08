---
ms.openlocfilehash: 018c99d60dc8926cae2682dc9c035e25fba711e5
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496444"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>Generación de código incorrecto al pasar y comparar valores UInt16

#### <a name="details"></a>Detalles

Debido a los cambios introducidos en .NET Framework 4.7, en algunos casos el código generado por el compilador JIT en las aplicaciones que se ejecutan en .NET Framework 4.7 compara dos valores <code>T:System.UInt16</code> de manera incorrecta. Para obtener más información, vea [Issue #11508: Silent bad codegen when passing and comparing ushort args](https://github.com/dotnet/coreclr/issues/11508) (Problema 11508: generación de código incorrecta en modo silencioso al pasar y comparar argumentos ushort) en GitHub.com.

#### <a name="suggestion"></a>Sugerencia

Si se producen problemas en la comparación de valores de 16 bits sin signo en .NET Framework 4.7, actualice a .NET Framework 4.7.1.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
