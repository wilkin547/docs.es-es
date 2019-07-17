---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802652"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="4e80b-101">.NET COM serializa correctamente los parámetros ByRef SafeArray en los eventos</span><span class="sxs-lookup"><span data-stu-id="4e80b-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4e80b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4e80b-102">Details</span></span>|<span data-ttu-id="4e80b-103">En .NET Framework 4.7.2 y versiones anteriores, un parámetro ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) en un evento COM no podía volver serializar al código nativo.</span><span class="sxs-lookup"><span data-stu-id="4e80b-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="4e80b-104">Con este cambio [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) ahora se serializa correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e80b-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="4e80b-105">[x] Anómalo</span><span class="sxs-lookup"><span data-stu-id="4e80b-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="4e80b-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4e80b-106">Suggestion</span></span>|<span data-ttu-id="4e80b-107">Si la serialización correcta de los parámetros ByRef SafeArray en eventos COM interrumpe la ejecución, puede deshabilitar este código agregando el siguiente modificador de configuración a la configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4e80b-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="4e80b-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4e80b-108">Scope</span></span>|<span data-ttu-id="4e80b-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="4e80b-109">Minor</span></span>|
|<span data-ttu-id="4e80b-110">Versión</span><span class="sxs-lookup"><span data-stu-id="4e80b-110">Version</span></span>|<span data-ttu-id="4e80b-111">4.8</span><span class="sxs-lookup"><span data-stu-id="4e80b-111">4.8</span></span>|
|<span data-ttu-id="4e80b-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e80b-112">Type</span></span>|<span data-ttu-id="4e80b-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4e80b-113">Runtime</span></span>|

