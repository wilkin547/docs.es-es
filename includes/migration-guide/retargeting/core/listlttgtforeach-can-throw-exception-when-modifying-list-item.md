---
ms.openlocfilehash: 3300a74b81fc9eeba670ee0ceb2c2615fd3925bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617285"
---
### <a name="listlttgtforeach-can-throw-exception-when-modifying-list-item"></a>List&lt;T&gt;.ForEach puede iniciar una excepción al modificar un elemento de lista

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, un enumerador <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> iniciará una excepción <xref:System.InvalidOperationException?displayProperty=fullName> si se modifica un elemento de la colección que realiza la llamada. En versiones anteriores no se iniciaban excepciones en estos casos, aunque sí podían producirse condiciones de carrera.

#### <a name="suggestion"></a>Sugerencia

Lo ideal es corregir el código para no modificar listas durante la enumeración de sus elementos, ya que esta nunca es una operación segura. Pero para revertir al comportamiento anterior, es posible seleccionar .NET Framework 4.0 como destino de una aplicación.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.5         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType>
