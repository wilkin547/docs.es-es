---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606271"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="172b2-101">.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos</span><span class="sxs-lookup"><span data-stu-id="172b2-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="172b2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="172b2-102">Details</span></span>

<span data-ttu-id="172b2-103">En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.</span><span class="sxs-lookup"><span data-stu-id="172b2-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="172b2-104">Con este cambio [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.</span><span class="sxs-lookup"><span data-stu-id="172b2-104">With this change the [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="172b2-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="172b2-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="172b2-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="172b2-106">Suggestion</span></span>

<span data-ttu-id="172b2-107">Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="172b2-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="172b2-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="172b2-108">Name</span></span>    | <span data-ttu-id="172b2-109">Valor</span><span class="sxs-lookup"><span data-stu-id="172b2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="172b2-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="172b2-110">Scope</span></span>   |<span data-ttu-id="172b2-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="172b2-111">Minor</span></span>|
|<span data-ttu-id="172b2-112">Versión</span><span class="sxs-lookup"><span data-stu-id="172b2-112">Version</span></span>|<span data-ttu-id="172b2-113">4.8</span><span class="sxs-lookup"><span data-stu-id="172b2-113">4.8</span></span>|
|<span data-ttu-id="172b2-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="172b2-114">Type</span></span>|<span data-ttu-id="172b2-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="172b2-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="172b2-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="172b2-116">Affected APIs</span></span>

<span data-ttu-id="172b2-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="172b2-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
