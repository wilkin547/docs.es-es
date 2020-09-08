---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497141"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a>Permitir Unicode en URI similares a los recursos compartidos UNC

#### <a name="details"></a>Detalles

En <xref:System.Uri?displayProperty=fullName>, la construcción de un URI que contenga un nombre de recurso compartido UNC y caracteres Unicode ya no dará como resultado un URI con el estado interno no válido. El comportamiento solo cambiará cuando se cumpla todo lo siguiente:<ul><li>El URI tiene el esquema <code>file:</code> y va seguido de cuatro o más barras diagonales.</li><li>El nombre de host comienza con un carácter de subrayado u otro símbolo no reservado.</li><li>El URI contiene caracteres Unicode.</li></ul>

#### <a name="suggestion"></a>Sugerencia

Las aplicaciones que trabajan con URI que contienen Unicode de forma coherente podrían haber usado este comportamiento para no permitir referencias a recursos compartidos UNC. En su lugar, esas aplicaciones deben usar <xref:System.Uri.IsUnc>.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
