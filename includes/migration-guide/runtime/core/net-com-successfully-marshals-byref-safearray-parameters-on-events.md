---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802652"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a>.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos

|   |   |
|---|---|
|Detalles|En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.  Con este cambio [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.<ul><li>[x] Anómalo</li></ul>|
|Sugerencia|Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Ámbito|Secundaria|
|Versión|4.8|
|Tipo|Tiempo de ejecución|

