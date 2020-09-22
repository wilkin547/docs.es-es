---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606175"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="baf16-101">HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial</span><span class="sxs-lookup"><span data-stu-id="baf16-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="baf16-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="baf16-102">Details</span></span>

<span data-ttu-id="baf16-103">A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> incluye un carácter de escape antes del carácter de Y comercial (&amp;).</span><span class="sxs-lookup"><span data-stu-id="baf16-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="baf16-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="baf16-104">Suggestion</span></span>

<span data-ttu-id="baf16-105">Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="baf16-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="baf16-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="baf16-106">Name</span></span>    | <span data-ttu-id="baf16-107">Valor</span><span class="sxs-lookup"><span data-stu-id="baf16-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="baf16-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="baf16-108">Scope</span></span>   |<span data-ttu-id="baf16-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="baf16-109">Minor</span></span>|
|<span data-ttu-id="baf16-110">Versión</span><span class="sxs-lookup"><span data-stu-id="baf16-110">Version</span></span>|<span data-ttu-id="baf16-111">4.5</span><span class="sxs-lookup"><span data-stu-id="baf16-111">4.5</span></span>|
|<span data-ttu-id="baf16-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="baf16-112">Type</span></span>|<span data-ttu-id="baf16-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="baf16-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="baf16-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="baf16-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
