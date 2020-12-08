---
ms.openlocfilehash: ab9431780422dfece5dcf8007d13e6d584f5118f
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477987"
---
### <a name="avoiding-endless-recursion-for-iworkflowinstancemanagementtransactedcancel-and-iworkflowinstancemanagementtransactedterminate"></a>Evitar la recursión sin fin para IWorkflowInstanceManagement.TransactedCancel e IWorkflowInstanceManagement.TransactedTerminate

#### <a name="details"></a>Detalles

En algunas circunstancias, cuando se usan las API <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType> para cancelar o finalizar una instancia del servicio de flujo de trabajo, se puede producir un desbordamiento de pila en la instancia de flujo de trabajo debido a la recursión sin fin cuando el tiempo de ejecución de `Workflow` intenta conservar la instancia del servicio como parte del procesamiento de la solicitud. El problema se produce si la instancia del flujo de trabajo está en un estado en el que espera que finalice otra solicitud de WCF pendiente a otro servicio. Las operaciones `TransactedCancel` y `TransactedTerminate` crean elementos de trabajo que se ponen en cola para la instancia del servicio de flujo de trabajo. Estos elementos de trabajo no se ejecutan como parte del procesamiento de la solicitud de `TransactedCancel/TransactedTerminate`. Como la instancia del servicio de flujo de trabajo está ocupada en espera a que finalice la otra solicitud de WCF pendiente, el elemento de trabajo que se crea permanece en cola. La operación `TransactedCancel/TransactedTerminate` se completa y el control se devuelve al cliente. Cuando la transacción asociada con la operación `TransactedCancel/TransactedTerminate` intenta confirmar, debe conservar el estado de la instancia del servicio de flujo de trabajo. Pero como existe una solicitud de `WCF` pendiente para la instancia, el tiempo de ejecución del flujo de trabajo no puede conservar la instancia del servicio de flujo de trabajo y un bucle de recursión sin fin genera el desbordamiento de pila. Dado que `TransactedCancel` y `TransactedTerminate` solo crean un elemento de trabajo en memoria, el hecho de que exista una transacción no tiene ningún efecto. La reversión de la transacción no descarta el elemento de trabajo. Para solucionar este problema, a partir de .NET Framework 4.7.2, se ha introducido un `AppSetting` que se puede agregar a la sección `web.config/app.config` del servicio de flujo de trabajo que le indica que ignore las transacciones para `TransactedCancel` y `TransactedTerminate`. Esto permite que la transacción se confirme sin esperar a que se conserve la instancia del flujo de trabajo. La opción AppSetting para esta característica se denomina `microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate`. Un valor de `true` indica que la transacción se debe ignorar, lo que evita el desbordamiento de pila. El valor predeterminado de este AppSetting es `false`, por lo que las instancias del servicio de flujo de trabajo existentes no se ven afectadas.

#### <a name="suggestion"></a>Sugerencia

Si se usa AppFabric u otro cliente de <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> y se produce un desbordamiento de pila en la instancia del servicio de flujo de trabajo al intentar cancelar o finalizar una instancia del flujo de trabajo, se puede agregar lo siguiente a la sección `<appSettings>` del archivo web.config/app.config del servicio de flujo de trabajo:

<pre><code class="lang-xml">&lt;add key=&quot;microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate&quot; value=&quot;true&quot;/&gt;&#13;&#10;</code></pre>

Si el problema no se produce, no es necesario hacer esto.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |
