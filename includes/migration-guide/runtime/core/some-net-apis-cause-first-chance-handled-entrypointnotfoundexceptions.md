---
ms.openlocfilehash: 6431f3b4d0983c44629e4fe760c75adcc277ddd4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496575"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Algunas API de .NET generan primeras excepciones EntryPointNotFoundExceptions (controladas)

#### <a name="details"></a>Detalles

En .NET Framework 4.5, un pequeño número de métodos de .NET comenzaron a iniciar primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=fullName>. Estas primeras excepciones se controlaban dentro de .NET Framework, pero podían interrumpir la automatización de las pruebas que no las esperasen. Estas mismas API interrumpen algunos escenarios de ApiVerifier con el elemento HighVersionLie habilitado.

#### <a name="suggestion"></a>Sugerencia

Este error puede evitarse actualizando a .NET Framework 4.5.1. Como alternativa, se puede actualizar la automatización de pruebas para que no se interrumpa con las primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=fullName>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)>

<!--

#### Affected APIs

- `M:System.Diagnostics.Debug.Assert(System.Boolean)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)`
- `M:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])`
- `M:System.Xml.Serialization.XmlSerializer.#ctor(System.Type)`

-->
