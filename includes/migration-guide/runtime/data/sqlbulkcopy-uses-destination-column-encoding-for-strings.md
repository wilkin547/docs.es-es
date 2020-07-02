---
ms.openlocfilehash: 1329a86db4227f75dfba7c50bbbdc2fc23099528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620599"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy usa la codificación de columna de destino para las cadenas

#### <a name="details"></a>Detalles

Al insertar datos en una columna, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> utiliza la codificación de la columna de destino en lugar de la codificación predeterminada para los tipos <code>VARCHAR</code> y <code>CHAR</code>. Este cambio elimina la posibilidad de que se produzcan daños en los datos al usar la codificación predeterminada cuando la columna de destino no utiliza la codificación predeterminada. En raras ocasiones, una aplicación existente podría iniciar una excepción SqlException si el cambio de codificación genera datos que son demasiado grandes como para caber en la columna de destino.

#### <a name="suggestion"></a>Sugerencia

Espere que <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> ya no dañe los datos debido a diferencias de codificación. Si se copian cadenas cerca del límite de tamaño de la columna de destino, puede que sea necesario codificar previamente los datos (que se van a copiar para comprobar que caben en la columna de destino) o capturar las excepciones <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)></li></ul>|
