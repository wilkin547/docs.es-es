---
ms.openlocfilehash: ffafb0c9e3982dd168f907d32a8f59f96e6040d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804561"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>Se puede producir un error MSB4062 al compilar un archivo edmx de Entity Framework con Visual Studio 2013 si se usan las tareas EntityDeploySplit o EntityClean

|   |   |
|---|---|
|Detalles|Las herramientas de MSBuild 12.0 (incluidas en Visual Studio 2013) cambiaron las ubicaciones de los archivos de MSBuild, lo que invalida los archivos de destinos antiguos de Entity Framework. El resultado es un error de las tareas <code>EntityDeploySplit</code> y <code>EntityClean</code> debido a que no pueden buscar <code>Microsoft.Data.Entity.Build.Tasks.dll</code>. Tenga en cuenta que esta interrupción se produce como consecuencia del cambio en un conjunto de herramientas (MSBuild/VS), no en .NET Framework. Solo se producirá al actualizar las herramientas de desarrollo, no al actualizar únicamente .NET Framework.|
|Sugerencia|Los archivos de destinos de Entity Framework se corrigieron para funcionar con el nuevo diseño de MSBuild a partir de .NET Framework 4.6. Este problema se soluciona actualizando a esta versión de .NET Framework. También es posible usar [esta solución alternativa](https://stackoverflow.com/a/24249247/131944) para aplicar la revisión directamente a los archivos de destinos.|
|Ámbito|Major|
|Versión|4.5.1|
|Tipo|Redestinación|
