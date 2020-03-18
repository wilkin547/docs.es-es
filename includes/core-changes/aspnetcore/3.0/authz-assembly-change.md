---
ms.openlocfilehash: b91cdc7a0d2e4258662155a840500ce21ab35760
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74101472"
---
### <a name="authorization-addauthorization-overload-moved-to-different-assembly"></a><span data-ttu-id="2d1bd-101">Autorización: la sobrecarga de AddAuthorization se ha cambiado a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="2d1bd-101">Authorization: AddAuthorization overload moved to different assembly</span></span>

<span data-ttu-id="2d1bd-102">Se ha cambiado a `AddAuthorizationCore` el nombre de los métodos `AddAuthorization` principales que antes se encontraban en `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-102">The core `AddAuthorization` methods that used to reside in `Microsoft.AspNetCore.Authorization` were renamed to `AddAuthorizationCore`.</span></span> <span data-ttu-id="2d1bd-103">Los métodos `AddAuthorization` antiguos todavía existen, pero ahora se encuentran en el ensamblado `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-103">The old `AddAuthorization` methods still exist, but are in the `Microsoft.AspNetCore.Authorization.Policy` assembly instead.</span></span> <span data-ttu-id="2d1bd-104">Las aplicaciones en las que se usen ambos métodos no se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-104">Apps using both methods should see no impact.</span></span> <span data-ttu-id="2d1bd-105">Tenga en cuenta que `Microsoft.AspNetCore.Authorization.Policy` ahora se incluye en el marco compartido en lugar de en un paquete independiente, tal como se describe en [Marco compartido: se han quitado los ensamblados de Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="2d1bd-105">Note that `Microsoft.AspNetCore.Authorization.Policy` now ships in the shared framework rather than a standalone package as discussed in [Shared framework: Assemblies removed from Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2d1bd-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2d1bd-106">Version introduced</span></span>

<span data-ttu-id="2d1bd-107">3.0</span><span class="sxs-lookup"><span data-stu-id="2d1bd-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2d1bd-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="2d1bd-108">Old behavior</span></span>
<span data-ttu-id="2d1bd-109">Los métodos `AddAuthorization` existían en `Microsoft.AspNetCore.Authorization`.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-109">`AddAuthorization` methods existed in `Microsoft.AspNetCore.Authorization`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="2d1bd-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="2d1bd-110">New behavior</span></span>

<span data-ttu-id="2d1bd-111">Los métodos `AddAuthorization` existen en `Microsoft.AspNetCore.Authorization.Policy`.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-111">`AddAuthorization` methods exist in `Microsoft.AspNetCore.Authorization.Policy`.</span></span> <span data-ttu-id="2d1bd-112">`AddAuthorizationCore` es el nuevo nombre de los métodos antiguos.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-112">`AddAuthorizationCore` is the new name for the old methods.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2d1bd-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="2d1bd-113">Reason for change</span></span>

<span data-ttu-id="2d1bd-114">`AddAuthorization` es un nombre de método más indicado para agregar todos los servicios comunes necesarios para la autorización.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-114">`AddAuthorization` is a better method name for adding all common services needed for authorization.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2d1bd-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2d1bd-115">Recommended action</span></span>

<span data-ttu-id="2d1bd-116">Agregue una referencia a `Microsoft.AspNetCore.Authorization.Policy` o, en su lugar, use `AddAuthorizationCore`.</span><span class="sxs-lookup"><span data-stu-id="2d1bd-116">Either add a reference to `Microsoft.AspNetCore.Authorization.Policy` or use `AddAuthorizationCore` instead.</span></span>

#### <a name="category"></a><span data-ttu-id="2d1bd-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="2d1bd-117">Category</span></span>

<span data-ttu-id="2d1bd-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2d1bd-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2d1bd-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2d1bd-119">Affected APIs</span></span>

<xref:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.Extensions.DependencyInjection.AuthorizationServiceCollectionExtensions.AddAuthorization(Microsoft.Extensions.DependencyInjection.IServiceCollection,System.Action{Microsoft.AspNetCore.Authorization.AuthorizationOptions})`

-->
