---
ms.openlocfilehash: 1654d58651bf14b0e7c21de2afa827634b7db858
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235901"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>La aplicación de secuencias de escape de System.Uri ahora es compatible con RFC 3986

|   |   |
|---|---|
|Detalles|La aplicación de secuencias de escape a los URI se ha modificado en .NET Framework 4.5 para que sea compatible con [RFC 3986](https://tools.ietf.org/html/rfc3986). Cambios concretos:<ul><li>El método <xref:System.Uri.EscapeDataString(System.String)?displayProperty=name> incluye los caracteres reservados entre caracteres de escape de con arreglo a RFC 3986.</li><li>El método <xref:System.Uri.EscapeUriString(System.String)?displayProperty=name> no incluye entre caracteres de escape los caracteres reservados.</li><li>El método <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> no inicia una excepción si encuentra una secuencia de escape no válida.</li><li>Los caracteres de escape no reservados no se incluyen en una secuencia de escape.</li></ul>|
|Sugerencia|<ul><li>Actualice las aplicaciones para que no se basen en el inicio de <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=name> en caso de tratarse de secuencias de escape no válidas. Ahora, este tipo de secuencias deben detectarse directamente.</li><li>De igual modo, cabe esperar que los URI y las cadenas de datos con secuencias de escape y sin ellas varíen entre .NET Framework 4.0 y .NET Framework 4.5, y no se deben comparar directamente entre versiones de .NET. En lugar de ello, deben analizarse y normalizarse en una única versión de .NET antes de efectuar cualquier comparación.</li></ul>|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType></li><li><xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType></li></ul>|
