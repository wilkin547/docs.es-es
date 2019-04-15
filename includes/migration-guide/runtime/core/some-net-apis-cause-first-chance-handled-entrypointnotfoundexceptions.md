---
ms.openlocfilehash: b23f06ec5b27fbd7976a4b62ba6105c607eaee39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236702"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Algunas API de .NET generan primeras excepciones EntryPointNotFoundExceptions (controladas)

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, un pequeño número de métodos de .NET comenzaron a iniciar primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=name>. Estas primeras excepciones se controlaban dentro de .NET Framework, pero podían interrumpir la automatización de las pruebas que no las esperasen. Estas mismas API interrumpen algunos escenarios de ApiVerifier con el elemento HighVersionLie habilitado.|
|Sugerencia|Este error puede evitarse actualizando a .NET Framework 4.5.1. Como alternativa, se puede actualizar la automatización de pruebas para que no se interrumpa con las primeras excepciones <xref:System.EntryPointNotFoundException?displayProperty=name>.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li></ul>|
