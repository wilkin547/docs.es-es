---
ms.openlocfilehash: f50022d9a7bacd7be40fe3050ced26e7c25cf7aa
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497826"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Al quitar un elemento de una colección personalizada de INCC se produce un bloqueo en Selector

#### <a name="details"></a>Detalles

Se puede iniciar una excepción <code>T:System.InvalidOperationException</code> en el escenario siguiente:<ul><li>El ItemsSource de un control <code>T:System.Windows.Controls.Primitives.Selector</code> es una colección con una implementación personalizada de <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>El elemento seleccionado se quita de la colección.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> tiene <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (lo que indica una posición desconocida).</li></ul>La pila de llamadas de la excepción comienza en System.Windows.Threading.Dispatcher.VerifyAccess() en System.Windows.DependencyObject.GetValue(DependencyProperty dp) en System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject elemento). Esta excepción se puede iniciar en .NET Framework 4.5 si la aplicación tiene más de un subproceso de distribuidor. En .NET Framework 4.7, la excepción también se puede iniciar en las aplicaciones con un único subproceso de distribuidor. El problema se corrigió en .NET Framework 4.7.1.

#### <a name="suggestion"></a>Sugerencia

Actualice a .NET Framework 4.7.1.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.7|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
