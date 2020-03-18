---
ms.openlocfilehash: a573a78109036b87201b53f72aa8dba6755e7a21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802463"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Al quitar un elemento de una colección personalizada de INCC se produce un bloqueo en Selector

|   |   |
|---|---|
|Detalles|Se puede iniciar una excepción <code>T:System.InvalidOperationException</code> en el escenario siguiente:<ul><li>El ItemsSource de un control <code>T:System.Windows.Controls.Primitives.Selector</code> es una colección con una implementación personalizada de <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>El elemento seleccionado se quita de la colección.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> tiene <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = -1 (lo que indica una posición desconocida).</li></ul>La pila de llamadas de la excepción comienza en System.Windows.Threading.Dispatcher.VerifyAccess() en System.Windows.DependencyObject.GetValue(DependencyProperty dp) en System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject elemento). Esta excepción se puede iniciar en .NET Framework 4.5 si la aplicación tiene más de un subproceso de distribuidor. En .NET Framework 4.7, la excepción también se puede iniciar en las aplicaciones con un único subproceso de distribuidor. El problema se corrigió en .NET Framework 4.7.1.|
|Sugerencia|Actualice a .NET Framework 4.7.1.|
|Ámbito|Secundaria|
|Versión|4.7|
|Tipo|Tiempo de ejecución|
