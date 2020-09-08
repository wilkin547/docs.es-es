---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497835"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>ContentDisposition DateTimes devuelve una cadena ligeramente diferente

#### <a name="details"></a>Detalles

Se han actualizado las representaciones de cadena de los elementos <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>, a partir de la versión 4.6, para que representen siempre el componente de hora de un elemento <xref:System.DateTime?displayProperty=fullName> con dos dígitos. La finalidad es cumplir con [RFC822](https://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). De este modo, <xref:System.Net.Mime.ContentDisposition.ToString> devuelve una cadena ligeramente diferente en escenarios de la versión 4.6 en los que uno de los elementos de hora de la disposición era anterior a las 10:00. Tenga en cuenta que los elementos ContentDisposition a veces se serializan convirtiéndolos en cadenas, por lo que debería revisarse cualquier operación <xref:System.Net.Mime.ContentDisposition.ToString>, serialización o llamada a GetHashCode.

#### <a name="suggestion"></a>Sugerencia

No espere que las representaciones de cadena de elementos ContentDisposition de otras versiones de .NET Framework se comparen correctamente entre sí. Vuelva a convertir las cadenas a elementos ContentDisposition, si fuera posible, antes de realizar una comparación.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
