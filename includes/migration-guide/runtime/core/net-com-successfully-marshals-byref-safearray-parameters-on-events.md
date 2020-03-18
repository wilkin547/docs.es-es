---
ms.openlocfilehash: 6ff23bbe8c48235770d39cb7d35a1df7de6c5201
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "68440286"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="8dbe5-101">.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos</span><span class="sxs-lookup"><span data-stu-id="8dbe5-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8dbe5-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8dbe5-102">Details</span></span>|<span data-ttu-id="8dbe5-103">En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.</span><span class="sxs-lookup"><span data-stu-id="8dbe5-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="8dbe5-104">Con este cambio [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.</span><span class="sxs-lookup"><span data-stu-id="8dbe5-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="8dbe5-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="8dbe5-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="8dbe5-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8dbe5-106">Suggestion</span></span>|<span data-ttu-id="8dbe5-107">Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="8dbe5-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="8dbe5-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8dbe5-108">Scope</span></span>|<span data-ttu-id="8dbe5-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8dbe5-109">Minor</span></span>|
|<span data-ttu-id="8dbe5-110">Versión</span><span class="sxs-lookup"><span data-stu-id="8dbe5-110">Version</span></span>|<span data-ttu-id="8dbe5-111">4.8</span><span class="sxs-lookup"><span data-stu-id="8dbe5-111">4.8</span></span>|
|<span data-ttu-id="8dbe5-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="8dbe5-112">Type</span></span>|<span data-ttu-id="8dbe5-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8dbe5-113">Runtime</span></span>|
