---
ms.openlocfilehash: 2278d82d5362fe217ca4bce02a052d4b440843c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803199"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="ea23f-101">ASP.NET MVC ahora aplica caracteres de escape a los espacios de las cadenas que se pasan a través de parámetros de ruta</span><span class="sxs-lookup"><span data-stu-id="ea23f-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ea23f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea23f-102">Details</span></span>|<span data-ttu-id="ea23f-103">Para cumplir con RFC 2396, ahora se aplican caracteres de escape a los espacios de las rutas de acceso al rellenar parámetros de acción desde una ruta.</span><span class="sxs-lookup"><span data-stu-id="ea23f-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="ea23f-104">Por tanto, mientras que <code>/controller/action/some data</code> antes coincidía con la ruta <code>/controller/action/{data}</code> y proporcionaba <code>some data</code> como parámetro de datos, ahora proporciona <code>some%20data</code>.</span><span class="sxs-lookup"><span data-stu-id="ea23f-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="ea23f-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ea23f-105">Suggestion</span></span>|<span data-ttu-id="ea23f-106">Debería actualizarse el código para no eliminar las secuencias de escape de los parámetros de las cadenas desde una ruta.</span><span class="sxs-lookup"><span data-stu-id="ea23f-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="ea23f-107">Si se necesita el identificador URI original, se puede tener acceso a él con la API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.</span><span class="sxs-lookup"><span data-stu-id="ea23f-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="ea23f-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ea23f-108">Scope</span></span>|<span data-ttu-id="ea23f-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="ea23f-109">Minor</span></span>|
|<span data-ttu-id="ea23f-110">Versión</span><span class="sxs-lookup"><span data-stu-id="ea23f-110">Version</span></span>|<span data-ttu-id="ea23f-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="ea23f-111">4.5.2</span></span>|
|<span data-ttu-id="ea23f-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ea23f-112">Type</span></span>|<span data-ttu-id="ea23f-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ea23f-113">Runtime</span></span>|
|<span data-ttu-id="ea23f-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ea23f-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
