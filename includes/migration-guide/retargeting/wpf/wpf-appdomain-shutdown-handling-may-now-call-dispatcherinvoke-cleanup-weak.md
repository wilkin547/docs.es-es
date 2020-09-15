---
ms.openlocfilehash: 8b804d23247b95381f3ff83bc12c32215a420fb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614956"
---
### <a name="wpf-appdomain-shutdown-handling-may-now-call-dispatcherinvoke-in-cleanup-of-weak-events"></a>Es posible que el control de apagados de AppDomain en WPF llame a Dispatcher.Invoke durante la limpieza de eventos débiles

#### <a name="details"></a>Detalles

En .NET Framework 4.7.1 y versiones anteriores, WPF crea potencialmente un parámetro <xref:System.Windows.Threading.Dispatcher?displayProperty=nameWithType> en el subproceso finalizador de .NET durante el apagado de AppDomain.  Esto se ha solucionado en .NET Framework 4.7.2 y versiones posteriores configurando la limpieza de eventos débiles para que tenga en cuenta los subprocesos.  Por ello, es posible que WPF llame a <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> para completar el proceso de limpieza. En algunas aplicaciones, este cambio en el horario del finalizador podría generar excepciones durante el apagado de AppDomain o de procesos.  Esto suele detectarse en aplicaciones que no apagan correctamente los distribuidores que se ejecutan en los subprocesos de trabajo antes del apagado de AppDomain o de procesos.  Estas aplicaciones deberían encargarse de administrar correctamente la vigencia de los distribuidores.

#### <a name="suggestion"></a>Sugerencia

En .NET Framework 4.7.2 y versiones posteriores, los desarrolladores pueden deshabilitar esta corrección para reducir (no eliminar) los problemas de horario que se pueden producir debido al cambio en la limpieza. Para deshabilitar dicho cambio, use la siguiente marca de AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.DoNotInvokeInWeakEventTableShutdownListener=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |
