---
ms.openlocfilehash: a806107456a65a4919592da9535a2617f677cfe0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496641"
---
### <a name="wpf-dispatchersynchronizationcontextcreatecopy-now-returns-a-new-copy-instead-of-the-current-instance"></a>El elemento DispatcherSynchronizationContext.CreateCopy de WPF ahora devuelve una copia nueva en lugar de la instancia actual

#### <a name="details"></a>Detalles

En .NET Framework 4, <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> devolvía una referencia a la instancia actual, principalmente como optimización del rendimiento. En .NET Framework 4.5, devuelve una nueva instancia que permite concluir por primera vez que las mismas referencias indican que el subproceso de ejecución se encuentra en el contexto de sincronización correcto.  Es poco probable que el código que comprueba la identidad de estas referencias se vea afectado, pero debido al cambio, el código que llama a <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> se debería probar como parte de la migración a .NET Framework 4.5 o una versión posterior.

#### <a name="suggestion"></a>Sugerencia

Tenga en cuenta que <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy> ahora devolverá un objeto <xref:System.Threading.SynchronizationContext?displayProperty=fullName> nuevo. Anteriormente, el código que usaba la equivalencia de referencias generadas de esta forma no comprobaba en realidad si se encontraba en el contexto correcto, pero sí lo hace si se compila en .NET Framework 4.5 o una versión posterior.  Aunque es poco probable que cause problemas, debería bastar con ejecutar las rutas de acceso del código afectado para comprobar si lo hace.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Threading.DispatcherSynchronizationContext.CreateCopy`

-->
