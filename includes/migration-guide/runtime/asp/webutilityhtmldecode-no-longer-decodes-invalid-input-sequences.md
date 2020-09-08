---
ms.openlocfilehash: ef3114a4eb9f62030c3ec36d3b463d07ccd59f6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496882"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="78ae3-101">WebUtility.HtmlDecode ya no descodifica secuencias de entrada no válidas</span><span class="sxs-lookup"><span data-stu-id="78ae3-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

#### <a name="details"></a><span data-ttu-id="78ae3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="78ae3-102">Details</span></span>

<span data-ttu-id="78ae3-103">De forma predeterminada, los métodos de descodificación ya no descodifican secuencias de entrada no válidas en una cadena UTF-16 no válida.</span><span class="sxs-lookup"><span data-stu-id="78ae3-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="78ae3-104">En su lugar, devuelven la entrada original.</span><span class="sxs-lookup"><span data-stu-id="78ae3-104">Instead, they return the original input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="78ae3-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="78ae3-105">Suggestion</span></span>

<span data-ttu-id="78ae3-106">El cambio en la salida del descodificador solo es importante si se almacenan datos binarios en lugar de datos UTF-16 en cadenas.</span><span class="sxs-lookup"><span data-stu-id="78ae3-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="78ae3-107">Para controlar este comportamiento de manera explícita, establezca el atributo <code>aspnet:AllowRelaxedUnicodeDecoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) en <code>true</code> para habilitar el comportamiento heredado o en <code>false</code> para habilitar el actual.</span><span class="sxs-lookup"><span data-stu-id="78ae3-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>

| <span data-ttu-id="78ae3-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="78ae3-108">Name</span></span>    | <span data-ttu-id="78ae3-109">Valor</span><span class="sxs-lookup"><span data-stu-id="78ae3-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="78ae3-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="78ae3-110">Scope</span></span>   |<span data-ttu-id="78ae3-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="78ae3-111">Minor</span></span>|
|<span data-ttu-id="78ae3-112">Versión</span><span class="sxs-lookup"><span data-stu-id="78ae3-112">Version</span></span>|<span data-ttu-id="78ae3-113">4.5</span><span class="sxs-lookup"><span data-stu-id="78ae3-113">4.5</span></span>|
|<span data-ttu-id="78ae3-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="78ae3-114">Type</span></span>|<span data-ttu-id="78ae3-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="78ae3-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="78ae3-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="78ae3-116">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.WebUtility.HtmlDecode(System.String)`
- `M:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)`
- `M:System.Net.WebUtility.UrlDecode(System.String)`

-->
