---
ms.openlocfilehash: 6ff23bbe8c48235770d39cb7d35a1df7de6c5201
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "68440286"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.  Con este cambio [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.<ul><li>[x] Anómalo</li></ul>|
|Sugerencia|Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
