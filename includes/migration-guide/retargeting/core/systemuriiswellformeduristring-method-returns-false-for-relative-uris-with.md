---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617282"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>El método System.Uri.IsWellFormedUriString devuelve false para los identificadores URI relativos con un carácter de dos puntos en el primer segmento

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratará los identificadores URI relativos con un `:` en el primer segmento como mal formados. Se trata de un cambio con respecto al comportamiento de <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> en .NET Framework 4.0 que se realizó para cumplir con RFC3986.

#### <a name="suggestion"></a>Sugerencia

Este cambio (como muchos otros cambios de URI) solo afecta a las aplicaciones destinadas a .NET Framework 4.5 (o una versión posterior). Para seguir usando el comportamiento anterior, cambie el destino de la aplicación a .NET Framework 4.0. Como alternativa, examine el URI antes de llamar a <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> en busca de caracteres `:` que se puedan quitar con fines de validación, si quiere el comportamiento anterior.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.5         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
