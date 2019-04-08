---
ms.openlocfilehash: 529d1b83c0637f705b725a64aa82e2c053bbfd19
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58467086"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>ContentDisposition DateTimes devuelve una cadena ligeramente diferente

|   |   |
|---|---|
|Detalles|Se han actualizado las representaciones de cadena de los elementos <xref:System.Net.Mime.ContentDisposition?displayProperty=name>, a partir de la versión 4.6, para que representen siempre el componente de hora de un elemento <xref:System.DateTime?displayProperty=name> con dos dígitos. La finalidad es cumplir con [RFC822](https://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). De este modo, <xref:System.Net.Mime.ContentDisposition.ToString> devuelve una cadena ligeramente diferente en escenarios de la versión 4.6 en los que uno de los elementos de hora de la disposición era anterior a las 10:00. Tenga en cuenta que los elementos ContentDisposition a veces se serializan convirtiéndolos en cadenas, por lo que debería revisarse cualquier operación <xref:System.Net.Mime.ContentDisposition.ToString>, serialización o llamada a GetHashCode.|
|Sugerencia|No espere que las representaciones de cadena de elementos ContentDisposition de otras versiones de .NET Framework se comparen correctamente entre sí. Vuelva a convertir las cadenas a elementos ContentDisposition, si fuera posible, antes de realizar una comparación.|
|Ámbito|Secundaria|
|Versión|4.6|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|

