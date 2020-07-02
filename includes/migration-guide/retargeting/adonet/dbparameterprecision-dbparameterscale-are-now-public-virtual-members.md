---
ms.openlocfilehash: 063e10b0310880af255793215a80a5529a5db0ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616111"
---
### <a name="dbparameterprecision-and-dbparameterscale-are-now-public-virtual-members"></a>DbParameter.Precision y DbParameter.Scale son ahora miembros virtuales públicos

#### <a name="details"></a>Detalles

<xref:System.Data.Common.DbParameter.Precision> y <xref:System.Data.Common.DbParameter.Scale> se implementan como propiedades públicas virtuales. Reemplazan las implementaciones de interfaz explícitas correspondientes, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision> y <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale>.

#### <a name="suggestion"></a>Sugerencia

Al volver a compilar un proveedor de base de datos de ADO.NET, estas diferencias necesitarán que se aplique la palabra clave "override" a las propiedades Scale y Precision. Esto solo es necesario al volver a compilar los componentes; los archivos binarios existentes continuarán funcionando.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.5.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Data.Common.DbParameter.Precision?displayProperty=nameWithType>
- <xref:System.Data.Common.DbParameter.Scale?displayProperty=nameWithType>
