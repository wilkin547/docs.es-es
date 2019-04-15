---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235926"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="f63e9-101">HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial</span><span class="sxs-lookup"><span data-stu-id="f63e9-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f63e9-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f63e9-102">Details</span></span>|<span data-ttu-id="f63e9-103">A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> incluye un carácter de escape antes del carácter de Y comercial (&amp;).</span><span class="sxs-lookup"><span data-stu-id="f63e9-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="f63e9-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f63e9-104">Suggestion</span></span>|<span data-ttu-id="f63e9-105">Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f63e9-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="f63e9-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f63e9-106">Scope</span></span>|<span data-ttu-id="f63e9-107">Secundaria</span><span class="sxs-lookup"><span data-stu-id="f63e9-107">Minor</span></span>|
|<span data-ttu-id="f63e9-108">Versión</span><span class="sxs-lookup"><span data-stu-id="f63e9-108">Version</span></span>|<span data-ttu-id="f63e9-109">4.5</span><span class="sxs-lookup"><span data-stu-id="f63e9-109">4.5</span></span>|
|<span data-ttu-id="f63e9-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="f63e9-110">Type</span></span>|<span data-ttu-id="f63e9-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f63e9-111">Runtime</span></span>|
|<span data-ttu-id="f63e9-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f63e9-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
