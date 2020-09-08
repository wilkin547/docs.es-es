---
ms.openlocfilehash: e7001fcfdf88fd9e710fbb702f2ed39d63b1e080
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496981"
---
### <a name="systemuri-escaping-now-supports-rfc-3986"></a>La aplicación de secuencias de escape de System.Uri ahora es compatible con RFC 3986

#### <a name="details"></a>Detalles

La aplicación de secuencias de escape a los URI se ha modificado en .NET Framework 4.5 para que sea compatible con [RFC 3986](https://tools.ietf.org/html/rfc3986). Cambios concretos:<ul><li>El método <xref:System.Uri.EscapeDataString(System.String)?displayProperty=fullName> incluye los caracteres reservados entre caracteres de escape de con arreglo a RFC 3986.</li><li>El método <xref:System.Uri.EscapeUriString(System.String)?displayProperty=fullName> no incluye entre caracteres de escape los caracteres reservados.</li><li>El método <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> no inicia una excepción si encuentra una secuencia de escape no válida.</li><li>Los caracteres de escape no reservados no se incluyen en una secuencia de escape.</li></ul>

#### <a name="suggestion"></a>Sugerencia

<ul><li>Actualice las aplicaciones para que no se basen en el inicio de <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=fullName> en caso de tratarse de secuencias de escape no válidas. Ahora, este tipo de secuencias deben detectarse directamente.</li><li>De igual modo, cabe esperar que los URI y las cadenas de datos con secuencias de escape y sin ellas varíen entre .NET Framework 4.0 y .NET Framework 4.5, y no se deben comparar directamente entre versiones de .NET. En lugar de ello, deben analizarse y normalizarse en una única versión de .NET antes de efectuar cualquier comparación.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri.EscapeDataString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.EscapeUriString(System.String)?displayProperty=nameWithType>
- <xref:System.Uri.UnescapeDataString(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.EscapeDataString(System.String)`
- `M:System.Uri.EscapeUriString(System.String)`
- `M:System.Uri.UnescapeDataString(System.String)`

-->
