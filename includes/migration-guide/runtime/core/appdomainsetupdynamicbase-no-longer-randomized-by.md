---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621413"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase ya no es aleatorio debido a UseRandomizedStringHashAlgorithm

#### <a name="details"></a>Detalles

Antes de .NET Framework 4.6, el valor de <xref:System.AppDomainSetup.DynamicBase> era aleatorio entre los dominios de aplicación, o bien entre los procesos si UseRandomizedStringHashAlgorithm estaba habilitado en el archivo de configuración de la aplicación. A partir de .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> devolverá un resultado estable entre otras instancias de una aplicación en ejecución y entre otros dominios de aplicación. Las bases dinámicas seguirán siendo diferentes para cada aplicación; este cambio solo quita el elemento de nomenclatura aleatorio para otras instancias de la misma aplicación.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que habilitar <code>UseRandomizedStringHashAlgorithm</code> no dará como resultado que <xref:System.AppDomainSetup.DynamicBase> sea aleatorio. Si se necesita una base aleatoria, se debe generar en el código de la aplicación, en lugar de hacerlo a través de esta API.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
