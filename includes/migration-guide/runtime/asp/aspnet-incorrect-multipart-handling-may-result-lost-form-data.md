---
ms.openlocfilehash: ed669364efe9dd8f57d831a3764dd3fc68cd5e05
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497529"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a><span data-ttu-id="0b038-101">El control incorrecto de varias partes de ASP.NET puede dar lugar a que se pierdan datos de formularios.</span><span class="sxs-lookup"><span data-stu-id="0b038-101">ASP.NET Incorrect multipart handling may result in lost form data.</span></span>

#### <a name="details"></a><span data-ttu-id="0b038-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0b038-102">Details</span></span>

<span data-ttu-id="0b038-103">En las aplicaciones que tienen como destino .NET Framework 4.7.2 y versiones anteriores, ASP.Net podría analizar incorrectamente valores de límite de varias partes, lo que da lugar a que los datos de formulario no estén disponibles durante la ejecución de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0b038-103">In applications that target .NET Framework 4.7.2 and earlier versions, ASP.Net might incorrectly parse multipart boundary values, resulting in form data being unavailable during request execution.</span></span> <span data-ttu-id="0b038-104">Las aplicaciones que tienen como destino .NET Framework 4.8 o versiones posteriores analizan correctamente datos de varias partes, por lo que los valores del formulario están disponibles durante la ejecución de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="0b038-104">Applications that target .NET Framework 4.8 or later versions correctly parse multipart data, so form values are available during request execution.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0b038-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0b038-105">Suggestion</span></span>

<span data-ttu-id="0b038-106">A partir de las aplicaciones que se ejecutan en .NET Framework 4.8, cuando el destino sea .NET Framework 4.8 o posterior mediante el uso del elemento <code>targetFrameworkVersion</code>, el comportamiento predeterminado cambia para quitar delimitadores.</span><span class="sxs-lookup"><span data-stu-id="0b038-106">Starting with applications running on .NET Framework 4.8, when targeting .NET Framework 4.8 or later by using the <code>targetFrameworkVersion</code> element, the default behavior changes to strip delimiters.</span></span> <span data-ttu-id="0b038-107">Cuando se usan versiones anteriores de Framework o no se usa <code>targetFrameworkVersion</code>, los delimitadores finales de algunos valores todavía se devuelven.Este comportamiento también se puede controlar explícitamente con <code>appSetting</code>:</span><span class="sxs-lookup"><span data-stu-id="0b038-107">When targeting previous framework versions or not using <code>targetFrameworkVersion</code>, trailing delimiters for some values are still returned.This behavior can also be explicitly controlled with an <code>appSetting</code>:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="0b038-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0b038-108">Name</span></span>    | <span data-ttu-id="0b038-109">Valor</span><span class="sxs-lookup"><span data-stu-id="0b038-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0b038-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0b038-110">Scope</span></span>   |<span data-ttu-id="0b038-111">Desconocido</span><span class="sxs-lookup"><span data-stu-id="0b038-111">Unknown</span></span>|
|<span data-ttu-id="0b038-112">Versión</span><span class="sxs-lookup"><span data-stu-id="0b038-112">Version</span></span>|<span data-ttu-id="0b038-113">4.8</span><span class="sxs-lookup"><span data-stu-id="0b038-113">4.8</span></span>|
|<span data-ttu-id="0b038-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="0b038-114">Type</span></span>|<span data-ttu-id="0b038-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0b038-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0b038-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0b038-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
