---
ms.openlocfilehash: 1907c9b82c9685899d328f67da8001c0fa4fb697
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497940"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="65f19-101">.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos</span><span class="sxs-lookup"><span data-stu-id="65f19-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="65f19-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="65f19-102">Details</span></span>

<span data-ttu-id="65f19-103">En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.</span><span class="sxs-lookup"><span data-stu-id="65f19-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="65f19-104">Con este cambio [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.</span><span class="sxs-lookup"><span data-stu-id="65f19-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="65f19-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="65f19-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="65f19-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="65f19-106">Suggestion</span></span>

<span data-ttu-id="65f19-107">Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="65f19-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="65f19-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="65f19-108">Name</span></span>    | <span data-ttu-id="65f19-109">Valor</span><span class="sxs-lookup"><span data-stu-id="65f19-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="65f19-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="65f19-110">Scope</span></span>   |<span data-ttu-id="65f19-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="65f19-111">Minor</span></span>|
|<span data-ttu-id="65f19-112">Versión</span><span class="sxs-lookup"><span data-stu-id="65f19-112">Version</span></span>|<span data-ttu-id="65f19-113">4.8</span><span class="sxs-lookup"><span data-stu-id="65f19-113">4.8</span></span>|
|<span data-ttu-id="65f19-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="65f19-114">Type</span></span>|<span data-ttu-id="65f19-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="65f19-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="65f19-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="65f19-116">Affected APIs</span></span>

<span data-ttu-id="65f19-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="65f19-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
