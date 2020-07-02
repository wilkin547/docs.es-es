---
ms.openlocfilehash: c53fe57f3278741a927a2f00b11af6e26dafce66
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620537"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="b60dd-101">ASP.NET MVC ahora aplica caracteres de escape a los espacios de las cadenas que se pasan a través de parámetros de ruta</span><span class="sxs-lookup"><span data-stu-id="b60dd-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="b60dd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b60dd-102">Details</span></span>

<span data-ttu-id="b60dd-103">Para cumplir con RFC 2396, ahora se aplican caracteres de escape a los espacios de las rutas de acceso al rellenar parámetros de acción desde una ruta.</span><span class="sxs-lookup"><span data-stu-id="b60dd-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="b60dd-104">Por tanto, mientras que <code>/controller/action/some data</code> antes coincidía con la ruta <code>/controller/action/{data}</code> y proporcionaba <code>some data</code> como parámetro de datos, ahora proporciona <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="b60dd-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b60dd-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b60dd-105">Suggestion</span></span>

<span data-ttu-id="b60dd-106">Debería actualizarse el código para no eliminar las secuencias de escape de los parámetros de las cadenas desde una ruta.</span><span class="sxs-lookup"><span data-stu-id="b60dd-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="b60dd-107">Si se necesita el identificador URI original, se puede tener acceso a él con la API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="b60dd-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="b60dd-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b60dd-108">Name</span></span>    | <span data-ttu-id="b60dd-109">Valor</span><span class="sxs-lookup"><span data-stu-id="b60dd-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b60dd-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b60dd-110">Scope</span></span>   |<span data-ttu-id="b60dd-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="b60dd-111">Minor</span></span>|
|<span data-ttu-id="b60dd-112">Versión</span><span class="sxs-lookup"><span data-stu-id="b60dd-112">Version</span></span>|<span data-ttu-id="b60dd-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b60dd-113">4.5.2</span></span>|
|<span data-ttu-id="b60dd-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="b60dd-114">Type</span></span>|<span data-ttu-id="b60dd-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b60dd-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b60dd-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b60dd-116">Affected APIs</span></span>

-<xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)></li></ul>|
