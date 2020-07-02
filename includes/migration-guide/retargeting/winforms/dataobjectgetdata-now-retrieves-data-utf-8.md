---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616083"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData ahora recupera los datos como UTF-8

#### <a name="details"></a>Detalles

Para las aplicaciones que tienen como destino .NET Framework 4 o que se ejecutan en .NET Framework 4.5.1 o versiones anteriores, `DataObject.GetData` recupera los datos con formato HTML como una cadena ASCII. Como resultado, los caracteres que no son ASCII (cuyos códigos ASCII son mayores que 0x7F) se representan mediante dos caracteres aleatorios.<p/>Para aplicaciones que tienen como destino .NET Framework 4.5 o posterior y que se ejecutan en .NET Framework 4.5.2, `DataObject.GetData` recupera datos con formato HTML como UTF-8, que representa correctamente caracteres mayores que 0x7F.

#### <a name="suggestion"></a>Sugerencia

Si implementó una solución alternativa para el problema de codificación mediante cadenas con formato HTML (por ejemplo, mediante la codificación explícita de la cadena HTML recuperada del Portapapeles y su transferencia a <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) y va a redestinar la aplicación de la versión 4 a la versión 4.5, esa solución alternativa se debe eliminar. Si por algún motivo se necesita el comportamiento anterior, la aplicación se puede destinar a .NET Framework 4.0 para obtenerlo.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
