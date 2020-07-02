---
ms.openlocfilehash: 0b7d6d9543035ab0a8fdda675ae71572ace12a1f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620541"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a><span data-ttu-id="00c33-101">WebUtility.HtmlDecode ya no descodifica secuencias de entrada no válidas</span><span class="sxs-lookup"><span data-stu-id="00c33-101">WebUtility.HtmlDecode no longer decodes invalid input sequences</span></span>

#### <a name="details"></a><span data-ttu-id="00c33-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="00c33-102">Details</span></span>

<span data-ttu-id="00c33-103">De forma predeterminada, los métodos de descodificación ya no descodifican secuencias de entrada no válidas en una cadena UTF-16 no válida.</span><span class="sxs-lookup"><span data-stu-id="00c33-103">By default, decoding methods no longer decode an invalid input sequence into an invalid UTF-16 string.</span></span> <span data-ttu-id="00c33-104">En su lugar, devuelven la entrada original.</span><span class="sxs-lookup"><span data-stu-id="00c33-104">Instead, they return the original input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="00c33-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="00c33-105">Suggestion</span></span>

<span data-ttu-id="00c33-106">El cambio en la salida del descodificador solo es importante si se almacenan datos binarios en lugar de datos UTF-16 en cadenas.</span><span class="sxs-lookup"><span data-stu-id="00c33-106">The change in decoder output should matter only if you store binary data instead of UTF-16 data in strings.</span></span> <span data-ttu-id="00c33-107">Para controlar este comportamiento de manera explícita, establezca el atributo <code>aspnet:AllowRelaxedUnicodeDecoding</code> del elemento [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) en <code>true</code> para habilitar el comportamiento heredado o en <code>false</code> para habilitar el actual.</span><span class="sxs-lookup"><span data-stu-id="00c33-107">To explicitly control this behavior, set the <code>aspnet:AllowRelaxedUnicodeDecoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) element to <code>true</code> to enable legacy behavior or to <code>false</code> to enable the current behavior.</span></span>

| <span data-ttu-id="00c33-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="00c33-108">Name</span></span>    | <span data-ttu-id="00c33-109">Valor</span><span class="sxs-lookup"><span data-stu-id="00c33-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="00c33-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="00c33-110">Scope</span></span>   |<span data-ttu-id="00c33-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="00c33-111">Minor</span></span>|
|<span data-ttu-id="00c33-112">Versión</span><span class="sxs-lookup"><span data-stu-id="00c33-112">Version</span></span>|<span data-ttu-id="00c33-113">4.5</span><span class="sxs-lookup"><span data-stu-id="00c33-113">4.5</span></span>|
|<span data-ttu-id="00c33-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="00c33-114">Type</span></span>|<span data-ttu-id="00c33-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="00c33-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="00c33-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="00c33-116">Affected APIs</span></span>

-<xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType></li><li><xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType></li></ul>|
