---
ms.openlocfilehash: 9c72bc686e014a0bffdf272e3813358d1b29cc66
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65199450"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="c65bc-101">.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos</span><span class="sxs-lookup"><span data-stu-id="c65bc-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c65bc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c65bc-102">Details</span></span>|<span data-ttu-id="c65bc-103">En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.</span><span class="sxs-lookup"><span data-stu-id="c65bc-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="c65bc-104">Con este cambio [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.</span><span class="sxs-lookup"><span data-stu-id="c65bc-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshaled successfully.</span></span><ul><li><span data-ttu-id="c65bc-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="c65bc-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="c65bc-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c65bc-106">Suggestion</span></span>|<span data-ttu-id="c65bc-107">Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="c65bc-107">If properly marshaling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="c65bc-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c65bc-108">Scope</span></span>|<span data-ttu-id="c65bc-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="c65bc-109">Minor</span></span>|
|<span data-ttu-id="c65bc-110">Versión</span><span class="sxs-lookup"><span data-stu-id="c65bc-110">Version</span></span>|<span data-ttu-id="c65bc-111">4.8</span><span class="sxs-lookup"><span data-stu-id="c65bc-111">4.8</span></span>|
|<span data-ttu-id="c65bc-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="c65bc-112">Type</span></span>|<span data-ttu-id="c65bc-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c65bc-113">Runtime</span></span>|
