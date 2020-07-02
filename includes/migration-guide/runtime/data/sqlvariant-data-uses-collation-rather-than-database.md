---
ms.openlocfilehash: d606fbc4048421bc572cfe3db2e06bbcd4529e25
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620605"
---
### <a name="sql_variant-data-uses-sql_variant-collation-rather-than-database-collation"></a>Los datos de sql_variant usan la intercalación de sql_variant en lugar de la intercalación de base de datos

#### <a name="details"></a>Detalles

Los datos de <code>sql_variant</code> utilizan la intercalación de <code>sql_variant</code> en lugar de la intercalación de base de datos.

#### <a name="suggestion"></a>Sugerencia

Este cambio soluciona posibles daños en los datos si la intercalación de la base de datos difiere de la intercalación de <code>sql_variant</code>. Las aplicaciones que se basan en datos dañados pueden experimentar errores.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Transparente|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
