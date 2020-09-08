---
ms.openlocfilehash: 196b6a13d32c7767b858d6d68ca775eb49324805
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497272"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Problema de enlace de IsSelected de ListBoxItem con ObservableCollection&lt;T&gt;.Move

#### <a name="details"></a>Detalles

Las llamadas a <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> o <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> en una colección enlazada a un control <xref:System.Windows.Controls.ListBox?displayProperty=fullName> con elementos seleccionados puede provocar un comportamiento incorrecto en la selección o anulación de selecciones futuras de elementos <xref:System.Windows.Controls.ListBox?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Las llamadas a <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=fullName> y <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=fullName> en lugar de a <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> serán la solución alternativa a este problema. Este problema se resolvió en .NET Framework 4.6, por lo que otra posible solución es actualizar a esta versión de .NET Framework.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.ObjectModel.ObservableCollection`1.Move(System.Int32,System.Int32)``
- ``M:System.Collections.ObjectModel.ObservableCollection`1.MoveItem(System.Int32,System.Int32)``

-->
