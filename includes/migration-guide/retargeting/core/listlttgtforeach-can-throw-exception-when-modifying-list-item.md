---
ms.openlocfilehash: 4e81087431091dfa4d5432d5ea5e2b665be2b130
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774406"
---
### <a name="listtforeach-can-throw-exception-when-modifying-list-item"></a>List\<T>.ForEach puede iniciar una excepción al modificar un elemento de lista

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5, un enumerador <xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})> iniciará una excepción <xref:System.InvalidOperationException?displayProperty=name> si se modifica un elemento de la colección que realiza la llamada. En versiones anteriores no se iniciaban excepciones en estos casos, aunque sí podían producirse condiciones de carrera.|
|Sugerencia|Lo ideal es corregir el código para no modificar listas durante la enumeración de sus elementos, ya que esta nunca es una operación segura. Pero para revertir al comportamiento anterior, es posible seleccionar .NET Framework 4.0 como destino de una aplicación.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.Collections.Generic.List%601.ForEach(System.Action{%600})?displayProperty=nameWithType></li></ul>|
