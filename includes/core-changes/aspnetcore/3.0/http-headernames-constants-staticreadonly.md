---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901736"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="b4303-101">HTTP: las constantes HeaderNames se han cambiado a static readonly</span><span class="sxs-lookup"><span data-stu-id="b4303-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="b4303-102">A partir de ASP.NET Core 3.0 Preview 5, los campos de <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> se han cambiado de `const` a `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="b4303-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="b4303-103">Para obtener información, vea [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span><span class="sxs-lookup"><span data-stu-id="b4303-103">For discussion, see [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b4303-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b4303-104">Version introduced</span></span>

<span data-ttu-id="b4303-105">3.0</span><span class="sxs-lookup"><span data-stu-id="b4303-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b4303-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b4303-106">Old behavior</span></span>

<span data-ttu-id="b4303-107">Estos campos solían ser `const`.</span><span class="sxs-lookup"><span data-stu-id="b4303-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b4303-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b4303-108">New behavior</span></span>

<span data-ttu-id="b4303-109">Ahora estos campos son `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="b4303-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b4303-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b4303-110">Reason for change</span></span>

<span data-ttu-id="b4303-111">El cambio:</span><span class="sxs-lookup"><span data-stu-id="b4303-111">The change:</span></span>

* <span data-ttu-id="b4303-112">Impide que los valores se inserten en los límites de los ensamblados, lo que permite corregirlos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b4303-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="b4303-113">Permite comprobaciones de igualdad de referencia más rápidas.</span><span class="sxs-lookup"><span data-stu-id="b4303-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b4303-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b4303-114">Recommended action</span></span>

<span data-ttu-id="b4303-115">Vuelva a compilar para la versión 3.0.</span><span class="sxs-lookup"><span data-stu-id="b4303-115">Recompile against 3.0.</span></span> <span data-ttu-id="b4303-116">El código fuente que use estos campos de las maneras siguientes ya no podrá hacerlo:</span><span class="sxs-lookup"><span data-stu-id="b4303-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="b4303-117">Como un argumento de atributo</span><span class="sxs-lookup"><span data-stu-id="b4303-117">As an attribute argument</span></span>
* <span data-ttu-id="b4303-118">Como un objeto `case` en una instrucción `switch`</span><span class="sxs-lookup"><span data-stu-id="b4303-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="b4303-119">Al definir otra instancia de `const`</span><span class="sxs-lookup"><span data-stu-id="b4303-119">When defining another `const`</span></span>

<span data-ttu-id="b4303-120">Para solucionar el cambio importante, use constantes de nombre de encabezado autodefinidas o literales de cadena.</span><span class="sxs-lookup"><span data-stu-id="b4303-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="b4303-121">Categoría</span><span class="sxs-lookup"><span data-stu-id="b4303-121">Category</span></span>

<span data-ttu-id="b4303-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b4303-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b4303-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b4303-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
