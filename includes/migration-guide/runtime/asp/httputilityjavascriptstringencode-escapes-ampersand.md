---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620534"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="f9bdb-101">HttpUtility.JavaScriptStringEncode aplica un carácter de escape a la Y comercial</span><span class="sxs-lookup"><span data-stu-id="f9bdb-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="f9bdb-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f9bdb-102">Details</span></span>

<span data-ttu-id="f9bdb-103">A partir de .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> incluye un carácter de escape antes del carácter de Y comercial (&amp;).</span><span class="sxs-lookup"><span data-stu-id="f9bdb-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f9bdb-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f9bdb-104">Suggestion</span></span>

<span data-ttu-id="f9bdb-105">Si la aplicación depende del comportamiento anterior de este método, puede agregar un ajuste aspnet:JavaScriptDoNotEncodeAmpersand al [elemento appSettings de ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9bdb-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="f9bdb-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f9bdb-106">Name</span></span>    | <span data-ttu-id="f9bdb-107">Valor</span><span class="sxs-lookup"><span data-stu-id="f9bdb-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f9bdb-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f9bdb-108">Scope</span></span>   |<span data-ttu-id="f9bdb-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="f9bdb-109">Minor</span></span>|
|<span data-ttu-id="f9bdb-110">Versión</span><span class="sxs-lookup"><span data-stu-id="f9bdb-110">Version</span></span>|<span data-ttu-id="f9bdb-111">4.5</span><span class="sxs-lookup"><span data-stu-id="f9bdb-111">4.5</span></span>|
|<span data-ttu-id="f9bdb-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="f9bdb-112">Type</span></span>|<span data-ttu-id="f9bdb-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f9bdb-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f9bdb-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f9bdb-114">Affected APIs</span></span>

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
