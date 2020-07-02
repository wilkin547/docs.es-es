---
ms.openlocfilehash: ed526095459a48aa37b585dfed79cc12b9fb9e56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622141"
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

-<xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)></li></ul>|
