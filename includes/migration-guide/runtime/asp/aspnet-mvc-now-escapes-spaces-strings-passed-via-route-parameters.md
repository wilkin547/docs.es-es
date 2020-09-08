---
ms.openlocfilehash: afbf34710c75d0f0586ddfdb2e7937d8d76d5399
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497882"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="583c2-101">ASP.NET MVC ahora aplica caracteres de escape a los espacios de las cadenas que se pasan a través de parámetros de ruta</span><span class="sxs-lookup"><span data-stu-id="583c2-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

#### <a name="details"></a><span data-ttu-id="583c2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="583c2-102">Details</span></span>

<span data-ttu-id="583c2-103">Para cumplir con RFC 2396, ahora se aplican caracteres de escape a los espacios de las rutas de acceso al rellenar parámetros de acción desde una ruta.</span><span class="sxs-lookup"><span data-stu-id="583c2-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="583c2-104">Por tanto, mientras que <code>/controller/action/some data</code> antes coincidía con la ruta <code>/controller/action/{data}</code> y proporcionaba <code>some data</code> como parámetro de datos, ahora proporciona <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="583c2-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="583c2-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="583c2-105">Suggestion</span></span>

<span data-ttu-id="583c2-106">Debería actualizarse el código para no eliminar las secuencias de escape de los parámetros de las cadenas desde una ruta.</span><span class="sxs-lookup"><span data-stu-id="583c2-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="583c2-107">Si se necesita el identificador URI original, se puede tener acceso a él con la API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="583c2-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>

| <span data-ttu-id="583c2-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="583c2-108">Name</span></span>    | <span data-ttu-id="583c2-109">Valor</span><span class="sxs-lookup"><span data-stu-id="583c2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="583c2-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="583c2-110">Scope</span></span>   |<span data-ttu-id="583c2-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="583c2-111">Minor</span></span>|
|<span data-ttu-id="583c2-112">Versión</span><span class="sxs-lookup"><span data-stu-id="583c2-112">Version</span></span>|<span data-ttu-id="583c2-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="583c2-113">4.5.2</span></span>|
|<span data-ttu-id="583c2-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="583c2-114">Type</span></span>|<span data-ttu-id="583c2-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="583c2-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="583c2-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="583c2-116">Affected APIs</span></span>

- <xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)>

<!--

#### Affected APIs

- `M:System.Web.Mvc.RouteAttribute.#ctor(System.String)`

-->
