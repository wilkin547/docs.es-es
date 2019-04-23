---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235837"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>Los datos de sql_variant usan la intercalación de sql_variant en lugar de la intercalación de base de datos

|   |   |
|---|---|
|Detalles|Los datos de <code>sql_variant</code> utilizan la intercalación de <code>sql_variant</code> en lugar de la intercalación de base de datos.|
|Sugerencia|Este cambio soluciona posibles daños en los datos si la intercalación de la base de datos difiere de la intercalación de <code>sql_variant</code>. Las aplicaciones que se basan en datos dañados pueden experimentar errores.|
|Ámbito|Transparente|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
