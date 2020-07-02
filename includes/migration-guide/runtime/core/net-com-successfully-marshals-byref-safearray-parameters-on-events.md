---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622084"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="62b1c-101">.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos</span><span class="sxs-lookup"><span data-stu-id="62b1c-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="62b1c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="62b1c-102">Details</span></span>

<span data-ttu-id="62b1c-103">En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.</span><span class="sxs-lookup"><span data-stu-id="62b1c-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="62b1c-104">Con este cambio [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.</span><span class="sxs-lookup"><span data-stu-id="62b1c-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="62b1c-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="62b1c-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="62b1c-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="62b1c-106">Suggestion</span></span>

<span data-ttu-id="62b1c-107">Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="62b1c-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="62b1c-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="62b1c-108">Name</span></span>    | <span data-ttu-id="62b1c-109">Valor</span><span class="sxs-lookup"><span data-stu-id="62b1c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="62b1c-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="62b1c-110">Scope</span></span>   |<span data-ttu-id="62b1c-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="62b1c-111">Minor</span></span>|
|<span data-ttu-id="62b1c-112">Versión</span><span class="sxs-lookup"><span data-stu-id="62b1c-112">Version</span></span>|<span data-ttu-id="62b1c-113">4.8</span><span class="sxs-lookup"><span data-stu-id="62b1c-113">4.8</span></span>|
|<span data-ttu-id="62b1c-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="62b1c-114">Type</span></span>|<span data-ttu-id="62b1c-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="62b1c-115">Runtime</span></span>|
