---
ms.openlocfilehash: 6f8e6d2786d20e055c9bef63891db4d6f88bc64b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75902037"
---
### <a name="identity-signinmanager-constructor-accepts-new-parameter"></a><span data-ttu-id="368cb-101">Identity: el constructor SignInManager acepta un nuevo parámetro</span><span class="sxs-lookup"><span data-stu-id="368cb-101">Identity: SignInManager constructor accepts new parameter</span></span>

<span data-ttu-id="368cb-102">A partir de ASP.NET Core 3.0, se ha agregado un nuevo parámetro `IUserConfirmation<TUser>` al constructor `SignInManager`.</span><span class="sxs-lookup"><span data-stu-id="368cb-102">Starting with ASP.NET Core 3.0, a new `IUserConfirmation<TUser>` parameter was added to the `SignInManager` constructor.</span></span> <span data-ttu-id="368cb-103">Para obtener más información, consulte [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span><span class="sxs-lookup"><span data-stu-id="368cb-103">For more information, see [dotnet/aspnetcore#8356](https://github.com/dotnet/aspnetcore/issues/8356).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="368cb-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="368cb-104">Version introduced</span></span>

<span data-ttu-id="368cb-105">3.0</span><span class="sxs-lookup"><span data-stu-id="368cb-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="368cb-106">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="368cb-106">Reason for change</span></span>

<span data-ttu-id="368cb-107">La motivación del cambio consistió en agregar compatibilidad con nuevos flujos de correo electrónico o de confirmación en Identity.</span><span class="sxs-lookup"><span data-stu-id="368cb-107">The motivation for the change was to add support for new email / confirmation flows in Identity.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="368cb-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="368cb-108">Recommended action</span></span>

<span data-ttu-id="368cb-109">Si crea manualmente un elemento `SignInManager`, proporcione una implementación de `IUserConfirmation` o capte una de la inserción de dependencias que se va a proporcionar.</span><span class="sxs-lookup"><span data-stu-id="368cb-109">If manually constructing a `SignInManager`, provide an implementation of `IUserConfirmation` or grab one from dependency injection to provide.</span></span>

#### <a name="category"></a><span data-ttu-id="368cb-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="368cb-110">Category</span></span>

<span data-ttu-id="368cb-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="368cb-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="368cb-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="368cb-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.SignInManager%601.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Identity.SignInManager`1.#ctor`

-->
